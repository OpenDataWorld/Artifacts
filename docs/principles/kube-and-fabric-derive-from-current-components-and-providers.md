# AnyDB Foundation Principle: Kube and Fabric Derive from Current Components and Providers

Status: Normative Foundation Principle

## Principle

> Kube and Fabric are implementation definitions derived from the components, providers, protocols, tools, and operating models currently available to us.

They are practical abstractions shaped by today’s technological landscape. They are not permanent descriptions of reality, and they must not become tied to one vendor, product, provider, or generation.

## Core Rule

> Define from what exists. Abstract what is common. Preserve provider neutrality. Evolve when better components mature.

## Current Implementation Basis

Kube and Fabric may presently be implemented through components such as:

- Linux and operating systems
- Kubernetes and container runtimes
- cloud and edge infrastructure
- databases and graph stores
- identity providers
- wallets and credentials
- policy engines
- observability systems
- model runtimes
- agent frameworks
- APIs and protocols
- storage and networking providers
- enterprise delivery partners

These components influence the current implementation, but do not own the definitions.

## Canonical Distinction

```text
Nature and First Principles
        ↓
Kube and Fabric Abstractions
        ↓
Current Component and Provider Mapping
        ↓
Concrete Implementation
```

## Provider Mapping

Each implementation should publish a mapping such as:

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: ImplementationMapping
metadata:
  id: urn:anydb:implementation:current-stack:v1
  version: 1.0.0
spec:
  kube:
    runtime: kubernetes
    storage: surrealdb
    identity: did-vc
    policy: opa
    relationships: openfga
  fabric:
    orchestration: juju
    transport: cloudevents
    observability: opentelemetry
    deployment:
      - cloud
      - edge
  providers:
    compute:
      - provider-a
      - provider-b
status:
  lifecycle: active
  portability: verified
```

## Replaceable Providers

Every provider-backed dimension should declare:

- purpose
- interface
- provider
- version
- dependencies
- portability
- migration path
- failure mode
- exit procedure
- replacement candidates

```text
Stable Definition
+
Replaceable Provider
=
Sustainable Implementation
```

## Current Does Not Mean Canonical

A component may be the best available implementation today without becoming the permanent standard.

The platform must distinguish:

```text
Current Choice
    ≠
Universal Truth
```

and:

```text
Reference Implementation
    ≠
Only Valid Implementation
```

## Adoption Lifecycle

New components and providers enter through:

```text
candidate
→ evaluated
→ mapped
→ simulated
→ verified
→ production-eligible
→ preferred
→ deprecated
→ retired
```

## Selection Criteria

Components and providers should be selected based on:

- capability fit
- maturity
- interoperability
- openness
- portability
- security
- privacy
- compliance
- recoverability
- support
- cost
- ecological impact
- backward compatibility
- provider exit

## No Provider Sovereignty

No provider may become the hidden owner of:

- identity
- context
- contracts
- provenance
- knowledge
- trust
- lifecycle
- customer exit

The platform holds the contract. Providers implement bounded capabilities.

## Evolution

As new components emerge:

```text
Observe
→ Evaluate
→ Model
→ Trial
→ Verify
→ Map
→ Adopt
→ Migrate
→ Retire Old Tool Gracefully
```

The Kube and Fabric definitions may evolve when new implementation capabilities reveal a better abstraction, but all changes must preserve provenance and compatibility.

## Platform Invariants

1. Kube and Fabric are based on currently available implementation options.
2. They remain abstractions above specific products and providers.
3. Every provider mapping is explicit and versioned.
4. Portability and exit are mandatory.
5. No current component becomes permanently canonical by default.
6. New providers pass capability, maturity, conformance, and quality checks.
7. Old implementations retire gracefully.
8. Historical mappings remain interpretable.
9. The platform contract remains stable across provider changes.
10. Real-world outcomes determine whether an implementation remains useful.

## Foundation Formula

```text
Current Implementation
=
Kube and Fabric Definitions
+ Available Components
+ Selected Providers
+ Explicit Mappings
```

```text
Provider-Neutral Evolution
=
Stable Contracts
+ Replaceable Implementations
+ Portability
+ Graceful Migration
```

## Final Statement

> Kube and Fabric are defined using the components and providers available in the current generation. They make implementation easier, but remain provider-neutral, replaceable, and open to evolution. The abstraction stays stable enough to preserve continuity; the underlying technologies change as better capabilities mature.
