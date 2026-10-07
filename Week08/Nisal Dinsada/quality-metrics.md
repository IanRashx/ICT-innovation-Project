# Week 8 – Quality Metrics and Evaluation

**Member:** Nisal Dinsada  
**Role:** Evaluation and Metrics

---

## 1. Purpose

The purpose of this document is to define measurable quality metrics for
evaluating the Agent Resilience project.

Measurable metrics allow the team to compare observed technical behaviour
against agreed project targets.

---

## 2. Jailbreak Detection Rate

Jailbreak Detection Rate measures how many labelled jailbreak/adversarial
test inputs are correctly identified.

Formula:

Jailbreak Detection Rate =
(Number of correctly detected jailbreak prompts / Total labelled jailbreak prompts tested) x 100

**Target: >= 80%**

---

## 3. Benign Prompt Acceptance Rate

Benign Prompt Acceptance Rate measures whether legitimate prompts continue
to operate when security controls are enabled.

Formula:

Benign Prompt Acceptance Rate =
(Number of benign prompts accepted / Total benign prompts tested) x 100

**Target: >= 90%**

---

## 4. Attack Success Rate (ASR)

Attack Success Rate measures the proportion of adversarial test attempts
that achieve the defined attack-success condition.

Formula:

ASR =
(Successful adversarial test outcomes / Total adversarial attempts) x 100

The interpretation of ASR depends on the agreed test dataset and attack
success definition.

ASR results should therefore be reported within the scope of the tested
dataset rather than treated as a universal model-security score.

---

## 5. Detection Processing Time

Detection processing time measures the time required for the project's
detection/protection process.

**Target: <= 2 seconds**

External model or API response time is excluded from this measurement.

Multiple executions should be recorded where practical rather than relying
on a single timing measurement.

---

## 6. System Reliability

Reliability measures the percentage of planned evaluation test cases that
complete without application failure.

Formula:

Reliability =
(Number of evaluation tests completed without application failure /
Total planned evaluation tests executed) x 100

**Target: >= 95%**

---

## 7. Refusal Behaviour

Refusal behaviour records whether the model refuses or otherwise prevents
completion of an adversarial request.

Refusal results can be compared between baseline and modified/protected
configurations where applicable.

Refusal behaviour should not be treated as the only measure of security;
it should be interpreted together with detection and attack outcomes.

---

## 8. Result Interpretation

A result should include enough information to identify:

- test ID;
- test category;
- expected result;
- actual result;
- metric contribution;
- pass/fail status; and
- supporting evidence.

Results that do not meet the target should be recorded and investigated
rather than excluded.

---

## 9. Week 8 Outcome

The Week 8 quality-metrics definition provides measurable criteria for
evaluating the security, performance and reliability of the available
Agent Resilience components.

These metrics will be applied to actual test outputs as technical testing
progresses.
