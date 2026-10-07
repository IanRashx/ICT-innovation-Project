# Week 8 – Team Meeting Minutes

**Project:** Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware  
**Unit:** ICT30016 – ICT Innovation Project  
**Group:** LLM11  
**Week:** 8  
**Date:** 02/10/2026  
**Workshop:** Friday 12:30–2:30 PM  
**Meeting Lead:** Ian Rashmika  
**Client:** Swinburne Cybersecurity Lab  

---

## 1. Members Present

- Ian Rashmika
- Achinhya Hirushan
- Shalitha Pramod Perera
- Nisal Dinsada
- Vilan Nethaka

---

## 2. Meeting Purpose

The purpose of the Week 8 meeting was to develop a Testing and Quality
Assurance (QA) plan for the Agent Resilience project.

The team reviewed the main project features, identified measurable quality
expectations, discussed preventive QA and detective QC approaches, and
allocated testing responsibilities across the team.

The meeting also reviewed the gaps identified during Week 7 and considered
how testing can provide evidence that those gaps are being addressed.

---

## 3. Review of Week 7 Actions

The team reviewed the main gaps and actions identified during Week 7.

The areas requiring continued attention include:

- reproducibility of the local testing environment;
- standardisation of adversarial and benign test cases;
- defence/resilience testing;
- consistent application of evaluation metrics;
- integration between independently developed components; and
- consolidation of technical evidence.

These areas were used to guide the Week 8 testing and QA plan.

---

## 4. Features Selected for Testing

The team identified the following areas for QA and testing:

1. Test prompt submission and execution
2. Jailbreak/adversarial prompt detection
3. Available defence and resilience controls
4. Benign prompt handling
5. Test result and response recording
6. Detection performance and system reliability

The team agreed that components that have not yet been implemented will
remain outside executable testing until they become available.

---

## 5. Agreed Quality Targets

The team reviewed the existing project requirements and selected measurable
targets for testing.

| Quality Measure | Target |
|---|---:|
| Jailbreak detection rate | >= 80% |
| Benign prompt acceptance rate | >= 90% |
| Detection processing time | <= 2 seconds |
| Planned evaluation test completion without application failure | >= 95% |

Detection processing time excludes external model/API response time.

The team agreed that these targets should be evaluated using recorded test
results rather than subjective assessment.

---

## 6. Quality Assurance Approach

The team discussed preventive QA activities intended to reduce defects
before technical testing.

The agreed QA approaches include:

- use of standardised test-case templates;
- use of a common test-result structure;
- documentation of expected outcomes before execution;
- peer review of important test cases and technical changes;
- incremental integration rather than waiting until the end of development;
- maintenance of technical evidence through GitHub.

These activities are intended to improve consistency and reproducibility.

---

## 7. Quality Control Approach

The team also discussed detective QC activities used to identify defects
in implemented components.

The agreed QC activities include:

- functional testing;
- adversarial/security testing;
- integration testing;
- system testing;
- performance testing;
- comparison of actual results against expected outcomes; and
- regression testing after changes or defect fixes.

Failed tests will be recorded and investigated rather than removed from
the evaluation evidence.

---

## 8. Test Evidence Requirements

The team agreed that technical testing should produce accessible evidence.

Evidence may include:

- structured test-result files;
- terminal/test execution output;
- logs;
- comparison summaries;
- screenshots;
- GitHub commits; and
- supporting technical documentation.

Where a machine-readable result file exists, it should be retained rather
than relying only on a screenshot.

---

## 9. Testing Responsibilities

| Member | Responsibility |
|---|---|
| **Ian Rashmika** | Coordinate QA planning, monitor testing progress, maintain meeting documentation and consolidate project evidence |
| **Achinthya Hirushan** | Prepare adversarial and benign security test cases and support attack-testing activities |
| **Shalitha Pramod Perera** | Define and perform testing for available defence/resilience controls |
| **Nisal Dinsada** | Define quality metrics and evaluate recorded test results |
| **Vilan Nethaka** | Define integration/system-testing approach and support component integration |

The responsibilities were divided according to the existing project roles
to maintain a balanced workload.

---

## 10. Testing Workflow

The team agreed to follow the general testing process:

**Requirements and Quality Targets**  
↓  
**Create Test Cases**  
↓  
**Execute Tests**  
↓  
**Record Results**  
↓  
**Compare Results Against Targets**  
↓  
**Identify Defects**  
↓  
**Fix / Improve**  
↓  
**Regression Test**

If the relevant test passes and the required evidence is available, the
feature can proceed toward acceptance.

---

## 11. Definition of Done

The team agreed that a feature should not be considered complete only
because implementation has been finished.

A feature is considered complete when:

1. the implementation is available in the project repository;
2. required test cases have been executed;
3. actual and expected outcomes have been compared;
4. applicable quality targets have been checked;
5. critical defects have been resolved or documented;
6. evidence has been recorded; and
7. the feature can be reviewed or reproduced using the available
   documentation.

---

## 12. Decisions Made

The team agreed to:

- use measurable quality targets during evaluation;
- standardise test-case and result-recording formats;
- test both benign and adversarial inputs;
- clearly separate implemented features from proposed features;
- perform integration incrementally;
- retain failed test results as evidence;
- perform regression testing following significant changes;
- keep sensitive testing within the authorised local/controlled
  environment; and
- maintain individual GitHub evidence for Week 8 contributions.

---

## 13. Actions Before Next Workshop

| Owner | Action | Due |
|---|---|---|
| **Ian** | Review testing progress and consolidate QA documentation and evidence | Before Week 9 workshop |
| **Achinthya** | Finalise agreed benign/adversarial security test cases and prepare them for execution | Before Week 9 workshop |
| **Shalitha** | Prepare and execute testing for available defence/resilience control(s) | Before Week 9 workshop |
| **Nisal** | Prepare metric calculations and apply them to available test outputs | Before Week 9 workshop |
| **Vilan** | Progress integration testing and verify the common input/output structure | Before Week 9 workshop |

---

## 14. Current Blockers and Risks

The main technical challenge remains integration between independently
developed project components.

Potential testing risks include:

- inconsistent test-result formats;
- incomplete integration;
- differences in local environment configuration;
- insufficient test evidence;
- false positives when testing benign prompts;
- inconsistent interpretation of adversarial test outcomes; and
- limited time remaining for regression testing after integration.

The team agreed to reduce these risks through standardised test cases,
common result formats, incremental integration and regular review of test
evidence.

---

## 15. Week 8 GitHub Evidence

The following Week 8 documentation will be maintained in the project
repository:

- `Week08/Ian Rashmika/qa-plan.md`
- `Week08/Ian Rashmika/meeting-minutes.md`
- `Week08/Achinthya Hirushan/security-test-cases.md`
- `Week08/Shalitha Pramod Perera/defence-testing.md`
- `Week08/Nisal Dinsada/quality-metrics.md`
- `Week08/Vilan Nethaka/integration-testing.md`

Additional technical evidence will be added to the Week 8 evidence folder
when the corresponding tests are executed.

---

## 16. Next Meeting Focus

The next project review will focus on:

- security test execution;
- available defence-control testing;
- application of agreed quality metrics;
- integration-testing progress;
- failed tests and identified defects;
- regression-testing requirements; and
- evidence of individual technical contributions.
