# ai-engineering-subject
ai engineering subject

# Project Scoping Template

**Project Name**  
Student Internship Assistant  

**Domain**  
Higher Education / Career Services & Academic Advising  

**Problem Statement**  
Students struggle to find suitable companies that accept internship applications matching their academic background and career goals. Career information is fragmented across multiple platforms, and manual matching by university career centers is constrained by staff availability. AI engineering makes it possible to build a personalized, document-grounded internship matching assistant that aligns student profiles with verified opportunities and official university internship guidelines.

**Evidence of the Problem**  
**Evidence 1:** 
A significant portion of fresh graduates face unemployment or underemployment partly due to difficulties in securing relevant industry exposure during their studies. Securing a relevant internship is a critical hurdle for undergraduates.  
*Source / citation:* 
Ministry of Higher Education (MOHE) Graduate Tracer Study Reports (e.g., 2024), which highlight ongoing challenges in graduate employability and the critical role of pre-graduation internships.  

**Evidence 2:** Students frequently report high stress and logistical challenges in finding relevant roles that match their specific field of study, often encountering unclear expectations or insufficient guidance.  
*Source / citation:* Recent studies on Work-Integrated Learning (WIL) note that students struggle with internship placement challenges, limiting their exposure to diverse professional opportunities and creating a gap between training and practice.  

**Initial Related Work (at least 3)**  
**Study / solution 1:** University Career Center Portals / Internal Job Boards  
*Source / citation:* Internal university career services websites and manual notice boards.  
*Key limitation:* Often static, manually updated, and lack personalized matching based on a student’s specific academic transcript, skills, or career preferences.  

**Study / solution 2:** General-purpose job search platforms (e.g., LinkedIn, JobStreet)  
*Source / citation:* Public commercial job platforms.  
*Key limitation:* Not tailored to university-specific internship requirements (e.g., required credit hours, faculty approvals, assessment criteria) and contain high "noise" (full-time or irrelevant roles).  

**Study / solution 3:** Manual academic and career advising  
*Source / citation:* Traditional human career counseling models within universities.  
*Key limitation:* Highly contextual and valuable, but severely constrained by staff availability and scalability, leading to delayed or generic advice during peak internship application seasons.  

**Engineering Gap / Limitation**  
*Gap / Limitation:* Existing solutions are either too generic (public job boards), too rigid (static university portals), or unscalable (human advisors). There is a lack of an AI-driven, document-grounded system that can simultaneously understand official university internship policies, parse student academic profiles, and match them to verified, suitable company opportunities with explainable, grounded recommendations.

**Initial Project Objectives (2–3)**  
**O1:** To design an AI-powered internship matching assistant that aligns student profiles (major, skills, preferences) with suitable company opportunities based on official university guidelines.  
**O2:** To develop the proposed solution using Retrieval-Augmented Generation (RAG) to ensure recommendations are strictly grounded in verified university internship policies and curated job datasets.  
**O3:** To evaluate the solution in terms of matching relevance, recommendation explainability, and user satisfaction among target students.  

**Target Users**  
Undergraduate students (particularly those in their pre-internship semester) and university career counselors who facilitate and monitor student placements.

**Data Sources (at least 2)**  
**Source 1:** University Internship Guidelines / Student Handbook PDF — *URL:* [Official University Career Centre Website]  
**Source 2:** Curated Internship Job Listings Dataset (e.g., verified internship openings from partner companies or public platforms) — *URL:* [Partner Company Portal or Public Job Board]  
**Source 3 (if any):** Faculty-specific Programme Guide PDFs (detailing specific internship credit and assessment requirements) — *URL:* [Official University Faculty Website]  

**Similar to EduAdvisor**  
- Uses document-grounded AI (RAG) to answer questions and provide recommendations based on official, authoritative documents (e.g., internship policies instead of course catalogs).  
- Aims to reduce the administrative burden on university staff while providing 24/7, instant assistance to students.  

**Different from EduAdvisor**  
- Focuses on *career and internship matching* rather than internal academic course advising.  
- Requires integrating and reasoning over *external* or semi-structured data (company job descriptions, student resumes/profiles) in addition to internal university documents.  
- Involves higher stakes regarding personal data privacy (handling student resumes, grades, and contact information).  

**Responsible AI Risks (at least 2)**  
**Risk 1 — Hallucination / Misinformation:** The model might recommend fake, outdated, or ineligible internship openings, causing students to waste time or miss critical application deadlines.  
**Risk 2 — Privacy & Data Security:** Handling sensitive student data (e.g., resumes, academic transcripts, contact info) poses significant risks if the data is not properly anonymized, encrypted, or access-controlled.  
**Risk 3 — Bias / Fairness:** The matching algorithm might inadvertently favor certain demographics, universities, or well-known companies, leading to unequal access to high-quality internship opportunities for marginalized students.  
