# AnyDB Principle: ML Libraries as Intelligence Providers

Status: Normative Principle

## Principle

> Machine-learning libraries provide intelligence capabilities to AnyDB, but they do not own the data, identity, policy, memory, model lifecycle, or platform contract.

AnyDB treats ML libraries as replaceable intelligence providers operating over governed entities, events, features, artifacts, and projections.

## Architectural Position

```text
Governed AnyDB Data
        |
        v
Feature and Context Views
        |
        v
ML Library / Model Provider
        |
        v
Inference or Training Result
        |
        v
Evidence + Evaluation + Event
        |
        v
Reconciliation and Trust
```

ML capability is a surface of the platform, not the platform itself.

## Intelligence Providers

Possible providers include:

- PyTorch
- TensorFlow
- JAX
- scikit-learn
- XGBoost
- LightGBM
- ONNX Runtime
- llama.cpp
- vLLM
- local or remote model runtimes

Any one provider may be preferred for a workload, but no library becomes a mandatory AnyDB dependency unless a deployment profile explicitly requires it.

## Core Separation

AnyDB separates:

```text
Data          -> governed source truth
Features      -> versioned derivations
Models        -> versioned artifacts
Libraries     -> execution providers
Inference     -> recorded decisions or observations
Evaluation    -> measurable evidence
Policy        -> execution constraints
Reconciliation -> verified operational outcome
```

This separation prevents model and library choices from becoming irreversible architecture decisions.

## Model as Artifact

Every model used by AnyDB should be registered as a versioned artifact.

Recommended metadata:

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: ModelArtifact
metadata:
  id: urn:anydb:model:fraud-classifier:3
  owner: urn:anydb:organization:opendataworld
  version: 3.0.0
spec:
  task: classification
  framework: pytorch
  format: onnx
  trainingDataset: urn:anydb:dataset:fraud-training:12
  featureSet: urn:anydb:featureset:fraud:v5
  evaluation: urn:anydb:evaluation:fraud-model:3
  policy: urn:anydb:policy:model-execution:v2
status:
  lifecycle: approved
  digest: sha256:...
  provenance: []
```

The portable model format should be preferred over framework-specific serialization when practical.

## Feature Contract

ML libraries must consume features through versioned contracts rather than undocumented dataframe shapes.

Each feature should preserve:

- canonical entity identity
- feature name and version
- event or source lineage
- computation time
- valid time
- transformation identity
- missing-value semantics
- authorization context

This makes training, serving, replay, and audit comparable.

## Training Contract

A training run should record:

- model identity
- library and version
- code artifact and digest
- dataset versions
- feature versions
- parameters
- random seeds where applicable
- runtime environment
- hardware profile
- metrics
- evaluator identity
- policy decision
- output artifact digest

Training must produce a reproducible evidence trail even when exact numerical reproducibility is not possible across hardware or providers.

## Inference Contract

An inference request should include:

- model identity and version
- caller identity
- subject or input entity identities
- feature or context versions
- purpose
- policy context
- requested latency and quality profile
- correlation and causation IDs

An inference result should include:

- output
- confidence or score where meaningful
- model version
- provider and runtime version
- input lineage
- execution time
- policy decision
- evaluation or guardrail results
- evidence references

## Intelligence Is Not Authority

A model output is a proposal, observation, ranking, prediction, or generated artifact.

It does not automatically become authoritative state.

```text
Inference
   |
   v
Proposed Decision
   |
   v
Policy + Constraints + Approval
   |
   v
Command
   |
   v
Execution
   |
   v
Verified Outcome
```

High-consequence actions must pass through governed command and reconciliation flows.

## Library Portability

A workload should be portable between compatible providers when the model and semantics allow it.

Examples:

```text
PyTorch Training -> ONNX Artifact -> ONNX Runtime Serving
scikit-learn -> ONNX -> Edge Runtime
Transformer Weights -> llama.cpp or vLLM Provider
```

Provider-specific optimizations are allowed, but they must be declared as extensions rather than hidden in the core contract.

## Provider Declaration

Each intelligence provider should publish capabilities such as:

```yaml
apiVersion: anydb.opendata.world/v1alpha1
kind: IntelligenceProvider
metadata:
  name: onnx-runtime
