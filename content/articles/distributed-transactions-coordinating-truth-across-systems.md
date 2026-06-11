# Distributed Transactions: Coordinating Truth Across Systems

A transaction inside one database is difficult enough.

A transaction across multiple services, databases, queues, and external providers is fundamentally harder.

Distributed transactions exist because modern systems rarely complete important work in one place. A payment may require an order service, ledger, inventory system, identity provider, notification service, and external payment network to cooperate.

The challenge is not merely execution.

The challenge is preserving truth when some participants succeed, some fail, and the network makes it impossible to know which state each participant has reached.

## The Core Problem

Consider an order workflow:

1. Reserve inventory.
2. Authorize payment.
3. Create shipment.
4. Confirm the order.

If the payment succeeds but inventory reservation fails, the platform must decide how to recover.

A single ACID transaction cannot normally span all participants safely and efficiently.

Distributed transaction patterns provide different ways to coordinate this work.

## Two-Phase Commit

Two-phase commit, or 2PC, uses a coordinator and multiple participants.

### Phase One: Prepare

The coordinator asks each participant whether it can commit.

Each participant performs validation, reserves resources, and responds with either:

- prepared
- abort

### Phase Two: Commit or Roll Back

If every participant is prepared, the coordinator instructs all of them to commit.

If any participant rejects the transaction, the coordinator instructs all participants to roll back.

## Strengths of Two-Phase Commit

2PC can provide strong atomicity across participants.

It is useful when:

- participants support distributed transactions
- strict consistency is required
- the number of participants is controlled
- coordination latency is acceptable

## Weaknesses of Two-Phase Commit

2PC introduces blocking and coordination risk.

A participant may remain locked while waiting for the coordinator.

If the coordinator fails after participants prepare but before they receive the final decision, they may be unable to proceed independently.

This can reduce availability and create operational complexity.

For internet-scale systems, long-running workflows, and heterogeneous services, 2PC is often too expensive or brittle.

## Three-Phase Commit

Three-phase commit adds an additional coordination phase intended to reduce blocking.

The protocol typically uses:

1. CanCommit
2. PreCommit
3. DoCommit

In theory, the additional phase gives participants more information about the transaction state.

In practice, 3PC assumes network and timing properties that are difficult to guarantee in real distributed systems. It is therefore much less common than 2PC.

## Sagas

A saga breaks one global transaction into a sequence of local transactions.

Each local transaction commits independently.

If a later step fails, previously completed steps are undone through compensating actions.

For example:

```text
ReserveInventory
AuthorizePayment
CreateShipment
```

If shipment creation fails, the system may execute:

```text
ReleaseInventory
VoidPaymentAuthorization
```

The workflow does not roll back through one global database transaction. It moves forward through explicit recovery actions.

## Compensation Is Not Rollback

A compensating action does not erase history.

It creates a new business action that offsets a prior one.

A refunded payment is not the same as a payment that never occurred.

A cancelled shipment is not the same as a shipment that was never created.

This distinction matters for:

- auditability
- accounting
- customer communication
- legal records
- event history

Sagas preserve the reality that work happened and was later corrected.

## Choreography

In a choreographed saga, services react to events without one central workflow coordinator.

Example:

```text
OrderCreated
  -> InventoryReserved
  -> PaymentAuthorized
  -> ShipmentCreated
  -> OrderConfirmed
```

Each service consumes events and emits the next result.

### Benefits

- loose coupling
- independent service evolution
- no central orchestration service

### Risks

- difficult end-to-end visibility
- hidden workflow logic
- event cycles
- complex failure handling
- hard-to-understand ownership

## Orchestration

In an orchestrated saga, one workflow component coordinates the sequence.

The orchestrator sends commands and receives outcomes.

Example:

```text
OrderOrchestrator
  -> ReserveInventory
  -> AuthorizePayment
  -> CreateShipment
```

### Benefits

- explicit workflow
- centralized progress tracking
- clearer compensation logic
- easier operational visibility

### Risks

- stronger dependency on the orchestrator
- potential concentration of domain logic
- coordinator availability requirements

## The Transactional Outbox Pattern

A common problem occurs when a service must update its database and publish an event.

Consider:

1. Update order status.
2. Publish OrderConfirmed.

If the database update commits but event publication fails, downstream services never learn about the change.

If the event is published first but the database update fails, consumers receive a fact that never became authoritative.

The transactional outbox solves this by writing both the business change and an outbox record in the same local transaction.

```text
BEGIN
  UPDATE orders ...
  INSERT INTO outbox ...
COMMIT
```

A separate publisher reads the outbox and delivers the event.

This provides atomicity between local state and the intention to publish.

## Inbox and Deduplication

Messages can be delivered more than once.

Consumers should therefore track processed message identifiers or use naturally idempotent operations.

An inbox pattern stores received message IDs and processing results.

Before executing work, the consumer checks whether the message has already been handled.

This prevents duplicated business effects.

## At-Most-Once, At-Least-Once, and Exactly-Once

### At-Most-Once

A message is delivered zero or one time.

Duplicates are avoided, but messages may be lost.

### At-Least-Once

A message is retried until acknowledged.

Loss is reduced, but duplicates are possible.

### Exactly-Once

The business effect occurs exactly once.

