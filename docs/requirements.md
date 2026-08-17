# Agent Resilience – Preliminary Requirements

## Document Status

These requirements are preliminary Week 2 requirements.

They will be reviewed and updated after discussion with the tutor/client.

---

# Functional Requirements

Functional requirements describe what the proposed system should do.

---

## FR1 – Submit Test Prompts

The system shall allow a user to submit normal and adversarial prompts to an AI
agent for testing.

### Purpose

This allows AI agent behaviour to be evaluated under different conditions.

---

## FR2 – Identify Potential Jailbreak Attempts

The system shall analyse submitted prompts and identify potentially malicious
or jailbreak-style inputs.

### Purpose

This provides a way to recognise prompts that may attempt to manipulate the AI
agent.

---

## FR3 – Apply a Resilience Mechanism

The system shall apply an appropriate resilience or protection mechanism when
suspicious input is identified.

Possible approaches may include:

- Input filtering.
- Prompt classification.
- Rule-based detection.
- Prompt sanitisation.
- Output checking.
- Secondary verification.

The final approach has not yet been selected.

---

## FR4 – Record and Display Test Results

The system shall record relevant information from each test.

This may include:

- Prompt.
- Prompt category.
- Detection result.
- AI response.
- Attack success or failure.
- Processing time.
- Resilience outcome.

---

# Preliminary Non-Functional Requirements

The following measurements are proposed targets and must be confirmed with the
client.

---

## NFR1 – Detection Processing Time

The prompt detection component should classify an input within approximately:

**2 seconds**

This measurement excludes external AI model/API response time.

---

## NFR2 – Detection Performance

The prototype should aim to correctly identify at least:

**80% of jailbreak prompts**

within the agreed evaluation dataset.

---

## NFR3 – Legitimate Prompt Handling

At least:

**90% of approved benign prompts**

should continue to be processed successfully while the resilience mechanism is
enabled.

---

## NFR4 – System Reliability

The prototype should successfully complete at least:

**95% of planned evaluation test cases**

without an application failure.

---

# Proposed Features

## Feature 1 – AI Testing Environment

A controlled environment where normal and adversarial prompts can be submitted
to an AI agent.

### Related Need

Need 1 – Agent Reliability

---

## Feature 2 – Jailbreak Detection

A component that analyses prompts and identifies potentially suspicious inputs.

### Related Need

Need 2 – Identification of Suspicious Interactions

---

## Feature 3 – Resilience Mechanism

A mechanism for safely handling potentially malicious prompts.

### Related Need

Need 3 – Reduction of Attack Impact

---

## Feature 4 – Evaluation Component

A component that records and calculates results from AI resilience testing.

### Related Need

Need 4 – Resilience Measurement

---

## Feature 5 – Safe Fallback

A possible fallback mechanism that allows the agent to continue operating safely
after suspicious activity is identified.

### Related Need

Need 5 – Continued Legitimate Use

---

# Possible Evaluation Metrics

The following metrics are being considered.

## Attack Success Rate

Measures how many jailbreak attempts successfully manipulate the AI agent.

Attack Success Rate:

Successful Jailbreaks / Total Jailbreak Attempts × 100

---

## Detection Rate

Measures how many jailbreak prompts are correctly identified.

Detection Rate:

Correctly Detected Attacks / Total Attacks × 100

---

## False Positive Rate

Measures how many normal prompts are incorrectly classified as attacks.

---

## Benign Prompt Success Rate

Measures whether legitimate prompts continue to work when protection is
enabled.

---

## Response Time

Measures the time required to analyse and process an interaction.

---

## Recovery Rate

A potential metric for measuring whether the AI agent returns to its expected
behaviour after being exposed to an adversarial interaction.
