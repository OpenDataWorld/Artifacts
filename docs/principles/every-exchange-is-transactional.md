# AnyDB Foundation Principle: Every Exchange Is Transactional

Status: Normative Foundation Principle

## Principle

> Every exchange of data, value, rights, context, artifacts, authority, credentials, work, or evidence is transactional.

An exchange is never merely a message in transit. It is a governed state transition between identified parties, under an explicit contract, with atomic admission, immutable evidence, and a terminal outcome.

## Core Rule

> No partial exchange. No ambiguous ownership. No uncommitted authority. No success without evidence.

## What Counts as an Exchange

An exchange may involve:

- data
- AnythingKubes
- context
- memory fragments
- credentials
- passports and visas
- artifacts
- models
- permissions
- delegations
- payments
- entitlements
- ownership
- custody
- contracts
- trust claims
- evidence
- work results

## Transactional Exchange Model

```text
Offer
  ↓
Governance Gate
  ↓
Atomic Transfer
  ↓
Destination Commit
  ↓
Receipt
  ↓
Evidence
  ↓
Terminal Outcome
```

The exchange either commits under the contract or does not commit.

## Exchange Contract

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: ExchangeContract
metadata:
  id: urn:anydb:exchange:01J...
  version: 1.0.0
spec:
  sender: urn:anydb:identity:peer-a
  receiver: urn:anydb:identity:peer-b
  subject: urn:anydb:anythingkube:artifact:42
  domain:
    source: urn:anydb:domain:research
    destination: urn:anydb:domain:publishing
  transaction:
    mode: atomic
    pass: one
    reverse: prohibited
  consideration:
    type: none
  policy:
    - urn:anydb:policy:exchange:v1
  time:
    validFrom: 2026-06-11T12:00:00Z
    expiresAt: 2026-06-11T12:05:00Z
  evidenceRequirements:
    - sender-signature
    - receiver-receipt
    - integrity-digest
    - policy-decision
status:
  state: pending
```

## Atomicity

Atomicity means the destination does not expose partial authoritative state.

A successful exchange commits together:

1. destination state
2. new version
3. transfer event
4. provenance
5. policy decision
6. receipt
7. terminal exchange status

If any required part cannot commit, the exchange fails before completion.

## Consistency

The exchange must preserve the active domain rules and platform invariants.

Examples:

- valid identity
- valid schema
- compatible units
- lawful basis
- ownership rules
- policy constraints
- no unresolved critical gaps
- current visa or delegation

## Isolation

Concurrent exchanges must not silently create contradictory rights, versions, balances, ownership, or custody.

The contract should declare the isolation behavior required by consequence.

## Durability

Once committed, the exchange becomes immutable history.

Corrections, refunds, revocations, or compensation are new forward transactions.

## One Step, One Pass, No Reverse

Every real exchange follows:

```text
one governed boundary transition
one direct payload movement
one destination commit
no reversal of committed history
```

A later return, correction, or compensation is a separate transaction with a new contract and event chain.

## Peer-to-Peer

The payload may move directly between peers while the platform holds the exchange contract and verifies evidence.

```text
Peer A Wallet / Fabric
        ↓
Governance Gate
        ↓
Peer-to-Peer Exchange
        ↓
Peer B Wallet / Fabric
```

The platform need not become a central data custodian.

## Wallet Settlement

Wallet-mediated exchange may carry:

- identity proofs
- rights
- receipts
- payment authorization
- ownership claims
- visas
- delegation
- artifact references

Sensitive payloads remain off-chain by default.

## Context Exchange

Context delivery is transactional.

The receiver gets one purpose-bound, time-bound, policy-filtered context package with a version and receipt.

No unbounded context stream is implied by one exchange.

## Trust Exchange

Trust itself is not blindly transferred.

What is exchanged is:

- evidence
- attestations
- issuer identity
- evaluation time
- trust-model reference

The destination performs its own local trust evaluation.

## Value Exchange

Where consideration exists, the transaction must bind:

- asset or service
- amount
- unit or currency
- payer
- payee
- authorization
- settlement state
- receipt
- refund or compensation rules

## Failure States

Recommended terminal outcomes:

```text
committed
rejected
expired
quarantined
failed-before-entry
compensated-by-new-transaction
escalated-before-entry
```

`pending` is never a terminal outcome.

## Recovery

Recovery is transactional and forward-only.

```text
Failure Detected
      ↓
Recovery Contract
      ↓
Repair Transaction
      ↓
New State
      ↓
Verification
      ↓
Reconciliation
```

## Reconciliation

After commit, the platform verifies that:

- sender recorded the exit
- receiver recorded the entry
- identity and version match
- evidence is complete
- consideration settled where applicable
- no duplicate effect occurred
- the terminal outcome is consistent on both sides

## Idempotency

Every exchange must have a unique transaction ID or idempotency key.

Duplicate delivery must not create duplicate business effects.

## Privacy and Compliance

Every exchange must evaluate:

- purpose
- lawful basis
- minimization
- jurisdiction
- residency
- consent or authority
- retention
- disclosure limits

## Platform Invariants

1. Every exchange has identified parties.
2. Every exchange has an explicit contract.
3. Every exchange is atomic at the declared boundary.
4. Every exchange is one step, one pass, no reverse.
5. Every exchange has a unique transaction identity.
6. Every committed exchange becomes immutable history.
7. Every correction or compensation is a new transaction.
8. Every destination performs local admission.
9. Every exchange produces evidence and a receipt.
10. Every exchange ends in an explicit terminal state.

## Foundation Formula

```text
Exchange = Contract + Parties + Subject + Gate + Atomic Commit + Receipt + Evidence
```

```text
Transactional Exchange = All Required Effects or No Commit
```

## Final Statement

> Every exchange is transactional. Data, value, rights, context, artifacts, and authority move only through an explicit contract, one governed pass, an atomic destination commit, and a verifiable terminal outcome.
