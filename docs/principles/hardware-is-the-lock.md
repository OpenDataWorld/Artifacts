# Hardware Is the Lock

Status: Normative Foundation Principle

## Principle

> Hardware is the final lock on digital execution.

Software may propose. Policy may authorize. The platform may attest. The kernel may schedule. But the registered physical substrate is the final boundary that permits, contains, measures, and stops real execution.

Hardware is where digital intention meets physical reality.

## Core Rule

> Identity provides the key. The contract defines the permitted use. Policy checks the key. The kernel turns it. Hardware is the lock.

## Canonical Model

```text
Instruction
    ↓
Identity + Contract
    ↓
Compliance + Conformance
    ↓
Platform Attestation
    ↓
Metal-Native Kernel
    ↓
Registered Hardware Lock
    ↓
Bounded Physical Execution
    ↓
Measured Evidence
```

## Hardware as Reality Boundary

The hardware layer establishes the real limits of:

- computation;
- memory;
- storage;
- networking;
- acceleration;
- sensing;
- actuation;
- power;
- timing;
- physical location;
- failure;
- shutdown.

```text
Hardware Reality
=
What Can Actually Execute
within Measured Physical Limits
```

No software declaration can create physical capability that the substrate does not possess.

## The Lock Model

```text
Owner
    = owns the lock or its lawful use

Identity
    = identifies the key holder

Contract
    = defines when and how the key may be used

Policy
    = checks whether use is permitted

Kernel
    = mediates the requested operation

Hardware
    = enforces the final physical boundary
```

The lock must never open merely because a request reached it.

## Registered Hardware

Every consequential hardware substrate must register with the platform and declare:

- canonical identity;
- owner and accountable principal;
- manufacturer and model;
- processor architecture;
- firmware;
- trusted boot capabilities;
- memory;
- storage;
- network interfaces;
- accelerators;
- sensors and actuators;
- physical or logical location;
- jurisdiction;
- drivers;
- measurable limits;
- health and heartbeat;
- recovery and retirement.

Unknown hardware remains ineligible by default.

## Metal-Native Kernel

The kernel is the trusted mediator between software contracts and hardware capability.

It must provide:

- verified boot where available;
- process and memory isolation;
- device mediation;
- resource accounting;
- driver control;
- privilege separation;
- observability;
- deterministic interfaces for consequential operations;
- emergency stop and recovery;
- signed state and health evidence.

```text
Metal-Native Kernel
=
Stable Mediation Contract
between Fabric and Hardware
```

## Hardware-Native Capability

A workload becomes hardware-native only after the platform validates:

- architecture compatibility;
- driver eligibility;
- resource requirements;
- timing requirements;
- device access;
- security boundaries;
- thermal and power limits;
- expected failure modes;
- recovery behaviour;
- measured performance.

Simulation may test logic. Emulation may test expected behaviour. Hardware validation establishes real execution fitness.

## Root of Trust

Where supported, hardware-backed roots of trust may protect:

- device identity;
- boot integrity;
- signing keys;
- workload attestation;
- sealed secrets;
- measured launch;
- tamper evidence;
- trusted time or monotonic counters.

A hardware root of trust supports assurance, but it does not create ownership or universal authority.

```text
Hardware Attestation
    = evidence of substrate state
not
permission to perform every action
```

## Physical Consequence

For actions affecting physical systems, infrastructure, people, property, or irreversible state, the hardware lock must require:

- exact instruction;
- active contract;
- named owner;
- accountable principal;
- approved operating model;
- current eligibility and ability;
- consequence classification;
- required human authorization;
- bounded tool or device lease;
- stop and recovery controls.

## Hardware Does Not Own the Work

```text
Hardware Custody
    ≠ Ownership of Data

Hardware Execution
    ≠ Ownership of Outcome

Hardware Provider
    ≠ Owner of the Realm
```

The hardware provider may supply and maintain the substrate. Ownership of the Kube, data product, model, contract, and resulting work remains explicitly assigned elsewhere.

