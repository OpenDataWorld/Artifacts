# AnyDB Foundation Principle: Documents in the Cloud; Data Intelligence on a Metal-Native Substrate

Status: Normative Foundation Principle

## Principle

> Documents are stored and distributed through the cloud. Governed data and intelligence rest on a durable, metal-native substrate.

AnyDB separates presentation and distribution from the deepest layer of truth.

Documents, reports, media, and published artifacts may live in cloud object storage and content-delivery systems. Canonical data, event history, identity, policy, features, models, memory maps, and reconciliation evidence must remain anchored to a durable substrate that the platform can operate, verify, migrate, and recover independently.

## Core Rule

> The cloud is a distribution surface. The substrate is the continuity layer.

## Layer Model

```text
Documents and Published Artifacts
              ↓
        Cloud Distribution
              ↓
    APIs, Search, Agents, Channels
              ↓
       AnyDB Data Kernel
              ↓
 Data + Events + Memory + Intelligence
              ↓
    Metal-Native Solid Substrate
```

## Documents Are Artifacts

A document is a governed ArtifactKube or AnythingKube representation.

Examples include:

- articles
- specifications
- reports
- contracts
- datasets
- images
- videos
- model cards
- policy documents
- evidence bundles

The cloud may provide:

- object storage
- replication
- content delivery
- browser access
- collaboration
- publication

The document must still retain:

- canonical identity
- version
- digest
- owner
- license
- provenance
- policy
- source relationships
- retention rules

## Data Is the Durable Truth Layer

The canonical data layer preserves:

- identities
- entities
- events
- temporal versions
- relationships
- policies
- contracts
- decisions
- evidence
- reconciliation states

Documents are views or artifacts connected to this truth layer.

A document must not become the only place where authoritative facts exist unless its contract explicitly declares it as the source artifact.

## Intelligence Is Stored as Governed Data

Intelligence is not only executable code.

It includes:

- feature definitions
- feature values
- model artifacts
- training lineage
- evaluations
- prompts
- memory maps
- inference records
- agent decisions
- tool outcomes
- trust evidence

These objects belong to the AnyDB data and artifact model.

ML libraries and model runtimes execute intelligence, but the platform stores its identity, lineage, policy, and outcomes.

## Metal-Native Substrate

A metal-native substrate means that the platform can run directly on controlled compute and storage without depending on a proprietary cloud service for its essential continuity.

It may include:

- bare-metal servers
- Linux
- local block storage
- replicated disks
- object storage
- Kubernetes
- edge clusters
- local registries
- durable event logs
- database providers

Metal-native does not prohibit cloud deployment.

It ensures that cloud operation is a deployment choice rather than an ownership dependency.

## Solid Substrate Properties

The substrate should be:

- durable
- ACID-capable at authoritative boundaries
- recoverable
- observable
- portable
- replaceable by layer
- offline-capable where required
- cryptographically verifiable
- policy-controlled
- reconciliation-aware

## Cloud and Substrate Relationship

```text
Metal-Native Substrate
         |
         +-- Private Cloud
         +-- Public Cloud
         +-- Regional Cloud
         +-- Edge Cloud
         +-- Air-Gapped Deployment
```

The cloud is built on the substrate.

The substrate is not defined by one cloud vendor.

## Cloud-Native Without Cloud Dependence

AnyDB is cloud-native because it supports:

- declarative deployment
- containerized workloads
- horizontal scale
- service discovery
- automated reconciliation
- observability
- resilient distribution

It is not cloud-dependent because:

- canonical data can be exported
- control can run on owned infrastructure
- contracts are vendor-neutral
- providers are replaceable
- edge sites can continue locally
- backups can restore outside the originating cloud

## Document Flow

```text
Canonical Data and Evidence
          ↓
Document Generation
          ↓
Artifact Digest and Signature
          ↓
Cloud Object Storage
          ↓
CDN / Website / API / Channel
          ↓
Usage and Feedback Events
          ↓
AnyDB Reconciliation
```

The published document remains linked to the exact canonical versions that produced it.

## Intelligence Flow

```text
Canonical Data
      ↓
Feature and Context Maps
      ↓
Model Artifact
      ↓
Runtime on Cloud or Edge
      ↓
Inference or Agent Decision
      ↓
Evidence and Outcome Events
      ↓
AnyDB Memory and Reconciliation
```

## Memory on the Substrate

Memory is a map, not an opaque provider-owned conversation log.

The substrate stores:

- canonical memory nodes
- typed relationships
- temporal positions
- domain context
- provenance
- policy
- derived summaries and embeddings

Cloud services may accelerate access, but they must not become the sole holder of agent memory or decision history.

## Edge Continuity

At the edge, the solid substrate provides:

- local data
- local event history
- local policy
- local model artifacts
- local memory maps
- local execution
- durable evidence

The edge synchronizes with wider cloud surfaces when connectivity permits.

## Lossless Movement

Movement between substrate and cloud surfaces must preserve:

- canonical IDs
- versions
- time dimensions
- location dimensions
- provenance
- policy references
- artifact digests
- declared transformation loss

Cloud publication must not flatten governed data into an untraceable file.

## Data Placement

Recommended placement classes:

```text
metal-authoritative
edge-authoritative
region-authoritative
cloud-replicated
cloud-distributed
projection-only
ephemeral
```

The placement class must be explicit and policy-governed.

## Security Boundary

The substrate should protect:

- encryption keys
- canonical identity records
- policy state
- authoritative event logs
- model provenance
- customer-owned data
- trust and reconciliation evidence

Cloud surfaces should receive only the data and artifacts required by their contracts.

## Recovery

A solid substrate must support recovery of:

- canonical data
- event history
- contracts
- policies
- model and artifact registries
- memory maps
- projection checkpoints
- trust evidence

Recovery must not require the original cloud vendor.

## Platform Invariants

1. Documents are governed artifacts, not disconnected files.
2. Canonical facts remain anchored in AnyDB.
3. Intelligence artifacts preserve data and model lineage.
4. The platform can operate on controlled metal-native infrastructure.
5. Cloud services remain replaceable distribution and scale surfaces.
6. Edge sites retain local continuity.
7. Data movement preserves identity, time, location, policy, and provenance.
8. Memory and decision history do not exist only inside a model vendor.
9. Backups restore outside the originating provider.
10. The substrate remains the durable continuity layer beneath all surfaces.

## Foundation Formula

```text
Cloud = Distribution and Elasticity
```

```text
Metal-Native Substrate = Durability and Control
```

```text
AnyDB = Governed Truth and Intelligence
```

```text
Document = Published Artifact of Governed Truth
```

## Final Statement

> Documents travel through the cloud. Data, memory, intelligence, identity, contracts, and evidence remain anchored to a solid metal-native substrate. The cloud extends the platform; it does not own its truth.
