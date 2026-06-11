# AnyDB Platform Repository Surfaces

AnyDB should be organized as a platform composed of independently governed surfaces rather than as a collection of unrelated repositories.

A **surface** is a stable product, protocol, runtime, integration, or knowledge boundary through which the AnyDB platform is implemented, operated, extended, or understood.

The repositories remain independently deployable and reviewable, but they are rebased conceptually onto one platform architecture.

## Platform Definition

> AnyDB is a governed data fabric for any model, any workload, and any runtime—built around canonical identity, temporal truth, policy, provenance, and reconciliation.

## Canonical Surface Map

```text
AnyDB Platform
│
├── 00 Foundation Surface
│   ├── foundation
│   └── Fabric-Foundation
│
├── 10 Control Surface
│   └── Platform
│
├── 20 Source Surface
│   └── Data-Sources
│
├── 30 Ingest Surface
│   └── structured-data-parser
│
├── 40 Store Surface
│   └── Data-store
│
├── 50 Search Surface
│   └── Semantic-Search
│
├── 60 Intelligence Surface
│   └── feature-store-as-a-service
│
├── 70 Assurance Surface
│   └── Test-Dara-Management
│
└── 90 Knowledge Surface
    └── Artifacts
```

## Surface Responsibilities

### 00 — Foundation Surface

Repositories:

- `OpenDataWorld/foundation`
- `OpenDataWorld/Fabric-Foundation`

Purpose:

- define AnyDB principles and terminology
- define canonical identity, time, event, policy, evidence, and decision primitives
- define provider and projection contracts
- define Fabric integration
- define governance and reconciliation semantics
- maintain architectural decision records

Boundary:

The Foundation surface declares what AnyDB means. It should not become the primary application runtime.

Recommended distinction:

- `foundation`: AnyDB product constitution, specifications, and common contracts
- `Fabric-Foundation`: governance, work-loop, trust, and reconciliation integration with The Fabric

### 10 — Control Surface

Repository:

- `OpenDataWorld/Platform`

Purpose:

- operate the AnyDB control plane
- register providers and projections
- manage tenants, workspaces, schemas, policies, and identities
- expose administration and developer APIs
- coordinate lifecycle, health, reconciliation, and deployment

Core responsibilities:

- provider registry
- schema registry
- policy binding
- identity mapping
- workload routing
- projection lifecycle
- reconciliation control
- observability

Boundary:

The Control surface governs the system. It should not contain every provider implementation.

### 20 — Source Surface

Repository:

- `OpenDataWorld/Data-Sources`

Purpose:

- describe and connect external data origins
- maintain source metadata and provenance contracts
- support databases, APIs, streams, files, object stores, and applications
- declare source capabilities and synchronization modes

Core responsibilities:

- connector definitions
- source discovery
- source identity
- credential references
- change-data-capture declarations
- polling and streaming contracts
- provenance metadata

Boundary:

A source describes where data originates. It does not define the canonical AnyDB entity by itself.

### 30 — Ingest Surface

Repository:

- `OpenDataWorld/structured-data-parser`

Purpose:

- parse, validate, normalize, and enrich incoming data
- transform external representations into AnyDB envelopes
- retain source fidelity and transformation provenance

Core responsibilities:

- structured-data parsing
- schema validation
- type inference
- canonical field mapping
- entity extraction
- deduplication hints
- lineage generation
- quarantine and error handling

Boundary:

The Ingest surface proposes normalized entities and events. Canonical identity assignment remains governed by the platform.

### 40 — Store Surface

Repository:

- `OpenDataWorld/Data-store`

Purpose:

- implement the authoritative AnyDB storage contract
- expose record, document, graph, event, temporal, vector, and artifact capabilities
- coordinate provider adapters and local transaction boundaries

Core responsibilities:

- canonical entity storage
- temporal versions
- relationship storage
- event persistence
- transaction handling
- provider abstraction
- projection checkpoints
- retention and archival

Boundary:

The Store surface owns authoritative persistence contracts. Search indexes and analytical features should remain rebuildable projections unless explicitly promoted to authoritative state.

### 50 — Search Surface

Repository:

- `OpenDataWorld/Semantic-Search`

Purpose:

- provide lexical, semantic, graph-aware, and metadata-aware discovery
- preserve links from every result to canonical identity, source version, provenance, and policy

Core responsibilities:

- full-text indexing
- vector indexing
- hybrid retrieval
- ranking
- filtered search
- result provenance
- policy-aware retrieval
- projection freshness

Boundary:

Search is a governed projection of AnyDB truth, not an independent source of truth.

### 60 — Intelligence Surface

Repository:

- `OpenDataWorld/feature-store-as-a-service`

Purpose:

- define, compute, version, serve, and monitor reusable data features
- support analytical systems, machine learning, decision intelligence, and agents

Core responsibilities:

- feature definitions
- online and offline views
- point-in-time correctness
- lineage
- freshness
- training-serving consistency
- feature authorization
- drift and quality checks

Boundary:

A feature is a derived, versioned projection. It must remain traceable to canonical AnyDB entities, events, and source versions.

### 70 — Assurance Surface

Repository:

- `OpenDataWorld/Test-Dara-Management`

Proposed corrected product name:

- **Test Data Management**

Purpose:

- validate AnyDB contracts, providers, projections, migrations, and policies
- generate or manage safe test datasets
- verify consistency, privacy, temporal correctness, and reconciliation behavior

