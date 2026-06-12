# Governance Graph Data Platform Contracts v1

Status: Draft Milestone Contract Set

## Purpose

This contract set turns the Governance Graph from a diagram into an operational data platform fed by real events, real ownership, real contracts, real environments, and real outcomes.

The platform must continuously reconcile:

```text
Declared State
        ↕
Observed State
```

## Contract Families

1. `EntityContract` — canonical identity for every person, organization, agent, platform, tool, provider, environment, artifact, and Kube.
2. `OwnershipContract` — exactly one active owner at every instant.
3. `AuthorityContract` — bounded right to act.
4. `AccountabilityContract` — named duty to answer for consequence.
5. `EnvironmentContract` — registered execution boundary.
6. `KubeContract` — common accountable unit of work, state, evidence, and lifecycle.
7. `GateContract` — deterministic admission, progression, denial, recovery, and exit.
8. `DecisionContract` — context, options, evidence, authority, and outcome.
9. `EvidenceContract` — immutable provenance for instructions, checks, transitions, and results.
10. `ToolLeaseContract` — time-bound, scoped execution capability.
11. `ServiceContract` — platform-held service terms, performance, remedy, and exit.
12. `LifecycleContract` — allowed states and transitions.
13. `HeartbeatContract` — signed proof that an entity remains active, healthy, eligible, and accountable.
14. `TransferContract` — atomic handoff with no dual ownership or unowned transit.
15. `ReconciliationContract` — comparison of declared and observed reality.

## Required Graph Edges

```text
Entity --OWNS--> Kube
Entity --ACCOUNTABLE_FOR--> Kube
Kube --BOUND_BY--> Contract
Kube --RUNS_IN--> Environment
Kube --USES--> ToolLease
Kube --PRODUCES--> Evidence
Decision --AUTHORIZES--> Transition
Gate --VALIDATES--> Transition
Transition --CHANGES--> State
Evidence --PROVES--> Transition
Heartbeat --ATTESTS--> Entity
ServiceContract --GOVERNS--> Delivery
TransferContract --MOVES_OWNERSHIP_OF--> Kube
```

## Global Invariants

1. Every node has a canonical ID, type, owner, version, created time, and lifecycle state.
2. Every consequential edge is contract-bound and evidenced.
3. Every Kube has exactly one active owner.
4. Authority and accountability remain paired digital twins.
5. Unknown, stale, ownerless, unobservable, or expired nodes close progression by default.
6. Every loop has an owner, purpose, maximum duration, exit condition, and terminal state.
7. No transformation may silently alter canonical truth.
8. Every real transition has one eligible committer.
9. Every environment is registered before execution.
10. Every operation is observable and attributable.

## Canonical Envelope

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "apiVersion": "governance.opendata.world/v1",
  "kind": "KubeContract",
  "metadata": {
    "id": "urn:odw:kube:01J...",
    "version": 1,
    "createdAt": "2026-06-11T00:00:00Z",
    "updatedAt": "2026-06-11T00:00:00Z",
    "owner": "urn:odw:entity:owner-01",
    "labels": {}
  },
  "spec": {},
  "status": {
    "state": "proposed",
    "observedAt": "2026-06-11T00:00:00Z"
  }
}
```

## Minimal Event Contract

Every source system emits events in this shape:

```json
{
  "eventId": "urn:odw:event:01J...",
  "eventType": "kube.state.changed",
  "occurredAt": "2026-06-11T00:00:00Z",
  "observedAt": "2026-06-11T00:00:01Z",
  "source": "github|kubernetes|juju|surrealdb|identity|otel|billing|human",
  "actor": "urn:odw:entity:actor-01",
  "subject": "urn:odw:kube:01J...",
  "contract": "urn:odw:contract:01J...",
  "environment": "urn:odw:environment:01J...",
  "previousState": "approved",
  "newState": "executing",
  "evidence": ["urn:odw:evidence:01J..."],
  "correlationId": "urn:odw:correlation:01J...",
  "idempotencyKey": "string"
}
```

## Initial Source Adapters

- GitHub: repositories, commits, PRs, reviews, checks, releases, owners.
- Kubernetes/k0s: clusters, nodes, namespaces, workloads, services, storage, events.
- Juju: controllers, models, applications, units, relations, status.
- SurrealDB: canonical graph nodes, contracts, events, ownership, decisions.
- Identity: users, organizations, agents, roles, credentials, lifecycle.
- OpenTelemetry: traces, logs, metrics, service and resource identity.
- Billing: usage, price, settlement, contributor share, service credits.
- Human gates: approvals, denials, reasons, conflicts, appeals.

## Loop Resolution Contract

A loop is valid only when it declares:

```yaml
owner: urn:odw:entity:owner-01
purpose: reconcile-desired-and-observed-state
maximumDuration: PT15M
maximumIterations: 20
progressMetric: unresolved-drift-count
exitConditions:
  - unresolved-drift-count == 0
  - deadline-reached
terminalStates:
  - completed
  - failed
  - escalated
  - retired
```

Invalid loops are quarantined and escalated.

## First Milestone

```text
M1 — Governance Graph Core

Deliver:
- canonical schemas;
- SurrealDB graph model;
- event ingestion API;
- GitHub adapter;
- Kubernetes/k0s adapter;
- Juju adapter;
- reconciliation engine;
- loop detector;
- ownerless-node detector;
- stale-heartbeat detector;
- governance dashboard;
- evidence export.
```

## Final Statement

> The Governance Graph is the continuously reconciled operational record of who owns what, who may act, who must answer, which contract applies, where execution occurs, what evidence exists, and how every lifecycle loop terminates.
