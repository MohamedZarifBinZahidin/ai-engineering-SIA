# Architecture Decisions & Traceability — Student Internship Assistant
Version: 1.0

## Step C2: Architecture Needs from Requirements

| Requirement ID | What does the requirement need? | Architecture Response |
| --- | --- | --- |
| **FR3 / RAI4** | Answers must include verifiable source references. | Knowledge Source (Vector Database) + RAG retrieval pipeline. |
| **RAI2** | Out-of-scope queries must be refused. | Scope / Safety Control (Guardrail or prompt-based classifier). |
| **NFR2** | Academic answers must meet the defined correctness threshold. | Grounded generation via RAG, preventing reliance on base model parametric memory. |
| **RAI3** | Student PII must not be transmitted to external APIs. | PII Redaction / Anonymization component before the LLM API call. |

---

## Step C3: V1 Conceptual Architecture Description
*(Use this description to draw your diagram in Draw.io)*

![diagram should be here](SIA_Diagram_1.png)

1. **User (Student)**: Initiates the query via a chat interface.
2. **AI Application Interface**: Receives the input and routes it to the safety control.
3. **Scope / Safety Control**: Checks if the query is within the internship advising domain. If not, returns a polite refusal/redirect.
4. **PII Redaction Component**: Scans and masks any sensitive student data (e.g., student ID, phone number) before external transmission.
5. **AI Capability (LLM Service)**: Processes the sanitized query.
6. **Knowledge Source (Vector Database)**: Contains embedded university internship policies and curated job datasets. The LLM queries this to retrieve relevant context.
7. **Response / Output**: Returns a grounded, cited recommendation back through the interface to the user.
8. **Evaluation Point**: Logs interactions (anonymized) for later correctness and latency evaluation.

---

## Step C4: Architecture Decision Record (ADR)

| Decision | Requirement / Constraint | Alternatives Considered | Selected Option | Trade-off Accepted |
| --- | --- | --- | --- | --- |
| **Include dedicated Knowledge Source (RAG)** | FR3, RAI4: Answers must be grounded in approved information with citations. | Base model only; Full model fine-tuning; Static keyword search. | RAG with a Vector Database component. | More system complexity and slight latency increase, but ensures factual correctness, traceability, and easy policy updates. |
| **Include PII Redaction component** | RAI3: The system shall not transmit student PII to external model APIs. | Trusting the LLM provider's privacy policy; Hosting an open-source LLM on-premise. | Lightweight PII redaction layer before the external LLM API call. | Slight increase in processing time and potential false positives in redaction, but guarantees strict compliance with student privacy standards. |

---

## Initial Requirements Traceability Matrix

| Objective | Requirement | Evaluation Criterion | Architecture Element | Later Evidence |
| --- | --- | --- | --- | --- |
| **O1** | FR2 | Recommendation Correctness | Knowledge Source + AI Capability | Evaluation test set relevance score (≥ 85%) |
| **O2** | FR3 / RAI4 | Source Citation and Support | Knowledge Source + AI Capability | Citation match rate audit (≥ 95% match) |
| **O3** | RAI3 | PII Protection | PII Redaction Component | Payload inspection test (0 PII leaks detected) |
