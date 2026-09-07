# Week 5 – Requirements Review

## Project
Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware

## Purpose

The purpose of this review is to examine the functional and non-functional requirements established during Week 2 and determine whether they remain appropriate as the project moves towards implementation.

The review focuses particularly on jailbreak detection, protection mechanisms, usability and reliability.

---

# Functional Requirements Review

## FR1 – Submit Test Prompts

### Requirement

The system shall allow a user to submit normal and adversarial prompts to an AI agent for testing.

### Review

This requirement remains necessary because the project requires controlled comparison between legitimate and adversarial interactions.

Supporting both types of prompts allows the team to evaluate security without focusing only on malicious behaviour.

### Status

**Retain**

---

# FR2 – Detect Potential Jailbreaks

### Requirement

The system shall analyse submitted prompts and identify potentially malicious or jailbreak-style inputs.

### Review

This remains a core security requirement.

A resilience mechanism needs a way to distinguish potentially dangerous interactions from legitimate requests.

The detection mechanism should also be evaluated quantitatively rather than relying only on manual observations.

### Related NFRs

- NFR1 – Detection Response Time
- NFR2 – Detection Effectiveness

### Status

**Retain**

---

# FR3 – Apply Protection

### Requirement

The system shall apply a resilience or protection mechanism when suspicious input is identified.

### Review

Detection alone does not improve resilience unless the system can respond appropriately.

The protection mechanism could involve blocking, filtering, refusing or safely handling suspicious input depending on the final implementation.

However, protection should not unnecessarily interfere with legitimate prompts.

### Related NFR

- NFR3 – Benign Prompt Acceptance

### Status

**Retain**

---

# FR4 – Record and Display Results

### Requirement

The system shall record the submitted prompt, classification, AI response and attack outcome and make the results available for evaluation.

### Review

This requirement is important because the project needs measurable evidence.

Recording results enables comparison between:

- normal and adversarial prompts;
- protected and unprotected configurations;
- different model configurations;
- successful and unsuccessful attacks.

### Related NFR

- NFR4 – System Reliability

### Status

**Retain**

---

# Non-Functional Requirements Review

## NFR1 – Detection Response Time

### Target

Detection should complete within **2 seconds**, excluding external LLM/API response time.

### Review

This target remains relevant because an excessively slow detection mechanism could reduce practical usability.

### Status

**Retain**

---

# NFR2 – Detection Effectiveness

### Target

The system should detect at least **80% of jailbreak prompts** in the agreed evaluation dataset.

### Review

This provides a measurable baseline for evaluating the effectiveness of the detection mechanism.

The result should be interpreted within the limits of the selected evaluation dataset.

### Status

**Retain**

---

# NFR3 – Benign Prompt Acceptance

### Target

At least **90% of approved legitimate prompts** should continue to be processed correctly when protection is enabled.

### Review

This requirement is important because an overly aggressive defence could achieve security by blocking legitimate requests.

The project therefore needs to measure security and usability together.

### Status

**Retain**

---

# NFR4 – System Reliability

### Target

At least **95% of planned evaluation test cases** should complete without application failure.

### Review

A reliable testing process is required so that attack and defence results can be compared meaningfully.

Failures caused by the testing environment should be distinguished from genuine security results.

### Status

**Retain**

---

# Key Implementation Considerations

The requirements review identified several important implementation considerations.

## 1. Security and Usability Balance

The system should not maximise security by simply rejecting every prompt.

Jailbreak detection must therefore be evaluated alongside benign prompt acceptance.

## 2. Measurable Evaluation

Security decisions should be supported by measurable metrics such as:

- Jailbreak Detection Rate
- Attack Success Rate (ASR)
- Refusal Rate
- Benign Prompt Acceptance Rate
- System Reliability

## 3. Reproducibility

Testing configurations, prompts and results should be documented so that experiments can be repeated.

## 4. Protection Behaviour

The final protection mechanism should have clearly defined behaviour when suspicious input is detected.

## 5. Scope Control

New requirements should not be introduced unless they can be connected to an identified stakeholder need or agreed project objective.

---

# Review Outcome

All four existing functional requirements and four non-functional requirements remain relevant to the Agent Resilience project.

No additional FR5 or FR6 is proposed at this stage.

Additional requirements should only be introduced where a clear stakeholder need or implementation requirement is identified.
