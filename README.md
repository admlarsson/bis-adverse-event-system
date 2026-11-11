# bis-adverse-event-system
# Business Process Modeling & Requirements Engineering: Adverse Event Reporting System (BIS)

## Project Overview
This project was developed as part of the Information Systems B / Business Process Modeling course at Uppsala University[cite: 7]. The goal was to design a conceptual Business Information System (BIS) for a pharmaceutical company to improve the reporting, validation, and automated distribution of Adverse Drug Reactions (ADRs)[cite: 23, 24].

The project demonstrates a structured approach to translating complex business processes and legal requirements into functional IT specifications[cite: 21, 27].

## Business Context & Problem Statement
Pharmaceutical companies are legally obligated to report all known adverse drug reactions to national and international authorities within strict timeframes[cite: 23].

**The Challenge:**
The company's existing routines for reporting adverse events were failing. Medical policies (requiring ADR reporting) conflicted with sales policies (incentivizing sales volume)[cite: 110]. This caused severe underreporting by internal staff, such as sales representatives, and a lack of structured data capture from external actors[cite: 109, 110].

**The Proposed Solution:**
We designed the BIS (Biverknings-informationssystem) – a centralized system that allows patients to report ADRs directly, enables specialists to validate data with physicians, and automates regulatory reporting[cite: 23, 24]. Importantly, it also bridges the gap between conflicting internal policies.

## Methodology
The project utilized SEMLa (Systemic Enterprise Modeling Language) to ensure a holistic understanding of the enterprise[cite: 15, 30]. The modeling process followed a structured life-cycle approach:
1. Goal Modeling: Defining the purpose of the system[cite: 22, 59].
2. Scenario & Process Modeling: Mapping the "as-is" and "to-be" workflows[cite: 21, 60].
3. Conceptual Modeling: Structuring the domain data (patients, drugs, diagnoses)[cite: 22, 67].
4. Requirements Engineering: Formulating functional IT specifications based on the models[cite: 21].

## Enterprise Models
*(Note: The visual models were originally created in Lucidchart.)*

### 1. Goal Model
![Goal Model](assets/goal-model.png)
*Primary Objective: Protect patients by collecting, analyzing, and reporting adverse events.*[cite: 59]

### 2. Business Process Models
The core workflow was mapped from a high-level main process down to four distinct sub-processes[cite: 62].

**Main Process Overview:**
![Main Process](assets/main-process-flow.png)

**Detailed Sub-processes:**
* **Process 1: Patient Contact:** The patient initiates contact (via phone or web app) to report a side effect[cite: 64].
![Sub-process 1](assets/sub-process-1-patient.png)

* **Process 2: Registration & Validation:** An ADR Specialist registers the report in BIS and contacts the prescribing physician to validate the data (retrieving diagnosis, prognosis, and treatment regime)[cite: 65].
![Sub-process 2](assets/sub-process-2-registration.png)

* **Process 3: Automated Regulatory Reporting:** BIS automatically transfers validated "Clear Reports" to national (SBS) and EU (EBS) databases[cite: 66].
![Sub-process 3](assets/sub-process-3-automated-report.png)

* **Process 4: Data Analysis:** R&D and authorities analyze the aggregated data to update medical recommendations[cite: 67].
![Sub-process 4](assets/sub-process-4-analysis.png)

### 3. Conceptual Data Model
![Conceptual Data Model](assets/conceptual-data-model.png)
Key entities defined for the system architecture include:
* Actors: In-reporter (Patient/Relative), Adverse Event Specialist, Responsible Physician, Authorities[cite: 67].
* Core Data: Patient ID, Drug Name, Indication, Dosage, Start/End Dates, Concomitant Medications[cite: 75].
* Validation Data: Medical prognosis, diagnosis, and treatment plan (provided by the physician)[cite: 68].

## Functional Requirements (Extract)
Based on the models, the following functional requirements were specified for the BIS application[cite: 69]:

**For the In-Reporter (Patient/Nurse):**
* Must be able to select a reporting method (Web App or Phone)[cite: 70].
* Must be able to submit mandatory fields (Patient info, Drug, Usage data)[cite: 70].

**For the Adverse Event Specialist:**
* Must be able to register and update ADRs in the BIS database[cite: 71].
* Must be able to request supplementary medical information from the responsible physician[cite: 71].
* Must be able to mark a report as "Clear" only when validated[cite: 71].

**For the BIS System Engine:**
* Must automatically trigger data transfer to the Swedish ADR System (SBS) upon "Clear" status[cite: 73].
* Must enforce a 5-day deadline from initial contact to authority reporting[cite: 73].
* Must maintain a strict audit log (who did what, and when)[cite: 73].

## Key Learnings & Reflections
* **Resolving Policy Conflicts:** The modeling revealed that IT systems alone cannot solve business problems. The conflicting KPIs between the Medical Department (compliance) and Sales Department (volume) had to be addressed structurally for the system to succeed[cite: 110].
* **Traceability:** By moving from Goal Models to Process Models to Conceptual Models to IT Requirements, we ensured that every functional requirement in the IT system directly supported a verified business goal[cite: 28, 93].
* **The "Happy Path" vs. Reality:** The developed models represent the "to-be" scenario (the Happy Path)[cite: 91]. In reality, edge cases (such as unresponsive physicians or incomplete patient data) require robust exception handling in the final IT architecture[cite: 91, 92].

---
*Project developed by David Palmér, Filip Sundberg, and Adam Larsson (2026).*[cite: 55]