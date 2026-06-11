# Ownership Transfer and Native Agent Reconstruction Protocol

Status: Normative Protocol

## Principle

> The Fabric is the digital twin and totem of the Kube. It preserves the Kube’s identity, history, rights, obligations, state, provenance, and accountable relationships across time and environments.

When a Kube moves between Fabrics, ownership and accountability do not travel implicitly. They must be transferred through an explicit, time-bounded protocol. The destination then reconstructs a native agent under local identity, context, law, contracts, tools, maturity, and governance.

## Core Rule

> Preserve continuity in the Fabric. Transfer ownership explicitly. Reconstruct natively. Bind authority and accountability to time.

## Canonical Model

```text
Source Kube
    ↓
Source Fabric Twin
    ↓
Partitioned Transit Envelope
    ↓
Ownership Transfer Offer
    ↓
Destination Gate Validation
    ↓
Destination Acceptance
    ↓
Native Kube Reconstruction
    ↓
Time-Bounded Ownership and Accountability
    ↓
Continuous Reconciliation
```

## Fabric as Digital Twin and Totem

The Fabric is the durable representation of the Kube across its lifecycle.

It preserves:

- canonical identity;
- current and historical owners;
- accountable principals;
- active and prior contexts;
- contracts;
- instructions;
- state transitions;
- capabilities;
- rights;
- obligations;
- provenance;
- attestations;
- trust evidence;
- transfer history;
- expiry and retirement.

```text
Fabric Twin
=
Identity
+ State
+ Ownership
+ Accountability
+ Provenance
+ Lifecycle
```

The Fabric does not replace the Kube. It is the governed mirror and continuity anchor through which the Kube remains explainable and accountable.

## Ownership Is Not Authority by Itself

Ownership may establish stewardship, custody, or commercial rights, but it does not automatically create unlimited operating authority.

```text
Ownership
    ≠
Universal Authority
```

Operational authority still requires:

- valid identity;
- active context;
- applicable contract;
- jurisdiction;
- platform eligibility;
- ability;
- signed delegation;
- maturity;
- surface conformance.

## Ownership Transfer

Every transfer must declare:

- source owner;
- destination owner;
- Kube identity;
- transfer purpose;
- legal or contractual basis;
- rights transferred;
- rights retained;
- rights excluded;
- obligations transferred;
- obligations retained;
- assets and data included;
- provenance obligations;
- effective time;
- expiry or review time;
- revocation conditions;
- recovery and exit path.

## Transfer States

```text
proposed
→ published
→ registered
→ offered
→ under-review
→ conditionally-accepted
→ accepted
→ activated
→ renewed
→ restricted
→ revoked
→ expired
→ returned
→ retired
```

No ownership transfer becomes effective before explicit destination acceptance and gate validation.

## Native Agent Reconstruction

The destination never imports foreign authority as-is.

It reconstructs a native Kube using:

- the portable identity and provenance envelope;
- destination-local identity or alias;
- destination context;
- destination contract;
- destination jurisdiction;
- destination operating model;
- destination tools and drivers;
- local policy;
- local maturity ceiling;
- local attestation;
- local lifecycle;
- local recovery and exit.

```text
Native Destination Agent
=
Portable Continuity
+ Local Identity
+ Local Contract
+ Local Eligibility
+ Local Ability
+ Local Attestation
```

## Always Native Agents

Every active agent must be native to the Fabric in which it operates.

That means:

- authority is issued locally;
- permissions are local and explicit;
- tools are destination-approved;
- memory is locally reconstructed from accepted evidence;
- compliance is evaluated locally;
- accountability is assigned locally;
- provenance links back to the source remain intact.

A foreign agent may be represented, but it cannot execute until reconstructed and attested as a local native agent.

## Time-Bounded Ownership

Every ownership or stewardship assignment must declare:

- `validFrom`;
- `validUntil` or review date;
- renewal conditions;
- suspension triggers;
- revocation authority;
- return or reassignment procedure;
- archival and provenance rules.

```text
Valid Ownership
=
Named Owner
+ Defined Scope
+ Effective Time
+ Expiry
+ Review
+ Revocation
```

Permanent undefined ownership is not permitted.

## Time-Bounded Accountability

Every operating period must identify:

- accountable human or legal organization;
- operating agent;
- approver;
- validator;
- recovery owner;
- consequence class;
- start and end time;
- accepted obligations;
- terminal-state responsibility.

Accountability cannot be orphaned during transit, renewal, suspension, or retirement.

## Responsibility Transfer

Responsibility transfers only after:

1. destination identity is verified;
2. destination authority is valid;
3. destination accepts the Kube;
4. local eligibility and ability pass;
5. native reconstruction completes;
6. ownership and accountability records are signed;
7. source and destination receipts are preserved.

Until completion, the source remains responsible for the transfer process.

## Separation of Duties

High-consequence transfers should separate:

```text
Transfer Initiator
Transfer Approver
Rights Validator
Technical Reconstructor
Security Validator
Destination Owner
Auditor
Recovery Owner
```

No actor may silently initiate, approve, execute, and certify the same material transfer.

## Canonical Transfer Envelope

