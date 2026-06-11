# AnyDB Foundation Principle: Time Is the Edge; Time Is the Cliff

Status: Normative Foundation Principle

## Principle

> Time is the edge where intent becomes action. Time is the cliff where an unfulfilled contract becomes failure, expiry, compensation, or escalation.

Every decision, command, contract, delegation, policy, artifact, agent, and reconciliation loop exists inside a temporal boundary.

The platform must therefore treat time not only as a dimension of truth, but as an active execution boundary.

## Core Rule

> Before the deadline, the system may still converge. At the deadline, the contract must resolve.

## The Edge of Time

The temporal edge is the moment at which the platform must decide whether to:

- execute
- defer
- reject
- renew
- compensate
- escalate
- terminate

Before that edge, the state may remain pending.

At that edge, ambiguity must become an explicit outcome.

## The Cliff of Time

The cliff is the terminal boundary after which the original promise can no longer be fulfilled under the same contract.

Examples include:

- an approval window expires
- an inventory hold lapses
- a credential becomes invalid
- a payment authorization times out
- an agent delegation ends
- a model approval expires
- an edge command exceeds its safe execution window
- a reconciliation deadline is missed

Once the cliff is crossed, the platform must not pretend the original contract remains valid.

## Temporal Contract Model

```text
Contract Created
      |
      v
Valid Window Opens
      |
      v
Intent / Execution / Reconciliation
      |
      +-- converged before deadline
      +-- rejected before deadline
      +-- cancelled before deadline
      |
      v
Temporal Edge
      |
      +-- extend under new contract
      +-- compensate
      +-- escalate
      +-- expire
      |
      v
Temporal Cliff
      |
      v
Terminal Outcome
```

## Canonical Temporal Fields

Every high-consequence contract should declare:

```yaml
spec:
  time:
    validFrom: 2026-06-11T10:00:00Z
    executeBy: 2026-06-11T10:05:00Z
    reconcileBy: 2026-06-11T10:10:00Z
    expiresAt: 2026-06-11T10:15:00Z
    retentionUntil: 2033-06-11T00:00:00Z
```

### `validFrom`

The earliest time at which the contract may be acted upon.

### `executeBy`

The execution deadline.

### `reconcileBy`

The deadline by which the actual outcome must be verified.

### `expiresAt`

The point after which the contract is no longer valid.

### `retentionUntil`

The time until which evidence and history must be retained.

## Temporal States

Recommended states:

```text
not-yet-valid
active
pending
executing
awaiting-evidence
awaiting-reconciliation
converged
expired
missed-deadline
compensating
compensated
escalated
failed-with-evidence
```

## Time as a Governance Boundary

Policy may change as time advances.

Examples:

- access valid only during business hours
- an agent budget resets daily
- a credential is valid for one hour
- an approval expires after 15 minutes
- data must be deleted after a retention period
- a model may run only during an approved release window

The platform must resolve the policy version valid at the relevant decision and execution times.

## Time as a Safety Boundary

Some actions become unsafe when delayed.

Examples:

- medical alerts
- industrial shutdown commands
- fraud holds
- inventory reservations
- market instructions
- emergency access

A stale command must not execute merely because it eventually arrived.

The edge must verify temporal validity before action.

## Time at the Edge

The edge is both spatial and temporal.

```text
Where = Edge Location
When  = Temporal Edge
```

A command becomes admissible only when both conditions are valid:

- it is authorized at this location
- it is valid at this time

```text
Command
   + Location Policy
   + Time Policy
   = Edge Admission Decision
```

## AnyAgent and Temporal Autonomy

AnyAgent autonomy must be bounded by time.

An agent contract should define:

- activation time
- execution window
- delegation expiry
- approval timeout
- maximum task duration
- retry interval
- reconciliation deadline
- termination time

An agent must not continue acting under an expired delegation or stale context.

## Time and Reconciliation

Reconciliation is not open-ended.

Every work loop should define:

- expected convergence time
- retry schedule
- maximum retry duration
- compensation deadline
- escalation deadline
- terminal deadline

If convergence is not established by the temporal cliff, the platform must emit a terminal event.

Recommended events:

```text
ExecutionDeadlineMissed
ReconciliationDeadlineMissed
ContractExpired
CompensationStarted
CompensationCompleted
HumanEscalationRequired
WorkFailedWithEvidence
```

## Time and Single Version of Truth

The authoritative version is time-bound.

A version may be:

- current
- future-effective
- superseded
- expired
- retroactively corrected

AnyDB must preserve valid time and transaction time so the platform can distinguish what was true from what was believed at each moment.

## Time and Lossless Transformation

Transformations must preserve all material time dimensions.

A projection must not collapse:

- occurrence time
- observation time
- ingestion time
- processing time
- projection time
- reconciliation time

into one ambiguous timestamp.

## Time and Supply Chain

Every supply-chain stage has a temporal contract:

```text
Source Freeze
Build Window
Test Window
Approval Window
Release Window
Deployment Window
Rollback Window
Support Window
Retention Window
```

An artifact delivered after its valid window may be technically intact but operationally invalid.

## Time and Trust

Trust decays when evidence becomes stale.

Examples:

- certifications expire
- keys rotate
- vulnerabilities emerge
- model evaluations become outdated
- provider capabilities change
- partner status changes

Trust must include evaluation time and expiry or review conditions.

## Clock Trust

Time claims need provenance.

The platform should record:

- clock source
- synchronization status
- measured skew
- device or runtime identity
- confidence

A timestamp from an untrusted or drifting clock must not be treated as equally authoritative.

## Failure Semantics

When a temporal cliff is crossed, the platform must choose one explicit outcome:

```text
expired
rejected
cancelled
compensated
failed-with-evidence
escalated-to-human
renewed-under-new-contract
```

The platform must never silently extend a contract beyond its time boundary.

## Platform Invariants

1. Every high-consequence contract has explicit time boundaries.
2. Execution checks temporal validity at the point of action.
3. Reconciliation has a deadline.
4. Expired authority cannot be reused silently.
5. Stale commands do not execute automatically.
6. Trust assertions include evaluation time and freshness.
7. Transformations preserve material time dimensions.
8. Deadlines produce events and terminal outcomes.
9. Extensions require a new or amended contract.
10. The platform never hides missed temporal obligations.

## Foundation Formula

```text
Time Edge = Last Safe Point for Action
```

```text
Time Cliff = Point After Which the Original Contract Cannot Be Fulfilled
```

```text
Trustworthy Work = Correct Action + Correct Location + Correct Time + Verified Outcome
```

## Final Statement

> Time is the edge because every action must occur inside a valid window. Time is the cliff because every promise eventually reaches a point where it must be fulfilled, renewed, compensated, escalated, or closed.
