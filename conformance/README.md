# Conformance requirements (v0.1 draft)

A compliant implementation must show that:
1. Each contract and evidence payload validates against the specified versioned JSON Schema.
2. Required evaluations are bound to the same artifact digest and policy version.
3. Missing required checks, FAIL and UNKNOWN do not silently produce PASS.
4. A guard cannot be ENFORCED without evidence that positive and negative fixtures were evaluated.
5. Evaluation identity and version are preserved, and revised evaluators are recalibrated.
6. Producer and quality-policy-approval authority are separated.
7. Duplicate callbacks and bounded retries cannot silently re-execute irreversible or paid operations.
8. Evidence, superseded rules and decisions can be traced without exposing unrelated data.

This repository provides the interface and checklist only. It does not contain an executable evaluator, reference producer or real project fixtures.
