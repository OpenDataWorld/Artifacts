# AnyDB Foundation Principle: One World, Forward Exit, Passport-Governed Entry

Status: Normative Foundation Principle

## Principle

> There is one world with many governed domains. Once an AnythingKube exits a domain through a real boundary, that transfer does not reverse. It may continue forward into another eligible domain only with valid identity, passport, visa, contract, and local admission.

The world is singular. Domains are contextual and constitutional regions within it.

Movement between domains is governed travel, not duplication, rollback, or loss of identity.

## Core Rule

> Exit is final for that transfer. Entry is conditional. Identity continues. History never reverses.

## World Model

```text
Single World
   |
   +-- Domain A
   +-- Domain B
   +-- Domain C
   +-- Domain D
```

An AnythingKube may travel across domains while preserving one canonical identity and one forward-only history.

## Forward Movement

```text
Domain A
   ↓ exit gate
Transit
   ↓ entry gate
Domain B
   ↓ future exit
Domain C
```

The same transfer never returns to Domain A.

A later movement to Domain A, when permitted, is a new forward journey under a new contract, passport check, visa, and event history.

## No Return Means No Reversal

`No return` means:

- no rollback of the original crossing
- no rewriting of the exit event
- no reuse of the original admission decision
- no silent restoration of the previous domain state
- no reverse movement through the same transfer contract

It does not mean permanent exile from a domain.

A future re-entry may occur as a new forward operation if the destination domain permits it.

## Canonical Travel Model

```text
Identity
   +
Passport
   +
Visa
   +
Journey Contract
   +
Exit Decision
   +
Entry Decision
   =
Governed Domain Movement
```

## Passport

The passport establishes persistent identity and origin.

A passport should declare:

- canonical AnythingKube identity
- issuing authority
- home domain
- owner
- type and schema
- constitutional version
- validity period
- integrity proof
- revocation status

Example:

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: WorldPassport
metadata:
  id: urn:anydb:passport:anythingkube:artifact-42
  version: 1
spec:
  subject: urn:anydb:anythingkube:artifact:42
  issuer: urn:anydb:domain:research
  homeDomain: urn:anydb:domain:research
  validFrom: 2026-06-11T00:00:00Z
  validTo: 2027-06-11T00:00:00Z
  constitutionalVersion: 0.1
  identityProof: urn:anydb:evidence:identity-proof-42
status:
  state: valid
  trust: verified
```

## Visa

The visa is destination-specific permission to enter and operate.

A visa should declare:

- destination domain
- permitted purpose
- permitted actions
- data and context scope
- location boundary
- time window
- conditions
- evidence requirements
- number of entries
- expiry

Example:

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: DomainVisa
metadata:
  id: urn:anydb:visa:artifact-42:publishing:v1
spec:
  subject: urn:anydb:anythingkube:artifact:42
  destination: urn:anydb:domain:publishing
  purpose: publication
  permittedActions:
    - submit
    - validate
    - publish
  entries: single
  validFrom: 2026-06-11T10:00:00Z
  expiresAt: 2026-06-11T12:00:00Z
  conditions:
    - preserve-provenance
    - retain-source-license
  evidenceRequirements:
    - passport-verification
    - content-digest
    - policy-decision
status:
  state: granted
```

## Journey Contract

Every crossing uses one explicit journey contract.

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: JourneyContract
metadata:
  id: urn:anydb:journey:research-to-publishing:01J...
spec:
  subject: urn:anydb:anythingkube:artifact:42
  origin: urn:anydb:domain:research
  destination: urn:anydb:domain:publishing
  passport: urn:anydb:passport:anythingkube:artifact-42
  visa: urn:anydb:visa:artifact-42:publishing:v1
  transfer:
    mode: peer-to-peer
    step: one
    pass: one
    reverse: prohibited
  payload:
    sourceVersion: 7
    digest: sha256:...
  terminalStates:
    - admitted
    - rejected
    - expired
    - quarantined
    - failed-before-entry
