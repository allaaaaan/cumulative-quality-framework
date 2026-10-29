# Finding-to-guard lifecycle

1. **Observe** — record a finding against the exact artifact revision and evidence.
2. **Triage** — classify new defect, escaped regression, suggestion or unknown.
3. **Propose** — define a scoped guard, evaluator method and expected failure handling.
4. **Calibrate** — assess negative fixtures (known failures), positive fixtures (accepted samples), and unseen edge cases.
5. **Validate** — record effectiveness, false-positive limitations and evaluator revision.
6. **Enforce** — promote only after an authorized review of the proposed rule.
7. **Monitor** — track later escapes and evaluator regressions.
8. **Retire / revise** — preserve history; version changes rather than deleting a previous rule.

Valid guard statuses: `proposed`, `validated`, `enforced`, `retired`.

Three evaluation modes:
- **deterministic** — exact structural or computational assertions;
- **semantic** — interpretation requiring a qualified evaluator;
- **perceptual** — subjective or sensory judgment requiring calibration and sometimes human arbitration.

The goal is enforceable process and measurable improvement, **not a promise that judgments will never be wrong**. Every evaluation must retain PASS, FAIL or UNKNOWN distinctly.
