# AnyDB Foundation Principle: Everything Is in a Wallet

Status: Normative Foundation Principle

## Principle

> Every governed identity, AnythingKube, credential, contract, artifact, permission, proof, and trust claim may be held, referenced, presented, transferred, or revoked through a blockchain-compatible wallet.

The wallet is the portable custody and consent surface of the platform.

It does not replace AnyDB, the Fabric, the Constitution, or the domain. It gives identities a controlled way to carry and present the proofs, rights, references, and assets needed to participate in them.

## Core Rule

> Put proofs, keys, claims, references, receipts, and revocation state in or through the wallet. Keep sensitive operational data off-chain unless an explicit lawful contract requires otherwise.

## Wallet Model

```text
Wallet
├── Identity Keys
├── Passports
├── Visas
├── Credentials
├── Contract References
├── Policy Grants
├── Artifact Receipts
├── AnythingKube References
├── Trust Assertions
├── Evidence Digests
├── Delegations
├── Payments and Entitlements
└── Revocation State
```

## Wallet Is Not the Database

The wallet does not need to contain every byte of an AnythingKube.

It may contain:

- canonical or contextual identity references
- content-addressed artifact references
- encrypted pointers
- verifiable credentials
- signatures
- hashes
- ownership and custody claims
- access grants
- consent receipts
- transaction receipts

AnyDB remains the governed data kernel and memory fabric.

## On-Chain and Off-Chain Separation

### Suitable for On-Chain or Ledger Anchoring

- integrity digests
- timestamps
- ownership claims
- issuance and revocation events
- contract references
- public keys
- asset-transfer receipts
- governance votes where applicable
- audit anchors

### Keep Off-Chain by Default

- personal data
- confidential documents
- private memory
- health data
- credentials containing sensitive attributes
- model context
- detailed operational logs
- proprietary trust-scoring logic
- secrets and private keys

## Canonical Wallet Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: Wallet
metadata:
  id: urn:anydb:wallet:person:chinmay-panda
  version: 1
  owner: urn:anydb:person:chinmay-panda
spec:
  identities:
    - urn:anydb:identity:person:chinmay-panda
  credentials:
    - urn:anydb:credential:domain-passport:01J...
  contracts:
    - urn:anydb:contract:partner-delivery:v1
  holdings:
    - type: artifact-reference
      subject: urn:anydb:anythingkube:artifact:anydb-constitution
      digest: sha256:...
  delegations: []
  chains:
    - network: declared-ledger
      address: "0x..."
status:
  lifecycle: active
  recovery: configured
  reconciliation: converged
  trust: verified
```

## AnythingKube in a Wallet

An AnythingKube may be represented in a wallet through:

- a verifiable credential
- a signed manifest
- an encrypted reference
- a content digest
- an ownership token
- a custody receipt
- a domain passport
- a destination visa
- a contract entitlement

The wallet representation must preserve:

- subject identity
- Kube type
- source version
- issuer
- owner or holder
- domain
- validity period
- policy
- digest
- revocation method

## Passport and Visa

The World Passport Protocol maps naturally to wallets.

```text
Wallet
  ├── Persistent Passport
  ├── Destination Visa
  ├── Journey Contract
  └── Entry and Exit Receipts
```

A passport proves identity and origin.

A visa proves destination-specific permission.

Neither overrides local law, domain policy, or entry admission.

## AnyAgent Wallet

Every AnyAgent should have a wallet or wallet-bound identity containing references to:

- agent identity
- accountable owner
- model and runtime attestations
- permitted tools
- delegation
- budget
- domain visas
- contract scope
- credential validity
- trust state
- stop or revocation controls

An agent wallet does not grant unrestricted autonomy.

It presents evidence to governance gates.

## Domain Wallet

A verified domain may maintain a wallet for:

- domain identity
- constitutional declaration
- published framework
- signing keys
- provider credentials
- federation contracts
- trust attestations
- revocation lists
- recovery authorities

## Partner Wallet

A partner wallet may hold:

- verified partner identity
- certifications
- delivery entitlements
- marketplace rights
- customer-specific visas
- contract references
- insurance or assurance evidence
- delivery receipts
- trust and suspension status

## Artifact Wallet

Artifacts may have wallet representations containing:

- author
- owner
- license
- version
- digest
- source repository
- provenance
- signature
- permitted use
- commercial rights

This supports protection and transfer of original artifacts without placing their complete content on-chain.

## Wallet Transfer

Wallet-mediated transfer follows the platform's forward-only rule.

```text
Holder Wallet
      ↓
