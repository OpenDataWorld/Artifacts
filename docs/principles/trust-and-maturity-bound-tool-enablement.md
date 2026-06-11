# Trust- and Maturity-Bound Tool Enablement

Status: Normative Foundation Principle

## Principle

> The platform enables tools according to the agent’s current trust score, maturity level, registered environment, and demonstrated execution ability.

Tool access is not universal and does not arise merely from identity, installation, model capability, or network reachability. Every tool must be enabled contextually, progressively, and revocably under the platform contract.

## Core Rule

> Trust determines how much autonomy may be considered. Maturity determines which operating level is permitted. Ability determines what the agent can actually execute. The platform enables only the intersection.

## Canonical Model

```text
Agent Identity
    ↓
Compliance and Eligibility
    ↓
Trust Score
    ↓
Maturity Level
    ↓
Execution Ability
    ↓
Environment Compatibility and Conformance
    ↓
Tool Selection
    ↓
Bounded Tool Lease
    ↓
Heartbeat, Evidence, and Continuous Revalidation
```

## Tool Enablement Is a Platform Decision

The platform owns the tool contract and decides:

- whether the tool is registered;
- whether it is compatible with the environment;
- whether it conforms to the active contract;
- whether the agent is eligible;
- whether the agent is able;
- whether the trust score is sufficient;
- whether the maturity level permits the consequence class;
- whether maker–checker or human approval is required;
- whether the tool must remain read-only, simulated, staged, or executable.

An agent may request a tool. It may not self-enable one.

## Trust Score

Trust should be evidence-based, contextual, time-bound, and revocable.

It may consider:

- identity integrity;
- instruction-to-outcome alignment;
- successful Kubes;
- conformance history;
- quality results;
- recovery performance;
- policy adherence;
- heartbeat health;
- provenance completeness;
- incident history;
- unresolved disputes;
- ownership and accountability continuity.

```text
Trust Score
=
Verified Delivery History
+ Conformance
+ Provenance
+ Recovery Performance
- Unresolved Risk
```

A trust score from one domain or environment does not automatically transfer to another.

## Maturity Level

Maturity defines the agent’s approved operating level.

A practical ladder is:

```text
L0 — Unregistered
L1 — Identified
L2 — Observable
L3 — Assisted
L4 — Supervised
L5 — Bounded Execution
L6 — Production-Bounded
L7 — Operationalized
L8 — Federated
L9 — Continuously Assured
```

The effective maturity ceiling is the lowest critical maturity among the agent, tool, environment, operating model, platform, and dependencies.

```text
Effective Maturity
=
Minimum(
  Agent Maturity,
  Tool Maturity,
  Environment Maturity,
  Operating Model Maturity,
  Platform Maturity,
  Critical Dependency Maturity
)
```

## Execution Ability

Ability asks whether the agent can perform the intended operation under current conditions.

It includes:

- verified skill;
- tool-specific competence;
- current capacity;
- correct operating model;
- required resources;
- environment readiness;
- quality assurance;
- recovery readiness;
- ability to produce evidence;
- ability to stop safely.

Past success is evidence, but not permanent proof of current ability.

## Tool Classes

Tools should be classified by consequence and reversibility.

```text
T0 — Observe
T1 — Read and Search
T2 — Draft and Recommend
T3 — Simulate and Test
T4 — Create Reversible Changes
T5 — Execute Bounded Operational Changes
T6 — High-Consequence or Irreversible Operations
```

Higher classes require stronger trust, maturity, validation, separation of duties, and human authority.

## Enablement Matrix

| Trust / Maturity State | Permitted Tool Access |
|---|---|
| Unknown or unregistered | No tools; registration only |
| Low trust / early maturity | Read-only and sandboxed tools |
| Developing trust | Draft, recommend, and simulate |
| Verified and supervised | Reversible tools with approval |
| Production-bounded | Contracted operational tools within strict limits |
| High consequence | Independent checker, human authority, and single eligible committer required |

No score alone grants access. All mandatory checks must pass.

## Canonical Tool Enablement Envelope

