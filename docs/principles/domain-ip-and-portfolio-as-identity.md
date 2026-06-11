# AnyDB Foundation Principle: Domain IP Is Protected; Intelligence, Skills, and Portfolio Form the Identity Card

Status: Normative Foundation Principle

## Principle

> Every domain retains ownership and control of its lawful intellectual property. A person’s, agent’s, organization’s, or operator’s intelligence, skills, experience, and portfolio form its meaningful identity card. Registries should contain only the minimum aliases, profiles, references, and verification state needed for discovery and admission.

Identity must not be reduced to a single registry record, nor should a registry become the owner of a person, agent, community, domain, or body of knowledge.

## Core Rule

> The registry indexes identity. It does not contain the whole identity.

## Identity Card Model

A meaningful identity card may reference:

- verified subject identity
- domain affiliations
- skills
- competencies
- intelligence capabilities
- qualifications
- work history
- portfolio artifacts
- research contributions
- licenses
- trust state
- lifecycle state
- current operating profiles
- evidence and attestations

```text
Identity Card
=
Verified Subject
+ Intelligence
+ Skills
+ Portfolio
+ Evidence
+ Trust
```

## Registry Minimization

A registry should store only the minimum metadata required for:

- discovery
- alias resolution
- profile lookup
- credential verification
- trust-state lookup
- routing
- admission
- revocation
- lifecycle status

A registry entry may contain:

- alias
- profile identifier
- subject reference
- domain reference
- credential references
- portfolio references
- trust state
- lifecycle state
- issuer
- validity
- revocation state

It should not contain the full private memory, internal reasoning, protected portfolio content, or complete domain IP unless an explicit lawful contract requires it.

## Canonical Alias Profile

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: AliasProfile
metadata:
  id: urn:anydb:alias-profile:operator:chinmay-panda
  version: 1
spec:
  alias: thefractionalpm
  subject: urn:anydb:identity:person:chinmay-panda
  domains:
    - urn:anydb:domain:platform-architecture
    - urn:anydb:domain:agent-systems
  profiles:
    - urn:anydb:profile:founder-architect
    - urn:anydb:profile:platform-operator
  skills:
    - urn:anydb:skill:platform-design
    - urn:anydb:skill:agent-governance
  portfolio:
    - urn:anydb:portfolio:open-data-world
  trustState: verified
  lifecycle: active
status:
  visibility: public-minimal
  revocation: clear
```

## Domain Intellectual Property

Every domain may own or steward original intellectual property such as:

- definitions
- ontologies
- taxonomies
- frameworks
- scoring models
- procedures
- research
- datasets
- specifications
- policies
- software
- model artifacts
- diagrams
- training material
- cultural knowledge

Every protected artifact should preserve:

- author
- owner
- steward
- creation time
- version
- provenance
- digest
- license
- permitted uses
- restrictions

## Intelligence as Identity

Intelligence is part of identity when it is evidenced through capability and contribution.

It may be represented through:

- demonstrated problem solving
- original research
- validated methods
- authored artifacts
- domain judgment
- creative work
- operational outcomes
- peer or institution attestations

A claim of intelligence without evidence is a profile claim, not a verified capability.

## Skills as Identity

Skills should be:

- named
- domain-bound
- versioned where standards change
- evidenced
- current or expired
- linked to real work where possible

Recommended skill states:

```text
claimed
assessed
verified
practiced
current
stale
expired
disputed
```

## Portfolio as Identity

A portfolio is the evidence-bearing history of contribution.

It may include:

- authored artifacts
- deployed systems
- completed work
- research
- publications
- designs
- decisions
- outcomes
- references
- community contribution
- recovery or incident work

The portfolio should preserve provenance and ownership rather than being copied into a central registry.

## Multi-Profile Identity

One identity may expose multiple profiles for different purposes.

Examples:

```text
Founder Profile
Researcher Profile
Operator Profile
Partner Profile
Community Profile
Agent Profile
Regional Profile
Customer-Specific Profile
```

Each profile must declare:

- purpose
- domain
- visibility
- permitted claims
- validity period
- issuer
- evidence
- revocation

## Alias Is Not Identity

```text
Alias
    ≠
Identity
```

An alias is a discoverable name or handle that resolves to a governed identity reference.

Aliases may change. Historical identity and portfolio provenance remain intact.

## Profile Is Not the Whole Person or Agent

```text
Profile
    =
Purpose-Bound View of Identity
```

A profile should expose only the attributes needed for its purpose.

## Wallet Relationship

The wallet may hold or reference:

- identity proofs
- aliases
- profiles
- skill credentials
- portfolio receipts
- licenses
- domain visas
- trust attestations
- revocation state

The registry points to the wallet or credential issuer without becoming the sole custodian of identity.

## Common Collective Knowledge Registry

The common registry may index:

- authors
- contributors
- domain owners
- artifact references
- portfolio references
- licenses
- verification state

It must preserve attribution and must not absorb ownership of the underlying intellectual property.

## Privacy

Identity-first remains privacy-first.

The platform should support:

- selective disclosure
- alias-based discovery
- private profiles
- purpose-bound credentials
- minimal registry metadata
- revocable references
- separated public and private portfolios
- pseudonymity where lawful

## Trust

Trust evaluation may consider:

- verified identity
- current skills
- portfolio evidence
- domain standing
- contribution history
- contract outcomes
- incident history
- recovery performance

The platform may protect its exact trust-scoring logic while publishing mandatory eligibility gates and material reasons.

## Portability

A subject must be able to export and carry:

- identity credentials
- skill proofs
- portfolio references
- authorship evidence
- licenses
- trust attestations where portable
- alias mappings

No registry may hold a person’s or agent’s identity hostage.

## Platform Invariants

1. Every domain retains lawful ownership of its IP.
2. Identity is richer than a registry record.
3. Intelligence, skills, and portfolio are part of the identity card.
4. Claims require evidence before they become verified capabilities.
5. Registries store minimal aliases, profiles, references, and status.
6. Aliases and profiles never replace the underlying identity.
7. Portfolio ownership and provenance remain with the lawful owner.
8. Identity disclosure is purpose-bound and privacy-preserving.
9. Multiple profiles may coexist under one identity.
10. Identity, skills, and portfolio remain portable across registries and domains.

## Foundation Formula

```text
Identity Card
=
Identity
+ Intelligence
+ Skills
+ Portfolio
+ Evidence
+ Trust
```

```text
Registry
=
Alias
+ Profile
+ References
+ Verification State
```

```text
Domain Asset
=
Original IP
+ Ownership
+ Provenance
+ License
```

## Final Statement

> Every domain owns and protects its original intellectual property. Your intelligence, skills, work, and portfolio form the real identity card. Registries contain only aliases, profiles, references, and verification state—enough to discover and trust you, never enough to own or replace you.
