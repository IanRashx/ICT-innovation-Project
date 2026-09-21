# Week 6 – Evaluation Metrics

**Project:** Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware  
**Member:** Nisal Dinsada  
**Role:** Evaluation and Metrics

## 1. Purpose

The evaluation component provides measurable evidence for comparing AI security behaviour.

Rather than relying only on subjective observations, the project aims to use defined metrics to evaluate attack outcomes, defensive effectiveness, legitimate prompt handling, and system reliability.

## 2. Attack Success Rate (ASR)

Attack Success Rate measures the proportion of adversarial test attempts that successfully produce the defined undesirable outcome.

ASR can be expressed as:

ASR = (Successful Adversarial Attacks / Total Adversarial Attack Attempts) × 100

A lower ASR after applying an effective resilience control may indicate improved resistance within the tested dataset.

Results should only be interpreted within the scope of the selected test set and experimental configuration.

## 3. Jailbreak Detection Rate

Jailbreak Detection Rate measures the proportion of agreed jailbreak prompts correctly identified by the detection process.

The project requirement targets:

**Jailbreak Detection Rate ≥ 80%**

This should be evaluated using the agreed project test dataset.

## 4. Benign Prompt Acceptance

Benign Prompt Acceptance measures whether legitimate prompts continue to function when resilience controls are enabled.

The project requirement targets:

**Benign Prompt Acceptance ≥ 90%**

This is important because an overly restrictive security mechanism may block attacks while also preventing legitimate use.

## 5. System Reliability

System reliability measures the proportion of planned evaluation test cases that complete without application failure.

The project requirement targets:

**System Reliability ≥ 95%**

This provides an indication of whether the testing workflow can operate consistently during evaluation.

## 6. Refusal Behaviour

Refusal behaviour records whether the target model refuses or complies with selected test requests.

This can be compared across:

- baseline behaviour;
- modified model behaviour; and
- protected configurations where applicable.

Refusal behaviour provides additional context alongside quantitative metrics such as ASR.

## 7. Result Structure

For reproducible evaluation, each test result should ideally record:

- test identifier;
- test category;
- prompt/input;
- target model or configuration;
- model response;
- detected/not detected outcome where applicable;
- attack success/failure outcome;
- refusal/compliance behaviour; and
- execution status.

Structured formats such as JSON or JSONL can support later automated analysis.

## 8. Week 6 Outcome

The Week 6 evaluation work defines how project requirements can be translated into measurable technical outcomes.

These metrics provide a common basis for comparing results produced by different parts of the Agent Resilience testing workflow.
