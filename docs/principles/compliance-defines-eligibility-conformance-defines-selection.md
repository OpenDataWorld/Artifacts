# Compliance Defines Eligibility; Conformance Defines Selection

Status: Normative Foundation Principle

## Principle

> Compliance defines whether a person, agent, platform, provider, model, tool, Kube, or implementation is eligible to participate. Conformance defines whether that eligible participant satisfies the specific selection criteria for the active contract, context, surface, and consequence class.

Compliance answers: **May this participant enter the eligible pool?**

Conformance answers: **Which eligible participant best matches the declared requirements here and now?**

## Core Rule

> Compliance opens eligibility. Conformance determines selection. Neither alone authorizes execution.

## Canonical Model

```text
Candidate
    ↓
Compliance Check
    ↓
Eligible Pool
    ↓
Conformance Check
    ↓
Qualified Selection Set
    ↓
Ability, Conflict, and Gate Checks
    ↓
Selected Execution Kube
    ↓
Platform Attestation
```

## Compliance

Compliance evaluates whether the candidate satisfies applicable baseline obligations such as:

- law;
- regulation;
- policy;
- safety requirements;
- privacy requirements;
- licensing;
- identity verification;
- jurisdiction;
- mandatory controls;
- lifecycle and reporting obligations;
- prohibited-use restrictions.

```text
Compliance
=
Baseline Eligibility
```

A compliant candidate may enter the eligible pool, but compliance does not prove that it is the right candidate for a particular task.

## Conformance

Conformance evaluates whether an eligible candidate matches the declared specification, operating model, interface, protocol, quality threshold, context, and outcome requirements.

It may assess:

- exact contract version;
- schema and interface compatibility;
- domain fit;
- operating-mode fit;
- capability maturity;
- quality criteria;
- reliability;
- performance;
- recovery readiness;
- interoperability;
- evidence completeness;
- surface requirements;
- destination acceptance criteria.

```text
Conformance
=
Contextual Selection Fitness
```

## Eligibility and Selection

```text
Compliance Pass
    = Eligible to be considered

Conformance Pass
    = Qualified for this specific selection
```

A candidate may be compliant but nonconformant for the requested role.

A candidate may technically conform to a specification but remain ineligible because it fails legal, policy, licensing, jurisdictional, privacy, or safety requirements.

## Decision Matrix

| Compliance | Conformance | Result |
|---|---|---|
| Pass | Pass | Eligible and qualified for further gate checks |
| Pass | Fail | Eligible generally, not selectable for this contract |
| Fail | Pass | Technically matching but legally or institutionally ineligible |
| Fail | Fail | Reject, redesign, or quarantine |

## Selection Criteria

Conformance criteria must be declared before selection and should include:

- required capability;
- accepted specification;
- domain;
- context;
- consequence class;
- maturity threshold;
- quality threshold;
- performance boundary;
- cost and resource limit;
- recovery expectation;
- required evidence;
- expiry;
- tie-break or ranking method.

Selection criteria must not be invented after results are known.

## Canonical Check Envelope

```yaml
apiVersion: fabric.opendata.world/v1alpha1
kind: ComplianceConformanceCheck
metadata:
  id: urn:fabric:check:01J...
  version: 1
spec:
  candidate: urn:fabric:kube:agent-42
  context:
    domain: urn:fabric:domain:operations
    jurisdiction: IN
    environment: production
    consequenceClass: C2-bounded-operational
  compliance:
    identity: passed
    legalBasis: valid
    jurisdiction: valid
    privacy: passed
    safetyPolicy: passed
    license: valid
    lifecycle: active
  conformance:
    contract: urn:fabric:contract:operations:v3
    interface: passed
    capability: passed
    maturity: operationalized
    quality: passed
    recovery: verified
    evidence: complete
  selection:
    criteriaVersion: urn:fabric:criteria:operations-selection:v2
    rank: 1
status:
  eligibility: eligible
  qualification: conformant
  nextGate: urn:fabric:gate:ability-and-conflict-review
```

## Relationship to Ability

Conformance and Ability are related but distinct.

```text
Conformance
    = matches the declared requirements

Ability
    = can actually deliver under current conditions
```

A candidate may conform on paper but lack the current resources, availability, tools, capacity, or recovery readiness to perform.

## Relationship to Eligibility

The complete eligibility decision may include:

```text
Eligibility
=
Compliance
+ Identity
+ Jurisdiction
+ Valid Contract
+ Responsibility Coverage
+ No Disqualifying Conflict
```

Conformance then narrows the eligible pool to the candidates that fit the task.

## Relationship to Selection

Selection occurs only after:

1. compliance establishes eligibility;
2. conformance establishes fit;
3. ability establishes current delivery capacity;
4. maker-checker and conflict checks establish independence;
5. the platform gate validates and signs the decision.

```text
Selected Kube
=
Compliant
+ Conformant
+ Able
+ Conflict-Cleared
+ Attested
```

## Continuous Checks

Compliance and conformance must be reevaluated when:

- law or regulation changes;
- context changes;
- jurisdiction changes;
- contract version changes;
- implementation changes;
- dependencies change;
- maturity changes;
- evidence expires;
- a new surface is entered;
- the selected candidate is replaced.

## Platform Responsibilities

The platform must:

- keep compliance requirements separate from conformance criteria;
- version both sets of rules;
- publish selection criteria before evaluation;
- prevent noncompliant candidates from entering the eligible pool;
- prevent nonconformant candidates from being selected;
- preserve the exact evidence and rule versions used;
- expose reasons for rejection, qualification, and selection;
- support review, appeal, correction, expiry, and revalidation.

## Platform Invariants

1. Compliance defines baseline eligibility.
2. Conformance defines contextual selection fitness.
3. Compliance and conformance remain separate checks.
4. A compliant candidate is not automatically selectable.
5. A conformant candidate is not automatically legally or institutionally eligible.
6. Selection criteria are explicit, versioned, and declared before evaluation.
7. Ability and conflict checks remain mandatory after conformance.
8. The platform signs the final bounded selection.
9. Material changes trigger revalidation.
10. Every decision preserves evidence, rule versions, reasons, and appeal paths.

## Foundation Formula

```text
Eligible Pool
=
Compliance-Passing Candidates
```

```text
Qualified Selection Set
=
Eligible Pool
∩
Conformance-Passing Candidates
```

```text
Final Selection
=
Compliance
+ Conformance
+ Ability
+ Independence
+ Platform Attestation
```

## Final Statement

> Compliance decides who or what is eligible to participate. Conformance decides which eligible candidate satisfies the exact selection criteria for the current contract and context. Ability, independence, and platform attestation then determine who may perform the bounded action. Compliance creates the pool; conformance selects from it.
