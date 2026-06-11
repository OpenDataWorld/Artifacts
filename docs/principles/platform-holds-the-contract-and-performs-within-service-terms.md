# Platform Holds the Contract and Performs Within Service Terms

Status: Normative Foundation Principle

## Principle

> The platform holds the contract, protects the declared reality, and ensures performance only within the explicit terms of service it has accepted.

The platform does not guarantee every possible outcome, every external dependency, every user expectation, or every condition outside the contract. Its responsibility is to preserve the integrity of the contracted reality and to deliver, measure, explain, recover, and account for performance within the agreed scope.

## Core Rule

> Protect only the reality defined by the contract. Guarantee only the performance promised by the service terms. Make every limit, dependency, exclusion, and remedy explicit.

## Canonical Model

```text
Declared Reality
    ↓
Platform Contract
    ↓
Service Terms
    ↓
Eligibility and Ability
    ↓
Bounded Delivery
    ↓
Measured Performance
    ↓
Evidence, Remedy, Renewal, or Exit
```

## Platform as Contract Holder

The platform must hold or reference the authoritative contract governing:

- the service identity;
- the customer, user, organization, or public principal;
- the accountable platform owner;
- the supported environment;
- the accepted workload;
- the operating model;
- the service boundaries;
- the performance commitments;
- the obligations of each party;
- the exclusions;
- the validity period;
- the remedy and exit path.

The platform may delegate execution, hosting, support, or validation, but it may not delegate away the accountability attached to the contract it holds.

## Declared Reality

The contract must define the reality the platform is responsible for protecting, including:

- registered identities;
- registered environments;
- approved software and agents;
- accepted data boundaries;
- current state;
- intended service state;
- dependencies;
- jurisdiction;
- consequence class;
- accepted risk;
- recovery objectives;
- terminal conditions.

```text
Protected Reality
=
What the Contract Explicitly Defines
```

Unknown, unregistered, unowned, expired, or out-of-scope entities do not silently become platform obligations.

## Service Terms

The service terms must explicitly state:

- service description;
- supported use cases;
- operating hours where applicable;
- availability target;
- latency or throughput target;
- capacity limits;
- data durability commitments;
- security controls;
- privacy commitments;
- support level;
- incident response;
- recovery time and recovery point objectives;
- maintenance windows;
- metering and pricing;
- customer obligations;
- external dependencies;
- exclusions;
- credits, remediation, or other remedies;
- suspension, termination, and exit.

## Performance Within Terms

```text
Performance Obligation
=
Declared Metric
+ Defined Scope
+ Measurement Method
+ Time Window
+ Accepted Dependencies
+ Remedy
```

The platform must not claim vague or unlimited performance.

It must report whether the service is:

```text
within-terms
within-terms-with-conditions
degraded-but-within-accepted-tolerance
out-of-terms
suspended
recovering
expired
```

## No Implied Universal Guarantee

```text
Platform Contract
    ≠
Guarantee of All Possible Outcomes
```

The platform is not automatically responsible for:

- unregistered environments;
- unsupported versions;
- unauthorized changes;
- out-of-contract workloads;
- undisclosed dependencies;
- external events expressly excluded by the contract;
- user actions beyond delegated authority;
- third-party failures outside accepted responsibility;
- consequences outside the declared service boundary.

Exclusions must be clear, lawful, proportionate, and reviewable. They cannot be used to hide negligence, nonconformance, or obligations imposed by law.

## Reality Protection

Protecting reality means preserving:

- identity integrity;
- contract integrity;
- state integrity;
- ownership and accountability;
- provenance;
- data boundaries;
- instruction lineage;
- service continuity;
- recovery evidence;
- lawful rights and remedies.

The platform must continuously reconcile:

```text
Contracted State
        ↕
Observed State
```

Material drift triggers restriction, remediation, renegotiation, or exit.

## Platform Eligibility

Before accepting a service obligation, the platform must verify:

- the environment is registered;
- the software is compatible;
- the implementation is conformant;
- the capability is native or can be reconstructed natively;
- the agent is eligible and able;
- the production system is mature enough;
- responsibilities are assigned;
- conflicts of interest are cleared;
- recovery is feasible;
- the requested service terms are achievable.

The platform must not sign a contract it cannot reasonably perform.

## Shared Responsibility

The contract must distinguish:

```text
Platform Responsibilities
Customer or Principal Responsibilities
Provider Responsibilities
Agent Responsibilities
Statutory Responsibilities
```

Shared responsibility does not mean unclear responsibility. Every obligation must have one identified owner at every point in time.

## Single Ownership and Accountability

For every service interval, the contract identifies:

- one active service owner;
- one accountable principal;
- responsible operators;
- independent validators where required;
- recovery owner;
- valid-from and valid-until times.

No faceless transaction, unowned service, or dual active ownership is permitted.

## Changes to Service Terms

A material change creates a new contract version.

```text
Service Contract v1
    ↓ proposal, review, acceptance
Service Contract v2
```

The platform must not silently change:

- scope;
- price;
- performance commitments;
- data use;
- ownership;
- rights;
- liability;
- recovery objectives;
- termination terms.

## Service-Term Gate

Before execution, the gate checks:

1. exact contract identity and version;
2. named parties;
3. registered environment;
4. supported software and agent versions;
5. eligibility and ability;
6. service scope;
7. performance ceiling;
8. capacity and dependency state;
9. data and jurisdiction boundaries;
10. ownership and accountability;
11. metering and commercial authorization;
12. recovery and remedy;
13. expiry and exit.

## Service Evidence

Every material service action preserves:

- instruction;
- contract version;
- operator;
- environment;
- observed performance;
- dependency state;
- incident state;
- evidence;
- remedy;
- resulting state.

## Failure and Remedy

When performance falls outside the service terms:

```text
Detect
→ Preserve Evidence
→ Notify Accountable Parties
→ Restrict or Stabilize
→ Recover
→ Apply Contracted Remedy
→ Reconcile
→ Renew, Amend, or Exit
```

The remedy may include:

- restoration;
- service credit;
- refund;
- corrective action;
- workload migration;
- provider replacement;
- contract amendment;
- termination;
- lawful compensation where applicable.

## Platform Invariants

1. The platform holds the authoritative service contract.
2. The platform protects only the reality explicitly defined by that contract and applicable law.
3. Performance obligations are limited to explicit, measurable service terms.
4. Every service has named parties, one active owner, and one accountable principal.
5. The platform must verify feasibility before accepting the contract.
6. Unsupported or out-of-scope operation does not silently become an obligation.
7. Exclusions cannot hide negligence, unlawful conduct, or known nonconformance.
8. Every material change creates a new contract version.
9. Performance is continuously measured against the contracted state.
10. Failure outside terms triggers evidence, remedy, recovery, renegotiation, or exit.
11. Delegation does not erase the platform’s contractual accountability.
12. Rights, privacy, provenance, and lawful remedies remain protected.

## Foundation Formula

```text
Platform Responsibility
=
Contracted Reality
+ Explicit Service Terms
+ Measured Performance
+ Evidence
+ Remedy
```

```text
Valid Service Commitment
=
Defined Scope
+ Demonstrated Ability
+ Registered Environment
+ Assigned Accountability
+ Achievable Performance Terms
+ Exit Path
```

## Final Statement

> The platform holds the contract. It protects the reality that the contract defines and ensures performance only within the exact service terms it has accepted. It must make scope, limits, dependencies, ownership, accountability, measurement, remedy, and exit explicit. Trust comes from delivering the promised service faithfully—not from claiming responsibility for an undefined world.