Core responsibilities:

- contract testing
- schema compatibility
- synthetic data
- masked datasets
- migration verification
- provider conformance
- projection replay tests
- policy and access tests

Boundary:

The Assurance surface must not leak production-sensitive data into test environments.

### 90 — Knowledge Surface

Repository:

- `OpenDataWorld/Artifacts`

Purpose:

- publish architecture, specifications, protocols, research, decisions, and implementation guidance
- serve as the durable knowledge and publication layer for AnyDB

Core responsibilities:

- architecture articles
- specifications
- protocol definitions
- ADRs
- tutorials
- provider guides
- research papers
- release narratives

Boundary:

Artifacts documents and explains the platform. Executable specifications may live here only when ownership and validation are explicit.

## Platform Flow

```text
External Systems
      |
      v
Data-Sources
      |
      v
Structured Data Parser
      |
      v
Canonical Identity + Policy Resolution
      |
      v
Data Store
      |
      +-------------------+-------------------+
      |                   |                   |
      v                   v                   v
Semantic Search     Feature Store       Other Projections
      |                   |                   |
      +-------------------+-------------------+
                          |
                          v
                    Platform APIs
                          |
                          v
              Applications, Agents, Analytics
```

Cross-cutting surfaces:

```text
Foundation       -> contracts and principles
Fabric Foundation -> governance and reconciliation
Assurance        -> conformance and safety
Artifacts        -> knowledge and publication
```

## Shared AnyDB Contract

Every surface should recognize the canonical AnyDB envelope:

```yaml
id: canonical entity identifier
type: declared entity type
schema: schema identifier and version
version: entity version
owner: accountable identity
created_at: first recording time
updated_at: latest authoritative update
valid_from: business validity start
valid_to: business validity end
provenance: source and transformation lineage
policy: applicable policy references
relationships: typed canonical links
events: related event stream references
trust: verification and confidence metadata
```

Not every repository stores the full envelope, but every surface must preserve its identifiers and semantics.

## Shared Repository Standard

Each AnyDB surface repository should adopt:

```text
README.md
LICENSE
SECURITY.md
CONTRIBUTING.md
CODEOWNERS
CHANGELOG.md
docs/
spec/
examples/
tests/
.github/workflows/
```

Each README should declare:

1. Surface name
2. Platform role
3. Inputs
4. Outputs
5. Source-of-truth status
6. Consistency model
7. Identity behavior
8. Policy boundary
9. Reconciliation behavior
10. Deployment model

## Repository Naming Direction

The current repository names can remain during transition. Their canonical platform identities should be declared as:

| Current Repository | Canonical Surface Identity |
|---|---|
| `foundation` | AnyDB Foundation |
| `Fabric-Foundation` | AnyDB Fabric Foundation |
| `Platform` | AnyDB Platform |
| `Data-Sources` | AnyDB Sources |
| `structured-data-parser` | AnyDB Ingest |
| `Data-store` | AnyDB Store |
| `Semantic-Search` | AnyDB Search |
| `feature-store-as-a-service` | AnyDB Features |
| `Test-Dara-Management` | AnyDB Test Data |
| `Artifacts` | AnyDB Artifacts |

Possible later repository names:

```text
anydb-foundation
anydb-fabric
anydb-platform
anydb-sources
anydb-ingest
anydb-store
anydb-search
anydb-features
anydb-test-data
anydb-artifacts
```

Renaming should be a controlled migration, not the first step.

## Rebase Strategy

### Phase 1 — Conceptual Rebase

- publish the surface map
- assign every repository one platform role
- declare inputs, outputs, and source-of-truth status
- stop adding unrelated responsibilities

### Phase 2 — Contract Rebase

- introduce shared entity envelopes
- introduce schema and event versioning
- align identity and policy references
- define provider and projection contracts

### Phase 3 — Delivery Rebase

- standardize CI and security checks
- add conformance tests
- publish OCI artifacts where appropriate
- add deployment manifests and operator contracts

### Phase 4 — Naming Rebase

- rename repositories only after contracts stabilize
- preserve GitHub redirects
- update package names, images, documentation, and release workflows

### Phase 5 — Platform Release

- version the surfaces together through an AnyDB compatibility matrix
- publish release manifests from the Platform and Artifacts surfaces

## Source-of-Truth Classification

| Surface | Classification |
|---|---|
| Foundation | Normative specification |
| Fabric Foundation | Normative governance specification |
| Platform | Operational control plane |
| Sources | External-origin registry |
| Ingest | Transformation pipeline |
| Store | Authoritative data plane |
| Search | Rebuildable projection |
| Features | Rebuildable/versioned intelligence projection |
| Assurance | Validation and evidence |
| Artifacts | Published knowledge and documentation |

## Platform Rule

> No repository is the whole AnyDB platform. Each repository is a governed surface with an explicit contract to the canonical data fabric.

## Final Topology

```text
                    AnyDB Platform
                           |
          +----------------+----------------+
          |                                 |
     Control Plane                       Data Plane
       Platform          Sources -> Ingest -> Store
          |                                 |
          +----------------+----------------+
                           |
                 Projection Plane
                  Search + Features
                           |
          +----------------+----------------+
          |                |                |
      Foundation       Assurance        Artifacts
          |
   Fabric Governance
```

This topology gives OpenDataWorld a coherent platform structure without forcing every capability into one repository or one runtime.
