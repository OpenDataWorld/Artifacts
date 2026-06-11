# AnyDB Foundation Principle: Rationality Checks Possibility at Every Gate

Status: Normative Foundation Principle

## Principle

> Every gate must test rationality before accepting a claim, model, instruction, transaction, transformation, agent action, or proposed future as possible.

Rationality is the disciplined test of whether a proposal is internally coherent, consistent with known evidence, compatible with Nature's Laws, appropriate to its domain, and proportionate to its intended consequence.

## Core Rule

> Logic opens the possibility space. Rationality decides whether a possibility deserves further evaluation. Evidence, capability, safety, and governance decide whether it may become real.

## Possibility Ladder

```text
Imaginable
   ↓
Logically Coherent
   ↓
Rationally Plausible
   ↓
Compatible with Nature's Laws
   ↓
Technically Feasible
   ↓
Operationally Mature
   ↓
Safe and Lawful
   ↓
Authorized for One Real Step
```

## Rationality Check

A rationality check asks:

- Is the proposal internally consistent?
- Are its assumptions explicit?
- Does the conclusion follow from the stated premises?
- Is it compatible with documented knowledge and trusted sources?
- Does it contradict established observations without sufficient new evidence?
- Is the active domain appropriate?
- Are time, location, units, dimensions, and versions clear?
- Is the proposed cause capable of producing the expected effect?
- Are alternative explanations considered?
- Is uncertainty declared?
- Is the expected value proportionate to cost, risk, and consequence?
- Can the proposal be tested, falsified, measured, or reviewed?

## Rationality Is Not Certainty

A rational possibility may still be wrong.

```text
Rational
    ≠
Proven
```

Rationality establishes that a proposal is coherent enough to test or evaluate. It does not establish truth by itself.

## Rationality and Logic

```text
Logic
=
Formal structure of reasoning

Rationality
=
Contextual application of logic, evidence, assumptions, and consequence
```

A formally valid argument may still be irrational in practice when its premises are false, stale, irrelevant, or incomplete.

## Rationality and Mathematics

Mathematics may express a possibility precisely, but the platform must still verify:

- whether the variables represent real things
- whether units are valid
- whether assumptions hold
- whether the model fits the domain
- whether uncertainty is represented
- whether the result has real-world meaning

## Rationality and Science

Science tests rational explanations against observation and evidence.

```text
Concept
  ↓
Logical Form
  ↓
Rational Hypothesis
  ↓
Scientific Test
  ↓
Evidence
  ↓
Accepted, Revised, or Rejected Explanation
```

## Rationality at Every Gate

Rationality checks apply at:

- identity and claim gates
- knowledge registry admission
- model registration
- simulation creation
- virtual-to-production promotion
- agent planning
- agent tool invocation
- transactions
- domain admission
- partner federation
- research review
- production deployment
- recovery and compensation

## Canonical Rationality Check Envelope

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: RationalityCheck
metadata:
  id: urn:anydb:rationality-check:01J...
  version: 1
spec:
  subject: urn:anydb:proposal:42
  domain: urn:anydb:domain:operations
  assumptions:
    - source-capacity-is-available
    - destination-contract-is-active
  checks:
    internalConsistency: passed
    evidenceCompatibility: passed
    natureCompatibility: passed
    causalPlausibility: passed
    proportionality: passed
    testability: passed
  alternativesConsidered:
    - urn:anydb:proposal:41
  uncertainty: declared
status:
  possibilityState: rationally-plausible
  nextGate: technical-feasibility
```

## Possibility States

```text
incoherent
contradictory
logically-possible
rationally-plausible
scientifically-testable
technically-feasible
operationally-eligible
safe-and-lawful
authorized
rejected
```

## Agent Requirements

Before an AnyAgent proposes or performs an action, it must distinguish:

- what is known
- what is assumed
- what is inferred
- what is simulated
- what is uncertain
- what is prohibited

An agent must not convert a merely imaginable possibility into a production command.

## High-Consequence Rationality

The higher the consequence, the stronger the rationality check.

High-consequence proposals require:

- documented sources
- multiple perspectives
- alternative explanations
- explicit uncertainty
- independent review
- domain expertise
- human approval where required
- measurable stop conditions

## Rationality and Belief

Belief may inspire a possibility, but shared action requires rational explanation, lawful authority, and evidence appropriate to the consequence.

## Rationality and Protected IP

A protected model or scoring method may remain confidential, but it must still provide enough information to evaluate:

- inputs
- output meaning
- assumptions
- limitations
- evidence class
- decision scope
- review path

## Failure Behavior

When rationality cannot be established, the gate must:

```text
Pause
→ Mark Assumptions and Unknowns
→ Request Evidence or Review
→ Simulate or Test Safely
→ Re-evaluate
```

It must not fabricate certainty.

## Platform Invariants

1. Every possibility passes a rationality check before real-world promotion.
2. Rationality is distinct from truth and certainty.
3. Assumptions remain explicit.
4. Logic, evidence, domain, and consequence are evaluated together.
5. Nature's Laws remain binding.
6. Alternatives and uncertainty are considered where material.
7. High-consequence actions require stronger review.
8. Agents cannot promote imagination directly into production.
9. Failed rationality checks result in containment or further testing.
10. Only rational, feasible, mature, safe, lawful, and authorized possibilities may become real actions.

## Foundation Formula

```text
Rational Possibility
=
Logical Coherence
+ Explicit Assumptions
+ Evidence Compatibility
+ Causal Plausibility
+ Domain Fit
+ Proportionality
```

```text
Real-World Eligibility
=
Rational Possibility
+ Technical Feasibility
+ Capability Maturity
+ Safety
+ Law
+ Contract
```

## Final Statement

> Every gate checks sanity, clarity, and rationality. Sanity establishes coherence. Clarity establishes understandable intent. Rationality establishes whether the proposal is a plausible possibility. Only then may evidence, capability, maturity, safety, law, and contract determine whether one forward step may enter the real world.
