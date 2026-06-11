# AnyDB Foundation Principle: Surface-Native Operations Core Runtime

Status: Normative Foundation Principle

## Principle

> The next platform generation is surface-native: a headless, lightweight, fluid substrate driven by an operations-core runtime, protected by hardened scaffolding, and able to treat every hardware capability as a pluggable driver.

The platform must deliver governed work directly onto the relevant real surface without forcing the surface to conform to one cloud, one kernel, one database, one runtime, or one hardware vendor.

## Core Rule

> Keep the substrate fluid. Keep the scaffolding hardened. Keep delivery headless. Keep hardware replaceable. Let the operations core hold the runtime contract.

## Canonical Architecture

```text
Human Purpose and Enterprise Contract
                ↓
Agent Platform
                ↓
Operations Core Runtime
                ↓
Lightweight Fluid Substrate
                ↓
Pluggable Hardware and Provider Drivers
                ↓
AnySurface
```

## Surface-Native

Surface-native means the platform starts from the surface where value, interaction, and consequence become real.

A surface may be:

- web
- mobile
- API
- document
- device
- factory
- vehicle
- robot
- edge site
- cloud service
- wallet
- marketplace
- human workflow
- agent interface

Each surface declares:

- identity
- purpose
- context
- ingress
- egress
- trust boundary
- capability requirements
- provenance
- safety controls
- lifecycle

## Operations Core Runtime

The operations core runtime executes the platform contract across substrates.

It provides:

- identity resolution
- state transitions
- scheduling
- agent admission
- model and tool invocation
- policy evaluation
- transaction handling
- provenance capture
- observability
- reconciliation
- recovery
- graceful exit

The operations core is stable. Implementations beneath it remain replaceable.

## Lightweight Fluid Substrate

The substrate should minimize friction through:

- small operational footprint
- low idle overhead
- fast startup
- composable components
- provider neutrality
- portable state
- direct peer movement where appropriate
- minimal control-plane dependency
- hybrid cloud and edge placement
- offline or degraded-mode operation

Fluidity means implementation can move without losing identity, contract, state, evidence, or continuity.

## Hardened Scaffolding

The scaffolding protects the real surface through:

- default deny
- identity-first admission
- least privilege
- signed artifacts
- verified dependencies
- policy before execution
- workload isolation
- network segmentation
- secret protection
- immutable evidence
- rate and resource limits
- anomaly detection
- stop controls
- tested recovery

```text
Fluid Motion Inside
+
Hardened Boundary Outside
=
Safe Adaptability
```

## Headless Delivery

The platform is headless by default.

No user interface, channel, provider portal, or device owns the underlying operational model.

Delivery occurs through stable contracts such as:

- APIs
- events
- streams
- commands
- queries
- manifests
- schemas
- agent handoffs
- context packages

A surface is attached as a projection, not embedded as the core.

## Pluggable Hardware Drivers

Every hardware capability should be exposed through a bounded driver contract.

Examples include:

- CPU
- GPU
- NPU
- storage
- networking
- sensors
- cameras
- audio
- robotics
- accelerators
- trusted execution environments
- industrial controllers

Each driver must declare:

- hardware identity
- provider
- capabilities
- version
- permissions
- resource limits
- telemetry
- failure modes
- security posture
- lifecycle
- replacement path

## Canonical Driver Contract

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: HardwareDriver
metadata:
  id: urn:anydb:driver:gpu:provider-model:v1
  version: 1.0.0
spec:
  hardware: urn:anydb:hardware:gpu:01
  capability:
    - model-inference
    - parallel-compute
  interface: urn:anydb:contract:hardware-driver:v1
  permissions:
    - allocate-memory
    - execute-approved-workload
  limits:
    maxMemory: 24Gi
    maxPowerWatts: 300
  observability:
    metricsRequired: true
    provenanceRequired: true
  failureModes:
    - unavailable
    - degraded
    - integrity-failure
  lifecycle:
    reviewEvery: P6M
    expiryCondition: nonconformance-or-better-mature-replacement
status:
  eligibility: production
  trust: verified
```

## Driver Neutrality

```text
Hardware Capability
    ≠
Hardware Vendor
```

The platform binds to capability contracts rather than permanent vendor identities.

A driver may be replaced when another implementation provides better:

- efficiency
- conformance
- stability
- security
- portability
- supportability
- recoverability
- value

## Surface Promotion

A new surface enters production through:

```text
Surface Definition
→ Virtual Model
→ Driver Mapping
→ Feasibility
→ Conformance
→ Capability Maturity
→ Security and Quality Assurance
→ Human Approval Where Required
→ One Bounded Production Step
```

## Provider and Component Lifecycle

Every provider, component, driver, and surface mapping has:

- valid-from
- review cadence
- expiry
- renewal criteria
- deprecation trigger
- migration path
- retirement path
- provenance retention

No stale implementation remains permanently attached to the substrate.

## Platform Invariants

1. Delivery is surface-native.
2. The Agent Platform holds the shared contract.
3. The operations core runtime executes and reconciles that contract.
4. The substrate remains lightweight, fluid, and provider-neutral.
5. Every exposed surface is protected by hardened scaffolding.
6. The platform is headless by default.
7. Hardware is accessed through pluggable capability drivers.
8. No hardware or infrastructure vendor becomes sovereign.
9. Drivers, providers, and components have expiry and graceful retirement.
10. Identity, context, contract, provenance, and evidence survive every substrate change.

## Foundation Formula

```text
Surface-Native Platform
=
Operations Core Runtime
+ Lightweight Fluid Substrate
+ Hardened Scaffolding
+ Headless Delivery
+ Pluggable Drivers
```

```text
AnySurface Eligibility
=
Identity
+ Context
+ Contract
+ Mature Capability
+ Provenance
+ Safety
+ Recovery
```

## Final Statement

> The platform is surface-native. An operations-core runtime holds execution together, a lightweight fluid substrate removes unnecessary friction, hardened scaffolding protects every real boundary, headless delivery keeps the core independent of channels, and pluggable drivers allow any suitable hardware to participate without owning the platform contract.