spec:
  modes:
    - inference
  formats:
    - onnx
  hardware:
    - cpu
    - cuda
  deploymentModes:
    - embedded
    - edge
    - kubernetes
  supports:
    batching: true
    streaming: false
    deterministicMode: partial
```

## Agent-Native Use

Agents may invoke intelligence providers for:

- classification
- extraction
- prediction
- ranking
- summarization
- generation
- anomaly detection
- planning assistance

The agent must receive the model result together with provenance, confidence, policy, and freshness—not as an unexplained answer.

## Edge-Native Intelligence

AnyDB should support local inference at the edge when privacy, latency, resilience, or sovereignty requires it.

```text
Central Model Policy
        |
        v
Signed Model Artifact
        |
        v
Edge Intelligence Provider
        |
        v
Local Inference
        |
        v
Evidence + Outcome Event
        |
        v
Central Reconciliation
```

The edge must be able to verify model artifact identity and policy before execution.

## Cloud-Native Intelligence

In Kubernetes environments, intelligence providers should be independently deployable and observable.

Recommended properties:

- OCI-packaged runtime or model artifacts
- declarative deployment
- horizontal scaling
- health and readiness checks
- resource limits
- workload identity
- OpenTelemetry-compatible telemetry
- policy-controlled model loading
- signed supply-chain artifacts

## Evaluation as a First-Class Artifact

Every production model should have an evaluation artifact that records:

- benchmark dataset
- metrics
- thresholds
- safety tests
- bias or fairness checks where applicable
- robustness tests
- latency and cost
- evaluator version
- approval decision

Evaluation results must be versioned with the model and deployment profile.

## Drift and Reconciliation

AnyDB should reconcile intelligence continuously.

Examples:

- input feature drift
- output distribution drift
- quality degradation
- stale model deployment
- provider mismatch
- failed model signature verification
- training-serving skew
- policy changes

Possible outcomes:

```text
continue
warn
route-to-alternate-provider
rollback
require-human-review
suspend-model
retrain
```

## No Vendor Lock-In

The intelligence plane must preserve an exit path.

A provider integration is incomplete until the platform can export or retain:

- model artifacts
- schemas
- feature definitions
- training metadata
- evaluations
- inference history
- policy references
- provenance

Hosted APIs may be used, but canonical platform state must not exist only inside the provider.

## Security

ML libraries and model artifacts are part of the software supply chain.

Controls should include:

- dependency scanning
- model digest verification
- artifact signing
- restricted model loading
- sandboxed execution where appropriate
- secret isolation
- input validation
- output filtering
- resource quotas
- audit events

## Licensing

AnyDB must track licenses for:

- ML libraries
- model weights
- datasets
- generated artifacts
- runtime providers

A technically portable model is not commercially portable when its license prevents the intended use.

## Repository Surface

The existing `feature-store-as-a-service` repository becomes the initial **AnyDB Intelligence Surface** for:

- features
- model artifacts
- training and inference contracts
- evaluation
- provider adapters
- drift monitoring

A future canonical name may be:

```text
anydb-intelligence
```

The name should change only after the surface contract stabilizes.

## Platform Invariants

1. ML libraries are providers, not sources of truth.
2. Models are versioned artifacts.
3. Features preserve point-in-time lineage.
4. Inference results identify model and provider versions.
5. Model output does not bypass policy or approval.
6. High-consequence effects are verified through reconciliation.
7. Evaluation is required for production promotion.
8. Edge inference preserves artifact identity and evidence.
9. Intelligence providers remain replaceable.
10. Data and governance remain owned by the AnyDB platform.

## Final Invariant

> AnyDB supplies governed memory and context; ML libraries supply replaceable intelligence; The Fabric governs action; the edge verifies the outcome.
