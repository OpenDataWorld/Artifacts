# AnyDB Foundation Principle: Community Universes Must Not Become Opaque or Ungoverned

Status: Normative Foundation Principle

## Principle

> Every community may maintain its own universe of meaning, memory, language, beliefs, practices, institutions, and knowledge—but no community universe may participate in the platform through undocumented native sources, opaque governance, hidden authority, or unreviewable belief systems.

A community universe becomes unstable when its definitions, sources, decision rules, and authority cannot be inspected, attributed, challenged, or reconciled.

## Core Rule

> Local sovereignty is valid. Opaque authority is not. Community knowledge must be documented, attributable, reviewable, and governed before it can enter the shared knowledge economy.

## The Risk

A community universe may drift when it relies on:

- undocumented oral or native sources without provenance
- hidden decision-makers
- unversioned beliefs
- unreviewable authority
- unverifiable claims
- undefined membership rules
- opaque moderation
- undocumented exceptions
- silent changes in meaning
- inaccessible dispute processes
- concealed conflicts of interest

This produces:

```text
Opacity
  ↓
Information Asymmetry
  ↓
Unverifiable Authority
  ↓
Drift
  ↓
Instability
  ↓
Loss of Trust
```

## Native Knowledge Is Valid but Must Be Governed

Native, local, oral, cultural, traditional, and community knowledge may be valuable and authoritative within its context.

The platform must not discard it merely because it is not expressed in a conventional academic or technical format.

However, production participation requires a governed record of:

- source community
- custodian or steward
- meaning
- context
- method of transmission
- access restrictions
- consent expectations
- authority
- version or lineage
- dispute process
- known limitations

## Knowledge Documentation States

Recommended states:

```text
undocumented
partially-documented
community-attested
provenance-recorded
reviewed
verified
disputed
restricted
superseded
archived
```

Undocumented knowledge may remain within a private or exploratory community context, but should not silently govern high-consequence shared operations.

## Community Governance Declaration

Every participating community should publish or register:

- community identity
- accountable stewards
- constitution or governance framework
- membership rules
- decision process
- amendment process
- dispute and appeal process
- conflict-of-interest rules
- knowledge contribution rules
- cultural access restrictions
- privacy and consent rules
- federation and exit rules

## Canonical Governance Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: CommunityGovernanceDeclaration
metadata:
  id: urn:anydb:community-governance:example:v1
  version: 1.0.0
  owner: urn:anydb:community:example
spec:
  stewards:
    - urn:anydb:identity:steward-01
  constitution: urn:anydb:artifact:community-constitution:v1
  decisionProcess: urn:anydb:process:community-decision:v1
  disputeProcess: urn:anydb:process:community-dispute:v1
  knowledgePolicy: urn:anydb:policy:community-knowledge:v1
  restrictedKnowledgePolicy: urn:anydb:policy:cultural-restrictions:v1
  amendmentProcess: urn:anydb:process:community-amendment:v1
  federationPolicy: urn:anydb:policy:community-federation:v1
status:
  verification: verified
  trust: provisional
  eligibility: conditional
```

## Source Registration

Every source entering the common collective knowledge registry should declare:

- source type
- origin
- steward
- collection or transmission method
- date or temporal range
- language
- domain
- cultural context
- evidence
- access rights
- permitted use
- transformation history

## Oral and Traditional Sources

Oral and traditional sources may be registered through:

- steward attestations
- community review
- recorded testimony where consent permits
- lineage documentation
- multiple-source corroboration
- cultural authority declarations
- restricted-access metadata

Documentation must respect cultural and legal restrictions.

Transparency does not require public disclosure of sacred, private, or protected knowledge.

## Belief Systems

A belief system may exist as a community context, but it must not be presented as universal empirical fact without evidence appropriate to that claim.

The registry should distinguish:

```text
belief
tradition
interpretation
norm
historical account
observation
hypothesis
validated finding
legal rule
```

## Governance Must Be Explainable

A community governance decision should preserve:

- decision identity
- decision-maker or process
- authority
- active rules
- evidence considered
- conflicts disclosed
- outcome
- effective time
- review or appeal path

## No Opaque Automation

AnyAgent or algorithm used in community governance must declare:

- accountable owner
- purpose
- model and policy versions
- allowed inputs
- prohibited actions
- decision authority
- human review requirements
- evidence
- stop conditions

Automated ranking or moderation cannot become hidden community law.

## Common Collective Knowledge Registry Gate

Before knowledge is federated into the common registry, the admission gate should verify:

1. community identity
2. governance declaration
3. source provenance
4. knowledge classification
5. access and consent rules
6. license or permitted use
7. domain context
8. review status
9. dispute state
10. trust threshold

## Drift Detection

Community drift may include:

- definition drift
- belief drift
- governance drift
- authority drift
- membership drift
- policy drift
- cultural-context drift
- source-provenance loss

Drift must be visible and versioned.

## Stabilization

```text
Drift Detected
      ↓
Affected Knowledge or Rule Identified
      ↓
Steward and Community Review
      ↓
Source and Authority Revalidated
      ↓
New Version Published
      ↓
Mappings and Dependents Updated
      ↓
Trust Reevaluated
```

The original past record remains immutable.

## Fairness and Cultural Respect

Governance requirements must not privilege only dominant, written, technical, or academic traditions.

The platform should support multiple legitimate methods of documentation while requiring equivalent levels of:

- attribution
- accountability
- reviewability
- consent
- clarity
- dispute handling

## Eligibility

A community may be:

```text
private-unfederated
exploratory
verification-required
eligible-for-sandbox
eligible-with-conditions
eligible-for-federation
restricted
suspended
```

A community with opaque governance or undocumented high-consequence sources is not eligible for production federation.

## Platform Invariants

1. Community universes may remain culturally and semantically distinct.
2. Native and oral knowledge are valid source classes.
3. Every shared source has provenance, stewardship, context, and access rules.
4. Governance authority is declared and reviewable.
5. Belief, observation, law, and validated evidence remain distinct.
6. Sacred or restricted knowledge may remain protected.
7. Transparency does not require indiscriminate disclosure.
8. Opaque automated governance is prohibited.
9. Drift is measured, versioned, and reviewed.
10. No undocumented or unreviewable high-consequence knowledge governs the shared platform.

## Foundation Formula

```text
Stable Community Universe
=
Local Sovereignty
+ Documented Sources
+ Explainable Governance
+ Cultural Protection
+ Reviewable Authority
+ Drift Control
```

```text
Federation Eligibility
=
Verified Community
+ Governed Knowledge
+ Provenance
+ Consent
+ Trust
```

## Final Statement

> Every community may have its own universe, but no universe may become an opaque source of authority. Native knowledge must be respected, documented through culturally appropriate methods, attributed to its stewards, governed transparently, and federated only when its sources, rules, boundaries, and dispute processes can be understood and trusted.
