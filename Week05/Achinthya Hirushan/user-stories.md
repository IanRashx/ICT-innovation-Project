# Week 5 – User Stories

## Project
Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware

## Purpose

This document converts the stakeholder needs identified during the requirements analysis into user stories.

The two primary personas used are:

1. AI Security Researcher
2. AI Developer

Each user story follows the format:

> As a [user], I want to [goal], so that [benefit].

---

# US1 – Prompt Testing

**User:** AI Security Researcher

> As an AI Security Researcher, I want to submit normal and adversarial prompts to an AI agent so that I can evaluate how the agent behaves under legitimate and malicious inputs.

### Related Requirement

**FR1 – Submit Test Prompts**

The system shall allow a user to submit normal and adversarial prompts to an AI agent for testing.

### Related NFR

**NFR4 – System Reliability**

At least 95% of planned evaluation test cases should complete without application failure.

---

# US2 – Jailbreak Detection

**User:** AI Security Researcher

> As an AI Security Researcher, I want potentially malicious or jailbreak-style prompts to be identified so that I can measure how effectively adversarial interactions are detected.

### Related Requirement

**FR2 – Detect Potential Jailbreaks**

The system shall analyse submitted prompts and identify potentially malicious or jailbreak-style inputs.

### Related NFRs

**NFR1 – Detection Response Time**

Detection should complete within 2 seconds, excluding external LLM/API response time.

**NFR2 – Detection Effectiveness**

At least 80% of jailbreak prompts in the agreed evaluation dataset should be detected.

---

# US3 – Apply Protection

**User:** AI Developer

> As an AI Developer, I want a resilience mechanism to respond when suspicious input is detected so that the likelihood of successful manipulation of the AI agent can be reduced.

### Related Requirement

**FR3 – Apply Protection**

The system shall apply a resilience or protection mechanism when suspicious input is identified.

### Related NFR

**NFR3 – Benign Prompt Acceptance**

At least 90% of approved legitimate prompts should continue to work correctly when protection is enabled.

---

# US4 – Record and Evaluate Results

**User:** AI Security Researcher

> As an AI Security Researcher, I want prompts, classification results, AI responses and attack outcomes to be recorded so that I can quantitatively evaluate and compare resilience across different configurations.

### Related Requirement

**FR4 – Record and Display Results**

The system shall record submitted prompts, classifications, AI responses and attack outcomes and make the results available for evaluation.

### Related NFR

**NFR4 – System Reliability**

At least 95% of planned evaluation test cases should complete without application failure.

---

# US5 – Maintain Legitimate Functionality

**User:** AI Developer

> As an AI Developer, I want legitimate prompts to continue operating correctly when the resilience mechanism is enabled so that improving security does not unnecessarily reduce the usefulness of the AI agent.

### Related Requirement

**FR3 – Apply Protection**

The protection mechanism should improve resilience while maintaining legitimate system functionality.

### Related NFR

**NFR3 – Benign Prompt Acceptance**

At least 90% of approved legitimate prompts should continue to work correctly when protection is enabled.

---

# User Story Summary

| ID | Persona | Main Goal | Requirement | NFR |
|---|---|---|---|---|
| US1 | AI Security Researcher | Submit normal/adversarial prompts | FR1 | NFR4 |
| US2 | AI Security Researcher | Detect jailbreak prompts | FR2 | NFR1, NFR2 |
| US3 | AI Developer | Apply protection | FR3 | NFR3 |
| US4 | AI Security Researcher | Record and evaluate results | FR4 | NFR4 |
| US5 | AI Developer | Maintain legitimate functionality | FR3 | NFR3 |

---

## Conclusion

These user stories provide a direct connection between stakeholder needs and the project's requirements.

They ensure that the project features are being developed to address identified user needs rather than adding functionality without a clear purpose.
