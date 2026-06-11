# Shared Context with Separation of Concern

Status: Normative Foundation Principle

## Principle

> Participants may share context without merging concerns.

Shared context provides enough common meaning for humans, agents, platforms, domains, organizations, and nations to coordinate. Separation of concern preserves each participant’s distinct responsibility, authority, data boundary, operating model, ownership, and accountability.

## Core Rule

> Share what is necessary to coordinate. Keep concerns independently governed.

## Canonical Model

```text
Local Context A
    ↓ minimum necessary projection
Shared Context Envelope
    ↑ minimum necessary projection
Local Context B
```

The shared envelope does not become the owner of either local context.

## Shared Context

Shared context may contain:

- task identity;
- common cause;
- destination;
- current shared state;
- agreed definitions;
- relevant evidence;
- handoff status;
- contract version;
- shared constraints;
- required capabilities;
- timing;
- expected outcome;
- next gate;
- exit conditions.

It should exclude unrelated local memory, secrets, private data, internal policy, credentials, and non-transferable authority.

## Separation of Concern

Each participant retains independent control over:

- identity;
- local data;
- internal memory;
- domain models;
- operating procedures;
- tools;
- permissions;
- legal obligations;
- commercial rights;
- security controls;
- recovery;
- audit;
- lifecycle.

```text
Shared Context
    ≠
Shared Ownership
```

```text
Shared Cause
    ≠
Merged Authority
```

## Context Projection

Each participant publishes a bounded projection of its local context.

```text
Local Context
    ↓ policy and purpose filter
Context Projection
    ↓ trusted gate
Shared Context
```

Every projection must declare:

- source;
- purpose;
- recipients;
- fields included;
- fields withheld;
- validity period;
- permitted use;
- onward-sharing rules;
- provenance;
- revocation conditions.

## Canonical Shared Context Envelope

```yaml
apiVersion: fabric.opendata.world/v1alpha1
kind: SharedContext
metadata:
  id: urn:fabric:shared-context:01J...
  version: 1
spec:
  purpose: coordinated-service-recovery
  cause: urn:fabric:cause:service-continuity
  participants:
    - urn:fabric:kube:operations-agent
    - urn:fabric:kube:security-agent
    - urn:fabric:kube:recovery-agent
  shared:
    task: urn:fabric:kube:work:42
    currentState: degraded
    destinationState: healthy
    contract: urn:fabric:contract:recovery:v3
    evidence:
      - urn:fabric:evidence:incident-summary:v2
    constraints:
      - restore-without-data-loss
    nextGate: urn:fabric:gate:recovery-approval
  concerns:
    operations:
      owner: urn:fabric:team:operations
      privateContext: retained-locally
    security:
      owner: urn:fabric:team:security
      privateContext: retained-locally
    recovery:
      owner: urn:fabric:team:recovery
      privateContext: retained-locally
  disclosure:
    minimumNecessary: true
    onwardSharing: prohibited
  validity:
    expiresAt: 2026-06-11T14:00:00Z
status:
  alignment: passed
  responsibilityCoverage: complete
```

## Agent Teams

In a multi-agent team:

- the orchestrator maintains the shared task context;
- specialist agents maintain private domain context;
- each agent receives only the minimum necessary projection;
- every handoff is contract-bound;
- responsibility remains attached to the relevant concern;
- the final outcome is collectively owned.

```text
Shared Task Context
+ Private Specialist Contexts
+ Explicit Interfaces
=
Coherent Multi-Agent Team
```

## Separation of Duties

Separation of concern complements separation of duties.

```text
Concern
    = what a role owns and understands

Duty
    = what a role is authorized to perform
```

A participant may understand shared context without receiving authority to execute another participant’s duty.

## Context at the Gate

Every gate checks:

1. whether the shared context is sufficient;
2. whether disclosure is minimal;
3. whether every concern has an owner;
4. whether authority remains separated;
5. whether local laws and policies permit sharing;
6. whether data rights are preserved;
7. whether the contract covers the exchange;
8. whether the context is current and versioned;
9. whether recipients accept their responsibilities;
10. whether an exit and deletion path exists.

## Federation

Across nations, domains, platforms, or clusters, shared context must be federated rather than centralized by default.

```text
Fabric A Local Context
    ↓ Gate A
Shared Federated Context
    ↓ Gate B
Fabric B Local Context
```

Each member retains sovereignty, jurisdiction, custody, and the Right to Deny.

## Privacy

Shared context follows:

- minimum necessary disclosure;
- purpose limitation;
- selective disclosure;
- local custody;
- time-bound access;
- retention limits;
- revocation;
- correction;
- audit;
- protected evidence.

Shared context must not become unrestricted surveillance or a permanent global memory.

## Reconciliation

The platform continuously compares:

```text
Shared Declared State
        ↕
Participant Observed States
```

Conflicts are surfaced, not silently overwritten.

Each participant remains responsible for reconciling its own concern and publishing an updated projection when required.

## Failure Handling

When shared context becomes stale, contradictory, excessive, or unauthorized:

```text
Close Gate
→ Preserve Evidence
→ Restrict Sharing
→ Notify Concern Owners
→ Reconcile Local Contexts
→ Issue New Shared Context Version
→ Revalidate
```

## Platform Invariants

1. Shared context does not merge ownership or authority.
2. Every concern has a named owner.
3. Only minimum necessary context is shared.
4. Local context and private memory remain locally governed.
5. Every projection is purpose-bound, versioned, expirable, and revocable.
6. Shared understanding does not grant execution rights.
7. Every handoff and context exchange is contract-bound.
8. Separation of duties remains enforced.
9. Conflicts remain visible and attributable.
10. Federation preserves sovereignty, privacy, and lawful exit.
11. Context expiry closes dependent authority by default.
12. Collective outcome ownership does not erase individual concern accountability.

## Foundation Formula

```text
Shared Context
=
Common Purpose
+ Minimum Necessary Facts
+ Shared Contract
+ Current State
+ Provenance
```

```text
Separation of Concern
=
Distinct Ownership
+ Distinct Authority
+ Local Data Boundaries
+ Explicit Interfaces
+ Independent Accountability
```

```text
Coherent Federation
=
Shared Context
+ Separation of Concern
+ Trusted Gates
+ Continuous Reconciliation
```

## Final Statement

> Share enough context to coordinate, but never collapse distinct concerns into one undifferentiated system. Each participant retains its own identity, authority, data, operating model, responsibility, and exit. The shared context connects the work; separation of concern preserves the integrity of the Fabric.
