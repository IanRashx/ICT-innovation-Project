# Week 8 – Integration and System Testing

**Member:** Vilan Nethaka  
**Role:** Toolkit / Integration

---

## 1. Purpose

The purpose of integration testing is to verify that independently
developed Agent Resilience components can exchange information and operate
together correctly.

The proposed workflow is:

Test Configuration
→ Attack Testing
→ Target LLM / AI Agent
→ Defence / Resilience Controls
→ Response Collection
→ Evaluation
→ Security Findings

Only currently available components will be included in executable
integration tests.

---

## 2. Integration Areas

Important integration points include:

### Test Input to Attack Module

The testing component must receive the required test identifier, category
and prompt/input.

### Attack Module to Target Model

The approved test input must be passed to the target model/system using
the expected configuration.

### Defence Component

Where an implemented defence component is available, its detection or
protection outcome should be recorded.

### Response Collection

The workflow should capture relevant model/system behaviour and test
outcomes.

### Evaluation

Recorded results should contain enough information for the agreed quality
metrics to be calculated.

---

## 3. Common Result Structure

A common result structure may include:

```text
test_id
test_category
prompt
expected_outcome
model_response
detection_outcome
protection_outcome
attack_outcome
execution_status
response_time
