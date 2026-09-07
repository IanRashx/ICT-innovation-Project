# Week 5 – Critical Success Factors and KPIs

## Project
Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware

## Purpose

This document defines the Critical Success Factors (CSFs) and Key Performance Indicators (KPIs) that will be used to evaluate the Agent Resilience project.

The measures are based on the functional and non-functional requirements established during Week 2.

---

# Critical Success Factors

## CSF1 – Effective Jailbreak Detection

The project must demonstrate that potentially malicious or jailbreak-style prompts can be identified at a measurable level of effectiveness.

### Success Measure

The resilience prototype should correctly identify at least **80% of jailbreak prompts** in the agreed evaluation dataset.

---

## CSF2 – Security Without Excessive Loss of Utility

The protection mechanism should improve security without unnecessarily preventing legitimate users from interacting with the AI agent.

### Success Measure

At least **90% of approved legitimate prompts** should continue to be processed correctly while the resilience mechanism is enabled.

---

## CSF3 – Reliable and Reproducible Evaluation

The project should provide a sufficiently reliable testing process so that attack and defence behaviour can be measured and compared.

### Success Measure

At least **95% of planned evaluation test cases** should complete without application failure and produce usable results.

---

# KPI 1 – Jailbreak Detection Rate

## Indicator Name

**Jailbreak Detection Rate**

## Strategic Goal / CSF

**CSF1 – Effective Jailbreak Detection**

## Key Performance Question

How effectively does the resilience prototype identify known jailbreak prompts in the agreed evaluation dataset?

## Audience

- Project team
- Tutor / supervisor
- Authorised client/project stakeholders

## Data Collection Method

An agreed labelled dataset containing jailbreak/adversarial prompts will be submitted to the detection component.

The predicted classifications will be compared against the expected classifications.

## Calculation

Jailbreak Detection Rate:

**(Correctly detected jailbreak prompts / Total jailbreak prompts tested) × 100**

## Target

**≥80%**

## Review Frequency

The metric will be reviewed after each relevant evaluation cycle and during weekly project reviews.

## How This KPI Will NOT Be Used

This KPI will not be treated as proof that the system can detect every possible jailbreak technique.

Performance against the agreed evaluation dataset does not guarantee equivalent performance against previously unseen or substantially different attacks.

---

# KPI 2 – Benign Prompt Acceptance Rate

## Indicator Name

**Benign Prompt Acceptance Rate**

## Strategic Goal / CSF

**CSF2 – Security Without Excessive Loss of Utility**

## Key Performance Question

Does the resilience mechanism continue to allow legitimate prompts to operate correctly while security protection is enabled?

## Audience

- Project team
- Tutor / supervisor
- Authorised client/project stakeholders

## Data Collection Method

An approved set of legitimate prompts will be submitted while the resilience mechanism is enabled.

Each result will be recorded as either:

- correctly processed; or
- incorrectly blocked/rejected.

## Calculation

Benign Prompt Acceptance Rate:

**(Correctly processed legitimate prompts / Total legitimate prompts tested) × 100**

## Target

**≥90%**

## Review Frequency

Reviewed after each relevant defence evaluation cycle.

## How This KPI Will NOT Be Used

This KPI will not be used by itself to determine overall system security.

A system could achieve a high benign prompt acceptance rate while still failing to detect malicious prompts.

---

# Additional KPI 3 – Detection Response Time

## Purpose

Measure the time required for the detection component to classify a submitted prompt.

## Target

**≤2 seconds**

External LLM/API response time is excluded where applicable.

## Related Requirement

**NFR1 – Detection Response Time**

---

# Additional KPI 4 – System Reliability

## Purpose

Measure whether the evaluation workflow completes planned tests without application failure.

## Calculation

**System Reliability = (Successfully completed test cases / Total planned test cases) × 100**

## Target

**≥95%**

## Related Requirement

**NFR4 – System Reliability**

---

# Additional KPI 5 – Attack Success Rate (ASR)

## Purpose

Measure the proportion of adversarial attempts that achieve the predefined attack objective.

## Calculation

**ASR = (Successful attacks / Total attack attempts) × 100**

## Use

ASR can be used to:

- compare baseline and modified model behaviour;
- compare protected and unprotected configurations;
- quantify changes in resilience;
- evaluate attack effectiveness.

## Interpretation

A higher ASR indicates that a greater proportion of attack attempts achieved the defined objective.

ASR should be interpreted together with other measures such as refusal behaviour and benign prompt acceptance.

No arbitrary project-wide ASR target is assigned unless a suitable target is agreed for a specific experiment.

---

# KPI Summary

| KPI | Target / Measure | Related CSF / NFR |
|---|---|---|
| Jailbreak Detection Rate | ≥80% | CSF1 / NFR2 |
| Benign Prompt Acceptance Rate | ≥90% | CSF2 / NFR3 |
| Detection Response Time | ≤2 seconds | NFR1 |
| System Reliability | ≥95% | CSF3 / NFR4 |
| Attack Success Rate | Measured per experiment | Security evaluation |

---

## Conclusion

The selected KPIs allow the project to evaluate both security and usability.

Rather than measuring jailbreak detection alone, the project also considers legitimate prompt acceptance, reliability and attack success.

This provides a more balanced evaluation of Agent Resilience.
