# Event Sourcing vs. CRUD: Why Modern Systems Store Facts Instead of State

Most software systems are built around a simple idea: store the current state, update it when something changes, and read it back when needed.

That model is CRUD.

Event sourcing takes a different approach. Instead of treating the latest state as the primary record, it stores the sequence of facts that produced that state.

This distinction changes how systems handle history, auditability, failure recovery, distributed coordination, and intelligent automation.

## What Is CRUD?

CRUD stands for:

- Create
- Read
- Update
- Delete

A CRUD application usually stores the latest version of an entity.

For example, a customer account might be represented as:

```json
{
  "id": "customer-42",
  "status": "active",
  "plan": "enterprise",
  "credit_limit": 50000
}
```

When the customer changes plans, the existing record is updated.

The database tells us what is true now, but not necessarily how it became true.

## Strengths of CRUD

CRUD is direct, familiar, and efficient for many workloads.

It works well when:

- only the current state matters
- business rules are simple
- history is not operationally important
- updates are local and synchronous
- application behavior is easy to reproduce

CRUD is often the right choice for administrative interfaces, content systems, simple catalogs, and internal tools.

## Limitations of CRUD

Updating state in place can erase important context.

A current record may not reveal:

- who changed it
- why it changed
- which rule authorized the change
- what the previous value was
- whether another service observed an intermediate state
- how the state should be reconstructed after failure

Audit tables and logs can help, but they are frequently added later and may not be part of the same consistency boundary as the business transaction.

## What Is Event Sourcing?

Event sourcing stores every meaningful state transition as an immutable event.

Instead of updating an account record directly, the system records facts such as:

```text
CustomerRegistered
EnterprisePlanSelected
CreditLimitApproved
AccountActivated
```

The current state is derived by replaying those events in order.

The event log is the source of truth. The current state is a projection.

## Events Are Facts

A well-designed event describes something that has already happened.

Examples:

- PaymentAuthorized
- AccessGranted
- PolicyRejected
- AgentSuspended
- ContractSigned
- InventoryReserved

Events should normally be immutable because changing a historical fact would make previously derived state unreliable.

Corrections are represented by new events rather than by rewriting old ones.

## Projections

Replaying every event for every read would be expensive.

Event-sourced systems therefore build projections: read-optimized views derived from the event stream.

A customer summary, account balance, search index, dashboard, or fraud score can each be maintained as a separate projection.

This allows one stream of facts to support many read models.

## CRUD vs. Event Sourcing

| Concern | CRUD | Event Sourcing |
|---|---|---|
| Primary record | Current state | Sequence of events |
| History | Optional or secondary | Built in |
| Auditability | Added through logs or audit tables | Native |
| State reconstruction | Limited | Replay events |
| Read simplicity | High | Requires projections |
| Write complexity | Lower | Higher |
| Temporal queries | Difficult | Natural |
| Integration | Often request-driven | Naturally event-driven |

## Event Sourcing Is Not Event Logging

Application logs describe system behavior.

Domain events describe business facts.

A log entry such as “request completed in 34 ms” is useful operationally but cannot reconstruct an account balance.

A domain event such as “FundsDeposited: 500” can participate directly in rebuilding business state.

## Event Sourcing and ACID

Event sourcing still needs transactional guarantees.

When a command is accepted, the resulting events must be appended atomically and durably.

Concurrency control is commonly enforced through stream versions or optimistic locking.

This prevents two writers from silently creating incompatible histories.

ACID protects the integrity of the event stream.

## Event Sourcing and BASE

After events are committed, projections and downstream consumers may update asynchronously.

That makes many event-sourced architectures eventually consistent at the read-model layer.

The event log can remain strongly consistent while search indexes, analytics views, caches, and remote replicas converge over time.

This is a practical combination of ACID and BASE:

- ACID for authoritative facts
- BASE for distributed projections

## Event Sourcing and the CAP Theorem

During a network partition, the authoritative event stream may prefer consistency and reject writes that cannot be safely ordered.

Other services may remain available using existing projections and reconcile when connectivity returns.

This allows architects to apply different CAP trade-offs to different parts of the platform.

The command side may operate as CP while some query and distribution paths behave more like AP.

## Event Sourcing and CQRS

CQRS separates commands from queries.

Commands express intent to change the system.

Queries read projections optimized for specific use cases.

Event sourcing and CQRS are frequently used together, but they are not the same pattern.

A system can use CQRS without event sourcing, and it can use event sourcing without a fully separated CQRS architecture.

## Temporal Data

Event streams naturally preserve time.

They can answer questions such as:

- What was true at 10:00 yesterday?
- Which policy was active when this decision was made?
- How did this account reach its current balance?
- Which event caused this permission to be revoked?

This makes event sourcing valuable in regulated, financial, security-sensitive, and decision-intensive systems.

## Event Sourcing for Agentic Systems

Autonomous agents do more than update records. They observe, decide, invoke tools, request approvals, and produce consequences.

A current-state-only model may show that an agent is suspended, but not:

- which observation triggered the decision
- which model produced the recommendation
- which policy evaluated the action
- who approved it
- which tool was called
- what external effect occurred

An event-sourced agent lifecycle can capture facts such as:

```text
AgentRegistered
CredentialIssued
TaskAssigned
ContextLoaded
DecisionProposed
PolicyEvaluated
HumanApprovalGranted
ToolInvocationStarted
ToolInvocationCompleted
TrustScoreReduced
AgentSuspended
```

This produces a durable decision history rather than an opaque automation trail.

## Agent Memory as an Event Stream

Agent memory is often treated as a collection of editable notes or embeddings.

A more reliable approach separates:

- immutable observations
- decisions and their evidence
- actions and outcomes
- derived summaries
- searchable semantic projections

The immutable event history preserves provenance. Summaries and embeddings remain rebuildable projections.

This distinction is critical because generated summaries can be wrong, stale, or incomplete, while source events preserve what actually happened.

## When to Use CRUD

Choose CRUD when:

- the domain is straightforward
- current state is sufficient
- history has low business value
- the team needs simple development and operations
- state transitions do not drive many downstream processes

## When to Use Event Sourcing

Choose event sourcing when:

- auditability is a core requirement
- historical reconstruction matters
- workflows span many services
- business rules depend on prior transitions
- multiple projections are needed
- decisions must be explainable
- failures require deterministic recovery
- automation must preserve provenance

## When Not to Use Event Sourcing

Event sourcing introduces real cost.

Teams must design event schemas, manage versioning, build projections, handle replay, control concurrency, and operate asynchronous consumers.

Using it for a simple content page or basic configuration record may add complexity without meaningful benefit.

The pattern should be applied where history is part of the product, not merely because events are fashionable.

## A Hybrid Architecture

Many strong systems use both models.

CRUD can manage simple reference data and user-facing configuration.

Event sourcing can protect high-consequence workflows such as:

- payments
- permissions
- contracts
- inventory movements
- policy decisions
- agent actions
- governance approvals

The goal is not to event-source everything.

The goal is to preserve the facts that must never be lost.

## Conclusion

CRUD stores what the system currently believes.

Event sourcing stores what the system knows happened.

Current state is useful for serving applications. Historical facts are essential for trust, explanation, recovery, and governance.

Modern platforms increasingly need both:

- state for efficient operation
- events for durable truth

For intelligent and autonomous systems, this distinction becomes even more important. An agent should not merely produce an outcome. It should leave behind a verifiable chain of observations, decisions, approvals, actions, and consequences.

That chain is the foundation of accountable automation.
