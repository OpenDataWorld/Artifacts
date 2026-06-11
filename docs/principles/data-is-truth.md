# AnyDB Foundation Principle: Data Is Truth

Status: Normative Foundation Principle

## Principle

> Data is truth when it is canonical, versioned, evidenced, governed, and reconciled.

AnyDB treats data as the durable record of reality across identities, events, policies, decisions, artifacts, models, agents, and outcomes.

Data is not merely stored information. It is the accountable representation of what exists, what happened, what was decided, what was permitted, and what was verified.

## Core Rule

> Truth must be represented as data, and data must remain explainable.

## Data Becomes Truth Through Five Guarantees

### Identity

Truth must identify what or whom it describes.

### Version

Truth must identify which authoritative state is current and how it changed.

### Time

Truth must record when a fact was valid, observed, recorded, and reconciled.

### Evidence

Truth must preserve its source, provenance, and supporting artifacts.

### Reconciliation

Truth must be compared with observed reality and corrected, compensated, or escalated when divergence appears.

## Single Version of Truth

Every governed object has one canonical identity and one authoritative version at a time.

```text
Canonical Truth
      |
      +-- Replica
      +-- Projection
      +-- Search Index
      +-- Feature View
      +-- Vector Representation
      +-- Edge Copy
      +-- External Observation
```

These derived representations do not become independent truths.

They remain traceable to the canonical version and expose their freshness, provenance, and reconciliation status.

## Data Is Not Automatically True

Raw input, model output, user claims, external observations, and generated content are data, but they are not automatically authoritative truth.

AnyDB classifies them explicitly as:

```text
observed
proposed
verified
authoritative
projected
derived
disputed
superseded
reconciled
```

The system must never hide this distinction.

## Events Preserve Causality

Entities represent current authoritative state.

Events preserve the facts that produced that state.

```text
Entity = Current Truth
Event  = Historical Truth
```

Together they provide both state and explanation.

## Policy Preserves Legitimacy

A fact may be technically correct but operationally invalid if it was produced without authorization, approval, or policy compliance.

AnyDB therefore records:

- actor identity
- policy version
- decision result
- evidence
- approval
- execution outcome

Truth includes not only what happened, but whether it was permitted and accountable.

## Intelligence Does Not Own Truth

ML libraries, models, and agents may classify, infer, predict, rank, summarize, or generate.

Their outputs are proposals or observations until accepted through governed platform processes.

```text
Model Output
    |
    v
Evidence + Evaluation
    |
    v
Policy + Approval
    |
    v
Authoritative Commit
```

Intelligence interprets data. It does not redefine truth unilaterally.

## Edge Verification

The edge is where intended state meets operational reality.

```text
Intent
  ↓
Command
  ↓
Edge Execution
  ↓
Observed Outcome
  ↓
Reconciliation
  ↓
Verified Truth
```

A command is not truth merely because it was accepted.

The resulting state becomes trusted only after observation and reconciliation.

## Truth Across Scale

Truth must retain the same semantics across:

- embedded runtimes
- single nodes
- edge clouds
- Kubernetes clusters
- regions
- federated organizations

Scaling must not alter canonical identity, policy meaning, event history, or provenance.

## No Vendor Owns Truth

AnyDB contracts define truth independently of one database, cloud, model provider, identity system, or policy engine.

Providers implement capabilities.

The platform retains ownership of:

- canonical identity
- schemas
- event history
- policies
- provenance
- artifacts
- reconciliation evidence
- export and migration paths

## Foundation Formula

```text
Data + Identity + Time + Evidence + Policy + Reconciliation = Truth
```

## Platform Invariants

1. Every truth has canonical identity.
2. Every authoritative change creates a new version.
3. Every version remains historically explainable.
4. Every derived view points to its source version.
5. Every external observation preserves provenance.
6. Every model output is classified before becoming authoritative.
7. Every high-consequence action is policy-governed.
8. Every distributed effect is verified through reconciliation.
9. Every divergence is visible.
10. No provider becomes the sole owner of platform truth.

## Final Statement

> Data is truth. AnyDB gives truth identity, time, evidence, policy, and continuity. The Fabric turns truth into governed work. Reconciliation proves that the work became real.
