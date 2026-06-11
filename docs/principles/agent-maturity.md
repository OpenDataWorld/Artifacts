# Agent Maturity

Status: Normative Foundation Principle

## Principle

> Agent maturity is the evidence-based progression through which an agent earns the right to move from definition, to simulation, to bounded production operation, to trusted participation in federated enterprise systems.

Maturity is not model size, autonomy, popularity, or intelligence claims. It is demonstrated capability under explicit context, contracts, controls, evidence, recovery, and accountable human governance.

## Core Rule

> Authority must never exceed demonstrated maturity.

## Maturity Lifecycle

```text
L0 — Undefined
L1 — Specified
L2 — Simulated
L3 — Demonstrated
L4 — Verified
L5 — Conformant
L6 — Production-Bounded
L7 — Operationalized
L8 — Industrialized
L9 — Federated
L10 — Trusted Principle Agent
```

## L0 — Undefined

The agent idea exists, but identity, purpose, scope, model, owner, and controls are incomplete.

Allowed:

- concept exploration
- documentation

Not allowed:

- trusted execution
- production access

## L1 — Specified

The agent has:

- verified or provisional identity
- accountable owner
- declared purpose
- domain
- context boundaries
- Standard Operating Model
- allowed and prohibited actions
- lifecycle and expiry

The agent is defined but not proven.

## L2 — Simulated

The agent operates only in virtual environments using controlled models, tools, and trial data.

Evidence includes:

- trial logs
- failure cases
- decision traces
- context-boundary tests
- stop-condition tests

Virtual authority remains virtual.

## L3 — Demonstrated

The agent successfully completes bounded Work Kubes in a controlled environment.

It demonstrates:

- task completion
- tool discipline
- handoff behavior
- evidence production
- terminal-state resolution

A demonstration proves capability, not enterprise readiness.

## L4 — Verified

Independent checks verify:

- identity
- ownership
- provenance
- security posture
- context discipline
- bounded rationality
- model and tool integrity
- recovery behavior

## L5 — Conformant

The agent conforms to:

- foundational principles
- active Standard Operating Model
- platform contracts
- domain rules
- security controls
- privacy controls
- quality requirements
- applicable law and policy

Conformance requires evidence, not declaration.

## L6 — Production-Bounded

The agent may operate on a real surface within a narrow, explicit authority envelope.

Requirements include:

- least privilege
- deterministic production checks
- validation at every gate
- human at the wall for defined consequence classes
- blast-radius limits
- observability
- immediate stop and revoke controls
- tested recovery

## L7 — Operationalized

The agent delivers repeatedly in production under service and support expectations.

It demonstrates:

- reliability
- repeatability
- measurable value
- stable handoffs
- incident response
- cost control
- lifecycle management
- definition–delivery alignment

## L8 — Industrialized

The agent operates at scale across workloads, teams, surfaces, regions, and providers.

It demonstrates:

- scalable throughput
- enterprise quality assurance
- supply-chain integrity
- portability
- provider replacement
- sustained efficiency
- compliance automation
- graceful upgrade and retirement

## L9 — Federated

The agent collaborates across independent organizations and domains through common interoperable language and governed handoff protocols.

It preserves:

- local sovereignty
- context
- authority
- provenance
- evidence
- trust boundaries
- lawful exit

## L10 — Trusted Principle Agent

The agent has earned contextual trust through a sustained portfolio of valuable, coherent, conformant, and recoverable Kubes.

It remains bounded, reviewable, revocable, and expirable.

Trusted does not mean unrestricted.

## Maturity Dimensions

Each level should be evaluated across:

- identity maturity
- contextual clarity
- operating-model maturity
- capability maturity
- handoff maturity
- tool-control maturity
- security maturity
- compliance maturity
- quality maturity
- observability maturity
- recovery maturity
- scale maturity
- federation maturity
- value maturity

## Agent Maturity Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: AgentMaturityProfile
metadata:
  id: urn:anydb:agent-maturity:operations-agent
  version: 1
spec:
  agent: urn:anydb:agent:operations-agent
  accountableOwner: urn:anydb:organization:enterprise-01
  domain: urn:anydb:domain:platform-operations
  level: L6-production-bounded
  dimensions:
    identity: verified
    contextualClarity: operationalized
    operatingModel: conformant
    capability: verified
    handoff: verified
    security: conformant
    quality: conformant
    recovery: verified
    scale: demonstrated
    federation: not-yet-eligible
  authority:
    allowedConsequenceClass: bounded-production
    expiresAt: 2026-12-11T00:00:00Z
  evidence:
    - urn:anydb:evidence:simulation-suite:v3
    - urn:anydb:evidence:quality-report:v2
    - urn:anydb:evidence:recovery-test:v1
status:
  eligibility: active-with-conditions
  nextReview: 2026-09-11T00:00:00Z
```

## Promotion Rule

An agent advances only when it has:

- completed the current level
- produced required evidence
- passed coherence and conformance validation
- demonstrated recovery
- received authorized approval
- accepted a new bounded profile

```text
Current Level
  + Required Evidence
  + Validation
  + Approval
  = Next Level Eligibility
```

## Demotion Rule

An agent may be demoted, restricted, suspended, or retired when:

- trust degrades
- evidence expires
- context changes materially
- conformance fails
- security posture weakens
- recovery fails
- value becomes negative
- the operating model is superseded
- ownership becomes unclear

## Authority and Maturity

```text
Permitted Authority
≤
Demonstrated Maturity
```

No agent may use success in one domain, context, or consequence class to claim universal maturity.

## Trust and Maturity

```text
Maturity
=
Demonstrated Readiness

Trust
=
Observed Alignment Between Definition and Delivery
```

Maturity makes the agent eligible to act. Valuable delivery earns trust.

## Platform Invariants

1. Every agent has an explicit maturity level.
2. Maturity is contextual and domain-specific.
3. Authority never exceeds demonstrated maturity.
4. Virtual success does not equal production maturity.
5. Promotion requires evidence, validation, and approval.
6. Production access remains bounded and revocable.
7. Scale, recovery, quality, and federation are separate maturity dimensions.
8. Trusted status never removes validation requirements.
9. Evidence expiry triggers review.
10. Agents retire gracefully when they no longer remain efficient, conformant, secure, or valuable.

## Foundation Formula

```text
Agent Maturity
=
Capability
+ Conformance
+ Quality
+ Recovery
+ Repeated Evidence
+ Accountable Operation
```

```text
Trusted Agent
=
Mature Agent
+ Valuable Kubes
+ Definition–Delivery Alignment
+ Preserved Provenance
```

## Final Statement

> Agent maturity is the disciplined path from specification to trusted enterprise operation. An agent earns each level through evidence, coherent behavior, conformant delivery, recovery, quality, and measurable value. Its authority remains bounded by its demonstrated maturity at every stage.
