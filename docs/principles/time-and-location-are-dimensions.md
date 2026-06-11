# AnyDB Foundation Principle: Time and Location Are Dimensions

Status: Normative Foundation Principle

## Principle

> Every fact exists in time and location.

AnyDB treats time and location as first-class dimensions of truth rather than optional metadata.

A data object is incomplete when the platform cannot explain when it was valid, when it was observed, where it originated, where it was processed, where it is governed, and where its effects became real.

## Core Rule

> Identity tells us what. Time tells us when. Location tells us where.

Together they define the operational context of truth.

## Dimensional Model

```text
Entity
  + Identity
  + Time
  + Location
  + State
  + Evidence
  = Contextual Truth
```

## Time Dimensions

AnyDB distinguishes several forms of time:

- valid time — when a fact is true in the domain
- transaction time — when AnyDB recorded the fact
- occurrence time — when an event happened
- observation time — when a source or edge observed it
- ingestion time — when the platform received it
- processing time — when a transformation ran
- projection time — when a derived view was produced
- decision time — when a policy or agent decision was made
- execution time — when work was performed
- reconciliation time — when intended and observed state were compared

These times must not be collapsed into one generic timestamp.

## Location Dimensions

AnyDB distinguishes several forms of location:

- physical location — geographic place of the subject or event
- logical location — tenant, namespace, workspace, or domain
- infrastructure location — node, cluster, region, or cloud
- data-residency location — jurisdiction where data is stored
- execution location — where a command or model ran
- observation location — where an outcome was measured
- authority location — organization or domain that owns the truth
- edge location — local site where work becomes real

These locations may differ for the same fact.

## Canonical Dimensional Envelope

```yaml
metadata:
  id: urn:anydb:event:01J...
  subject: urn:anydb:asset:42
  time:
    occurredAt: 2026-06-11T09:29:58Z
    observedAt: 2026-06-11T09:29:59Z
    recordedAt: 2026-06-11T09:30:00Z
    validFrom: 2026-06-11T09:29:58Z
    validTo: null
  location:
    physical:
      latitude: 19.0728
      longitude: 72.8826
    edge: urn:anydb:edge:mumbai-site-01
    cluster: urn:anydb:cluster:k0s-edge-01
    region: ap-south
    jurisdiction: IN
    authority: urn:anydb:organization:opendataworld
```

## Time as a Query Dimension

AnyDB should support questions such as:

- What was true at a specific moment?
- What did the platform know at that moment?
- Which policy was active then?
- Which identity relationship was valid?
- Which model version produced the result?
- How long did convergence take?

## Location as a Query Dimension

AnyDB should support questions such as:

- Where did this data originate?
- Where is the authoritative copy held?
- Which edge executed the command?
- Which jurisdiction governs the data?
- Where was the result observed?
- Which provider or cluster produced this projection?

## Policy Implications

Policy may depend on both dimensions.

Examples:

- allow access only during a declared time window
- keep data inside a jurisdiction
- allow edge execution but prohibit central replication
- require stronger approval outside a trusted site
- apply retention from the valid or recorded time
- route models based on location and sovereignty

## Event Semantics

Every event must preserve occurrence time and source location when known.

An event without temporal and spatial context may be retained, but it must explicitly declare those dimensions as unknown rather than silently omit them.

## Edge Semantics

The edge is the location where intended state becomes observable reality.

```text
Intent Location
      |
      v
Execution Location
      |
      v
Observation Location
      |
      v
Reconciliation Across Locations
```

The execution location and observation location may be the same edge, or different trusted observers.

## Data Placement

Placement policies should use location as a governed dimension.

Recommended classes:

```text
edge-only
site-bound
region-bound
jurisdiction-bound
global-replicated
central-authoritative
ephemeral-local
```

## Mobility

Entities may move.

AnyDB must preserve location history rather than overwrite the latest location without context.

Examples:

- devices
- vehicles
- people
- inventory
- workloads
- agents
- data replicas

Movement should be represented through temporal location relationships or events.

## Time and Location in Reconciliation

Reconciliation must compare state within explicit dimensional boundaries.

A stale edge copy may be correct for its last synchronization time but not current globally.

A regional policy may be correct locally but invalid in another jurisdiction.

Therefore, reconciliation should evaluate:

- expected time boundary
- observed time
- expected location
- observed location
- allowed propagation delay
- authority domain

## Clock and Coordinate Trust

Time and location claims require evidence.

Possible evidence includes:

- trusted clock source
- signed device attestation
- GPS or network location
- cluster identity
- region metadata
- source-system timestamp
- human assertion

The platform must record confidence and provenance rather than treat all claims as equally reliable.

## Privacy

Location can be highly sensitive.

AnyDB should support:

- precision reduction
- regional rather than exact location
- purpose-limited access
- selective disclosure
- retention limits
- pseudonymization

The need for dimensional truth does not justify unrestricted location exposure.

## Platform Invariants

1. Every authoritative fact declares its relevant time dimensions.
2. Every distributed fact declares its relevant location dimensions.
3. Unknown time or location is explicit.
4. Valid time and recording time remain distinct.
5. Execution and observation locations remain traceable.
6. Data placement is governed by location policy.
7. Mobility preserves historical location.
8. Reconciliation uses time and location boundaries.
9. Time and location claims retain provenance and confidence.
10. Privacy policy controls dimensional precision and exposure.

## Foundation Formula

```text
Truth = Identity + State + Time + Location + Evidence
```

## Final Statement

> Time and location are the coordinates of truth. AnyDB preserves both so every entity, event, decision, action, and outcome can be understood in the context in which it actually existed.
