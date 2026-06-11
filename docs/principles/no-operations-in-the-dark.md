# No Operations in the Dark

Status: Normative Foundation Principle

## Principle

> No consequential operation may occur in the dark.

Every operation must be attributable, contract-bound, observable, explainable, time-bounded, and connected to an accountable owner, an active instruction, an eligible environment, and a durable evidence trail.

Dark operation includes any action whose identity, authority, purpose, current state, effects, or responsible party cannot be determined by the parties entitled to oversight.

## Core Rule

> No hidden operator. No hidden instruction. No hidden authority. No hidden state transition. No hidden outcome.

## Canonical Model

```text
Instruction
    ↓
Named Operator
    ↓
Active Contract
    ↓
Registered Environment
    ↓
Observable Execution
    ↓
Heartbeat and Telemetry
    ↓
Outcome Evidence
    ↓
Review, Remedy, or Exit
```

## Visibility Requirements

Every consequential operation must expose, to authorized reviewers:

- operation identity;
- Kube identity;
- current owner;
- accountable principal;
- operator identity;
- instruction identity;
- exact contract version;
- active context and jurisdiction;
- environment identity;
- eligibility and ability status;
- start time;
- current state;
- resource use;
- expected terminal state;
- validation results;
- heartbeat status;
- stop, recovery, and exit controls;
- resulting outcome and evidence.

## No Faceless Operations

An operation is invalid when the platform cannot answer:

```text
Who instructed it?
Who approved it?
Who is operating it?
Who owns it?
Who is accountable?
Which contract permits it?
Which environment hosts it?
What state is it in?
How can it be stopped?
```

Pseudonymous participation may be allowed in low-consequence contexts, but the platform must still resolve the accountable principal required by the contract and consequence class.

## No Invisible Authority

Authority must be:

- explicit;
- signed;
- contextual;
- scoped;
- time-bounded;
- revocable;
- connected to accountability.

```text
Authority without visible accountability
=
Invalid authority
```

## No Invisible Execution

Every active operation must emit sufficient telemetry to establish:

- it is alive;
- it is executing the approved procedure;
- it remains within scope;
- its dependencies remain healthy;
- its resource usage remains within limits;
- its output remains conformant;
- recovery remains available.

A silent operation loses consequential authority by default.

## Heartbeat Rule

```text
Valid Operation
=
Active Contract
+ Valid Heartbeat
+ Current Eligibility
+ Observable State
```

When heartbeat expires:

```text
Close Gate
→ Restrict Authority
→ Preserve State
→ Notify Accountable Owner
→ Reconcile
→ Recover, Reattest, or Retire
```

## Instruction as Evidence

Every operation must remain linked to the instruction that caused it.

```text
Instruction
→ Interpretation
→ Validation
→ Action
→ Outcome
```

No operator may invent, expand, or replace the instruction silently.

## Observability Is Not Surveillance

No operations in the dark does not mean unrestricted observation of people or private data.

Observability must follow:

- purpose limitation;
- minimum necessary telemetry;
- selective disclosure;
- role-based access;
- privacy preservation;
- retention limits;
- lawful review;
- protected evidence;
- auditability of those who access the telemetry.

```text
Operational Visibility
    ≠
Unlimited Personal Surveillance
```

## Protected and Classified Operations

Security-sensitive, confidential, or classified operations may restrict who can see details, but they may not eliminate:

- accountable ownership;
- lawful authorization;
- internal oversight;
- evidence preservation;
- expiry;
- independent review where required;
- recovery and terminal state.

Confidentiality limits disclosure. It does not create unaccountable darkness.

## Agent Operations

Every agent operation must expose:

- agent identity and version;
- immutable soul reference;
- native Fabric identity;
- owner and accountable principal;
- active mode;
- operating model;
- current task Kube;
- tools invoked;
- permissions used;
- decisions and uncertainty;
- state changes;
- heartbeat;
- costs and usage;
- completion or failure state.

The agent may keep private reasoning or protected implementation details confidential, but its operational decisions, authority, evidence, and effects must remain reviewable.

## Platform Operations

The platform must itself be observable.

It must preserve evidence for:

- gate decisions;
- eligibility decisions;
- policy changes;
- contract changes;
- identity and ownership changes;
- privilege grants;
- revocations;
- billing and settlement;
- environment changes;
- recovery actions;
- administrator operations.

The platform cannot demand transparency from agents while operating its own control plane invisibly.

## Human at the Wall

For high-consequence work, an authorized human or lawful authority must be able to:

- see the operation’s current state;
- understand the applicable contract;
- inspect evidence;
- challenge or deny progression;
- pause or stop;
- invoke recovery;
- assign review;
- confirm terminal closure.

The human must have real control, not merely receive a report after the outcome.

## Dark-Operation Indicators

The platform must detect and block:

- unknown processes;
- unsigned workloads;
- unregistered environments;
- missing owners;
- expired authority;
- disabled telemetry;
- hidden tool calls;
- unexplained state changes;
- out-of-band administrative access;
- shadow agents;
- unmetered commercial operations;
- unresolved ownership;
- operations without terminal states.

## Gate Check

Every gate validates:

1. named parties;
2. one active owner;
3. accountable principal;
4. instruction evidence;
5. exact contract version;
6. registered environment;
7. eligibility and ability;
8. observability readiness;
9. heartbeat readiness;
10. authorized telemetry access;
11. stop and recovery controls;
12. expiry and terminal state.

If an operation cannot be observed safely and proportionately, it cannot cross into consequential execution.

## Durable Operational Record

Every material operation produces:

- start record;
- instruction record;
- gate decision;
- operator and environment record;
- significant state transitions;
- heartbeat history;
- policy decisions;
- outcome;
- error or incident evidence;
- remedy;
- final terminal state.

The past remains immutable provenance. Corrections create new forward records.

## Platform Invariants

1. No consequential operation occurs without an identifiable operator and accountable principal.
2. Every operation is bound to an exact contract and instruction.
3. Every environment is registered and attested.
4. Every active operation emits signed, expiring heartbeat and sufficient telemetry.
5. Silent, unknown, or unobservable operation closes the gate by default.
6. Confidentiality never erases accountability or lawful oversight.
7. Observability is proportionate and privacy-preserving.
8. Platform control-plane operations are subject to the same visibility requirements.
9. High-consequence operations expose meaningful human stop and recovery controls.
10. Every operation ends in a durable terminal, suspended, recovered, or retired state.

## Foundation Formula

```text
Visible Operation
=
Named Identity
+ Instruction
+ Contract
+ Registered Environment
+ Heartbeat
+ Telemetry
+ Evidence
```

```text
Trusted Operation
=
Visible Operation
+ Eligibility
+ Ability
+ Conformance
+ Accountability
+ Recovery
```

## Final Statement

> No operations in the dark. Every consequential action must have a visible identity, purpose, contract, owner, accountable principal, environment, state, heartbeat, evidence trail, stop control, and terminal outcome. Privacy may protect people and confidentiality may protect sensitive information, but neither may be used to hide authority, execution, consequence, or responsibility.
