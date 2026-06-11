# AnyDB Architecture: State Table, External Scaffolding, and Governed Mobility

Status: Foundational Architecture Decision

## Principle

> All governed states must be explicit. Scaffolding exists outside the AnythingKube. Bulk Kube movement occurs only through governed internal ports using large shipping containers. Humans, agents, and things move freely through the single world using valid passports and visas.

## 1. All States Table

### Universal Lifecycle States

| State | Meaning | Entry Condition | Exit Condition |
|---|---|---|---|
| proposed | Exists as an idea or candidate | Definition created | Validation begins |
| validating | Under identity, policy, schema, and evidence checks | Review started | Pass, fail, or remediation |
| verified | Identity and declared properties are verified | Evidence accepted | Trust evaluation |
| trusted | Meets minimum trust threshold | Trust criteria satisfied | Drift, expiry, or suspension |
| eligible | Allowed to participate for a declared purpose | Trust and policy gates passed | Contract activation or expiry |
| active | Operating under a valid contract | Admission complete | Pause, degrade, suspend, retire |
| degraded | Operating with reduced confidence or capability | Drift or partial failure detected | Repair, restrict, or suspend |
| restricted | Operation limited by policy or risk | Conditional decision | Remediation or closure |
| suspended | Temporarily unable to operate | Safety, trust, or compliance trigger | Reinstatement or termination |
| quarantined | Isolated from real surfaces | Integrity or policy concern | Verification, repair, or rejection |
| retiring | No new work accepted | Lifecycle closure begins | Graceful exit |
| graceful-exit | Work, rights, wallet, and obligations are closing | Retirement plan activated | Terminal closure |
| deceased | Operational life has ended | Exit completed | Archive only |
| archived | Retained for history, evidence, and knowledge | Retention policy applies | Lawful deletion or permanent archive |
| rejected | Admission denied | Mandatory gate failed | New proposal only |
| expired | Time boundary crossed | Contract or credential validity ended | Renewal as a new forward event |
| terminated | Operation ended by authority | Material breach or final closure | Archive |

### Transaction States

| State | Meaning |
|---|---|
| prepared | Complete payload and contract are ready |
| gated | Governance gate is evaluating the transaction |
| admitted | Entry approved before commit |
| committed | Atomic destination state has been written |
| received | Destination receipt has been produced |
| evidenced | Required evidence is complete |
| reconciled | Both sides agree on the terminal result |
| rejected | Transaction did not enter |
| expired | Validity window closed before admission |
| quarantined | Payload isolated before authoritative entry |
| failed-before-entry | No authoritative destination effect occurred |
| compensated | A new forward transaction offset the earlier effect |

### Mobility States

| State | Meaning |
|---|---|
| at-origin | Subject remains inside its current domain |
| cleared-for-exit | Exit gate approved movement |
| containerized | Bulk Kubes sealed into a governed shipping container |
| in-port | Waiting inside a governed internal port |
| in-transit | Moving directly between governed ports or peers |
| arrived | Reached the destination port or border |
| under-admission | Destination gate is validating entry |
| admitted | Entered the destination domain |
| refused | Destination denied entry |
| redirected | New forward route created under a new contract |
| settled | Destination state and evidence are complete |

## 2. Scaffolding Lives Outside the Kube

The AnythingKube contains the governed unit of meaning and state.

Scaffolding is external infrastructure that supports, carries, protects, observes, and reconciles the Kube.

```text
External Scaffolding
├── identity services
├── policy engines
├── trust services
├── registries
├── ports and gateways
├── container runtimes
├── storage systems
├── networks
├── observability
├── recovery systems
├── bridge services
└── contract enforcement

AnythingKube
├── identity reference
├── domain reference
├── state
├── time
├── location
├── contract reference
├── evidence reference
└── lifecycle state
```

### Rule

> Scaffolding must never be mistaken for the Kube itself.

The Kube remains portable because its meaning is not owned by the infrastructure that currently carries it.

## 3. Kube Movement Uses Large Shipping Containers

Individual data fragments should not leak across large-scale infrastructure boundaries.

Bulk Kube movement uses governed shipping containers.

A shipping container is a sealed, versioned, integrity-protected transport unit containing one or more AnythingKubes and their required manifests.

### Shipping Container Contents

```text
Kube Shipping Container
├── container identity
├── origin port
├── destination port
├── manifest
├── Kube identities
├── source versions
├── domain mappings
├── contracts
├── policy decisions
├── integrity digests
├── encryption metadata
├── evidence requirements
├── transport mode
└── terminal conditions
```

### Canonical Container Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: KubeShippingContainer
metadata:
  id: urn:anydb:container:shipment:01J...
  version: 1
  owner: urn:anydb:organization:opendataworld
