# ai-engineering-subject
ai engineering subject

# Project Scoping Template

# **Project Name**

Student Internship Assistant

# **Domain**

Higher Education / Career Services & Academic Advising

# **Problem Statement**

Students struggle to find suitable companies that accept internship applications matching their academic background and career goals. <br>
Career information is fragmented across multiple platforms, and manual matching by university career centers is constrained by staff availability. <br>
AI engineering makes it possible to build a personalized, document-grounded internship matching assistant that aligns student profiles with verified opportunities and official university internship guidelines.

# **Evidence of the Problem**

Evidence 1: A significant portion of fresh graduates face unemployment or underemployment partly due to difficulties in securing relevant industry exposure during their studies. Securing a relevant internship is a critical hurdle for undergraduates.

Source / citation: [Ministry of Higher Education (MOHE) Graduate Tracer Study Report (2024).](https://www.mohe.gov.my/en/download/statistics/2024-4/1708-bab-7-tracer-study-2024-pdf/file) 

Evidence 2: Students frequently report high stress and logistical challenges in finding relevant roles that match their specific field of study, often encountering unclear expectations or insufficient guidance.

Source / citation: [Recent studies on Work-Integrated Learning (WIL) and internship placement challenges in higher education.](https://www.ijwil.org/files/IJWIL_27_1_43_58.pdf)

# **Initial Related Work (at least 3)**

- Study / solution 1: University Career Center Portals / Internal Job Boards

Key limitation: Often static, manually updated, and lack personalized matching based on a student’s specific academic transcript or skills.

- Study / solution 2: General-purpose job search platforms (e.g., LinkedIn, JobStreet)

Key limitation: Not tailored to university-specific internship requirements (e.g., required credit hours, faculty approvals) and contain high "noise" (full-time or irrelevant roles).

- Study / solution 3: Manual academic and career advising

Key limitation: Highly contextual and valuable, but severely constrained by staff availability and scalability, leading to delayed or generic advice.

# **Engineering Gap / Limitation**

What practical or technical limitation remains unresolved?

Gap / Limitation: Existing solutions are either too generic (public job boards), too rigid (static university portals), or unscalable (human advisors). 
There is a lack of an AI-driven, document-grounded system that can simultaneously understand official university internship policies, parse student academic profiles, and match them to verified company opportunities with explainable recommendations.

# **Initial Project Objectives (2–3)**

- O1: To design an AI-powered internship matching assistant that aligns student profiles (major, skills, preferences) with suitable company opportunities based on official university guidelines.

- O2: To develop the proposed solution using Retrieval-Augmented Generation (RAG) to ensure recommendations are strictly grounded in verified university internship policies and curated job datasets.

- O3 (if applicable): To evaluate the solution in terms of matching relevance, recommendation explainability, and user satisfaction among target students.

# **Target Users**

Undergraduate students (particularly those in their pre-internship semester) and university career counselors who facilitate and monitor student placements.

# **Data Sources (at least 2)**

- Source 1: University Internship Guidelines / Student Handbook PDF — [URL](https://management.utm.my/industrial-training/?spm=a2ty_o01.29997173.0.0.2a93c921h1aSA0) 
- Source 2: Curated Internship Job Listings Dataset (e.g., verified internship openings from partner companies) — [URL](https://my.jobstreet.com/internship-jobs 
)

# **Responsible AI Risks (at least 2)** 

Risk 1: Hallucination / Misinformation 

- The model might recommend fake, outdated, or ineligible internship openings, causing students to waste time or miss critical application deadlines.

Risk 2: Privacy & Data Security 

- Handling sensitive student data (e.g., resumes, academic transcripts, contact info) poses significant risks if the data is not properly anonymized, encrypted, or access-controlled.

Risk 3: Bias / Fairness 

- The matching algorithm might inadvertently favor certain demographics or well-known companies, leading to unequal access to high-quality internship opportunities.

## Weekly Progress
| Week | Focus | Deliverable | Status |
|------|-------|-------------|--------|
| W1 | System map + project scope | README + docs | ✅ |

