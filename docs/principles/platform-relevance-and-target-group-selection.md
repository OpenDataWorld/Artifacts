# Platform Relevance and Target-Group Selection

Status: Normative Publishing and Curation Principle

## Principle

> The platform reserves the right to determine whether published content is relevant to the declared target group and to reject, restrict, redirect, or request revision when that content does not fit the audience, purpose, contract, quality threshold, or safety boundary.

This is a curation right, not an unrestricted censorship right. Relevance criteria must be explicit, versioned, consistently applied, reviewable, and connected to a clear appeal or resubmission path.

## Core Rule

> Open submission does not guarantee distribution. Publication eligibility depends on relevance, quality, rights, safety, and audience fit.

## Canonical Model

```text
Content Submission
    ↓
Registry Identity and Rights Check
    ↓
Target-Group Definition
    ↓
Relevance Assessment
    ↓
Quality and Safety Review
    ↓
Publish / Publish with Conditions / Redirect / Revise / Reject
```

## Target Group

Every publishing surface should declare its intended target group using criteria such as:

- domain;
- profession or role;
- maturity level;
- language;
- geography or jurisdiction;
- age or access class where lawful;
- technical level;
- organizational type;
- use case;
- consequence class;
- public, community, research, commercial, or statutory purpose.

The target-group definition must be published before relevance decisions are made.

## Relevance

Relevance asks whether the content materially serves the declared audience and purpose.

The platform may assess:

- alignment with the publishing surface;
- usefulness to the target group;
- domain fit;
- timeliness;
- completeness;
- clarity;
- evidence quality;
- duplication;
- originality or added value;
- legal and policy compatibility;
- safety;
- accessibility;
- licensing and commercial authorization.

```text
Relevant Content
=
Audience Fit
+ Purpose Fit
+ Context Fit
+ Quality
+ Rights Clearance
```

## Relevance Is Not Truth

A relevance decision does not determine whether an idea is universally true or valuable.

```text
Not Relevant Here
    ≠
Worthless Everywhere
```

Content rejected from one surface may be suitable for another audience, registry category, domain, or publication channel.

## Platform Rights

The platform may:

- accept content;
- accept with conditions;
- request revision;
- assign a different category;
- redirect to another surface;
- reduce distribution;
- restrict access by audience class;
- reject publication;
- suspend or remove content that later becomes nonconformant;
- require renewed review after material changes.

These rights must remain inside the published platform contract and applicable law.

## Platform Duties

The platform must:

- publish relevance and quality criteria;
- identify the target group;
- preserve the submitted version;
- provide a reason code or explanation for material rejection;
- distinguish relevance from safety, legality, quality, and commercial-rights decisions;
- avoid undisclosed viewpoint discrimination;
- apply criteria consistently;
- preserve reviewer identity or accountable review authority;
- disclose material conflicts of interest;
- support correction, resubmission, appeal, or redirection;
- retain provenance of the decision.

## Relevance Decision States

```text
relevant
relevant-with-conditions
revision-required
redirect-to-another-surface
limited-distribution
not-relevant-for-target-group
rejected-for-quality
rejected-for-rights
rejected-for-safety
expired
removed-after-review
```

Each state should identify the exact decision basis.

## Canonical Relevance Envelope

```yaml
apiVersion: fabric.opendata.world/v1alpha1
kind: ContentRelevanceDecision
metadata:
  id: urn:fabric:relevance:01J...
  version: 1
spec:
  artifact: urn:fabric:artifact:content:v3
  publisher: urn:fabric:identity:publisher-01
  surface: urn:fabric:surface:enterprise-research
  targetGroup:
    domain: enterprise-agentic-systems
    roles:
      - platform-architect
      - governance-lead
    maturity: advanced
    language: en
  criteria:
    version: urn:fabric:criteria:relevance:v2
    audienceFit: passed
    purposeFit: passed
    domainFit: passed
    evidenceQuality: conditional
    duplication: passed
    rights: passed
    safety: passed
  reviewer:
    identity: urn:fabric:identity:editor-01
    conflictCheck: passed
status:
  decision: relevant-with-conditions
  conditions:
    - add-source-evidence
  appealAvailable: true
  expiresAt: 2026-09-11T12:00:00Z
```

## Separation of Concerns

The platform must keep these checks distinct:

```text
Relevance
    = fit for this target group

Quality
    = meets editorial or technical standard

Safety
    = does not create unacceptable risk

Compliance
    = eligible under law and policy

Rights
    = permitted to publish and distribute
```

Failure in one dimension must not be misrepresented as failure in another.

## Maker–Checker and Conflict Review

For high-impact publication decisions:

- the content creator is the maker;
- the reviewer or editorial gate is the checker;
- reviewers must disclose material conflicts;
- appeals should be reviewed independently where feasible;
- automated relevance scoring should not be the sole authority for consequential rejection.

## Right to Reason

The publisher should be able to understand:

- which target group was used;
- which criteria were applied;
- which version of the criteria applied;
- which requirement failed;
- whether revision or redirection is possible;
- how to appeal.

## Right to Deny

The platform may deny publication on its governed surface when the content falls outside the declared contract.

The publisher retains the right to:

- decline requested changes;
- withdraw the submission;
- publish on another lawful surface;
- challenge the decision;
- retain ownership and provenance;
- exit the platform under the contract.

## Open Publishing and Commercial Rights

Open submission or registry publication does not guarantee placement on every platform surface.

The platform may curate a commercial or community channel for a particular audience while preserving:

- publisher ownership;
- attribution;
- reserved commercial rights;
- independent publication rights under the license;
- registry provenance.

## No Hidden Suppression

The platform must not silently make content undiscoverable after accepting it without recording the relevant moderation, ranking, expiry, or distribution decision.

```text
No Operations in the Dark
    applies to curation and distribution decisions.
```

## Continuous Relevance

Relevance may change when:

- the target group changes;
- the content becomes stale;
- new evidence emerges;
- the domain evolves;
- legal or policy conditions change;
- a different surface is used;
- the content is materially revised.

A new decision must reference the new context and criteria version.

## Platform Invariants

1. The platform may curate for its declared target group.
2. Open submission does not guarantee publication or distribution.
3. Target-group and relevance criteria are published before use.
4. Relevance, quality, safety, compliance, and rights remain separate checks.
5. Material rejection includes a reason, evidence, and review path.
6. Criteria are applied consistently and without hidden conflicts.
7. A platform decision does not erase publisher ownership or provenance.
8. Rejected content may be redirected to a more suitable lawful surface.
9. Automated relevance scoring does not independently decide high-impact cases without accountable oversight.
10. Curation and ranking decisions remain visible to authorized parties and contract-bound.

## Foundation Formula

```text
Publication Fit
=
Relevance
+ Quality
+ Safety
+ Compliance
+ Rights Clearance
```

```text
Legitimate Rejection
=
Published Criteria
+ Contextual Assessment
+ Accountable Reviewer
+ Reason
+ Appeal or Exit
```

## Final Statement

> The platform may decide what is relevant for the target group it serves and may reject content that does not fit that declared audience or purpose. That authority must remain contract-bound, transparent, evidence-based, conflict-checked, and reviewable. The platform curates its surface; it does not erase the publisher, the artifact, or the possibility that the content belongs elsewhere.
