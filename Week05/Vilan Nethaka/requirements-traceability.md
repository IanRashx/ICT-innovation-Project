# Week 5 – Requirements Traceability Matrix

## Project
Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware

## Purpose

The purpose of this document is to demonstrate traceability between:

- stakeholder personas;
- user stories;
- functional requirements;
- non-functional requirements;
- project scope;
- proposed implementation ideas.

This helps ensure that project functionality addresses an identified user need.

---

# Traceability Matrix

| Requirement ID | Requirement Description | Persona | User Story | Project Scope Element | Related NFR | Innovative / Implementation Idea |
|---|---|---|---|---|---|---|
| FR1 | Submit Test Prompts – allow normal and adversarial prompts to be submitted to an AI agent for testing | AI Security Researcher | US1 | Adversarial testing | NFR4 | Controlled normal/adversarial prompt-testing workflow |
| FR2 | Detect Potential Jailbreaks – analyse submitted prompts and identify potentially malicious or jailbreak-style inputs | AI Security Researcher | US2 | Jailbreak detection | NFR1, NFR2 | Automated jailbreak/prompt-risk detection |
| FR3 | Apply Protection – apply a resilience or protection mechanism when suspicious input is identified | AI Developer | US3, US5 | Defence and resilience | NFR3 | Detection-triggered protection and safe fallback behaviour |
| FR4 | Record and Display Results – record prompts, classifications, AI responses and attack outcomes for evaluation | AI Security Researcher | US4 | Evaluation and reporting | NFR4 | Structured resilience evaluation and evidence recording |

---

# Non-Functional Requirement Traceability

| NFR ID | Requirement | Target | Related FR / User Story |
|---|---|---|---|
| NFR1 | Detection Response Time | ≤2 seconds, excluding external LLM/API response time | FR2 / US2 |
| NFR2 | Detection Effectiveness | ≥80% jailbreak detection | FR2 / US2 |
| NFR3 | Benign Prompt Acceptance | ≥90% legitimate prompts processed correctly | FR3 / US3, US5 |
| NFR4 | System Reliability | ≥95% planned evaluation tests complete without application failure | FR1, FR4 / US1, US4 |

---

# Traceability Examples

## Example 1 – Jailbreak Detection

**Persona:** AI Security Researcher  
↓  
**User Story:** US2 – Identify jailbreak-style prompts  
↓  
**Functional Requirement:** FR2 – Detect Potential Jailbreaks  
↓  
**NFRs:** NFR1 and NFR2  
↓  
**Implementation:** Automated jailbreak/prompt-risk detection  
↓  
**Evaluation:** Detection Response Time and Jailbreak Detection Rate

---

## Example 2 – Protection and Usability

**Persona:** AI Developer  
↓  
**User Stories:** US3 and US5  
↓  
**Functional Requirement:** FR3 – Apply Protection  
↓  
**NFR:** NFR3 – Benign Prompt Acceptance  
↓  
**Implementation:** Detection-triggered protection mechanism  
↓  
**Evaluation:** Benign Prompt Acceptance Rate and security evaluation metrics

---

## Example 3 – Experimental Evaluation

**Persona:** AI Security Researcher  
↓  
**User Story:** US4  
↓  
**Functional Requirement:** FR4 – Record and Display Results  
↓  
**NFR:** NFR4 – System Reliability  
↓  
**Implementation:** Structured experiment-result recording  
↓  
**Evaluation:** ASR, refusal behaviour, reliability and other applicable metrics

---

# Scope Review

Week 2 established four functional requirements:

- FR1 – Submit Test Prompts
- FR2 – Detect Potential Jailbreaks
- FR3 – Apply Protection
- FR4 – Record and Display Results

FR5 and FR6 have not currently been defined.

The team will not introduce additional requirements simply to fill unused requirement IDs.

Any new requirement must:

1. address an identified stakeholder need;
2. contribute to the agreed project scope;
3. have an associated user story where appropriate;
4. have measurable acceptance criteria;
5. be reviewed by the team before implementation.

---

## Conclusion

The traceability analysis demonstrates that FR1–FR4 can be connected to identified users and user stories.

Maintaining this matrix throughout the project will help the team control scope and ensure that technical implementation remains aligned with stakeholder needs.
