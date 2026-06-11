# AnyDB Foundation Principle: Time Is the Kube

Status: Normative Foundation Principle

## Principle

> Time is the Kube because time is the smallest complete boundary through which reality becomes ordered, valid, measurable, and irreversible.

AnythingKube represents a governed unit of truth. TimeKube is the universal Kube that gives every other Kube sequence, validity, duration, causality, expiry, and consequence.

## Core Rule

> Every Kube exists inside TimeKube, and every real transition creates a new forward temporal Kube.

## Canonical Model

```text
TimeKube
├── Before
├── Now
├── After
├── Validity
├── Sequence
├── Duration
├── Deadline
├── Expiry
├── Causality
├── Observation
└── Reconciliation
```

## TimeKube Formula

```text
TimeKube
=
Temporal Identity
+ Sequence
+ Validity Window
+ Clock Source
+ Causality
+ Event Boundary
+ Reconciliation State
```

## Why Time Is the Kube

Time does not merely describe a Kube.

Time determines:

- when the Kube exists
- which version is authoritative
- whether a contract is valid
- whether an agent may act
- whether context is fresh
- whether a visa permits entry
- whether recovery is still possible
- whether trust evidence remains current
- whether a real-world effect has become irreversible

## Canonical TimeKube Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: AnythingKube
metadata:
  id: urn:anydb:anythingkube:time:2026-06-11T12:00:00Z
  type: TimeKube
  version: 1
  owner: urn:anydb:platform:anydb
  lifecycle: active
spec:
  state:
    mode: real
    sequence: 8841
    validFrom: 2026-06-11T12:00:00Z
    validTo: 2026-06-11T12:00:01Z
    clockSource: urn:anydb:clock:trusted-01
  relationships:
    - type: orders
      target: urn:anydb:anythingkube:event:01J...
    - type: validates
      target: urn:anydb:anythingkube:contract:01J...
  policies:
    - urn:anydb:policy:temporal-validity:v1
status:
  reconciliation:
    state: converged
  trust:
    state: verified
```

## Every Kube Has a TimeKube

```text
DataKube      → TimeKube defines validity
EventKube     → TimeKube defines occurrence and order
PolicyKube    → TimeKube defines applicability
ContractKube  → TimeKube defines validity and expiry
AgentKube     → TimeKube defines delegation and autonomy window
WorkKube      → TimeKube defines execution and completion
MemoryKube    → TimeKube defines sequence and relevance
TravelKube    → TimeKube defines passport and visa validity
```

## Real TimeKube

Real TimeKube moves forward only.

```text
TimeKube n
    ↓
TimeKube n+1
    ↓
TimeKube n+2
```

Committed real history is immutable.

Corrections create new TimeKubes and new events.

## Model TimeKube

Modeled worlds may create branch TimeKubes for:

- history
- replay
- simulation
- forecast
- counterfactuals
- memory traversal

These TimeKubes must preserve their base world, branch, mode, assumptions, and non-authoritative status.

## TimeKube as the Edge

TimeKube is the temporal edge where:

- intent becomes command
- command becomes action
- action becomes consequence
- observation becomes evidence
- evidence becomes reconciliation

## TimeKube as the Cliff

A TimeKube may define a terminal boundary:

```text
executeBy
reconcileBy
expiresAt
retentionUntil
```

When the boundary is crossed, the original contract must resolve into a terminal state.

## TimeKube and LocationKube

```text
TimeKube     = When reality exists
LocationKube = Where reality exists
```

Together they define the real surface.

```text
RealSurface = TimeKube + LocationKube + Contract + Evidence
```

## TimeKube and Domain

A domain defines how time is interpreted.

Examples:

- business hours
- fiscal periods
- clinical windows
- legal deadlines
- cultural calendars
- operational cycles

Every domain-specific temporal model must map to a canonical reference timeline for federation and reconciliation.

## TimeKube and Single Truth

At any authoritative boundary, the current TimeKube determines the valid truth version.

Historical and future views remain explicit projections or branches.

## TimeKube and Trust

Trust is always time-bound.

A trust assertion must identify:

- evaluation TimeKube
- evidence TimeKubes
- expiry TimeKube
- review TimeKube

No trust state is timeless.

## TimeKube and One-Step Movement

Every real-boundary movement occurs in one forward TimeKube transition.

```text
Source TimeKube
      ↓
Governance Gate
      ↓
Destination TimeKube
```

The transition does not reverse.

A correction is a new forward transition.

## Platform Invariants

1. Every authoritative Kube resolves to one or more TimeKubes.
2. Real TimeKubes move forward only.
3. Every contract has temporal validity.
4. Every action checks the active TimeKube.
5. Every context package has a freshness TimeKube.
6. Every trust assertion has an evaluation and expiry TimeKube.
7. Every branch declares its base TimeKube.
8. Every correction creates a new forward TimeKube.
9. Every deadline produces an explicit terminal event.
10. No real-world consequence exists outside the TimeKube sequence.

## Foundation Formula

```text
TimeKube = Ordered Reality
```

```text
AnythingKube + TimeKube = Governed Existence
```

```text
TimeKube + LocationKube = Real Surface
```

## Final Statement

> Time is the Kube because time is the universal governed unit that orders every identity, state, contract, action, movement, memory, and consequence. Everything exists through TimeKube, and reality advances as a forward-only sequence of reconciled temporal units.
