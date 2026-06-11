# Open Publishing Before the Gate

Status: Normative Foundation Principle

## Principle

> Every proposal, instruction set, operating model, protocol, agent profile, policy, capability, or implementation intended for consequential use must be published to a trusted registry before it can request admission at a gate.

Publishing creates a visible, versioned, attributable artifact. Registration gives the artifact a canonical identity and establishes the provenance required for validation.

## Core Rule

> Publish first. Register second. Validate third. Cross the gate only after eligibility is proven.

## Canonical Flow

```text
Idea or Proposal
    ↓
Open Publication
    ↓
Trusted Registry Registration
    ↓
Canonical Identity and Version
    ↓
Community or Independent Review
    ↓
Trusted Gate Request
    ↓
Eligibility + Ability Check
    ↓
Platform Attestation
    ↓
One Bounded Forward Step
```

## Open Publication

Open publication should expose enough information to enable understanding, review, challenge, comparison, and reuse.

It should include:

- title and canonical identity;
- author, owner, and accountable organization;
- purpose;
- domain and context;
- definitions;
- assumptions;
- intended capability;
- operating boundaries;
- evidence and source references;
- maturity state;
- known limitations;
- licensing and ownership;
- version;
- change history;
- review and feedback path;
- expiry or retirement conditions.

Open publication does not require disclosure of proprietary intelligence, private data, trade secrets, or security-sensitive implementation details.

## Registry Registration

The trusted registry assigns or verifies:

- canonical identifier;
- artifact type;
- publisher identity;
- version;
- integrity digest;
- publication timestamp;
- domain;
- license;
- provenance links;
- lifecycle state;
- supersedes and derived-from relations;
- review state;
- dispute state;
- expiry.

## Canonical Registration Envelope

```yaml
apiVersion: fabric.opendata.world/v1alpha1
kind: RegistryEntry
metadata:
  id: urn:fabric:registry:artifact:01J...
  version: 1
spec:
  artifact:
    type: standard-operating-model
    canonicalId: urn:fabric:model:operations:v1
    title: Standard Operations Model
  publisher:
    identity: urn:fabric:organization:publisher-01
    accountableOwner: urn:fabric:identity:owner-01
  context:
    domain: urn:fabric:domain:platform-operations
    intendedMode: simulation
  publication:
    uri: urn:fabric:artifact:operations-model:v1
    publishedAt: 2026-06-11T12:00:00Z
    integrity: sha256:...
    license: urn:fabric:license:open-standard
  provenance:
    derivedFrom:
      - urn:fabric:document:source:v1
  lifecycle:
    state: registered
    reviewEvery: P90D
    expiresAt: 2026-12-11T12:00:00Z
status:
  registration: verified
  gateEligibility: review-required
```

## Registry Before Gate

A gate request must reference a registered artifact.

```text
Unregistered Artifact
    = Not Gate-Eligible

Registered Artifact
    = Eligible for Validation, Not Automatically Eligible for Execution
```

Registration proves existence, identity, integrity, and provenance. It does not prove feasibility, conformance, maturity, safety, or production eligibility.

## Review Before Admission

The registry should support:

- public feedback;
- domain-expert review;
- independent validation;
- dispute and correction;
- alternative implementations;
- known limitations;
- safety concerns;
- compatibility reports;
- maturity evidence.

Feedback creates new forward records. It never silently changes the published artifact.

## Gate Validation

After registration, the Trusted Gate validates:

1. artifact identity and integrity;
2. publisher identity and responsibility;
3. active context;
4. contract and jurisdiction;
5. logical coherence;
6. bounded rationality;
7. feasibility;
8. compliance and conformance;
9. eligibility and ability;
10. maker–checker independence;
11. conflict-of-interest status;
12. maturity;
13. provenance;
14. quality assurance;
15. recovery and exit.

## Versioning

Every material change creates a new version.

```text
Published Artifact v1
    ↓ amendment or improvement
Published Artifact v2
```

The registry preserves:

- historical versions;
- change rationale;
- author and approver;
- compatibility status;
- migration guidance;
- supersession state.

## Open Publishing and Proprietary Intelligence

The public artifact may publish:

- principles;
- contracts;
- schemas;
- safety requirements;
- interfaces;
- test criteria;
- conformance evidence;
- known limitations.

It may protect:

- proprietary models;
- confidential implementation details;
- private customer data;
- protected intelligence;
- exploit-sensitive security information.

```text
Open Contract
+ Protected Implementation
=
Reviewable Innovation Without Forced Disclosure
```

## Agent Rule

An agent may draft or submit an artifact for publication.

It may not:

- treat an unpublished proposal as an approved model;
- self-register without an accountable publisher;
- alter a registered artifact silently;
- use registration as production authority;
- bypass gate validation;
- suppress disputes or known limitations.

## Platform Responsibilities

The platform must:

- require registry identity before gate requests;
- verify publisher identity;
- preserve immutable versions;
- expose provenance and lifecycle;
- support disputes, corrections, and supersession;
- distinguish registration from eligibility;
- block expired, revoked, or disputed artifacts where policy requires;
- link gate decisions to exact registered versions.

## Platform Invariants

1. Publication precedes registration.
2. Registration precedes gate admission.
3. Every registered artifact has canonical identity, version, provenance, and accountable ownership.
4. Registration does not grant execution authority.
5. Every gate decision references an exact registered version.
6. Material changes create new forward versions.
7. Open publication does not require disclosure of proprietary intelligence.
8. Disputes, limitations, and corrections remain visible.
9. Expired or revoked artifacts cannot silently remain eligible.
10. Only validated and attested registered artifacts may cross into consequential operation.

## Foundation Formula

```text
Gate-Ready Artifact
=
Open Publication
+ Trusted Registration
+ Canonical Identity
+ Provenance
+ Reviewability
```

```text
Production-Eligible Artifact
=
Gate-Ready Artifact
+ Eligibility
+ Ability
+ Conformance
+ Maturity
+ Platform Attestation
```

## Final Statement

> Publish openly before the gate. Register the artifact with canonical identity, version, ownership, provenance, integrity, and lifecycle. Let the registry make the proposal visible and reviewable. Then let the Trusted Gate determine whether the exact registered version is eligible, able, conformant, mature, and safe enough for one bounded real-world step.
