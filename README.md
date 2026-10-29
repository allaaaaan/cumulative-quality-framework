# Cumulative Quality Framework (CQF)

**A portable, interface-only specification for preventing recurring defects in AI-produced work.**

Feedback stored only as prompt text or notes can be forgotten or bypassed. CQF defines a protocol that converts observed defects into versioned, calibrated regression guards and evidence-backed release decisions, regardless of the producer, evaluator or workflow engine.

## Interfaces
- **ProductionContract** — artifact kind, objective, limits and mandatory policy.
- **Producer** — produces a versioned artifact; does not grant its own release permission.
- **Artifact** — immutable identity, revision, location and content digest.
- **QualityGuard** — applicable scope, validation method, positive/negative fixtures and enforcement status.
- **Evaluator** — returns PASS, FAIL or UNKNOWN with traceable evidence.
- **QualityGate** — deterministic decision based on required evidence and frozen policy.
- **Finding** — observed defect or uncertain outcome bound to the evaluated revision.
- **GuardEvolution** — proposal, fixture validation, approval, enforcement and retirement.

```text
Contract -> Producer -> Artifact -> Evaluator -> QualityGate -> Release / Rework
                                              ^
Finding -> Guard Proposal -> Calibration -> Enforced Guard
```

## Why this is different
CQF is **not** an agent runtime, workflow orchestrator, model evaluation service or observability platform.

| Existing tooling | Primary function | CQF's interface-level concern |
| --- | --- | --- |
| LangGraph / CrewAI | Coordinate execution roles | Independent acceptance and artifact-bound review |
| n8n / Temporal | Execute and recover workflows | Portable, mandatory quality gate evidence |
| Promptfoo / DeepEval | Execute evaluations | Scoped promotion of verified findings into enforced rules |
| Opik / Phoenix | Track experiments and evaluation results | Cross-run regression policy and authority boundaries |
| A2A / MCP | Exchange tasks and tool calls | Evidence and approval requirements for release |

These products can implement or complement parts of CQF; no exclusive novelty claim is made. See [related work](docs/related-work.md).

## Non-negotiable rules
1. Deterministic workflow control does not make subjective judgments deterministic.
2. Required missing evaluations and UNKNOWN outcomes **never silently PASS**.
3. Guards must be tested against accepted and rejected fixtures before enforcement.
4. Evaluators get relevant objective facts and artifact content, not the producer's self-approval.
5. Producer and policy-approver authority remain separate.
6. Policies and evidence are versioned and bound to exact artifact digests.
7. This specification contains **no implementation or real-world project material**.

## Structure
- [Architecture](docs/architecture.md)
- [Guard lifecycle](docs/quality-lifecycle.md)
- [Privacy boundary](docs/privacy-boundary.md)
- [Related tools](docs/related-work.md)
- [Schemas](schemas/) — Draft 2020-12 JSON Schema wire contracts
- [Conformance](conformance/README.md) — behavioral requirements, not executable production code

**Status: initial draft (v0.1).** No runtime, evaluator, model, domain plugin, live fixture or service is included. License not yet selected; public visibility alone does not grant an open-source license.
