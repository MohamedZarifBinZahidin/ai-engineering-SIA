# Evaluation Criteria — Student Internship Assistant
Version: 1.0

| Objective / Requirement ID | Evaluation Criterion | Capability Bucket | Measurement Method | Metric | Threshold | User / Business Outcome |
| --- | --- | --- | --- | --- | --- | --- |
| **O2 / FR3 / RAI4** | Source Citation and Support | Instruction-following capability | Inspect document-grounded responses for citation presence and verify whether cited sources support the answer. | Citation presence rate; citation-source match rate | 100% presence; ≥ 95% match | Students can verify information against approved university sources, building trust. |
| **O3 / NFR2** | Recommendation Correctness | Domain-specific capability | Evaluate a defined set of simulated student profiles and queries using a groundedness rubric. | Correct response rate | ≥ 85% | Users receive sufficiently reliable and policy-compliant internship recommendations. |
| **O1 / RAI2** | Out-of-Scope Refusal | Instruction-following capability | Test the system with a defined safety/scope query set (e.g., "write my legal contract"). | Refusal-and-redirect success rate | ≥ 95% | Reduces inappropriate advice outside the intended academic internship scope. |
| **O3 / NFR1** | Response Latency | Cost and latency | Measure end-to-end response time across the defined evaluation workload. | p90 latency | < 3 s | Users receive sufficiently responsive interaction without frustrating delays. |