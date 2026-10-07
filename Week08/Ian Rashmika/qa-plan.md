# Week 8 – Testing and Quality Assurance Plan

**Member:** Ian Rashmika  
**Role:** Project Lead / Coordination  
**Project:** Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware

---

## 1. Purpose

The purpose of the Week 8 QA plan is to establish a consistent approach
for verifying the quality of the Agent Resilience project.

The project requires both functional testing and security-focused testing
because the system is intended to evaluate AI-agent resilience against
adversarial and jailbreak-style inputs.

The QA plan focuses on measurable requirements, repeatable testing,
documented results and clear responsibilities.

---

## 2. Features to be Evaluated

The current testing scope includes:

1. Test prompt submission and execution
2. Jailbreak/adversarial prompt detection
3. Available defence/resilience controls
4. Benign prompt handling
5. Response and test-result recording
6. Detection performance and system reliability

Components that are only proposed and have not yet been implemented will
not be reported as successfully tested.

---

## 3. Quality Targets

The project will use the following agreed quality targets:

| Quality Area | Target |
|---|---:|
| Jailbreak detection rate | >= 80% |
| Benign prompt acceptance | >= 90% |
| Detection processing time | <= 2 seconds |
| Evaluation test completion without application failure | >= 95% |

Detection processing time excludes external model/API response time.

---

## 4. Quality Assurance – Preventive Activities

Quality Assurance focuses on preventing defects before testing.

### Standardised Test Cases

The team will use a common test-case structure containing:

- test ID;
- test objective;
- input/prompt;
- expected outcome;
- actual outcome;
- pass/fail result; and
- supporting evidence.

### Common Result Structure

Where possible, test outputs will use a common structured format so that
results from different modules can be compared consistently.

JSON or JSONL may be used for structured technical results.

### Peer Review

Important test cases, technical documentation and integration changes
should be reviewed by another team member before being treated as final.

---

## 5. Quality Control – Detective Activities

Quality Control focuses on identifying defects in implemented components.

QC activities include:

- executing functional test cases;
- executing adversarial/security test cases;
- checking actual results against expected outcomes;
- recording failed tests;
- regression testing after changes; and
- verifying resolved defects.

---

## 6. Testing Scope

### In Scope

- local Qwen/model-layer testing;
- approved benign prompts;
- approved adversarial/jailbreak prompts;
- available detection and resilience components;
- response/result recording;
- integration between available project modules;
- agreed security metrics; and
- performance/reliability testing that can be completed using available
  commodity hardware.

### Out of Scope

- attacks against unauthorised systems;
- testing against systems outside the project sandbox;
- commercial red-team platforms not required by the project;
- large-scale hardware benchmarking;
- claims about attack types that have not been tested; and
- proposed components that have not yet been implemented.

---

## 7. Definition of Done

A feature is considered complete when:

1. the implementation is available in the project repository;
2. required test cases have been executed;
3. actual outcomes have been compared with expected outcomes;
4. relevant quality targets have been checked;
5. critical defects have been resolved or documented;
6. test evidence has been recorded; and
7. another team member can review or reproduce the feature using the
   available documentation.

---

## 8. Week 8 Outcome

The Week 8 QA planning process establishes a measurable and repeatable
testing approach for the remaining project development.

The next stage is to execute the agreed test cases against available
components and record the resulting technical evidence.
