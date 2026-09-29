# Awesome Clinical Decision Support System (CDSS)

A curated list of top Clinical Decision Support System (CDSS) SaaS products and open-source GitHub projects focusing on evidence-based medicine knowledge, drug interaction checking, diagnostic assistance, and clinical workflow integration.

*Last Updated: September 2026*

---

This repository tracks notable SaaS platforms and open-source projects in the field of Clinical Decision Support Systems (CDSS). These tools help clinicians access evidence-based medical knowledge at the point of care, check for drug-drug interactions, assist with diagnostic decision-making, and integrate into Electronic Health Record (EHR) workflows using standardized interfaces (such as CDS Hooks and FHIR). 

Examples include industry leaders like Wolters Kluwer UpToDate, DynaMed, VisualDx, Elsevier ClinicalKey AI, Zynx Health, EBSCO Dynamic Health, Infermedica, Isabel Healthcare, OpenClinical, and First Databank.

> [!NOTE]
> **Open Source Landscape:** The open-source ecosystem in clinical decision support exhibits a clear divide. At the **knowledge base level**, commercial products like UpToDate remain overwhelmingly dominant, with viable open-source alternatives being extremely rare. However, at the **algorithm execution level** and **drug safety level**, the open-source community is highly active:
> - **medAL-suite** is deployed across 5 countries (including Rwanda and Tanzania), having completed over 300,000 pediatric outpatient consultations.
> - **HealthRex/CDSS** (Stanford) serves as an essential reference implementation for academic research.
> - **Snowstorm**, officially maintained by SNOMED International, provides standardized terminology server support for clinical logic.

Contributions are welcome! Submit a Pull Request to add or update entries. Please keep descriptions factual and link directly to official sites.

---

## Table of Contents