spec:
  originPort: urn:anydb:port:research-internal-01
  destinationPort: urn:anydb:port:publishing-internal-01
  manifest:
    kubes:
      - urn:anydb:anythingkube:artifact:42
      - urn:anydb:anythingkube:evidence:42
    aggregateDigest: sha256:...
  transfer:
    mode: bulk
    pass: one
    reverse: prohibited
  security:
    encrypted: true
    sealed: true
  contract: urn:anydb:contract:kube-container-transfer:v1
status:
  state: prepared
  reconciliation: pending
```

## 4. Governed Internal Ports

Bulk Kube containers may enter or leave only through governed internal ports.

A port is a controlled platform boundary that performs:

- identity verification
- container inspection
- manifest validation
- policy evaluation
- domain mapping
- law and jurisdiction checks
- trust verification
- integrity checks
- admission or refusal
- evidence capture
- reconciliation handoff

### Port States

```text
registered
verified
trusted
open
restricted
congested
degraded
quarantined
closed
retired
```

### Port Rule

> No container crosses a real Fabric boundary outside a governed port.

## 5. Container Movement Is Bulk, Direct, and Transactional

```text
Origin Kube Store
      ↓
Container Build
      ↓
Origin Port Gate
      ↓
Direct Bulk Transport
      ↓
Destination Port Gate
      ↓
Atomic Destination Admission
      ↓
Receipt and Evidence
      ↓
Reconciliation
```

Transport may use:

- optical fiber
- private network
- public network
- secure physical media
- object-store replication
- dedicated interconnect
- satellite or wireless links

The transport does not change the constitutional contract.

## 6. Humans, Agents, and Things Move Freely

Humans, AnyAgents, and governed things may move individually across domains using:

- passport
- visa
- purpose
- lawful basis
- wallet
- local admission

They are not required to move inside Kube shipping containers unless a specific safety, custody, or transport contract requires it.

### Mobility Model

```text
Identity
  + Passport
  + Visa
  + Wallet
  + Purpose
  + Entry Admission
  = Governed Free Movement
```

### Human Movement

Humans retain dignity, agency, lawful rights, privacy, and freedom of movement subject to applicable law and domain admission.

### Agent Movement

AnyAgents carry:

- agent identity
- accountable owner
- domain visas
- tool permissions
- context limits
- wallet state
- trust evidence
- lifecycle state

### Thing Movement

A governed thing may include:

- device
- artifact
- vehicle
- asset
- sensor
- service identity

Its passport and visa define what it is, where it may enter, and what it may do.

## 7. Difference Between Free Movement and Bulk Kube Transport

| Dimension | Humans / Agents / Things | Bulk Kube Shipping Containers |
|---|---|---|
| Purpose | Individual mobility and participation | Large-scale data and artifact movement |
| Credential | Passport and visa | Container manifest and port contract |
| Boundary | Domain admission gate | Governed internal port |
| Mode | Individual, contextual | Bulk, sealed, direct |
| State | Identity-centered | Payload-centered |
| Freedom | Broad within lawful scope | Strictly routed and inspected |
| Reversal | New forward journey only | New forward container only |

## 8. No Reverse

Once a container exits a port, that transaction does not reverse.

If it must return, a new container, new manifest, new contract, new port decision, and new forward journey are required.

The same applies to humans, agents, and things: re-entry is a new forward journey, not rollback.

## 9. Reconciliation

Reconciliation verifies:

- origin exit
- destination admission
- manifest completeness
- Kube identity continuity
- source and destination versions
- integrity digests
- policy conformance
- receipt
- terminal state

## 10. Platform Invariants

1. All states are explicit and finite.
2. Scaffolding remains outside the Kube.
3. The Kube remains portable across scaffolding.
4. Bulk Kube movement uses sealed shipping containers.
5. Containers move only through governed internal ports.
6. Container movement is direct, bulk, transactional, one-pass, and forward-only.
7. Humans, agents, and things move individually with passports and visas.
8. Free movement remains subject to law, trust, purpose, and local admission.
9. Re-entry is always a new forward journey.
10. Every movement produces evidence and a terminal state.

## Foundation Formula

```text
Surface Scaffolding = Ports + Bridges + Networks + Runtime + Policy + Recovery
```

```text
Bulk Kube Movement = Sealed Container + Governed Ports + Direct Transport + Atomic Admission
```

```text
Free Movement = Identity + Passport + Visa + Wallet + Local Admission
```

## Final Statement

> The scaffolding lives outside the Kube. Kubes move at scale only inside large governed shipping containers through internal ports. Humans, agents, and things move freely across the single world with valid passports and visas. Every movement is forward, transactional, evidenced, and governed at the boundary.
