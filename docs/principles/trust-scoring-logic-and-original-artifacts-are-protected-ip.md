# AnyDB Foundation Principle: Trust-Scoring Logic and Original Artifacts Are Protected Intellectual Property

Status: Normative Foundation Principle

## Principle

> The platform reserves the right to define, maintain, revise, and protect its trust-scoring logic as proprietary intellectual property.

The platform also treats its original artifacts—including frameworks, theories, schemas, scoring models, evaluation methods, specifications, software, documentation, data models, diagrams, and research—as protected assets.

Transparency of eligibility does not require disclosure of every proprietary method, weighting, heuristic, implementation detail, or internal control.

## Core Rule

> Publish the rules required for fair participation. Protect the original logic and artifacts that create differentiated platform value.

## Trust-Scoring Authority

The platform may define trust scores for:

- domains
- partners
- providers
- agents
- models
- artifacts
- edges
- surfaces
- contracts
- recovery capability
- federation relationships

The scoring model may consider evidence such as:

- identity verification
- constitutional conformance
- legal and policy compliance
- CNCF-grade maturity
- security posture
- recovery tests
- portability
- unresolved gaps
- delivery history
- reconciliation outcomes
- evidence freshness
- incident history

## What Must Be Transparent

To preserve fairness and accountability, the platform should publish:

- eligibility categories
- mandatory gates
- disqualifying conditions
- evidence requirements
- review cadence
- trust-state definitions
- decision and appeal process
- material reasons for restriction or rejection

## What May Remain Protected

The platform may protect:

- exact weights
- formulas
- feature engineering
- thresholds not required by law or contract
- anti-fraud signals
- anomaly models
- proprietary datasets
- internal heuristics
- model parameters
- evaluation pipelines
- implementation code
- trade-secret controls

## Trust Score Is Not a Universal Fact

A trust score is a platform evaluation produced for a declared purpose, time, domain, and contract.

It must include or resolve to:

- evaluator identity
- evaluation time
- evidence set
- applicable trust model version
- decision scope
- expiry or review condition

The numeric score or state must not be represented as universal truth outside that context.

## Protected Trust Evaluation Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: TrustEvaluation
metadata:
  id: urn:anydb:trust-evaluation:domain:logistics:01J...
  version: 1
spec:
  subject: urn:anydb:domain:logistics
  model: urn:anydb:trust-model:platform:v3
  purpose: production-eligibility
  evidence:
    - urn:anydb:evidence:identity-verification
    - urn:anydb:evidence:recovery-test
    - urn:anydb:evidence:security-assessment
  disclosure:
    outcome: public
    reasons: controlled
    formula: protected
    weights: protected
status:
  trustState: verified
  eligibility: eligible-with-conditions
  evaluatedAt: 2026-06-11T12:00:00Z
  reviewBy: 2026-09-11T12:00:00Z
```

## Original Artifacts as Assets

Original artifacts may include:

- Theory of Anything
- AnythingKube and AnyAgent definitions
- AnyDB and Fabric architecture
- Constitution
- trust models
- contracts and protocols
- diagrams
- domain frameworks
- software implementations
- evaluation methods
- recovery logic
- research and publications

These artifacts remain assets of their lawful owner unless explicitly licensed, assigned, or transferred.

## Ownership Metadata

Every protected artifact should declare:

- author
- owner
- creation time
- version
- license
- copyright notice
- source repository
- provenance
- digest
- permitted uses
- prohibited uses
- attribution requirements

## Open Framework, Protected Value

The platform may publish enough of the framework to enable:

- interoperability
- conformance
- eligibility assessment
- independent implementation
- recovery
- portability
- public review

At the same time, it may protect differentiated intellectual property that is not necessary for those purposes.

```text
Open Contracts
+ Testable Interfaces
+ Published Eligibility Rules
+ Protected Scoring Logic
+ Protected Original Artifacts
= Open, Fair, and Commercially Defensible Platform
```

## Licensing

Open publication does not automatically place an artifact in the public domain.

Every artifact must have an explicit license.

The platform may use different licenses for:

- specifications
- source code
- documentation
- research
- data
- models
- trademarks
- certification marks

## Confidentiality and Access

Protected logic and artifacts should be accessed only by authorized identities under explicit contracts.

Controls may include:

- least privilege
- separation of duties
- confidential repositories
- signed access agreements
- audit logs
- watermarking
- artifact signing
- restricted model access
- revocation

## Partner and Provider Use

Partners and providers may use protected assets only within their granted license and delivery contract.

They must not:

- claim authorship or ownership
- reproduce beyond licensed scope
- disclose confidential methods
- reverse engineer protected scoring logic where prohibited by applicable law and contract
- train competing systems on protected artifacts without permission
- remove attribution, notices, signatures, or provenance

## Fairness Safeguard

Protection of the formula must not permit arbitrary or discriminatory decisions.

The platform must retain evidence sufficient to show that:

- published mandatory rules were followed
- similarly situated participants were evaluated consistently
- conflicts were disclosed
- decisions were reviewable
- legal and constitutional obligations were met

## Security Safeguard

Some trust-scoring details may remain confidential because disclosure could enable gaming, fraud, evasion, or attacks.

Security-sensitive secrecy must be proportionate and must not conceal unlawful, unfair, or unreviewable conduct.

## Amendments

The platform may revise its trust logic as risks, laws, evidence, domains, and operational conditions change.

A revision should preserve:

- model version
- effective time
- affected scope
- migration behavior
- reevaluation requirements
- decision history

## Platform Invariants

1. The platform owns or lawfully controls its trust-scoring logic.
2. Exact proprietary formulas and weights need not be publicly disclosed.
3. Mandatory eligibility rules and evidence expectations remain published.
4. Trust decisions remain contextual, time-bound, and reviewable.
5. Original artifacts carry explicit ownership, provenance, and license metadata.
6. Open publication does not waive intellectual-property rights.
7. Partners and providers use protected assets only under license.
8. Confidentiality cannot be used to hide arbitrary or unlawful decisions.
9. Trust-model changes are versioned and historically explainable.
10. Unauthorized use, disclosure, or appropriation may result in restriction, suspension, termination, or legal action under applicable law.

## Foundation Formula

```text
Platform Trust Evaluation = Published Gates + Verified Evidence + Protected Scoring Logic
```

```text
Original Artifact = Authorship + Ownership + Provenance + License + Protected Value
```

## Final Statement

> We reserve the right to define and protect our trust-scoring logic. We publish enough to make eligibility fair, transparent, and reviewable, while preserving the proprietary methods and original artifacts that constitute our intellectual property and platform assets.
