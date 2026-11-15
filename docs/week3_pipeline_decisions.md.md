# Week 3 Pipeline Decisions

**Linked Requirement:** FR1 (Match students to internships based on official guidelines).

**Preparation Choices:**
1. **PDF Guidelines:** Chose fixed-size 500-character chunking. 
   - *Benefit:* Ensures consistent context window size for the RAG retriever.
   - *Limitation:* May split sentences mid-way; does not preserve page numbers.
2. **Job CSV:** Removed exact duplicates and stripped whitespace.
   - *Benefit:* Prevents the AI from recommending the same job multiple times.
   - *Limitation:* Did not impute missing values (e.g., missing stipend), preserving raw data integrity for Topic 4.

**Stage Contracts:** 
- Ingest: File must exist in `data/raw/`.
- Validate: Output file must exist in `data/processed/` and be > 0 bytes.