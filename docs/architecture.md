# Architecture

CQF standardizes the boundary between artifact creation, evaluation, and release authority.

## Role contracts
| Role | Responsibilities |
| --- | --- |
| ProductionContract | Objective, expected artifact, policy version, required checks, spending and approval limits |
| Producer | Produce an artifact and report its immutable digest and version |
| Evaluator | Inspect a scoped artifact with a specified guard version and return evidence |
| QualityGate | Evaluate complete evidence against fixed policy; decide pass, rework, blocked or human review |
| GuardEvolution | Validate proposed guards against representative positive and negative fixtures |
| RuntimeAdapter | Route work, persist states, enforce bounded retries and idempotency without affecting CQF semantics |

## Evidence and gating invariants
- Evidence must reference the exact artifact SHA-256 and guard version; stale evidence is invalid.
- All required blocking guards must run. Missing, FAILED or UNKNOWN results cannot be treated as PASS.
- UNKNOWN can route to human review or block according to the contract.
- An evaluator's verdict is evidence, not proof of absolute correctness.
- Quality policy modifications require independent authority from the producer.
- Approval of irreversible actions and paid operations is separate from artistic acceptance.
- The implementation is responsible for durable job IDs, timeouts, replay protection and audit logs.

## Independent review
The reviewer receives the objective, rubric, reference facts, produced artifact and evidence requirements. It does not receive the creator's internal reasoning, self-justifications or implied assertions of success. Separate sessions reduce contextual contamination but do not guarantee independent judgment.

## Interoperability
Schemas specify wire contracts. No specific language, queue, storage engine, model provider or orchestration library is required.
