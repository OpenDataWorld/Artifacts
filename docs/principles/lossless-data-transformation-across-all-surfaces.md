# AnyDB Foundation Principle: Lossless Data Transformation Across All Surfaces

Status: Normative Foundation Principle

## Principle

> No AnyDB surface may destroy source meaning during transformation.

Every transformation must either be reversible or preserve the original source alongside the transformed representation.

AnyDB treats transformation as a governed, versioned, evidence-producing operation. Parsing, normalization, enrichment, indexing, feature generation, model preparation, projection, export, and edge synchronization must preserve lineage and allow the platform to explain exactly how each representation was produced.

## Core Rule

> Transform freely. Lose nothing.

A transformed value may simplify, normalize, aggregate, tokenize, embed, classify, or project data, but it must remain traceable to the source values, source version, transformation logic, and resulting version.

## Lossless Does Not Mean Identical

A transformed representation may differ from its source.

Examples:

- CSV becomes canonical entities
- documents become search indexes
- records become graph relationships
- text becomes embeddings
- event streams become projections
- raw observations become features

The transformation is lossless when the platform preserves enough information to:

- retrieve or verify the original input
- explain the mapping
- reproduce the result where practical
- identify information intentionally omitted
- detect transformation drift
- rebuild downstream projections

## Surface Flow

```text
Original Source
      |
      v
Immutable Source Artifact
      |
      v
Validated Transformation
      |
      v
Canonical AnyDB Entity / Event
      |
      +-- Search Projection
      +-- Graph Projection
      +-- Feature Projection
      +-- Vector Projection
      +-- Edge Replica
      +-- Export Representation
```

Every arrow must carry provenance.

## Canonical Transformation Record

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: Transformation
metadata:
  id: urn:anydb:transformation:crm-customer:v2
  version: 2.0.0
  owner: urn:anydb:organization:opendataworld
spec:
  sourceSchema: urn:anydb:schema:crm-customer:v4
  targetSchema: urn:anydb:schema:customer:v1
  mode: normalize
  reversible: partial
  sourceRetention: required
  mappings:
    - source: customer_no
      target: metadata.aliases[crm]
    - source: full_name
      target: spec.data.displayName
  omissions:
    - source: internal_debug_flag
      reason: non-domain operational field
      retainedInSourceArtifact: true
status:
  codeDigest: sha256:...
  testEvidence: urn:anydb:evidence:transform-test:crm-customer-v2
```

## Required Transformation Metadata

Every transformation must record:

- transformation identity
- transformation version
- source identity
- source version
- target identity
- target version
- source schema
- target schema
- code or rules digest
- actor or runtime identity
- started and completed time
- mapping rules
- omissions
- defaults
- coercions
- errors and quarantines
- evidence

## Original Preservation

At least one of these guarantees is required:

### Reversible Transformation

The original can be reconstructed exactly from the transformed output and transformation definition.

### Source Artifact Retention

The original bytes or records are retained as immutable artifacts with digest and access policy.

### Authoritative Source Reference

The original remains durably available in an authoritative external source, and AnyDB preserves a stable reference, version, digest, and retrieval contract.

If none of these guarantees is available, the transformation must be classified as lossy and cannot silently replace authoritative source data.

## Transformation Classes

```text
lossless-reversible
lossless-source-retained
lossless-source-referenced
lossy-declared
invalid
```

`lossy-declared` transformations may be used for convenience views, but they must not become authoritative without an explicit promotion contract.

## Source Surface

The Source surface must preserve:

- source-system identity
- native source identifier
- source version or checkpoint
- original encoding
- observed time
- source digest where possible
- retrieval method

## Ingest Surface

The Ingest surface must:

- retain original values before coercion
- distinguish missing, null, empty, invalid, and defaulted values
- preserve unmapped fields
- record parsing errors
- quarantine untrusted or malformed input
- version every mapping

Normalization must not silently erase ambiguity.

## Store Surface

The Store surface must preserve:

- canonical entity history
- original source references
- authoritative versions
- schema versions
- transformation lineage
- tombstones and corrections

A normalized entity does not invalidate the source artifact that produced it.

## Event Surface

Events must preserve the facts as recorded at commit time.

Corrections are new events, not rewrites.

If an external event is transformed, the original external envelope and identifier must remain discoverable.

## Search Surface

Search indexes are projections.

They may tokenize, stem, rank, summarize, or denormalize, but every indexed document must preserve:

- canonical entity ID
- authoritative source version
- projection version
- indexed time
- source fields or references
- policy context
- freshness checkpoint

Search results must never become an untraceable copy of truth.

## Vector Surface

Embeddings are lossy mathematical projections.

Therefore, every vector must retain:

- source entity or artifact ID
- source version
- source segment identity
- embedding model identity
- model version
- preprocessing transform
- vector dimension
- generated time
- policy and provenance

The original text, image, audio, or source reference must remain available according to policy.

A vector alone is never authoritative truth.

## Feature Surface

Features must preserve point-in-time lineage.

Each feature value must identify:

- subject identity
- source entities and events
- source versions
- transformation definition
- computation time
- valid time
- feature version
- missing-value behavior

Aggregations must retain enough evidence to explain the result.

## Intelligence Surface

Training and inference transformations must preserve:

- input data versions
- feature versions
- preprocessing code
- model identity
- runtime identity
- output
- confidence where meaningful
- evaluation and guardrail results

Generated summaries or classifications must remain linked to their source context.

## Policy Surface

Policy transformations, such as compiling human-readable policy into executable bundles, must preserve:

- source policy document
- source version
- compiled artifact digest
- compiler identity and version
- test evidence
- effective-time boundaries

## Edge Surface

Edge synchronization must preserve:

- canonical identity
- authoritative version
- local version
- sync checkpoint
- original event order within declared streams
- conflict evidence
- local modifications
- reconciliation outcome

The edge must not overwrite central truth blindly after reconnecting.

## Export Surface

Exports must preserve:

- canonical IDs
- schemas
- versions
- temporal history
- provenance
- relationships
- policy references
- artifact digests

Provider migration is incomplete when data values move but identity, history, or lineage is lost.

## Round-Trip Testing

Every transform that claims reversibility must pass round-trip tests:

```text
Source
  -> Transform
  -> Reverse Transform
  -> Compare With Source
