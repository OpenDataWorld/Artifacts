# AnyDB Foundation Principle: Every Entity Has Its Own World Model but Obeys Universal Fundamentals

Status: Normative Foundation Principle

## Principle

> Every entity has its own contextual world model, but every world model must obey the universal fundamentals of the real world and the foundational laws of the core subjects.

An entity may interpret reality through its own domain, memory, language, culture, purpose, tools, and horizon. That local world model may differ from another entity's model. However, it cannot freely redefine the basic structures that make shared reality coherent.

## Core Rule

> Local interpretation is allowed. Universal fundamentals are not optional.

## Canonical Model

```text
Single Real World
      ↓
Universal Fundamentals
      ↓
Domain Laws
      ↓
Entity World Model
      ↓
Local Context and Action
```

## Entity World Model

Every entity may maintain a bounded world model containing:

- self-identity
- domain
- definitions
- time
- location
- relationships
- memory
- goals
- risks
- available actions
- permitted tools
- known limits
- trust state

Examples include:

- human mental models
- AnyAgent world models
- device state models
- organization operating models
- domain ontologies
- edge-local views
- partner delivery models

## Universal Fundamentals

Universal fundamentals are the shared rules required for interoperability, safety, measurement, reasoning, and trust.

They may include the basics of:

- mathematics
- logic
- physics
- chemistry
- biology
- ecology
- time
- space and location
- measurement
- information
- computation
- economics
- law
- ethics
- language
- history
- governance

The platform does not claim one implementation or interpretation for every subject. It requires each domain and entity model to declare how it maps to the shared fundamentals relevant to its purpose.

## Foundational Subject Registry

The platform should maintain a governed registry of core subjects and their shared primitives.

Example:

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: FundamentalSubject
metadata:
  id: urn:anydb:subject:measurement
  version: 1.0.0
spec:
  primitives:
    - quantity
    - unit
    - observer
    - time
    - location
    - precision
    - uncertainty
  invariants:
    - values requiring units must declare units
    - conversions must preserve source and precision behavior
```

## Mathematics and Logic

Entity models must preserve:

- explicit assumptions
- valid operations
- consistent units
- declared uncertainty
- non-contradictory inference where required

A domain may define custom scores or scales, but it must declare how they behave.

## Physics and the Real Surface

Any model that can affect a physical surface must respect relevant constraints such as:

- energy
- capacity
- latency
- distance
- temperature
- material limits
- signal propagation
- failure behavior

A simulated model may simplify these constraints, but must declare the simplification and fidelity limits.

## Biology and Living Systems

Models of people, organisms, ecosystems, or health must preserve:

- living-system boundaries
- lifecycle
- variability
- uncertainty
- privacy
- safety
- ethical constraints

A digital model is not the living subject itself.

## Ecology

Every generation and system exists within ecological limits.

Entity models should account for:

- resource use
- energy
- waste
- emissions
- habitat effects
- regeneration
- generational continuity

## Information and Computation

Every computational world model must distinguish:

- source data
- representation
- inference
- simulation
- observation
- decision
- real consequence

Information may be transformed, but identity, provenance, context, and declared loss must remain explainable.

## Economics

Economic models should declare:

- value definition
- ownership
- custody
- consideration
- risk
- incentives
- externalities
- settlement
- time horizon

No private score may silently redefine public value without context.

## Law and Governance

Every entity world model remains subject to:

- applicable law
- constitutional boundaries
- platform contract
- domain policy
- rights and obligations
- intervention limits
- review and appeal

A local model cannot manufacture legal authority.

## Ethics and Justice

A model should not be considered valid merely because it is technically executable.

High-consequence models must account for:

- fairness
- dignity
- proportionality
- consent
- preventable harm
- accountability
- future generations

## Language and Culture

Each entity may use its own language and cultural interpretation.

Federation requires mappings that preserve:

- source meaning
- target meaning
- ambiguity
- untranslatable concepts
- cultural sensitivity
- declared semantic loss

## History

Every world model must preserve that the past is real and cannot be altered.

New interpretations may be added, but historical events remain immutable.

## Domain Laws

The domain specializes universal fundamentals for a particular area.

```text
Universal Measurement
      ↓
Clinical Measurement

Universal Time
      ↓
Legal Deadline

Universal Identity
      ↓
Patient, Citizen, Agent, Partner
```

Domain laws may add constraints, but cannot silently contradict universal fundamentals.

## Local Freedom

An entity may define:

- its perspective
- its memory map
- its goals
- its preferred language
- its internal abstractions
- its workflow
- its simulations
- its local optimizations

provided those choices remain compatible with the shared fundamentals at the boundary where the entity interacts with others.

## Boundary Validation

Before an entity exchanges data or acts on a real surface, the platform should verify:

1. identity
2. domain
3. active world-model version
4. relevant fundamental-subject mappings
5. definitions
6. units and dimensions
7. law and policy
8. trust
9. evidence
10. compatibility with the receiving boundary

## Contradiction Handling

When an entity world model conflicts with a universal fundamental or another domain model, the platform should:

```text
Detect
→ Isolate the contradiction
→ Identify the affected subject
→ Compare assumptions and evidence
→ Map or reject
→ Record the decision
→ Advance with a new governed state
```

The contradiction is not hidden or silently normalized.

## AnyAgent World Models

Every AnyAgent should declare:

- the domains it understands
- the foundational subjects it depends upon
- its assumptions
- units
- simulation limits
- model limitations
- prohibited inferences
- uncertainty

An agent must not act outside subjects and domains for which it has sufficient verified competence and permission.

## Education

Education must result in enablement by helping participants understand and apply the fundamentals required for safe and meaningful action.

## Research

Research may challenge existing interpretations, but it must preserve evidence, method, definitions, and the distinction between hypothesis and established real-world result.

## Platform Invariants

1. Every entity may maintain its own contextual world model.
2. Every world model has a declared owner, domain, version, and scope.
3. Relevant universal fundamentals must be mapped explicitly.
4. Local interpretation cannot silently override shared boundary laws.
5. Definitions, dimensions, units, assumptions, and uncertainty remain explicit.
6. Simulations remain distinct from real-world effects.
7. Applicable law and constitutional governance remain binding.
8. Cultural and linguistic variation is preserved through explicit mappings.
9. Contradictions remain visible and governed.
10. Real-surface action requires compatibility with the relevant fundamentals.

## Foundation Formula

```text
Entity World Model
=
Local Perspective
+ Domain Context
+ Memory
+ Purpose
+ Universal Fundamental Mappings
```

```text
Shared Reality
=
Many Local World Models
+ Common Fundamentals
+ Governed Boundaries
+ Evidence
```

## Final Statement

> Everything may have its own world model. Humans, agents, systems, domains, and things may perceive and organize reality differently. But all must obey the universal fundamentals required for a shared real world: the basics of time, space, measurement, logic, living systems, information, law, ethics, and governance.
