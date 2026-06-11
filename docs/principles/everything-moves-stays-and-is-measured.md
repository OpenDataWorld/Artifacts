# AnyDB Foundation Principle: Everything Moves, Stays, and Is Measured

Status: Normative Foundation Principle

## Principle

> Everything either moves, stays, or changes state—and every such condition must be measurable in the units defined by its domain.

AnyDB represents every governed object as an AnythingKube. The domain defines what that Kube means, how it may move, what it means to remain stable, which dimensions apply, and which units make its state measurable.

## Core Rule

> The platform defines the universal Kube contract. The domain defines the Kube's meaning, dimensions, state model, transitions, and units.

## Universal Structure, Domain-Specific Meaning

```text
Platform Defines
- identity
- version
- time
- location
- policy
- evidence
- contract
- reconciliation

Domain Defines
- object type
- properties
- dimensions
- units
- valid states
- allowed movement
- stability rules
- measurement methods
- domain semantics
```

## Motion and Rest

Every AnythingKube may be understood through two fundamental conditions:

### Movement

Movement is any measurable change across a declared dimension.

Examples:

- location changes
- state transitions
- ownership changes
- value changes
- relationship changes
- lifecycle progression
- information flow
- work progression
- trust changes

### Staying

Staying is the preservation of state within declared tolerances over a period of time.

Stability is not the absence of time. It is a measured condition.

Examples:

- inventory remains at a site
- a policy remains valid
- a service remains healthy
- a model remains approved
- a relationship remains active
- a contract remains fulfilled

## Measurement

Every Kube type must declare how its state and changes are measured.

Measurements should specify:

- quantity
- unit
- dimension
- method
- tolerance
- precision
- observation time
- observation location
- observer identity
- confidence
- provenance

## Canonical Measurement Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: Measurement
metadata:
  id: urn:anydb:measurement:temperature:01J...
  subject: urn:anydb:anythingkube:device:42
  domain: urn:anydb:domain:industrial-operations
  observedAt: 2026-06-11T12:00:00Z
  observedAtLocation: urn:anydb:edge:plant-01
  observer: urn:anydb:device:sensor-7
spec:
  dimension: temperature
  quantity: 82.4
  unit: celsius
  method: thermocouple
  precision: 0.1
  tolerance:
    min: 0
    max: 85
status:
  confidence: 0.99
  provenance: []
  reconciliation:
    state: pending
```

## Domain Defines the Kube

A domain defines the semantic profile of an AnythingKube.

Example:

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: DomainKubeDefinition
metadata:
  id: urn:anydb:domain-definition:logistics:shipment
  domain: urn:anydb:domain:logistics
  version: 1.0.0
spec:
  kubeType: Shipment
  dimensions:
    - location
    - time
    - custody
    - temperature
    - condition
  units:
    distance: kilometer
    weight: kilogram
    temperature: celsius
    duration: second
  states:
    - created
    - packed
    - in-transit
    - delayed
    - delivered
    - returned
  transitions:
    - from: created
      to: packed
    - from: packed
      to: in-transit
    - from: in-transit
      to: delivered
  stability:
    condition: no-state-change
    toleranceWindow: 5m
```

The platform validates the envelope. The domain validates the meaning.

## Custom Dimensions

Domains may create custom dimensions when standard dimensions are insufficient.

Examples:

- clinical severity
- financial exposure
- cultural sensitivity
- manufacturing quality
- scientific confidence
- contractual risk
- agent autonomy level

A custom dimension must declare:

- canonical identity
- domain owner
- semantic definition
- data type
- allowed units
- valid range
- comparison rules
- aggregation rules
- conversion rules
- policy
- version

## Canonical Dimension Contract

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: Dimension
metadata:
  id: urn:anydb:dimension:clinical-severity
  version: 1.0.0
  owner: urn:anydb:organization:health-authority
spec:
  domain: urn:anydb:domain:healthcare
  valueType: ordinal
  allowedValues:
    - low
    - moderate
    - high
    - critical
  order:
    - low
    - moderate
    - high
    - critical
  aggregation: max
  policy: urn:anydb:policy:clinical-data:v1