## One Eligible Committer

Many systems may simulate, recommend, validate, and coordinate.

For one real physical state transition, only one eligible hardware-bound execution Kube may hold the active commit lease.

```text
Many Proposals
+ Many Validators
+ One Hardware-Bound Committer
=
One Durable Physical Outcome
```

Replication and redundancy must not create simultaneous conflicting physical authority.

## Hardware Heartbeat

Every active substrate should emit signed, expiring evidence of:

- hardware identity;
- firmware and kernel state;
- driver state;
- resource health;
- temperature and power where relevant;
- security-module state;
- active leases;
- current consequence ceiling;
- recovery readiness;
- last reconciliation time.

A stale or invalid heartbeat closes consequential execution by default.

## Emergency Stop

Every consequential hardware path must provide a real stop mechanism appropriate to its consequence class.

The stop path must be:

- independently reachable;
- tested;
- observable;
- attributable;
- protected from the workload it may need to stop;
- connected to recovery and investigation.

A software-only stop is insufficient where the software itself may be compromised.

## Hardware Ownership Transfer

Hardware ownership or custody changes must follow explicit transfer contracts.

Time, hosting, maintenance, possession, dependency, or physical access do not silently transfer ownership.

At every instant:

```text
Active Hardware Owner = 1
```

Custodian, operator, maintainer, and owner remain separate roles.

## Edge and Home Environments

In a trusted home, local laboratory, workshop, enterprise edge, or community node, hardware provides the local sovereignty boundary.

The platform may deliver sealed boxes, contracts, tools, and updates to the gate. It does not gain general access to the user’s hardware or private environment.

```text
Home Hardware
    = local execution lock

Platform
    = contract and coordination layer
```

## Cloud Relationship

Cloud infrastructure is capable because it controls large registered hardware estates.

Its guardian role remains bounded:

```text
Cloud
    = manages and protects eligible hardware capability

Realm Owner
    = owns the workload, data, and purpose

Platform
    = holds the service contract
```

The cloud cannot gain ownership through hardware custody, hosting duration, or operational dependency.

## No Operations in the Dark

Every consequential hardware action must preserve:

- instruction;
- actor;
- owner;
- accountable principal;
- contract;
- kernel and driver versions;
- hardware identity;
- active lease;
- measured operation;
- outcome;
- stop, recovery, and terminal state.

## Platform Responsibilities

The platform must:

- register hardware, firmware, kernels, and drivers;
- verify compatibility and conformance;
- assign hardware consequence ceilings;
- bind device access to short-lived leases;
- validate attestation and heartbeat;
- enforce one eligible committer;
- preserve ownership and accountability;
- provide emergency stop, recovery, migration, and retirement;
- block unknown, stale, compromised, or unobservable substrates.

## Platform Invariants

1. Hardware is the final physical execution lock.
2. Every consequential substrate is registered and attested.
3. Identity, contract, policy, and kernel mediation are required before the lock opens.
4. Hardware capability never creates ownership or universal authority.
5. Every real state transition has one eligible hardware-bound committer.
6. Device access is scoped, leased, expiring, and revocable.
7. Stale heartbeat or failed attestation closes consequential execution.
8. Physical consequence requires real stop and recovery controls.
9. Ownership, custody, operation, and maintenance remain distinct.
10. Every hardware action is observable, attributable, and evidenced.

## Foundation Formula

```text
Trusted Physical Execution
=
Identity
+ Contract
+ Policy
+ Metal-Native Kernel
+ Registered Hardware Lock
+ Evidence
```

```text
Hardware Lock
=
Known Physical Capability
+ Bounded Access
+ Measured State
+ Real Stop Control
```

## Final Statement

> Hardware is the lock because it is the final boundary between digital intention and physical consequence. Identity supplies the key, the contract defines its permitted use, policy validates it, and the metal-native kernel turns it. The registered substrate opens only for bounded, accountable execution and must always be able to measure, contain, stop, and prove what occurred.
