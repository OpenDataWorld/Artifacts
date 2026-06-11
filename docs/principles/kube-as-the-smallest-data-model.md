# AnyDB Foundation Principle: Kube Is the Smallest Complete Data Model

Status: Normative Foundation Principle

## Principle

> A Kube is the smallest complete, governable, and reconcilable unit of data in AnyDB.

A Kube is not merely a row, document, message, container, or graph node. It is a bounded data object that carries enough context to be identified, versioned, governed, moved, executed, observed, and reconciled without losing meaning.

## Core Rule

> No data unit is complete until it has identity, state, dimensions, policy, evidence, and lifecycle.

## Kube Model

```text
Kube
├── Identity
├── Type and Schema
├── State
├── Time
├── Location
├── Relationships
├── Policy
├── Provenance
├── Evidence
├── Events
├── Contract
└── Reconciliation Status
```

## Why Kube

Traditional data models separate context across many systems:

- the database stores state
- the event bus stores change
- IAM stores identity
- policy systems store rules
- logs store evidence
- workflow systems store progress
- monitoring stores observed state

The Kube binds these concerns into one canonical data boundary.

It does not require all bytes to live in one physical record. It requires all parts to resolve through one stable Kube identity and contract.

## Canonical Kube Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: Kube
metadata:
  id: urn:anydb:kube:artifact:acid-vs-base
  type: Artifact
  schema:
    id: urn:anydb:schema:kube:artifact
    version: 1.0.0
  version: 1
  owner: urn:anydb:organization:opendataworld
  lifecycle: active
  createdAt: 2026-06-11T00:00:00Z
  updatedAt: 2026-06-11T00:00:00Z
  time:
    validFrom: 2026-06-11T00:00:00Z
    validTo: null
    recordedAt: 2026-06-11T00:00:00Z
  location:
    authority: urn:anydb:organization:opendataworld
    repository: urn:anydb:repository:opendataworld-artifacts
spec:
  state: {}
  relationships: []
  policies: []
  contract: urn:anydb:contract:artifact-publication:v1
  evidence: []
status:
  provenance: []
  events: []
  projections: []
  reconciliation:
    state: unknown
  trust:
    state: provisional
```

## Kube as the Atomic Unit

A Kube is atomic at the semantic level.

This means:

- its identity is indivisible
- its authoritative version is explicit
- its contract is explicit
- its lifecycle is governed as one unit
- its completion status is reconciled as one unit

A Kube may reference external artifacts, streams, or providers, but those references remain part of its canonical boundary.

## Kube vs. Record

A record usually stores current values.

A Kube stores current state plus the context required to trust and operate that state.

```text
Record = Fields
Kube   = Fields + Identity + Time + Location + Policy + Evidence + Lifecycle
```

## Kube vs. Event

An event records a fact that happened.

A Kube is the durable unit whose state and history are described by events.

```text
Kube  = Governed unit
Event = Change to or observation about that unit
```

## Kube vs. Container

A software container packages executable code and dependencies.

A Kube packages governed data and its operational contract.

A Kube may point to or contain an OCI artifact, but it is not restricted to executable software.

## Kube vs. Kubernetes Pod

The term Kube here is an AnyDB data-model primitive, not a Kubernetes Pod.

The concepts align in one useful way:

- Kubernetes reconciles declared workload state
- AnyDB reconciles declared data and work state

A Kubernetes resource may itself be represented as a Kube.

## Kube Dimensions

Every Kube carries the relevant dimensions of truth.

### Identity

What the Kube is.

### Time

When the Kube and its facts are valid, observed, recorded, and reconciled.

### Location

Where the Kube originates, resides, executes, is governed, and is observed.

### State

What is currently authoritative.

### Event

How the state changed.

### Policy

What may happen to the Kube and who may act upon it.

### Evidence

Why the state or outcome should be trusted.

## Kube Contract

Every Kube must resolve to a contract that defines:

- allowed state transitions
- required policies
- accepted providers
- evidence requirements
- consistency expectations
- completion conditions
- retention
- portability and exit

The platform holds this contract.

## Kube Lifecycle

Recommended lifecycle states:

```text
proposed
validated
active
suspended
superseded
compensating
closed
archived
deleted
```

Lifecycle transitions must be recorded as events.

## Kube and ACID

The authoritative version of a Kube should be committed within a declared ACID boundary.

A valid Kube transition should atomically preserve:

- new authoritative state
- incremented version
- transition event
- actor and policy decision
- durable intent to update projections

## Kube and Reactive Surfaces

After commit, the Kube can reactively produce:

- search projections
- graph relationships
- semantic vectors
- features
- notifications
- agent context
- edge commands
- audit evidence

Every projection must point back to the Kube ID and source version.

## Kube at the Edge

A Kube can move to the edge as a signed, bounded operational unit.

```text
Kube Contract
      |
      v
Edge Admission
      |
      v
Local State and Execution
      |
      v
Observed Outcome
      |
      v
Evidence
      |
      v
Reconciliation
```

The edge may hold a local Kube version while disconnected, but divergence must remain visible and reconcilable.

## Kube Composition

Kubes compose into larger structures without losing their own identity.

```text
Kube
  ↓
KubeSet
  ↓
Graph
  ↓
Fabric
```

### KubeSet

A governed collection of Kubes sharing a contract or purpose.

### Graph

Typed relationships between Kubes.

### Fabric

A continuously reconciled network of Kubes, contracts, identities, events, providers, and outcomes.

## Kube as a Promise

A Kube can represent both declared intent and delivered reality.

```text
Desired State
     +
Observed State
     +
Contract
     +
Evidence
     =
Kube Status
```

The Kube is considered complete only when its reconciliation state reaches a declared terminal outcome.

## Terminal Outcomes

```text
converged
compensated
rejected
expired
cancelled
failed-with-evidence
escalated-to-human
```

Acceptance of a command is not completion of the Kube.

## Kube Types

Examples include:

```text
IdentityKube
DataKube
EventKube
PolicyKube
ArtifactKube
ModelKube
AgentKube
ContractKube
DecisionKube
WorkKube
EvidenceKube
ProviderKube
EdgeKube
```

All types extend the same foundation envelope.

## Lossless Transformation

A Kube may change representation across surfaces, but its canonical identity and lineage remain intact.

```text
Kube
  +-- record view
  +-- document view
  +-- graph view
  +-- event stream
  +-- vector view
  +-- edge replica
```

No view becomes an unrelated copy of the Kube.

## Single Version of Truth

At any authoritative boundary, one Kube version is canonical.

Other representations declare themselves as:

- replica
- projection
- observation
- proposal
- pending local version
- superseded version

## Platform Invariants

1. Every Kube has one canonical identity.
2. Every Kube declares a schema and version.
3. Every Kube carries relevant time and location dimensions.
4. Every Kube has explicit ownership and policy.
5. Every authoritative transition creates an event.
6. Every derived representation points to the Kube and source version.
7. Every Kube preserves provenance and evidence.
8. Every Kube has a contract held by the platform.
9. Every distributed Kube is reconciled.
10. No provider owns the Kube's identity or meaning.

## Foundation Formula

```text
Kube = Identity + State + Time + Location + Policy + Evidence + Contract + Reconciliation
```

And:

```text
AnyDB = Store and Graph of Kubes
Fabric = Reconciled Network of Kubes
```

## Final Statement

> The Kube is the smallest complete form of the AnyDB data model. It is one bounded unit of truth, context, contract, and lifecycle that can be stored, moved, transformed, executed, and reconciled without losing its identity or meaning.
