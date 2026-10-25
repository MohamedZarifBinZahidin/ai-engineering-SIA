# Requirements Specification — Student Internship Assistant
Version: 1.0

## Section 0 — Project Framing & Application Scope Checkpoint

| Framing element | Details |
| --- | --- |
| **Problem Evidence** | Students struggle to find suitable internships matching their academic background, and career information is fragmented across multiple platforms [[7]]. Manual matching by university career centers is constrained by staff availability and reactive outreach models [[19]]. |
| **Existing Approaches** | 1. Traditional university career portals (e.g., Handshake) provide job boards but lack personalized, document-grounded matching to specific university guidelines.<br>2. Generic AI resume builders offer feedback but do not verify alignment with official university internship policies.<br>3. Emerging AI matching frameworks optimize large-scale matching but often lack transparent, source-grounded explanations for individual students [[1]]. |
| **Project / Engineering Gap** | Current systems either lack personalization grounded in verified university policies or fail to provide transparent, explainable recommendations with source traceability. |
| **Objective O1** | To design an AI-powered internship matching assistant that aligns student profiles (major, skills, preferences) with suitable company opportunities based on official university guidelines. |
| **Objective O2** | To develop the proposed solution using Retrieval-Augmented Generation (RAG) to ensure recommendations are strictly grounded in verified university internship policies and curated job datasets. |
| **Objective O3** | To evaluate the solution in terms of matching relevance, recommendation explainability, and user satisfaction among target students. |
| **Intended Users** | University students seeking internships, and optionally, career services advisors. |
| **Supported Tasks** | Parsing student profiles, retrieving relevant internship opportunities, matching based on university guidelines, and generating explainable recommendations with source citations. |
| **Information / Knowledge Domain** | University internship policies, academic program requirements, and curated internship/job opportunity datasets. |
| **Operating Context** | Web-based or chat-based interface accessible to students during their internship search period (e.g., 1–2 semesters before the internship). |
| **Important Constraints** | Must rely only on verified, approved university documents and curated job datasets; cannot hallucinate policies or job requirements. |
| **Explicit Out-of-Scope Tasks** | The system SHALL NOT guarantee internship placement, write full resumes/cover letters on behalf of the student, or provide legal/financial advice regarding employment contracts. |
| **Evaluation Focus** | Determine whether the system provides accurate, policy-grounded internship recommendations with high user trust and explainability, while maintaining low latency. |

---

## Section 1 — Functional Requirements

| # | Requirement — The system SHALL | Scope Boundary — SHALL NOT (where relevant) |
| --- | --- | --- |
| **FR1** | Accept a student's academic profile (major, skills, preferences) as input for matching. | Store or retain sensitive student Personally Identifiable Information (PII) beyond the active session. |
| **FR2** | Retrieve and recommend internship opportunities that match the student's profile and comply with official university internship guidelines. | Recommend opportunities that violate mandatory university credit or policy requirements. |
| **FR3** | Provide verifiable source references (e.g., specific policy document names or job posting links) for all recommendations and policy-related answers. | Present unsupported information as if it came from an approved university source. |
| **FR4** | Decline queries that fall outside the academic internship advising scope and provide an appropriate redirect. | Provide legal, financial, or mental health advice, or write full application documents on the student's behalf. |
| **FR5** | Present answers and recommendations in clear, encouraging language appropriate for undergraduate students. | Use overly technical jargon or bureaucratic language that confuses the user. |

---

## Section 2 — Non-Functional Requirements

| # | Quality Attribute | Requirement | Measurement Method | Metric | Threshold |
| --- | --- | --- | --- | --- | --- |
| **NFR1** | Performance | The system shall keep interactive response latency within an acceptable target for chat-based interaction. | Measure end-to-end latency on a defined test workload. | p90 latency | < 3,000 ms |
| **NFR2** | Correctness | Recommendations and policy answers shall be factually consistent with approved source documents. | Score a curated evaluation set of student queries using a groundedness rubric. | Correct response rate (%) | ≥ 85% |
| **NFR3** | Cost | Inference cost shall remain within the project budget. | Record model/API usage over the evaluation workload. | Cost per 100 queries | < US$0.50 per 100 queries |
| **NFR4** | Maintainability | Approved university policy or job dataset updates shall be incorporated without rebuilding unrelated components. | Run a controlled document-update test. | Update time | < 15 min |

---

## Section 3 — Responsible AI Requirements

| # | Responsible AI Risk | Requirement | Measurement Method | Metric | Threshold |
| --- | --- | --- | --- | --- | --- |
| **RAI1** | Fairness | System recommendation quality shall not differ beyond an agreed tolerance across different student demographics (e.g., major, year of study). | Evaluate a stratified test set and compare relevance rates across student groups. | Absolute relevance-rate gap between groups | ≤ 10 percentage points |
| **RAI2** | Safety / Scope | The system shall refuse out-of-scope queries and redirect users appropriately. | Run a defined safety/scope test set containing at least 20 out-of-scope queries. | Refusal-and-redirect success rate | ≥ 95% |
| **RAI3** | Privacy | The system shall not transmit student PII to external model APIs without prior anonymization. | Run privacy test cases and inspect outgoing model/API payloads. | Number of detected PII transmissions | 0 |
| **RAI4** | Transparency / Grounding | The system shall provide a verifiable source reference for document-grounded answers and indicate when sufficient supporting evidence cannot be found. | Evaluate document-grounded responses for citation presence and whether the cited source supports the answer. | Citation presence rate; citation-source match rate | 100% presence; ≥ 95% match |