status:
  state: pending
```

## Exit Gate

The origin domain verifies:

- canonical identity
- passport validity
- authority to leave
- export and residency rules
- privacy and compliance
- source version
- integrity
- journey contract
- destination visa

The exit event becomes immutable history.

## Transit

Transit must minimize real surface area.

The transfer is:

- peer to peer
- encrypted
- complete before crossing
- single-pass
- digest-verifiable
- purpose-bound
- time-bound

Transit does not grant operational authority.

## Entry Gate

The destination domain independently verifies:

- passport
- visa
- destination law
- constitutional compatibility
- local domain policy
- schema compatibility
- integrity digest
- trust requirements
- time and location validity
- evidence

The destination retains the right to admit, condition, quarantine, or reject.

## Admission States

```text
admitted
admitted-with-conditions
rejected
expired
quarantined
escalated-before-entry
failed-before-entry
```

## New Domain, New Context

When admitted, the AnythingKube retains canonical identity but receives destination context.

```text
Same Identity
   +
New Domain Context
   +
New Local Relationships
   +
New Policies
   =
New Governed Domain State
```

The destination must not erase the home domain, source context, or journey provenance.

## Re-Entry

A return to a previous domain is never a reversal.

It is a new journey:

```text
Domain A → Domain B
```

followed later by:

```text
Domain B → Domain A
```

The second journey requires:

- a new visa
- a new journey contract
- current passport validity
- a new exit event
- a new entry decision
- current law and policy evaluation

## AnyAgent Travel

AnyAgent may cross domains only when its passport and visa also define:

- accountable owner
- objective
- allowed tools
- context scope
- memory scope
- autonomy level
- budget
- stop conditions
- evidence requirements

An agent may not carry unrestricted memory or authority across domain borders.

## Context Travel

Context is delivered just in time and should not travel as an unbounded memory copy.

A destination receives the smallest permitted context package for the declared purpose.

## Data and Artifact Travel

Data, documents, models, policies, and artifacts may travel as AnythingKubes.

Every journey preserves:

- identity
- version
- time
- location
- domain origin
- owner
- policy
- provenance
- digest
- declared transformation behavior

## Law of the Land

Each border applies the law of the land relevant to that boundary.

A valid passport does not guarantee entry.

A valid visa does not override applicable law.

## Cultural and Domain Sovereignty

Travel across domains must preserve local vocabulary, units, cultural context, and constitutional boundaries.

The destination may map meaning, but it must declare semantic loss or reinterpretation.

## Trust

Trust travels as evidence, not as unquestioned status.

The destination evaluates passport, visa, issuer, provenance, and prior outcomes under local policy.

## Recovery

A committed crossing is not reversed.

If a problem appears after entry, the destination may:

- quarantine
- restrict
- compensate
- suspend
- create a corrective journey
- initiate a new forward movement
- close with evidence

## Platform Invariants

1. There is one world with many governed domains.
2. Every traveler has canonical identity.
3. Every crossing requires a valid passport and destination visa.
4. Every crossing is one step, one pass, no reverse.
5. Exit and entry are independent governance decisions.
6. A committed exit remains immutable history.
7. Re-entry is a new forward journey, never rollback.
8. Domain context changes without changing canonical identity.
9. Local law and constitutional boundaries govern admission.
10. Every journey ends in an explicit terminal state.

## Foundation Formula

```text
Passport = Persistent Identity + Origin + Authority
```

```text
Visa = Destination Permission + Purpose + Scope + Time
```

```text
Journey = Passport + Visa + Contract + Exit Gate + Entry Gate
```

```text
One World = Many Domains + Governed Forward Movement
```

## Final Statement

> There is one world and many governed domains. Once an AnythingKube exits a domain, that journey never reverses. It may continue anywhere it is lawfully admitted, carrying one identity, a valid passport, the right visa, and an immutable forward history.
