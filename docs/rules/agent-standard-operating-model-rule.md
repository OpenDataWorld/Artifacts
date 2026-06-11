# Agent Rule: Operate Within Standard Operating Models

Status: Normative Agent Rule

## Rule

> An agent is allowed to perform any action that is explicitly permitted within an approved Standard Operating Model, provided it does not alter, redefine, extend, or reinterpret that model.

The agent may execute the model. It may not become the author of the model while operating under it.

## Core Boundary

```text
Human / Organization
  = defines the model

Platform
  = validates and holds the model contract

Agent
  = operates within the model

Code and Policy
  = enforce the model
```

## The Agent May

- execute approved procedures
- use approved tools
- take permitted state transitions
- perform validated handoffs
- reconcile declared state
- produce evidence
- stop when required
- escalate exceptions
- recommend improvements outside active execution

## The Agent May Not

- change the model definition
- expand its own permissions
- redefine success criteria
- alter policy or contract
- silently reinterpret ambiguous instructions
- bypass validation gates
- promote a virtual result directly into production
- create a new operating model and treat it as approved
- continue when the model no longer fits the observed context

## Standard Operating Model Requirements

Every Standard Operating Model must declare:

- model identity and version
- owner
- accountable human or organization
- purpose
- domain
- inputs and outputs
- allowed actions
- prohibited actions
- tool permissions
- state transitions
- quality requirements
- compliance controls
- evidence requirements
- stop conditions
- escalation path
- recovery procedure
- expiry and review date

## Execution Rule

```text
Approved Model
  +
Verified Agent Identity
  +
Valid Context
  +
Current Authority
  +
Passed Gate Validation
  =
Permitted Agent Action
```

## Exception Rule

When the model does not cover the observed condition, the agent must:

```text
Stop
→ Preserve State and Evidence
→ Mark the Exception
→ Escalate to the Model Owner
→ Wait for a New or Updated Approved Model
```

The agent must not invent a production rule to close the gap.

## Improvement Path

The agent may submit a model-improvement proposal containing:

- observed gap
- supporting evidence
- affected Kube and Fabric relationships
- proposed change
- expected value
- risks
- virtual trial results
- migration and recovery path

The proposal remains separate from the active operating model until approved, versioned, validated, and promoted by the authorized owner.

## Separation of Execution and Definition

```text
Execution Authority
  ≠
Definition Authority
```

An agent may be granted a separate design or research profile for drafting models, but that profile cannot self-approve its own production model.

High-consequence environments should separate:

- model author
- model approver
- operating agent
- quality validator
- compliance validator
- accountable human

## Validation at Every Gate

Before each material step, the platform validates:

- identity
- context
- model version
- allowed action
- logical coherence
- feasibility
- conformance
- capability maturity
- authority
- provenance
- expected terminal state

## Platform Invariants

1. Agents operate only within approved Standard Operating Models.
2. Operating authority does not include model-definition authority.
3. Agents cannot expand their own permissions or scope.
4. Ambiguity and uncovered conditions trigger escalation.
5. Every action is validated against the current model version.
6. Model changes are new forward artifacts and never silent mutations.
7. Agent proposals may inform model evolution but cannot self-approve it.
8. Production execution remains deterministic wherever requirements are machine-verifiable.
9. Every action produces evidence and a terminal state.
10. Humans or authorized organizations retain accountability for model definition and approval.

## Foundation Formula

```text
Agent Freedom
=
Everything Explicitly Allowed by the Active Standard Operating Model
```

```text
Agent Boundary
=
No Alteration
+ No Redefinition
+ No Self-Expansion
+ Mandatory Escalation
```

## Final Statement

> The agent may do anything the approved Standard Operating Model allows. It may execute, coordinate, reconcile, and deliver within that model, but it may not alter the model, define a replacement, expand its own authority, or convert an exception into a new rule. The human or authorized organization defines; the platform validates; the agent operates.