- [SaaS & Hosted Platforms](#saas--hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
  - [Clinical Algorithm Execution & Guideline Digitization](#clinical-algorithm-execution--guideline-digitization)
  - [Diagnostic Assistance & Differential Diagnosis](#diagnostic-assistance--differential-diagnosis)
  - [Drug Interactions & Medication Safety](#drug-interactions--medication-safety)
  - [Terminology Services & Standardization Infrastructure](#terminology-services--standardization-infrastructure)
- [Key Open-Source Recommendations](#key-open-source-recommendations)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

---

## SaaS & Hosted Platforms

| Product Name | Description | Pricing Model & Limits |
| :--- | :--- | :--- |
| **Wolters Kluwer UpToDate** | The most widely used evidence-based clinical knowledge resource globally. Provides topic reviews, drug monographs, patient education materials, and clinical recommendations. Adopted by most U.S. hospitals and medical schools. | **Paid / Commercial**<br>Institutional subscriptions; individual plans start at ~$500–$600/year (no free tier, limited trial available upon request). |
| **DynaMed** | EBSCO's evidence-based clinical decision support tool. Offers systematic literature monitoring, graded recommendations, and real-time updates focused on quickly answering point-of-care questions. | **Paid / Commercial**<br>Institutional and individual subscriptions (no permanent free tier; institutional licensing required). |
| **VisualDx** | Visual diagnostic decision support platform. Assists differential diagnosis in dermatology, infectious diseases, and more through image comparison and symptom analysis. Supports 3,000+ diseases and 50,000+ medical images. | **Paid / Commercial**<br>Individual plans start at ~$40/month or ~$400/year; 14-day free trial available. |
| **Elsevier ClinicalKey AI** | Elsevier’s AI-driven clinical decision support platform. Integrates evidence-based content with generative AI to provide rapid conversational clinical Q&A. | **Paid / Commercial**<br>Enterprise/Institutional licensing (pricing customized per healthcare organization; no public free tier). |
| **Zynx Health** | Provider of evidence-based care standards and clinical content. Delivers embeddable clinical decision support content and quality metrics directly for EHR integration. | **Paid / Commercial**<br>Enterprise B2B pricing model (custom contracts per healthcare system/EHR vendor). |
| **EBSCO Dynamic Health** | Clinical decision support tool designed for nursing and allied health professionals. Provides skill checklists, cultural competency content, and evidence-based nursing guidelines. | **Paid / Commercial**<br>Institutional subscriptions for hospitals and educational institutions (no individual free tier). |
| **Infermedica** | AI-driven symptom checking and triage platform. Embedded via API into telehealth, insurance, and healthcare systems to provide initial symptom assessment and triage guidance. | **Paid / Commercial**<br>B2B API pricing based on usage/volume; free developer sandbox/demo API tier available for testing. |
| **Isabel Healthcare** | Diagnostic decision support tool. Generates a comprehensive differential diagnosis list based on input symptoms and lab test results. | **Paid / Commercial**<br>Subscription-based for institutions and individuals (~$20–$30/month for clinicians); limited free web demo available. |
| **OpenClinical** | Clinical decision support knowledge management directory and resource. Maintains catalogs and comparisons of clinical guidelines, decision support tools, and knowledge bases. | **Free Resource / Open Directory**<br>Free to access web directory and open knowledge repository. |
| **First Databank (FDB)** | Drug knowledge base and clinical decision support provider. Delivers drug-drug interactions, dosing, allergies, and medication guidance data, widely integrated into EHRs and pharmacy systems. | **Paid / Commercial**<br>B2B enterprise licensing for EHR vendors, hospitals, and pharmacies (custom pricing). |

---

## Open-Source GitHub Projects

### Clinical Algorithm Execution & Guideline Digitization

- **medAL-suite**
  - **Description:** The most production-proven open-source CDSS software suite. Consists of four main components centered around `medAL-creator`—a no-code drag-and-drop interface allowing experienced clinicians (rather than developers) to design clinical algorithms directly. Algorithms automatically deploy to `medAL-reader` for frontline clinical use, while `medAL-data` and `medAL-hub` handle configuration, version control, and deployment.
  - **Scale:** Deployed in large-scale clinical research across Rwanda, Tanzania, Kenya, Senegal, and India to digitize primary care guidelines. Completed over 300,000 pediatric outpatient consultations in Rwanda and Tanzania alone, significantly reducing inappropriate antibiotic prescriptions. Focuses on sustainable digital systems for low-resource environments with high interoperability (EMR integration) and low power requirements.
  - **License:** Open Source.

- **TMR Knowledge Acquisition Platform**
  - **Description:** A knowledge acquisition platform and shared library for the TMR (Transition-based Medical Recommendations) computable guideline model. Developed by King's College London to solve the "knowledge acquisition bottleneck".
  - **Features:** Features a no-code knowledge acquisition dashboard and interactive visualizer. Integrates the Z3 theorem prover with the Snowstorm terminology server to automate clinical logic formalization using SNOMED CT. Supports conflict detection (e.g., contradictory recommendations), specifically addressing guideline conflicts in multimorbidity scenarios. Provides a "copy and modify" workflow for safe local protocol adaptation.
  - **License:** Open Source.

- **Cortocircuito / InternaXpert**
  - **Description:** CDSS designed for disease diagnosis and clinical management.
  - **License:** Open Source.

---

### Diagnostic Assistance & Differential Diagnosis

- **PhenoDP**
  - **Description:** Phenotype-driven diagnostic assistance tool for Mendelian diseases (*published in Genome Medicine, 2025*).
  - **Modules:** Comprises three core modules: 
    1. *Summarizer*: A Bio-Medical-3B-CoT model fine-tuned on DeepSeek-R1 that generates patient-centered clinical summaries from HPO (Human Phenotype Ontology) terms.
    2. *Ranker*: Integrates multiple similarity metrics to rank candidate diseases, outperforming existing methods on real-world datasets.
    3. *Recommender*: Recommends missing HPO terms via contrastive learning to refine differential diagnoses. Integrates with Summarizer and Ranker to generate structured clinical reports.
  - **Implementation:** Python implementation, open code.

- **PIE-Med**
  - **Description:** Explainable clinical decision support system (*published in ECIR 2025*).
  - **Architecture:** Combines Graph Convolutional Networks (GCN) with Large Language Models (LLM). The GCN generates recommendations based on patient health data and validated medical knowledge; explainability algorithms evaluate model reasoning; and an LLM agent translates insights into natural language explanations.
  - **Key Design:** Uses the LLM strictly as an auxiliary reasoning agent rather than the primary decision-maker to mitigate hallucination and bias risks.
  - **License:** Open Code.

- **NCD-CIE**
  - **Description:** Causal information-driven CDSS for non-communicable diseases (*published in AI in Healthcare, 2026*).
  - **Components:** Features an expert-curated causal knowledge graph (107 directed edges covering 8 clinical domains), a logic-linked risk engine with uncertainty quantification, and a topological what-if simulator to estimate Heterogeneous Treatment Effects (HTE) and identify high-benefit patients. Enhanced by a 3-layer LLM setup for graph validation (87.9% expert agreement), natural language query parsing (92% accuracy), and counterfactual explanation generation. Validated on the Framingham Heart Study cohort ($n=4,172$).
  - **License:** Open Source.

- **OneHealth+**
  - **Description:** Explainable, clinician-in-the-loop brain tumor MRI classification platform (*published in SoftwareX, 2026*).
  - **Pipeline:** Built around a validation-first pipeline: MRI Validator rejects non-medical inputs $\rightarrow$ DSCBAM-Net classifier categorizes scan (glioma, meningioma, pituitary, no tumor) $\rightarrow$ Each prediction is paired with confidence scores and Grad-CAM overlays $\rightarrow$ Predictions enter a pending physician verification queue $\rightarrow$ Clinicians log explicit verdicts (agree/disagree/uncertain).
  - **Deployment:** Docker Compose setup (Laravel + FastAPI + MySQL), running without requiring a dedicated GPU.
  - **License:** Open Source.

---

### Drug Interactions & Medication Safety

- **HealthRex/CDSS**
  - **Description:** Clinical decision support system developed by Stanford University's HealthRex Lab. Associated with high-value medical NLP projects including knowledge graphs (157 diseases, 491 symptoms learned from 270,000+ patient records), MIMIC-III to OMOP mappings, ICD code prediction from clinical notes, and MedCAT tutorials.
  - **Role:** Serves as a vital reference implementation for academic research.
  - **License:** Open Source.

- **PillChecker API**
  - **Description:** Backend API for checking drug-drug interactions.
  - **Architecture:** Complete pipeline: OCR cleaning $\rightarrow$ NER extraction (`OpenMed-NER-PharmaDetect`, 108M parameters) $\rightarrow$ RxNorm fallback (brand name mapping) $\rightarrow$ DrugBank interaction lookup (via MCP server accessing a 17,400-drug SQLite database) $\rightarrow$ Severity classification (template parser + DeBERTa v3 zero-shot classification). Returns transparent responses with `data_sources` and `limitations`.
  - **Deployment:** 3-stage Docker build, fully self-contained.
  - **License:** Open Source.

- **LLM-Drug-Interaction-Checker**
  - **Description:** Streamlit-based application utilizing Hugging Face free open foundation LLMs (GPT-2, GPT-J, BioGPT) to detect drug interactions and side effects. Provides a clean, minimalist UI where entering comma-separated drug names returns interaction insights.
  - **License:** Open Source.

- **Drug-Interaction-Checker (agnivadas)**
  - **Description:** Python tool using the PubChem API to identify and analyze specified drug interactions. Fetches interaction data, processes it into CSV files, and highlights risk levels directly in the terminal. Tailored for quick multi-drug interaction exploration by healthcare professionals and researchers.
  - **License:** Open Source.

---

### Terminology Services & Standardization Infrastructure

- **Snowstorm**
  - **Description:** The official SNOMED CT terminology server maintained by SNOMED International.
  - **Tech Stack:** Modern open-source stack built on Elasticsearch, Spring Boot, and Docker.
  - **Features:** Provides advanced SNOMED-specific APIs, read-only HL7 FHIR APIs, multilingual search and content retrieval, full compliance with ECL v1.3, complete version history, and support for both read-only and authoring modes. Essential infrastructure for formalizing CDSS clinical logic.
  - **License:** Open Source.

- **HAPI FHIR Server**
  - **Description:** Complete Java implementation of the HL7 FHIR specification, open-sourced by Smile Digital Health. Supports terminology operations and serves as the FHIR foundational layer for CDSS integrations.
  - **License:** Open Source.

---

## Key Open-Source Recommendations

When building a custom Clinical Decision Support System, consider combining these specialized open-source tools:

- **Clinical Algorithm Engine:** `medAL-suite` (for no-code clinical algorithm design and production deployment at scale) or `TMR Knowledge Platform` (SNOMED CT + Z3 theorem prover).
- **Diagnostic Assistance:** `PhenoDP` (HPO-driven for Mendelian diseases), `PIE-Med` (explainable GCN + LLM), `NCD-CIE` (causal graph & HTE estimation), or `OneHealth+` (clinician-in-the-loop MRI platform).
- **Drug Safety:** `PillChecker API` (DrugBank + RxNorm + NER pipeline), `HealthRex/CDSS`, or `LLM-Drug-Interaction-Checker`.
- **Terminology & Integration Infrastructure:** `Snowstorm` (official SNOMED CT server) and `HAPI FHIR` (standardized FHIR integration layer).
- **Persistence & Deployment:** PostgreSQL / Elasticsearch for storage with Docker Compose for orchestration.

---

## How to Contribute

1. Fork the repository.
2. Add or edit entries in `README.md` following the existing format.
3. Include: Name, link, 1–2 sentence description, and whether it is SaaS or Open Source.
4. Submit a Pull Request with a brief explanation.

*If you find this repository useful, please give it a star!*

---

## Disclaimer

This is a community-curated directory—it is neither exhaustive nor does it constitute medical endorsement. Clinical Decision Support Systems process sensitive patient health data; ensure strict compliance with HIPAA, GDPR, FDA guidelines, and applicable medical device regulations (such as EU MDR).

> [!WARNING]
> **Open Source vs. Commercial Knowledge Bases:** The open-source CDSS ecosystem is mature and production-ready for **algorithm execution** (`medAL-suite`) and **drug safety** (`PillChecker API`, `HealthRex/CDSS`). However, for **evidence-based clinical knowledge bases**, commercial platforms like UpToDate and DynaMed remain dominant. Open-source alternatives lag significantly in update frequency, peer-review rigor, and clinical authority.
> 
> Use commercial platforms when instant point-of-care medical reference is required; leverage open-source solutions when custom algorithms, localized workflows, and self-hosted deployments are needed.

*Built for clinicians, clinical informaticists, medical NLP researchers, and healthcare IT teams. Making clinical decision support more open, explainable, and patient-centered.*
