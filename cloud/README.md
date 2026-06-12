# OpenDataWorld Cloud

A local-first, industry-native, hybrid cloud foundation governed by the Governance Graph.

## Architecture

```text
GitHub / k0s / Juju / Identity / OpenTelemetry / Billing
                         ↓
                    Event Gateway
                         ↓
                    Governance Graph
                         ↓
             Reconciliation and Loop Control
                         ↓
             Policy, Dashboard, Evidence Export
```

## Components

- `apps/event-gateway` — receives normalized governance events.
- `apps/reconciler` — compares declared and observed state.
- `packages/contracts` — versioned contract schemas.
- `packages/graph` — SurrealDB schema and queries.
- `adapters/github` — repository, commit, PR, review, check, and release ingestion.
- `adapters/kubernetes` — cluster, node, workload, service, storage, and event ingestion.
- `adapters/juju` — controller, model, application, unit, relation, and status ingestion.
- `deploy/kubernetes` — k0s-compatible deployment manifests.

## Core Invariants

1. Every consequential entity has a canonical ID and one active owner.
2. Every transition is contract-bound and evidenced.
3. Authority and accountability are paired.
4. Every environment is registered before execution.
5. Every loop has a maximum duration, progress metric, exit condition, and terminal state.
6. No operation runs in the dark.
7. Providers, tools, models, and infrastructure remain replaceable.

## Initial Milestone

```text
M1 — Governance Graph Core

[ ] Event gateway
[ ] SurrealDB schema
[ ] GitHub adapter
[ ] Kubernetes adapter
[ ] Juju adapter
[ ] Reconciliation engine
[ ] Loop detector
[ ] Ownerless-node detector
[ ] Stale-heartbeat detector
[ ] Governance dashboard
[ ] Evidence export
```

## Local-first deployment

The first deployment target is the existing k0s cluster. External cloud providers are extensions, not the sovereign core.
