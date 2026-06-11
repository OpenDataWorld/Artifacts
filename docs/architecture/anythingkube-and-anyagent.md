# AnythingKube and AnyAgent

Status: Canonical Naming and Architecture Decision

## Decision

AnyDB adopts two related primitives:

- **AnythingKube** — the universal governed unit
- **AnyAgent** — the autonomous actor specialization of AnythingKube

## Canonical Definitions

> AnythingKube is the smallest complete, governable, portable, and reconcilable unit of truth, data, work, intelligence, or artifact in AnyDB.

> AnyAgent is an AnythingKube specialized for autonomous action under an explicit platform-held contract.

## Relationship

```text
AnythingKube
├── Data
├── Identity
├── Event
├── Policy
├── Artifact
├── Model
├── Contract
├── Decision
├── Work
├── Evidence
├── Provider
├── Edge
└── AnyAgent
```

AnyAgent does not replace AnythingKube.

It extends it.

## AnythingKube Formula

```text
AnythingKube
=
Identity
+ State
+ Time
+ Location
+ Policy
+ Evidence
+ Contract
+ Events
+ Reconciliation
```

## AnyAgent Formula

```text
AnyAgent
=
AnythingKube
+ Objective
+ Context
+ Skills
+ Tools
+ Memory
+ Delegation
+ Budget
+ Approval
+ Execution
+ Outcome
```

## Canonical Hierarchy

```text
Property
   ↓
AnythingKube
   ↓
AnythingKubeSet
   ↓
AnythingKubeGraph
   ↓
Fabric
   ↓
Platform
```

Autonomous execution path:

```text
AnythingKube
   ↓ specialized as
AnyAgent
   ↓ operates through
Work Contract
   ↓ executes at
Cloud / Edge
   ↓ returns
Evidence
   ↓ verified by
Reconciliation
   ↓ establishes
Trust
```

## Canonical Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: AnythingKube
metadata:
  id: urn:anydb:anythingkube:agent:billing-operator
  type: AnyAgent
  version: 1
  owner: urn:anydb:organization:opendataworld
  lifecycle: active
  dimensions:
    time:
      validFrom: 2026-06-11T00:00:00Z
      validTo: null
    location:
      authority: urn:anydb:organization:opendataworld
spec:
  state: {}
  contract: urn:anydb:contract:billing-agent:v1
  policies: []
  evidence: []
  agent:
    objective: reconcile-billing
    context: []
    skills: []
    tools: []
    memory: []
    delegation: null
    budget: null
status:
  events: []
  projections: []
  reconciliation:
    state: pending
  trust:
    state: provisional
```

## AnyAgent Requirements

Every AnyAgent must have:

- canonical identity
- accountable owner
- explicit objective
- bounded context
- declared skills
- declared tools
- memory policy
- authorization policy
- delegation scope
- budget or resource constraints
- approval requirements
- evidence requirements
- terminal conditions
- reconciliation behavior

## Agent Autonomy Boundary

AnyAgent autonomy exists inside the contract.

```text
Objective
  ↓
Context
  ↓
Reasoning
  ↓
Proposed Command
  ↓
Policy + Approval
  ↓
Execution
  ↓
Observed Outcome
  ↓
Reconciliation
```

Model output or agent intent does not become authoritative truth by itself.

## AnyAgent Lifecycle

Recommended lifecycle states:

```text
onboarding
active
probation
leave
suspended
terminated
alumni
archived
```

Every lifecycle transition must create an event.

## AnyAgent Memory

Memory remains governed data.

Recommended classes:

- observations
- working context
- episodic memory
- semantic memory
- decision history
- tool outcomes
- summaries

Derived summaries and embeddings must retain source lineage.

## AnyAgent at the Edge

An AnyAgent may operate locally at the edge when its contract, policies, artifacts, credentials, and limits are available and verifiable.

```text
Signed Agent Contract
        ↓
Edge Admission
        ↓
Local Context
        ↓
Local Reasoning
        ↓
Governed Command
        ↓
Observed Outcome
        ↓
Evidence + Reconciliation
```

## No Vendor Lock-In

AnyAgent must remain portable across compatible:

- model providers
- ML libraries
- runtimes
- clouds
- Kubernetes distributions
- memory providers
- tool providers
- policy engines

The platform owns the identity, contract, memory lineage, events, evidence, and trust state.

## Naming Migration

Previous references to `Kube` as the universal primitive should be interpreted as `AnythingKube` in future specifications.

Specialized names may remain as semantic aliases:

```text
DataKube       = AnythingKube<Data>
ArtifactKube   = AnythingKube<Artifact>
ModelKube      = AnythingKube<Model>
WorkKube       = AnythingKube<Work>
AgentKube      = AnyAgent
```

Existing draft files do not need to be deleted immediately. They should be revised through versioned migration to avoid losing architectural history.

## Platform Positioning

```text
AnythingKube = smallest complete unit of governed truth
AnyAgent     = smallest complete unit of governed autonomy
AnyDB        = store and graph of AnythingKubes
Fabric       = reconciled network of AnythingKubes and AnyAgents
Platform     = contract holder and trust provider
```

## Final Statement

> AnythingKube represents anything as governed truth. AnyAgent turns governed truth into governed autonomy. AnyDB remembers both, The Fabric connects them, and the platform verifies every outcome through reconciliation.