Governance Gate
      ↓
Signed One-Pass Transfer
      ↓
Recipient Wallet
      ↓
Receipt and Reconciliation
```

A correction or compensation is a new forward transaction.

## Custody vs. Ownership

The wallet must distinguish:

- holder
- custodian
- owner
- issuer
- beneficiary
- controller
- delegate

Possession of a wallet reference does not automatically prove ownership.

## Consent and Permission

Wallets may carry purpose-bound grants for:

- data access
- agent delegation
- domain entry
- context delivery
- artifact use
- payment authorization
- partner delivery

Each grant must be scoped by action, purpose, time, location, domain, and revocation.

## Trust and Wallets

A wallet may present trust evidence, but the destination domain evaluates it locally.

```text
Wallet Claim
   ↓
Issuer and Signature Verification
   ↓
Evidence and Revocation Check
   ↓
Local Domain Trust Evaluation
   ↓
Admission Decision
```

Trust is not transferred as unquestioned authority.

## Recovery

Wallet recovery is mandatory for production eligibility.

Recovery may use:

- social or organizational recovery
- multi-signature control
- hardware-backed keys
- delegated guardians
- recovery credentials
- key rotation
- revocation and reissuance

Recovery must preserve identity history without exposing secret material.

## Privacy

Wallet use must follow privacy-first principles.

The platform should support:

- selective disclosure
- pairwise or contextual identifiers
- zero-knowledge proofs where appropriate
- minimal credential presentation
- unlinkability where legally and operationally suitable
- consent receipts
- revocation without unnecessary disclosure

## Blockchain Neutrality

AnyDB is blockchain-compatible, not locked to one chain.

A wallet provider or ledger must declare:

- supported identity and credential standards
- privacy behavior
- finality model
- transaction cost
- recovery model
- portability
- export
- migration
- exit procedure

## No Token Requirement

Participation in AnyDB does not inherently require a speculative token, cryptocurrency, or public-chain transaction.

Wallets may operate with:

- verifiable credentials
- private or consortium ledgers
- public blockchains
- local secure stores
- hardware wallets
- enterprise key-management systems

The domain and contract determine the appropriate mechanism.

## Platform Invariants

1. Every wallet has verified identity and accountable ownership or custody.
2. Sensitive data remains off-chain by default.
3. AnythingKubes may be referenced without copying their full content into the wallet.
4. Every credential has issuer, validity, scope, and revocation behavior.
5. Passport and visa do not override local admission.
6. Agent wallets remain bounded by contract and policy.
7. Wallet transfer is one step, one pass, and forward-only.
8. Ownership, custody, and possession remain distinct.
9. Wallet recovery is mandatory for production use.
10. No single blockchain or wallet vendor owns the platform contract.

## Foundation Formula

```text
Wallet = Identity + Keys + Credentials + Rights + Proofs + References + Recovery
```

```text
AnythingKube in Wallet = Governed Reference + Integrity + Authority + Validity
```

## Final Statement

> Everything may be carried through a wallet, but not everything belongs on-chain. The wallet is the portable custody, identity, consent, and proof surface for AnythingKubes, AnyAgents, contracts, artifacts, passports, visas, and trust claims, while AnyDB preserves the governed data and the Fabric verifies every movement.