```yaml
apiVersion: fabric.opendata.world/v1alpha1
kind: OwnershipTransfer
metadata:
  id: urn:fabric:ownership-transfer:01J...
  version: 1
spec:
  kube: urn:fabric:kube:agent-42
  source:
    fabric: urn:fabric:fabric:source
    owner: urn:fabric:organization:source-owner
    accountablePrincipal: urn:fabric:identity:source-principal
  destination:
    fabric: urn:fabric:fabric:destination
    proposedOwner: urn:fabric:organization:destination-owner
    proposedPrincipal: urn:fabric:identity:destination-principal
  basis:
    contract: urn:fabric:contract:transfer:v2
    jurisdiction: IN
    purpose: bounded-commercial-operation
  rights:
    transferred:
      - operate-approved-capability
      - use-registered-artifact
    retained:
      - authorship
      - provenance
      - reserved-commercial-rights
    excluded:
      - source-admin-authority
      - private-source-memory
  obligations:
    transferred:
      - maintain-conformance
      - preserve-attribution
      - provide-recovery
  validity:
    validFrom: 2026-06-11T12:00:00Z
    validUntil: 2026-09-11T12:00:00Z
    renewalRequired: true
    revocationTriggers:
      - contract-breach
      - nonconformance
      - trust-degradation
      - ownership-dispute
  reconstruction:
    nativeRequired: true
    destinationOperatingModel: urn:fabric:model:local-agent:v3
status:
  sourceApproval: passed
  destinationAcceptance: pending
  ownershipState: offered
  responsibility: source
```

## Canonical Reconstruction Receipt

```yaml
apiVersion: fabric.opendata.world/v1alpha1
kind: NativeAgentReceipt
metadata:
  id: urn:fabric:native-agent-receipt:01J...
  version: 1
spec:
  transfer: urn:fabric:ownership-transfer:01J...
  sourceKube: urn:fabric:kube:agent-42
  nativeKube: urn:fabric:kube:destination-agent-42:v1
  destinationOwner: urn:fabric:organization:destination-owner
  accountablePrincipal: urn:fabric:identity:destination-principal
  localContext: urn:fabric:context:destination-production:v4
  localContract: urn:fabric:contract:local-agent:v3
  localAttestation: urn:fabric:attestation:native-agent:v1
  validity:
    validFrom: 2026-06-11T12:05:00Z
    validUntil: 2026-09-11T12:00:00Z
status:
  eligibility: passed
  ability: passed
  ownership: active
  responsibility: destination
  provenance: complete
```

## Commercial and Intellectual-Property Rights

Transfer of operational ownership does not automatically transfer:

- authorship;
- copyright;
- trademark;
- certification rights;
- proprietary intelligence;
- commercial licensing rights;
- source data ownership;
- rights retained by contributors.

Each category must be declared independently.

```text
Operational Ownership
    ≠
Intellectual-Property Ownership
    ≠
Commercial Rights
```

## Revocation, Expiry, and Return

When ownership expires or is revoked:

```text
Stop New Operations
→ Preserve Current State
→ Revoke Local Authority
→ Reconcile Obligations
→ Settle Usage and Contributors
→ Return / Reassign / Retire
→ Preserve Provenance
```

The native agent must not continue under stale ownership.

## Disputes

Ownership or accountability disputes must trigger:

- restriction or pause;
- evidence preservation;
- conflict review;
- independent validation;
- appeal or arbitration under the contract;
- protection of affected users and data;
- no destructive action until lawful resolution where feasible.

## Platform Responsibilities

The platform must:

- maintain the Fabric twin;
- preserve complete ownership history;
- validate transfer authority;
- require destination acceptance;
- enforce native reconstruction;
- issue time-bounded local attestation;
- block authority smuggling;
- preserve rights and obligations separately;
- monitor expiry and revocation;
- reconcile ownership with observed operation;
- expose review, dispute, recovery, and exit paths.

## Platform Invariants

1. The Fabric is the Kube’s digital twin and continuity totem.
2. Every active Kube has a clearly identified owner and accountable principal.
3. Ownership, authority, accountability, and intellectual-property rights are separate declarations.
4. Every ownership assignment is time-bounded, reviewable, expirable, and revocable.
5. No destination imports foreign execution authority directly.
6. Every destination reconstructs and attests a native local agent.
7. Responsibility transfers only after destination acceptance and completed reconstruction.
8. Source and destination Kubes remain linked through immutable provenance.
9. Expired or disputed ownership cannot silently remain operational.
10. Every transfer includes recovery, settlement, return, retirement, and exit paths.

## Foundation Formula

```text
Fabric Twin
=
Kube Identity
+ Ownership History
+ Accountability
+ State
+ Provenance
+ Lifecycle
```

```text
Legitimate Ownership Transfer
=
Valid Source Authority
+ Explicit Rights and Obligations
+ Destination Acceptance
+ Native Reconstruction
+ Time-Bounded Accountability
+ Durable Evidence
```

```text
Native Agent
=
Portable Continuity
+ Destination Fabric
+ Local Ownership
+ Local Accountability
+ Local Eligibility
+ Local Attestation
```

## Final Statement

> The Fabric is the digital twin and totem of the Kube. It preserves continuity while ownership, authority, and accountability change through time. Every transfer must be explicit, rights-aware, accepted, evidenced, and time-bounded. The destination never inherits uncontrolled foreign authority; it reconstructs a native agent under local governance, with ownership and accountability clearly assigned for a defined period.
