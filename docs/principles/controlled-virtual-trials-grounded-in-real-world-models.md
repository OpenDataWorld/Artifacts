# AnyDB Foundation Principle: Controlled Virtual Trials Grounded in Real-World Models

Status: Normative Foundation Principle

## Principle

> Multiple trials may be explored in virtual environments, but every trial must be grounded in real-world models, documented theories, trusted concepts, appropriate tools, and the operator’s own verified skills and controllable capabilities.

The virtual environment expands possibility. The real-world model supplies meaning. The operator’s skills determine what can be governed safely. The platform holds the contract and prevents imagined capability from being mistaken for real authority.

## Core Rule

> Explore broadly with what you can model, explain, operate, and control. Promote only what you can verify, govern, and support in the real world.

## Canonical Model

```text
Real-World Observation
        ↓
Trusted Theory and Documented Knowledge
        ↓
Concept
        ↓ learning
Model
        ↓
Virtual Environment
        ↓
Multiple Controlled Trials
        ↓
Comparison and Evidence
        ↓
Capability and Safety Review
        ↓
One Governed Production Step
```

## Trial Inputs

Every virtual trial should declare:

- source real-world model
- domain
- trusted theories
- documented concepts
- source documents
- assumptions
- tools
- operator identity
- operator skills
- capability maturity
- controllable variables
- uncontrollable variables
- fidelity limits
- expected evidence
- stop conditions

## What the Operator Must Control

The operator should control or explicitly bound:

- tools
- inputs
- permissions
- resources
- environment
- model versions
- agent roles
- time mode
- cost
- blast radius
- data access
- output destinations
- stop and cleanup procedures

Anything outside control must be declared as a dependency, uncertainty, or external condition.

## Skills Before Tools

```text
Tool Availability
    ≠
Safe Capability
```

A tool becomes operationally useful only when the operator has the relevant skill, context, judgment, and authority to use it constructively.

Recommended skill states:

```text
claimed
learned
demonstrated
verified
operationalized
industrialized
```

The required skill maturity must be proportional to the consequence of the trial.

## Trusted Knowledge Grounding

A trial may draw from:

- primary observations
- documented experiments
- peer-reviewed research
- official standards
- trusted domain registries
- verified community knowledge
- historical records
- proven operating practices

Every source must preserve identity, provenance, version, domain, trust state, and limitations.

## Multiple Trials

The virtual environment may support:

```text
Trial A — baseline
Trial B — alternate model
Trial C — alternate tool
Trial D — alternate operator profile
Trial E — stress condition
Trial F — failure condition
Trial N — counterfactual
```

Each trial must remain isolated, versioned, attributable, and non-authoritative until reviewed.

## Canonical Trial Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: ControlledVirtualTrial
metadata:
  id: urn:anydb:trial:01J...
  version: 1
  owner: urn:anydb:operator:example
spec:
  domain: urn:anydb:domain:operations
  sourceModel: urn:anydb:model:real-world-system:v3
  theories:
    - urn:anydb:theory:queueing:v2
  documents:
    - urn:anydb:document:benchmark:v4
  tools:
    - urn:anydb:tool:simulator:v2
  operator:
    identity: urn:anydb:identity:operator-01
    skills:
      - urn:anydb:skill:simulation:verified
      - urn:anydb:skill:domain-operations:operationalized
  controls:
    environment: isolated
    realWorldEffects: prohibited
    maxCost: 50
    maxDuration: 2h
    stopConditions:
      - integrity-failure
      - resource-limit-exceeded
      - policy-denied
  assumptions:
    - stable-network-latency
  uncertainties:
    - external-demand-variation
  evidenceRequired:
    - input-manifest
    - execution-log
    - output-report
    - comparison-result
status:
  state: prepared
  trust: provisional
```

## Rationality and Coherency Checks

Before a trial begins, the platform checks:

- sanity for coherence
- clarity for understandable intent
- logical coherency for internal consistency
- rationality for plausible possibility
- compliance for conformance
- capability maturity for safe operation

## Trial Results

Every result must be classified as:

```text
observed-in-trial
inferred
simulated
predicted
failed
inconclusive
validated-against-real-data
candidate-for-production-review
```

A virtual result is never automatically a real-world fact.

## Promotion to Production

```text
Trial Result
    ↓
Evidence Review
    ↓
Known-Fact Consistency
    ↓
Technical Feasibility
    ↓
Capability Maturity
    ↓
Quality Assurance
    ↓
Security, Privacy, and Compliance
    ↓
Human Approval Where Required
    ↓
One Bounded Production Step
```

## Human and Agent Roles

```text
Human
  = defines purpose, chooses the problem, accepts responsibility

Agent
  = orchestrates trials and operates bounded procedures

Technology
  = tools and execution capability

Platform
  = stable contract, safety gates, evidence, and promotion boundary
```

## No Imagined Control

The platform must reject claims of control that are not demonstrated.

Examples include:

- undeclared provider dependencies
- inaccessible model internals
- unknown hardware behavior
- unbounded external APIs
- uncontrolled agent delegation
- missing stop mechanisms
- unsupported recovery

## Platform Invariants

1. Virtual trials are grounded in real-world models.
2. Theories, concepts, and sources are documented and attributable.
3. Operators use only tools they are qualified and authorized to control.
4. Uncontrolled variables and dependencies remain explicit.
5. Every trial is isolated, versioned, evidenced, and terminal.
6. Multiple trials may explore different possibilities safely.
7. Trial results remain distinct from real-world outcomes.
8. Promotion requires enterprise-grade review and quality assurance.
9. Agents cannot expand authority through simulation.
10. Only verified, controllable, valuable, safe, and conformant outcomes may enter production.

## Foundation Formula

```text
Controlled Virtual Trial
=
Real-World Model
+ Trusted Theory
+ Documented Knowledge
+ Appropriate Tools
+ Verified Skills
+ Explicit Controls
+ Evidence
```

```text
Production Eligibility
=
Validated Trial
+ Real-World Feasibility
+ Capability Maturity
+ Quality Assurance
+ Governance
```

## Final Statement

> Use real-world models, trusted theories, documented concepts, appropriate tools, and only the skills and controls you genuinely possess. Explore many possibilities in virtual environments, but allow only verified, explainable, mature, and safely governed outcomes to take one decisive step into the real world.
