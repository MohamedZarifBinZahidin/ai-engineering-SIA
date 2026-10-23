# Group Reflections

## Part A Reflection: Conversational AI vs. Recommendation Systems

### 1. System Comparison
* **Conversational AI (ChatGPT):** Focuses on dynamic text generation, natural language understanding, and multi-turn dialogue handling.
* **Recommendation Systems:** Focuses on predicting user preferences based on historical data to surface relevant items (e.g., movies, products, or content).

### 2. Quality Dimension Difference
* **Key Quality Dimension:** **Accuracy / Factuality** versus **Relevance**.
  * Conversational AI systems heavily prioritize **factual accuracy** and **hallucination prevention** because users rely on generated text for direct factual answers.
  * Recommendation systems prioritize **relevance** and **diversity** rather than explicit factual truth, as their main objective is engaging the user with options they are likely to like.

### 3. Support from Other Group's Observation
* Based on observations presented by another group studying a recommendation system, their primary concern was recommendation accuracy (avoiding cold-start issues and filter bubbles). In contrast, our observation of ChatGPT showed that the primary vulnerability lies in generating confident yet factually incorrect statements (hallucinations), demonstrating how accuracy manifests differently across AI system types.

---

## Part B Reflection: System Failure Points & Engineering Focus

### 1. Component with the Most Potential Failure Points
* Based on our Conceptual AI System Map (`week1_system_map.png`), the interaction between the **Safety/Moderation Guardrails** and the **LLM Inference Engine (GPT Model)** contains the highest concentration of potential failure points (e.g., *Prompt Injection/Jailbreak*, *Model Hallucination*, and *False Positive Over-refusal*).

### 2. Focus for AI Engineering Effort
* Because Large Language Models (LLMs) are naturally non-deterministic, raw outputs cannot be fully trusted without validation layers. AI Engineering efforts must be heavily concentrated on:
  * **Input/Output Guardrail Engineering:** Implementing robust prompt filtering to stop adversarial inputs and filtering generated outputs before displaying them to users.
  * **Evaluation & Monitoring Pipelines:** Continuously monitoring for hallucinations, toxicity, and drift.

### 3. Connection to Quality Dimensions
* **Accuracy & Reliability:** Robust output filtering and hallucination detection directly improve factual correctness.
* **Safety & Fairness:** Input guardrails prevent malicious exploitation, keeping the system aligned with safety policies.
* **Latency:** Balancing multi-layer guardrail checks with real-time response generation is vital to ensure low latency and prevent connection timeouts.