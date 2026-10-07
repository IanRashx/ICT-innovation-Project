# Week 8 – Defence and Resilience Testing

**Member:** Shalitha Pramod Perera  
**Role:** Blue Team / Defence

---

## 1. Purpose

The purpose of defence testing is to evaluate whether implemented
resilience controls reduce the success of adversarial inputs while
allowing legitimate prompts to continue operating.

The project has identified potential resilience areas including:

- prompt filtering;
- jailbreak detection;
- tool/action restrictions; and
- monitoring and detection.

Only controls that are actually implemented will be treated as executable
test targets.

---

## 2. Defence Testing Objectives

The testing process should determine:

1. whether suspicious inputs are detected;
2. whether the intended protection behaviour is activated;
3. whether legitimate prompts remain usable;
4. whether security controls introduce unacceptable processing delay; and
5. whether the behaviour is repeatable across the agreed test set.

---

## 3. Test Approach

### Adversarial Input Testing

Approved adversarial prompts will be executed against the available
defence mechanism.

For each test, the following should be recorded:

- input category;
- expected detection result;
- actual detection result;
- protection/control behaviour;
- model/system response; and
- pass/fail result.

### Benign Input Testing

Legitimate prompts will also be tested.

The purpose is to determine whether the defence mechanism incorrectly
blocks legitimate input.

This supports measurement of benign prompt acceptance.

---

## 4. Quality Targets

The defence-testing process contributes to the following project targets:

| Metric | Target |
|---|---:|
| Jailbreak detection rate | >= 80% |
| Benign prompt acceptance | >= 90% |
| Detection processing time | <= 2 seconds |
| Planned evaluation test completion without application failure | >= 95% |

---

## 5. Pass/Fail Approach

A test passes when the observed behaviour matches the expected behaviour
defined in the test case.

A failed test should be recorded rather than removed.

Failed tests should be reviewed to determine whether the cause relates to:

- detection logic;
- configuration;
- integration;
- incorrect test expectations; or
- another technical defect.

---

## 6. Regression Testing

After a defence-related change or defect fix, the relevant test cases
should be executed again.

Regression testing is used to verify that:

- the identified issue has been addressed; and
- the change has not broken previously working behaviour.

---

## 7. Evidence

Testing evidence may include:

- test result files;
- logs;
- screenshots;
- comparison summaries; and
- GitHub commits.

---

## 8. Week 8 Outcome

The Week 8 defence-testing plan establishes how available resilience
controls will be evaluated using both adversarial and benign inputs.

Actual effectiveness claims will only be made after the relevant controls
have been implemented and tested.