True end-to-end exactly-once processing across independent systems is difficult. Many systems instead combine at-least-once delivery with idempotent business operations.

The practical goal is often exactly-once business semantics rather than exactly-once transport.

## Idempotency

An idempotent operation can be repeated without creating additional effects.

Examples include:

- setting a status to approved
- storing a command result under a stable idempotency key
- applying a payment only when its transaction ID has not been processed
- using a unique constraint on an external reference

Idempotency is essential because retries are unavoidable in distributed systems.

## Timeouts and Uncertainty

A timeout does not prove that an operation failed.

The remote system may have completed the request but failed to return the response.

The caller is left uncertain.

Reliable workflows need status queries, idempotency keys, durable command records, and reconciliation processes to resolve that uncertainty.

## Reconciliation

Reconciliation compares intended state with observed state and repairs divergence.

Examples include:

- checking whether a payment authorization exists
- confirming whether inventory remains reserved
- comparing local order state with the shipping provider
- retrying incomplete workflow steps
- escalating unresolved differences

Reconciliation is not merely error handling.

It is a continuous control loop for distributed truth.

## Distributed Transactions and CQRS

CQRS separates commands from queries.

Distributed transaction workflows often begin as commands and produce events that update projections.

The command side protects business invariants.

The query side may temporarily lag while distributed participants complete or compensate.

This makes workflow status an important first-class read model.

Instead of showing only success or failure, the system may expose states such as:

- pending
- authorized
- compensating
- partially completed
- awaiting confirmation
- reconciled
- failed permanently

## Distributed Transactions and Event Sourcing

Event sourcing provides a durable history of each workflow step.

A saga can be reconstructed from events such as:

```text
OrderCreated
InventoryReservationRequested
InventoryReserved
PaymentAuthorizationRequested
PaymentAuthorized
ShipmentCreationFailed
PaymentAuthorizationVoided
InventoryReleased
OrderCancelled
```

This history supports recovery, audit, and explanation.

## Distributed Transactions and Temporal Data

A distributed workflow unfolds over time.

Temporal records make it possible to answer:

- Which step was active at a particular moment?
- How long was the workflow blocked?
- Which policy version governed the decision?
- When did compensation begin?
- When did reconciliation complete?

This is important for service-level objectives, regulatory evidence, and incident analysis.

## Distributed Transactions and the CAP Theorem

During a partition, the system may be unable to coordinate all participants.

A strongly consistent coordinator may reject progress until communication is restored.

An available workflow may accept local progress and reconcile later.

The correct choice depends on the consequence of conflicting state.

A payment ledger and a recommendation cache should not use the same consistency policy.

## Agentic Workflows

Autonomous agents increasingly initiate distributed work.

An agent may:

- reserve a resource
- call an external API
- create a document
- request payment
- update a CRM
- send a notification

These actions cannot safely be treated as one opaque tool call.

Each effect should be represented as a governed command with:

- a stable command ID
- authenticated identity
- explicit authorization
- policy evaluation
- idempotency key
- expected outcome
- compensation strategy
- verification step
- audit event

## Agent Compensation

Agent actions may require domain-specific compensation.

Examples include:

- cancel a booking
- revoke a credential
- issue a refund
- retract a publication
- restore a previous configuration
- notify a human owner

Not every action is reversible.

The platform should classify actions as:

- reversible
- compensatable
- irreversible
- human-recoverable

High-consequence irreversible actions should require stronger approval and verification before execution.

## Human-in-the-Loop Transactions

Some distributed workflows include human approval.

These workflows may remain open for hours or days, making database locks and 2PC unsuitable.

A saga-style process can preserve durable state while waiting for approval.

For example:

```text
DecisionProposed
PolicyPassed
HumanApprovalRequested
HumanApprovalGranted
ActionExecuted
OutcomeVerified
```

The workflow is long-running, but every transition remains explicit and recoverable.

## Fabric and Reconciliation

A Fabric-style platform can model every unit of work as a durable, governed transaction across identities, policies, services, and outcomes.

The Fabric does not need to pretend that all participants share one database transaction.

Instead, it can preserve:

- intent
- accepted facts
- workflow state
- compensation actions
- evidence
- temporal history
- reconciliation status

The core principle becomes:

> Do not hide partial failure. Model it, govern it, and reconcile it.

## Choosing a Pattern

Use 2PC when:

- participants support it
- strict atomicity is essential
- transactions are short-lived
- availability trade-offs are acceptable

Use sagas when:

- workflows cross independent services
- work may be long-running
- compensation is meaningful
- eventual consistency is acceptable

Use the outbox pattern when:

- local state changes must reliably produce events

Use idempotency and inbox deduplication when:

- retries and duplicate delivery are possible

Use reconciliation when:

- external systems can diverge
- outcomes cannot be trusted from one response alone

## Conclusion

Distributed transactions are not solved by one universal protocol.

They are managed through a combination of atomic local writes, durable events, explicit workflows, idempotency, compensation, and reconciliation.

The strongest systems do not assume that every participant will succeed together.

They preserve enough truth to understand partial completion, recover safely, and prove what happened.

For autonomous systems, that discipline is even more important.

An agent should never be trusted merely because it issued a command. The platform must verify the effect, record the outcome, compensate when possible, and reconcile until the promise is either kept or explicitly closed.
