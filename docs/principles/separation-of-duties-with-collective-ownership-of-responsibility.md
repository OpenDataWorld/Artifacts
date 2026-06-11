# Separation of Duties with Collective Ownership of Responsibility

Status: Normative Foundation Principle

## Principle

> Duties must remain separated, but responsibility for the final outcome is collectively owned by the participating team, platform, and accountable organization.

Separation of duties prevents concentration of power, hidden self-approval, and unreviewed execution. Collective ownership prevents each participant from disclaiming responsibility by pointing to another role.

## Core Rule

> Separate the actions. Share the outcome. Preserve individual accountability at every step.

## Canonical Model

```text
Definition Owner
      ↓
Independent Approver
      ↓
Bounded Executor
      ↓
Quality Validator
      ↓
Compliance Validator
      ↓
Auditor
      ↓
Collectively Owned Outcome
```

## Separation of Duties

High-consequence workflows should separate:

- principle and framework definition
- operating-model definition
- model approval
- capability attestation
- execution
- quality assurance
- compliance validation
- security validation
- settlement
- audit
- incident response
- retirement

```text
Author ≠ Approver
Approver ≠ Executor
Executor ≠ Validator
Validator ≠ Auditor
```

No participant may silently approve or certify its own high-consequence work.

## Collective Ownership

Collective ownership means the team and accountable organization jointly own:

- the promised outcome
- continuity of service
- safety
- quality
- conformance
- evidence completeness
- customer or community impact
- recovery
- remediation
- graceful exit

Collective ownership does not make responsibility anonymous.

## Individual Accountability

Every step must still identify:

- responsible operator
- decision owner
- approving authority
- validation owner
- evidence owner
- recovery owner
- deadline or validity period
- accepted handoff

```text
Collective Responsibility
    ≠
Unassigned Responsibility
```

## Responsibility Matrix

A workflow should declare a responsibility matrix such as:

```text
Responsible
  = performs the work

Accountable
  = owns the outcome and final decision

Consulted
  = provides required domain input

Informed
  = receives state and outcome evidence
```

For agentic systems, each role may be held by a human, agent, team, platform authority, or organization according to its maturity and signed scope.

## Canonical Responsibility Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: CollectiveResponsibility
metadata:
  id: urn:anydb:collective-responsibility:01J...
  version: 1
spec:
  kube: urn:anydb:kube:work:42
  accountableOrganization: urn:anydb:organization:enterprise-01
  roles:
    definitionOwner: urn:anydb:identity:model-owner-01
    approver: urn:anydb:identity:approver-01
    executor: urn:anydb:agent:operations-agent
    qualityValidator: urn:anydb:identity:qa-lead-01
    complianceValidator: urn:anydb:identity:compliance-lead-01
    auditor: urn:anydb:identity:auditor-01
    recoveryOwner: urn:anydb:identity:incident-lead-01
  collectiveObligations:
    - deliver-defined-outcome
    - preserve-provenance
    - recover-on-failure
    - remediate-material-harm
  handoffs:
    acceptanceRequired: true
  evidence:
    - role-attestations
    - approval-records
    - execution-receipts
    - validation-reports
status:
  separationOfDuties: passed
  responsibilityCoverage: complete
```

## Handoff Rule

At every handoff:

```text
Source remains responsible
until
Destination explicitly accepts responsibility and authority
```

A handoff must preserve:

- current state
- active context
- contract
- completed work
- remaining obligations
- evidence
- authority
- next owner
- valid exits

## No Responsibility Fragmentation

The platform must reject or pause when:

- every role claims only partial responsibility and no one owns the outcome
- authority is distributed but accountability is absent
- validation owners are unidentified
- recovery has no accountable owner
- a handoff is sent but not accepted
- collective ownership is used to hide individual error
- individual accountability is used to deny collective obligations

## Agent Teams

For multi-agent teams:

- each agent owns its bounded Kube or step;
- the orchestrator owns coordination within signed scope;
- validators independently verify outputs;
- the platform owns enforcement of the shared contract;
- the human or legal organization owns the real-world outcome.

```text
Agent Step Responsibility
+ Platform Control Responsibility
+ Organizational Outcome Responsibility
=
Complete Responsibility Chain
```

## Failure and Recovery

When a workflow fails:

1. the current operator contains the failure;
2. the recovery owner assumes the recovery contract;
3. validators preserve independent evidence;
4. the accountable organization owns remediation;
5. the team collectively learns and updates the next forward model.

No participant may erase its part of the provenance chain.

## Platform Invariants

1. High-consequence duties remain separated.
2. Every step has one identified responsible operator.
3. Every workflow has one accountable human or legal organization.
4. The participating team collectively owns the promised outcome.
5. Collective ownership never makes accountability anonymous.
6. Individual accountability never removes shared obligations.
7. Handoffs transfer responsibility only after explicit acceptance.
8. Validation and audit remain independent from execution.
9. Every failure has a recovery owner and remediation path.
10. Every decision, action, and transfer preserves durable evidence.

## Foundation Formula

```text
Safe Collective Operation
=
Separated Duties
+ Individual Accountability
+ Collective Outcome Ownership
+ Independent Validation
+ Durable Evidence
```

```text
Complete Responsibility
=
Who Defined
+ Who Approved
+ Who Executed
+ Who Validated
+ Who Audited
+ Who Owns the Outcome
+ Who Recovers
```

## Final Statement

> Separate duties so no actor controls the entire high-consequence path. Assign every step to an identifiable owner. At the same time, make the team, platform, and accountable organization collectively responsible for the final outcome. Responsibility must be distributed without being diluted.