```

## Units

Units must be explicit and governed.

A numeric value without a unit is incomplete when the domain requires measurement.

AnyDB should support:

- standard units
- domain-specific units
- currencies
- scores
- ratings
- ordinal classes
- percentages
- probabilities
- counts
- durations
- distances
- data sizes
- trust levels

Unit conversion must preserve:

- source value
- source unit
- target value
- target unit
- conversion function
- precision loss
- rounding policy
- transformation provenance

## State and Movement

Movement is modeled as a state transition or dimensional delta.

```text
Previous Kube State
        |
        v
Transition Event
        |
        v
Measured Change
        |
        v
New Kube State
        |
        v
Reconciliation
```

Each movement should record:

- source state
- target state
- changed dimensions
- delta
- actor or cause
- time
- location
- contract
- evidence

## Stability

A Kube may remain stable only relative to declared dimensions and tolerances.

For example:

```text
A device may remain in the same location
while its temperature changes.
```

Therefore, stability must specify:

- which dimensions are expected to remain unchanged
- acceptable tolerance
- observation window
- measurement frequency
- evidence source

## Domain Context

Domain is the context that decides:

- which dimensions matter
- which changes are meaningful
- which units are valid
- which thresholds are safe
- which state transitions are permitted
- which evidence is sufficient

The same raw measurement may have different meaning in different domains.

## AnyAgent and Measurement

AnyAgent must act on measured, domain-contextualized state rather than unqualified values.

An agent should know:

- the dimension
- the unit
- the observation time
- the location
- the source
- the confidence
- the domain rule
- the acceptable tolerance

An agent must not compare values with incompatible units or domain semantics without an explicit mapping.

## Real-Time and Reactive Measurement

Measurements may trigger reactive behavior.

```text
Measurement
    |
    v
Threshold / Policy Evaluation
    |
    v
Command Proposal
    |
    v
Governed Execution
    |
    v
Observed Outcome
    |
    v
Reconciliation
```

Threshold events should retain the exact measurement and rule version that triggered them.

## Edge Measurement

The edge is often the point where movement, rest, and measurement become observable.

The edge should preserve:

- sensor or observer identity
- local time and clock confidence
- physical and logical location
- measurement unit
- calibration state
- local policy
- evidence

## Lossless Measurement Transformation

Unit conversion, aggregation, normalization, and scoring are transformations.

They must preserve:

- original value
- original unit
- transformation identity
- target value
- target unit
- rounding and precision behavior
- source provenance

A derived score must never erase the measurements that produced it.

## Single World, Multiple Models

The same real object may be represented through multiple domain models.

```text
One Canonical AnythingKube
        |
        +-- Logistics View
        +-- Finance View
        +-- Insurance View
        +-- Compliance View
```

Each domain view may define different dimensions and units while retaining one canonical identity and history.

## Reconciliation

Reconciliation compares:

- expected movement vs. observed movement
- expected stability vs. measured stability
- source unit vs. normalized unit
- domain state vs. provider state
- local edge measurement vs. canonical state

Possible outcomes:

```text
converged
within-tolerance
diverged
measurement-invalid
unit-mismatch
stale
compensating
escalated
```

## Platform Invariants

1. Every governed object is represented as an AnythingKube.
2. The platform defines the universal Kube envelope.
3. The domain defines the Kube's semantics.
4. Every meaningful change occurs across a declared dimension.
5. Every measurement declares a unit or explicit non-unit scale.
6. Stability is measured relative to tolerances and time windows.
7. Custom dimensions are versioned and governed.
8. Unit conversion preserves source values and precision behavior.
9. Domain views share canonical identity.
10. Every movement and measurement remains reconcilable.

## Foundation Formula

```text
AnythingKube = Universal Contract + Domain Meaning
```

```text
Movement = Change Across a Dimension
```

```text
Stability = No Material Change Within Declared Tolerance
```

```text
Measurement = Quantity + Unit + Time + Location + Observer + Evidence
```

## Final Statement

> Everything moves, stays, or changes in measurable ways. AnythingKube provides the universal governed unit; the domain defines what the Kube means, which dimensions matter, how change is measured, and what stability looks like.
