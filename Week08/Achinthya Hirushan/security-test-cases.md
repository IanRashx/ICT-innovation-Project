# Week 8 – Security Test Cases

**Member:** Achinthya Hirushan  
**Role:** Red Team / Adversarial Testing

---

## 1. Purpose

The purpose of the security-testing activity is to define repeatable test
cases for evaluating the behaviour of the target model/system when
processing benign and adversarial inputs.

The testing remains restricted to the authorised local project
environment.

---

## 2. Test Categories

The test set should contain two main categories.

### Benign Tests

Benign tests contain legitimate prompts that should be accepted and
processed normally.

These tests help determine whether security controls unnecessarily block
legitimate user requests.

### Adversarial Tests

Adversarial tests contain approved jailbreak-style or security-testing
inputs intended to evaluate the resilience of the target model/system.

These tests are executed only within the authorised project environment.

---

## 3. Test Case Structure

Each security test should record:

| Field | Description |
|---|---|
| Test ID | Unique identifier |
| Category | Benign or adversarial |
| Test objective | What the test evaluates |
| Input | Approved test prompt/input |
| Expected outcome | Expected system behaviour |
| Actual outcome | Behaviour observed during execution |
| Detection outcome | Whether suspicious input was detected |
| Protection outcome | Whether an available control was triggered |
| Pass/Fail | Comparison against expected outcome |
| Evidence | Result file, screenshot or log |

---

## 4. Example Test Definitions

### TC-01 – Benign Prompt Processing

**Objective:** Verify that a legitimate prompt can be processed normally.

**Category:** Benign

**Expected outcome:**  
The prompt should not be classified as a jailbreak and should continue
through the normal test workflow.

---

### TC-02 – Approved Adversarial Prompt

**Objective:** Evaluate whether an approved jailbreak-style input is
identified by the available detection process.

**Category:** Adversarial

**Expected outcome:**  
The system should identify the input as suspicious when the implemented
detection mechanism is designed to detect that attack category.

---

### TC-03 – Repeated Test Execution

**Objective:** Determine whether the same test procedure can be executed
consistently.

**Expected outcome:**  
The test should complete without application failure and generate the
required result fields.

---

### TC-04 – Result Recording

**Objective:** Verify that the testing workflow records sufficient
evidence.

**Expected outcome:**  
The result should include the test identifier, input category, model
response, relevant classification/outcome and execution status.

---

## 5. Evidence Requirements

Executed tests should provide evidence through one or more of:

- structured result files;
- application/test logs;
- terminal output;
- screenshots; or
- GitHub commits containing the relevant technical output.

A screenshot alone should not replace the original result file where a
machine-readable output is available.

---

## 6. Next Actions

The next steps are to:

1. finalise the approved test dataset;
2. execute the agreed test cases;
3. record results using a consistent format;
4. provide outputs for metric calculation; and
5. re-run relevant tests after technical changes.

---

## 7. Week 8 Outcome

Week 8 establishes the security test-case structure that can be used for
repeatable adversarial and benign testing during subsequent project work.
