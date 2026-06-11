# AnyDB Foundation Principle: Agent Maturity Is Baselined by Production System Maturity

Status: Normative Foundation Principle

## Principle

> Agent maturity must be baselined against the maturity of the production system in which the agent operates.

An agent may be well-specified, well-tested, and behaviorally reliable, but it cannot be considered production-mature when its runtime, data, infrastructure, policies, observability, security, recovery, or human-control surfaces remain immature.

The production system sets the maturity floor and the operational ceiling.

## Core Rule

> No agent is more production-ready than the least mature critical system it depends on.

## Canonical Model

```text
Agent Maturity
        ↓ constrained by
Production System Maturity
        ↓ composed from
Kernel + Runtime + Data + Infrastructure + Controls + Operations + Recovery
```

## Effective Maturity

```text
Effective Agent Maturity
=
Minimum(
  Agent Capability Maturity,
  Operating Model Maturity,
  Runtime Maturity,
  Data Maturity,
  Infrastructure Maturity,
  Security Maturity,
  Compliance Maturity,
  Observability Maturity,
  Recovery Maturity,
  Human Governance Maturity
)
```

A high score in one dimension cannot compensate for a critical failure in another.

## Production System Maturity Dimensions

The baseline must evaluate:

- platform contract maturity
- stable-kernel maturity
- runtime maturity
- identity and access maturity
- data quality and provenance maturity
- policy and compliance maturity
- security maturity
- observability maturity
- quality-assurance maturity
- deployment and release maturity
- incident-response maturity
- recovery and continuity maturity
- scale maturity
- provider and dependency maturity
- human-control maturity
- lifecycle and retirement maturity

## Agent vs. System Maturity

```text
Agent Maturity
  = readiness of the agent itself

Production System Maturity
  = readiness of the environment carrying real consequences

Production Eligibility
  = both are sufficiently mature for the consequence class
```

## Baseline Rule

Before assigning an agent maturity level for production, the platform must first establish the production-system baseline.

```text
Production Baseline
    ↓
Agent Evaluation
    ↓
Dependency Fit
    ↓
Consequence-Class Eligibility
```

## Canonical Baseline Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: ProductionMaturityBaseline
metadata:
  id: urn:anydb:production-baseline:platform-01
  version: 1
spec:
  platform: urn:anydb:platform:agent-platform
  environment: urn:anydb:environment:production
  dimensions:
    kernel: industrialized
    runtime: operationalized
    identity: conformant
    data: verified
    security: conformant
    compliance: conformant
    observability: operationalized
    qualityAssurance: operationalized
    recovery: verified
    scale: demonstrated
    humanControl: operationalized
    lifecycle: conformant
  weakestCriticalDimension: scale
  maximumAgentEligibility: production-bounded
status:
  baseline: accepted
  nextReview: 2026-09-11T00:00:00Z
```

## Consequence Classes

The production baseline should be matched to the consequence class:

```text
C0 — no real-world effect
C1 — informational or reversible
C2 — bounded operational effect
C3 — material financial, legal, privacy, or service effect
C4 — safety-critical or difficult-to-reverse effect
```

Higher consequence requires stronger system maturity.

## Maturity Ceiling

```text
Permitted Agent Authority
≤
Agent Demonstrated Maturity
≤
Production System Maturity Ceiling
```

Even a highly mature agent must be restricted when the surrounding system is less mature.

## Dependency Rule

Every production agent must declare critical dependencies such as:

- model provider
- database
- runtime
- identity provider
- policy engine
- network
- storage
- hardware drivers
- observability stack
- human escalation path

The effective maturity is constrained by the weakest critical dependency.

## Virtual and Production Separation

A mature virtual agent may still be ineligible for production.

```text
Virtual Maturity
    ≠
Production Maturity
```

Promotion requires the production system itself to demonstrate:

- stable contracts
- hardened scaffolding
- deterministic controls
- enterprise quality assurance
- provenance
- stop and revoke controls
- tested recovery
- accountable human oversight

## Baseline Changes

A material change to the production system requires revalidation of every dependent agent.

Examples include:

- runtime upgrade
- provider migration
- model change
- database change
- policy change
- identity change
- new surface
- new hardware driver
- new jurisdiction
- changed scale or load

## Demotion and Restriction

If the production baseline degrades, dependent agents must be:

- restricted
- demoted
- moved to simulation
- suspended
- or retired

until the system is restored and revalidated.

## Platform Invariants

1. Production-system maturity is measured before production agent maturity.
2. No agent exceeds the maturity ceiling of its environment.
3. The weakest critical dependency constrains effective maturity.
4. Maturity is consequence-class specific.
5. Virtual maturity does not imply production eligibility.
6. Material system changes trigger agent revalidation.
7. System degradation automatically reduces agent authority.
8. Human control, recovery, and provenance are part of production maturity.
9. Production readiness requires both mature agents and mature systems.
10. Enterprise trust is earned by the complete operating system, not the agent in isolation.

## Foundation Formula

```text
Effective Production Agent Maturity
=
Minimum(Agent Maturity, Production System Maturity)
```

```text
Production Readiness
=
Mature Agent
+ Mature Operating Model
+ Mature Production System
+ Appropriate Consequence Controls
```

## Final Statement

> Baseline Agent Maturity against Production System Maturity. An agent is never more production-ready than the platform, runtime, data, controls, recovery, and human governance that surround it. Enterprise readiness belongs to the whole operating system, not to the agent alone.
