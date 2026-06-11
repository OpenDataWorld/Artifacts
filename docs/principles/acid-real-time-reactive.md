# AnyDB Foundation Principle: ACID, Real-Time, and Reactive

Status: Normative Foundation Principle

## Principle

> AnyDB preserves ACID integrity at the authoritative core while remaining real-time and reactive across events, projections, agents, edges, and reconciliation loops.

Correctness and responsiveness are not competing product modes. AnyDB uses transactional guarantees where truth is committed, then propagates change through reactive, event-driven surfaces.

## Core Model

```text
Command
  ↓
ACID Commit
  ↓
Authoritative Event
  ↓
Reactive Distribution
  ↓
Projection / Agent / Edge
  ↓
Observed Outcome
  ↓
Reconciliation
```

## ACID Core

The authoritative store must protect:

- atomicity
- consistency
- isolation
- durability

ACID applies to the smallest declared authoritative transaction boundary.

Examples:

- canonical entity version change
- identity lifecycle transition
- policy assignment
- payment or contract state
- authoritative event append
- reconciliation state transition

## Real-Time

Real-time means that authoritative changes become observable to subscribed surfaces with bounded, measured latency.

Real-time behavior should expose:

- event publication latency
- projection lag
- edge synchronization lag
- policy propagation lag
- model or feature freshness
- reconciliation delay

The platform must declare whether a workload is:

```text
hard-real-time
soft-real-time
near-real-time
batch
```

AnyDB does not claim hard real-time guarantees unless the deployment profile, runtime, operating system, and hardware support them explicitly.

## Reactive

Reactive behavior means platform surfaces respond to state changes rather than depending only on polling or manual coordination.

Reactive participants may include:

- controllers
- operators
- projections
- agents
- policy engines
- edge runtimes
- notification services
- reconciliation loops

Every reaction must remain causally linked to the event that triggered it.

## Transaction to Event Boundary

An authoritative mutation and its corresponding event must be committed atomically within the provider boundary.

Recommended pattern:

```text
BEGIN
  update canonical state
  append authoritative event
COMMIT
```

When an external message broker is used, the transactional outbox or an equivalent durable mechanism must bridge the transaction and publication boundary.

## Reactive Event Flow

```text
Authoritative Event
      |
      +-- Search Projection
      +-- Feature Projection
      +-- Graph Projection
      +-- Agent Context
      +-- Edge Command
      +-- Audit Evidence
      +-- Reconciliation Trigger
```

Each consumer must process events idempotently and maintain checkpoints.

## Consistency by Surface

### Authoritative Surface

Strong consistency and explicit transaction boundaries.

### Projection Surface

Usually eventually consistent, with visible source version and freshness.

### Edge Surface

Locally consistent within the edge transaction boundary, then globally reconciled.

### Intelligence Surface

Model and feature outputs are versioned observations or proposals until accepted through an authoritative transaction.

## Real-Time Does Not Mean Unverified

A low-latency result is not automatically trusted.

```text
Fast Output
   ↓
Policy and Evidence
   ↓
Authoritative Acceptance
   ↓
Observed Outcome
   ↓
Reconciliation
```

Latency goals must not bypass policy, identity, or audit requirements.

## Reactive Commands

Events may trigger new commands, but events must not directly mutate authoritative state without passing through command validation.

```text
Event
  ↓
Reaction Rule
  ↓
Command
  ↓
Identity + Policy + Invariants
  ↓
ACID Commit
```

This prevents event chains from becoming uncontrolled side effects.

## Backpressure

Reactive systems must handle consumers that cannot keep pace.

Required controls may include:

- durable queues
- bounded buffers
- consumer checkpoints
- rate limits
- priority classes
- retry policies
- dead-letter or quarantine paths
- load shedding for non-critical projections

Critical authoritative events must not be silently dropped.

## Ordering

Ordering is guaranteed only within declared stream boundaries.

Recommended boundary:

```text
canonical subject + stream
```

Consumers must not assume global ordering from timestamps alone.

## Idempotency

Every reactive consumer must tolerate duplicate delivery.

Idempotency may use:

- event ID
- command ID
- idempotency key
- source version
- subject sequence
- consumer checkpoint

## Failure Recovery

Reactive failure must remain visible as data.

Recommended states:

```text
pending
processing
completed
retrying
blocked
quarantined
failed
compensating
reconciled
```

A failed projection or edge action must not be mistaken for a failed authoritative transaction.

## Edge Reactivity

At the edge, AnyDB should support local reaction during upstream disconnection.

```text
Local Event
   ↓
Local Policy
   ↓
Local Command
   ↓
Local ACID Commit
   ↓
Local Outcome
   ↓
Durable Evidence
   ↓
Later Global Reconciliation
```

The edge must preserve canonical identity, local sequence, source versions, and conflict evidence.

## Agent Reactivity

Agents may subscribe to governed event streams and produce proposed commands.

An agent reaction must include:

- agent identity
- triggering event ID
- context version
- model and runtime version
- policy reference
- command ID
- expected outcome

Agents do not receive permission to mutate truth merely because they react quickly.

## Temporal Semantics

The platform distinguishes:

- event occurrence time
- transaction commit time
- publication time
- consumer processing time
- projection time
- observation time
- reconciliation time

This allows latency and causality to remain explainable.

## Observability

The platform should measure:

- transaction latency
- commit failures
- event publication delay
- consumer lag
- duplicate processing
- projection freshness
- edge convergence time
- agent reaction time
- reconciliation backlog
- terminal outcome latency

## Reactive Contract Example

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: ReactiveContract
metadata:
  id: urn:anydb:reactive-contract:artifact-publication:v1
spec:
  trigger:
    eventType: ArtifactPublished
  source:
    authoritative: true
    stream: artifact-lifecycle
  reactions:
    - target: semantic-search
      mode: projection
      consistency: eventual
      maxLag: 5s
    - target: edge-cache
      mode: distribution
      consistency: eventual
      maxLag: 30s
  failure:
    retry: exponential
    quarantineAfter: 10
  reconciliation:
    required: true
```

## Platform Invariants

1. Authoritative truth is committed through declared ACID boundaries.
2. Every committed change produces a durable event or mutation record.
3. Reactive consumers preserve causation and source version.
4. Duplicate delivery does not duplicate business effects.
5. Projection lag is visible and measurable.
6. Events trigger governed commands, not uncontrolled mutation.
7. Backpressure never silently drops critical truth.
8. Edge reactions remain locally durable and globally reconcilable.
9. Real-time claims are tied to measurable service levels.
10. Completion is established through reconciliation, not event publication alone.

## Foundation Formula

```text
ACID Commit + Durable Event + Reactive Distribution + Reconciliation = Trusted Real-Time System
```

## Final Statement

> AnyDB is transactional at the core, reactive across every surface, real-time where the workload requires it, and reconciled wherever distributed reality can diverge.
