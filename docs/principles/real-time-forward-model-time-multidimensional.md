# AnyDB Foundation Principle: Real Time Moves Forward; Model Time May Move Across Dimensions

Status: Normative Foundation Principle

## Principle

> In the real world, time moves forward. In modeled worlds, time may move across versions, branches, simulations, memories, and dimensions—as long as clarity, causality, provenance, and sanity are preserved.

AnyDB distinguishes physical time from modeled time.

Physical time governs real execution, legal effect, observation, expiry, and irreversible consequence.

Modeled time supports replay, simulation, forecasting, branching, historical reconstruction, scenario analysis, and alternate views.

## Core Rule

> Real-world effects are forward-only. Model-world exploration may move freely, but must never be confused with committed reality.

## Two Time Realms

### Real Time

Real time governs:

- physical events
- authoritative commits
- legal validity
- payments
- credentials
- deadlines
- edge execution
- observed outcomes
- reconciliation

Real time is monotonic at the level of accepted history.

Corrections are new events, not rewrites of what already occurred.

### Model Time

Model time supports:

- replay
- time-travel queries
- branch exploration
- scenario simulation
- counterfactual analysis
- forecasting
- memory traversal
- alternate versions
- historical views

Model time may move backward, forward, sideways, or across branches.

It remains a representation, not physical reversal.

## Canonical Distinction

```text
Real World
  └── Forward-only event history

Model Worlds
  ├── Historical replay
  ├── Future simulation
  ├── Alternate branch
  ├── Counterfactual world
  ├── Memory map
  └── Domain projection
```

## Temporal Modes

Recommended temporal modes:

```text
real
historical
replay
simulation
forecast
counterfactual
branch
projection
memory
```

Every query, decision, model run, and agent action should declare its temporal mode when ambiguity is possible.

## Canonical Temporal Context

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: TemporalContext
metadata:
  id: urn:anydb:temporal-context:scenario-42
spec:
  mode: simulation
  baseWorld: urn:anydb:fabric:production
  baseVersion: 8841
  asOf: 2026-06-11T12:00:00Z
  branch: urn:anydb:branch:pricing-experiment
  horizon:
    from: 2026-06-11T12:00:00Z
    to: 2026-07-11T12:00:00Z
  commitEffects: false
status:
  provenance: []
  trust:
    state: provisional
```

## Real-World Invariant

An authoritative real-world event may not be removed or changed to create a cleaner history.

If an error occurs, AnyDB records:

```text
Original Event
      ↓
Correction Event
      ↓
Reconciled State
```

The system preserves both what happened and how the record was corrected.

## Branching Worlds

A branch is a modeled world derived from a known version of truth.

```text
Canonical World v18
      |
      +-- Branch A: policy change
      +-- Branch B: pricing change
      +-- Branch C: failure scenario
```

Each branch must declare:

- base world
- base version
- creator
- purpose
- time created
- assumptions
- transformations
- policy
- whether effects are executable

## Simulation

Simulation may advance time beyond the present or replay past states.

Simulation output must remain marked as:

```text
simulated
predicted
estimated
counterfactual
```

It must never silently enter authoritative state.

## Memory Traversal

Memory is a map and may be navigated non-linearly.

An agent may move:

- backward to a prior event
- across to a related domain
- forward to a predicted outcome
- sideways to another branch

The navigation path must preserve source identity, version, and temporal mode.

## Time Travel Queries

Historical queries may ask:

- What was true at time T?
- What did the platform believe at time T?
- What policy was active at time T?
- What context did an agent receive at time T?
- Which branch produced this result?

The answer must distinguish valid time from transaction time.

## Multi-Dimensional Time

Modeled time may include dimensions such as:

- valid time
- transaction time
- occurrence time
- observation time
- branch time
- simulation time
- model horizon
- reconciliation time
- cultural or domain calendar

Each dimension must be named and typed.

No generic `timestamp` should silently represent several meanings.

## Clarity and Sanity

Any movement across time or dimensions must preserve four guarantees.

### Clarity

The user or agent can tell whether it is viewing reality, history, simulation, forecast, or branch.

### Causality

The system preserves which events caused which states and outcomes.

### Provenance

Every modeled state points to its base world, version, transformations, model, and assumptions.

### Sanity

The system prevents incompatible time modes, impossible state transitions, circular causation, and accidental execution of simulated outcomes.

## Sanity Checks

Recommended checks:

1. no event causes itself
2. no branch predates its declared base version
3. no forecast is marked authoritative without promotion
4. no simulated credential authorizes real execution
5. no historical policy is applied as current without explicit mode
6. no future observation is recorded as completed fact
7. no branch merges silently into the canonical world
8. no circular temporal dependency remains unresolved
9. no timestamp crosses calendars or time zones without normalization
10. no model-world action reaches the real edge without a new real-world contract

## Promotion to Reality

A modeled result becomes real only through a governed promotion path.

```text
Simulation / Branch Result
          ↓
Review and Evidence
          ↓
Policy and Approval
          ↓
New Real-World Command
          ↓
Forward-Only Execution
          ↓
Observed Outcome
          ↓
Reconciliation
```

The model result itself is never retroactively treated as real execution.

## AnyAgent Temporal Boundaries

AnyAgent must know which temporal world it is operating in.

An agent contract should declare:

- temporal mode
- current authoritative version
- accessible historical range
- permitted simulation horizon
- branch permissions
- whether tool execution is real or simulated
- promotion and approval rules

A simulation agent must not accidentally invoke real tools.

## Time and the Edge

Real execution occurs at the temporal edge.

```text
Modeled Intent
      ↓
Real Contract
      ↓
Time-Valid Command
      ↓
Edge Execution
      ↓
Forward-Only Outcome
```

Time is the cliff when the valid execution or reconciliation window closes.

## Merge Semantics

A branch may influence the real world only through an explicit merge proposal.

The proposal must include:

- source branch
- base version
- changed AnythingKubes
- conflicts
- evidence
- policy decision
- expected outcomes
- rollback or compensation strategy

A merge creates new real-world events. It does not rewrite prior history.

## Domain and Cultural Time

Domains and cultures may use different calendars, cycles, business periods, fiscal years, and temporal interpretations.

AnyDB may support these as modeled dimensions while preserving a normalized reference timeline for interoperability.

Cultural or domain time must be represented respectfully and explicitly, not flattened into one unlabeled timestamp.

## Platform Invariants

1. Real-world authoritative history moves forward.
2. Corrections create new events.
3. Model worlds may traverse or branch across time.
4. Every temporal world and mode is explicit.
5. Every branch preserves its base world and version.
6. Simulated and predicted states never masquerade as authoritative truth.
7. Modeled outcomes require a new real-world contract before execution.
8. Causality and provenance survive every traversal.
9. Temporal sanity checks prevent contradiction and accidental execution.
10. The platform always distinguishes what happened from what could happen.

## Foundation Formula

```text
Real Time = Forward-Only Consequence
```

```text
Model Time = Multi-Dimensional Exploration
```

```text
Safe Temporal Freedom = Clarity + Causality + Provenance + Sanity
```

## Final Statement

> Real time moves forward because consequences cannot be undone. Model worlds may move through any temporal or contextual dimension, provided they preserve clarity, causality, provenance, and sanity—and never confuse possibility with reality.