```yaml
apiVersion: fabric.opendata.world/v1alpha1
kind: ToolEnablement
metadata:
  id: urn:fabric:tool-enablement:01J...
  version: 1
spec:
  agent: urn:fabric:agent:operations-agent
  accountablePrincipal: urn:fabric:organization:enterprise-01
  context:
    domain: urn:fabric:domain:platform-operations
    environment: urn:fabric:environment:production-cluster-a
    mode: execute
    consequenceClass: C2-bounded-operational
  trust:
    score: 82
    threshold: 75
    domain: platform-operations
    validUntil: 2026-06-12T12:00:00Z
  maturity:
    agent: L7-operationalized
    tool: L7-operationalized
    environment: L6-production-bounded
    effective: L6-production-bounded
  ability:
    skill: verified
    capacity: available
    recovery: verified
    evidenceProduction: passed
  tool:
    identity: urn:fabric:tool:reconciliation-runner:v3
    class: T5-bounded-operational
    allowedActions:
      - execute-approved-reconciliation
    prohibitedActions:
      - alter-operating-model
      - expand-scope
      - disable-telemetry
  lease:
    validFrom: 2026-06-11T12:00:00Z
    validUntil: 2026-06-11T12:15:00Z
    maximumInvocations: 1
    idempotencyKey: reconcile-state-42
status:
  decision: enabled-within-bounds
  signedBy: urn:fabric:platform-authority:tool-gate
```

## Tool Lease

Tool access should be granted as a bounded lease, not a permanent entitlement.

The lease must declare:

- tool identity and version;
- agent identity;
- active context;
- allowed actions;
- prohibited actions;
- invocation limit;
- time limit;
- cost limit;
- data boundary;
- environment;
- evidence requirements;
- stop conditions;
- revocation triggers;
- terminal state.

## Selection Logic

The platform selects tools from the eligible tool pool.

```text
Registered Tools
    ↓ Compatibility
Compatible Tools
    ↓ Compliance
Eligible Tools
    ↓ Conformance
Context-Fit Tools
    ↓ Trust + Maturity + Ability
Enabled Tool Set
```

The platform should select the least-powerful tool sufficient to achieve the contracted outcome.

```text
Minimum Necessary Capability
=
Lowest Consequence Tool
that can safely deliver the contract
```

## Human and Maker–Checker Controls

For higher consequence classes:

- the agent proposes the tool;
- an independent checker validates the choice;
- an authorized human or lawful authority approves where required;
- one eligible execution Kube receives the commit lease;
- the platform monitors the operation continuously.

## Continuous Revalidation

Tool enablement must be recalculated when:

- trust changes;
- maturity changes;
- ability degrades;
- the environment changes;
- the tool version changes;
- the operating mode changes;
- the contract changes;
- evidence expires;
- heartbeat fails;
- an incident occurs;
- the agent enters a new domain or jurisdiction.

## Revocation

The platform must restrict or revoke tool access when:

- trust falls below the threshold;
- maturity no longer supports the tool class;
- current ability cannot be demonstrated;
- context or contract changes;
- the environment becomes nonconformant;
- telemetry is disabled;
- the tool exceeds its lease;
- an ownership or accountability gap appears;
- the operation deviates from the approved procedure.

## No Operations in the Dark

Every tool invocation must preserve:

- requesting agent;
- approving authority;
- tool identity and version;
- instruction;
- context;
- contract;
- lease;
- inputs and outputs as permitted;
- state transition;
- cost and resource use;
- outcome;
- recovery or terminal state.

A tool that cannot produce proportionate operational evidence is not eligible for consequential use.

## Platform Invariants

1. Agents cannot self-enable tools.
2. Tool access depends on contextual trust, effective maturity, and current ability.
3. Every tool and environment must be registered.
4. Compatibility opens consideration; conformance determines contextual fit.
5. The platform enables the least-powerful sufficient tool.
6. Tool access is leased, scoped, metered, expirable, and revocable.
7. Higher consequence requires stronger separation of duties and human authority.
8. Trust from one domain or environment does not transfer automatically.
9. Heartbeat failure, evidence expiry, or accountability gaps close tool access by default.
10. Every invocation is contract-bound, attributable, observable, and evidenced.

## Foundation Formula

```text
Enabled Tool Set
=
Registered Tools
∩ Compatible Tools
∩ Compliant Tools
∩ Conformant Tools
∩ Trust-Permitted Tools
∩ Maturity-Permitted Tools
∩ Ability-Supported Tools
```

```text
Tool Execution Authority
=
Platform Selection
+ Bounded Lease
+ Eligible Agent
+ Able Agent
+ Registered Environment
+ Active Heartbeat
```

## Final Statement

> The platform enables tools according to the agent’s contextual trust score, effective maturity level, and demonstrated execution ability. It chooses the least-powerful tool sufficient for the contracted outcome, grants a short-lived bounded lease, monitors every invocation, and revokes access whenever trust, maturity, ability, environment, or accountability no longer supports the operation.
