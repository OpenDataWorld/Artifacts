# AnyDB Foundation Principle: Instruction as Evidence

Status: Normative Foundation Principle

## Principle

> Every instruction that causes a real action must be preserved as evidence.

An instruction is not merely input. It is part of the causal and accountability chain that explains why an agent, operator, tool, model, or system acted.

## Core Rule

> No consequential action without an attributable, contextual, versioned, and preserved instruction.

## Canonical Model

```text
Issuer Identity
    ↓
Instruction
    ↓
Context
    ↓
Contract and Authority
    ↓
Interpretation
    ↓
Validation
    ↓
Action
    ↓
Outcome
    ↓
Evidence
```

## What Must Be Preserved

Every consequential instruction record should include:

- instruction identity
- exact instruction content or integrity-preserving reference
- issuer identity
- accountable owner
- recipient identity
- issue time
- active context
- domain
- operating mode
- contract
- authority scope
- model or procedure version
- interpretation or normalized form
- validation result
- resulting action
- outcome
- provenance
- expiry or revocation state

## Instruction Types

Instructions may include:

- human requests
- policy decisions
- contracts
- workflow commands
- agent handoffs
- operating-model steps
- API calls
- deployment manifests
- recovery commands
- approval or rejection decisions

## Instruction Is Not Authority by Itself

```text
Instruction
    ≠
Permission
```

An instruction becomes executable only when:

```text
Instruction
+ Verified Identity
+ Active Context
+ Valid Contract
+ Sufficient Authority
+ Passed Validation
=
Eligible Action
```

## Exact and Normalized Forms

The system should preserve both:

1. the original instruction as received;
2. the normalized or structured instruction used for execution.

Any transformation between them must remain explainable and versioned.

## Canonical Instruction Evidence Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: InstructionEvidence
metadata:
  id: urn:anydb:instruction:01J...
  version: 1
spec:
  issuer: urn:anydb:identity:human-operator
  recipient: urn:anydb:agent:operations-agent
  issuedAt: 2026-06-11T12:00:00Z
  originalInstruction: urn:anydb:artifact:instruction-source:42
  normalizedInstruction:
    action: execute-approved-procedure
    target: urn:anydb:kube:work:42
  context: urn:anydb:context:production:v5
  contract: urn:anydb:contract:agent-platform:v2
  authority: urn:anydb:authority:bounded-production:v1
  validation:
    identity: passed
    context: passed
    contract: passed
    conformance: passed
  execution:
    actionRecord: urn:anydb:action:42
    outcome: urn:anydb:outcome:42
status:
  integrity: verified
  provenance: complete
  terminal: true
```

## Agent Rule

An agent must not:

- invent an instruction that was never issued;
- alter the original instruction record;
- silently expand the instruction scope;
- treat an ambiguous instruction as production authority;
- omit the instruction from the action evidence chain.

When an instruction is unclear, incomplete, contradictory, expired, or outside scope, the agent must pause, preserve the record, and follow an explicit exit or escalation path.

## Handoffs

Every handoff must preserve:

- the originating instruction;
- completed interpretations and decisions;
- current task state;
- remaining obligations;
- delegated authority;
- destination acceptance.

The receiving operator must know both what was requested and how prior operators interpreted it.

## Corrections

Corrections create new instructions.

```text
Original Instruction
    ↓ remains immutable
Correction Instruction
    ↓
New Forward Action
```

The past is provenance and must not be overwritten.

## Privacy and Selective Disclosure

Sensitive instructions may be protected, but the platform must retain sufficient verifiable evidence to establish:

- that the instruction existed;
- who issued it;
- which contract applied;
- what scope was authorized;
- which action resulted.

## Platform Invariants

1. Every consequential action resolves to an instruction record.
2. Every instruction has an identifiable issuer and recipient.
3. Original and normalized instruction forms are preserved.
4. Instructions are contextual, versioned, expirable, and revocable where applicable.
5. Instruction alone does not grant authority.
6. Every execution validates identity, context, contract, and scope.
7. Handoffs preserve the full instruction lineage.
8. Corrections create new forward instructions.
9. Agents cannot silently reinterpret or expand instructions.
10. Instruction, action, and outcome remain linked through provenance.

## Foundation Formula

```text
Instruction Evidence
=
Issuer
+ Original Instruction
+ Context
+ Contract
+ Interpretation
+ Validation
+ Action
+ Outcome
```

## Final Statement

> Instruction is evidence. Every real action must remain traceable to the exact authorized instruction that caused it, the context in which it was understood, the contract that permitted it, the operator who executed it, and the outcome it produced.