```

The comparison must define exact or semantic equivalence.

## Semantic Equivalence

Some transformations cannot preserve byte-for-byte equality because of encoding, ordering, or normalized formatting.

The contract must declare the equivalence model:

```text
byte-exact
field-exact
semantic-equivalent
aggregate-equivalent
source-retained-only
```

## Checksums and Digests

AnyDB should record digests for:

- original artifacts
- transformed outputs
- transformation code
- schemas
- model artifacts
- policy bundles

Digests provide integrity evidence but do not replace provenance or semantic validation.

## Schema Evolution

When schemas change, migrations must preserve:

- prior schema version
- prior entity version
- migration transform
- defaults and coercions
- removed-field retention strategy
- rollback or source-replay method

A field removed from the current schema must not disappear from history without a declared retention or privacy reason.

## Privacy and Redaction

Lossless preservation does not mean retaining personal or restricted data forever.

Privacy obligations may require:

- redaction
- pseudonymization
- tokenization
- retention expiry
- cryptographic erasure

These operations must be explicit, policy-authorized, and recorded as transformations or lifecycle events.

The platform should preserve evidence that a lawful transformation occurred without retaining erased content.

## Failure Handling

A transformation must not silently emit partial data as complete.

Possible states:

```text
pending
completed
completed-with-declared-loss
quarantined
partially-mapped
failed
rejected
```

Partial output must include missing-field and error metadata.

## Reconciliation

AnyDB reconciles transformations by comparing:

```text
Source Version
      |
      v
Transformation Definition
      |
      v
Produced Output
      |
      v
Expected Invariants
      |
      v
Verified or Diverged
```

Reconciliation detects:

- missing records
- duplicated records
- field truncation
- schema drift
- stale projections
- checksum mismatch
- unmapped fields
- changed preprocessing
- inconsistent edge replicas

## Surface Contract Requirement

Every AnyDB surface must publish:

- input contract
- output contract
- transformation class
- loss behavior
- source-retention strategy
- provenance fields
- rebuild method
- validation tests
- reconciliation method

## Platform Invariants

1. Original meaning is never silently destroyed.
2. Every transformation has canonical identity and version.
3. Every output points to its source identity and version.
4. Unmapped and omitted data is declared.
5. Lossy projections never silently become authoritative.
6. Vectors and features retain source lineage.
7. Schema migrations preserve historical explainability.
8. Edge synchronization preserves local and canonical versions.
9. Provider migration preserves identity, history, and provenance.
10. Every transformation can be tested and reconciled.

## Foundation Formula

```text
Source + Transformation + Lineage + Evidence = Explainable Output
```

And:

```text
Lossless Transformation = Reversible Output OR Preserved Original
```

## Final Statement

> AnyDB allows data to change form without losing truth. Every surface may transform the representation, but no surface may sever identity, history, provenance, or the path back to the source.
