# Week 6 – Attack Testing

**Project:** Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware  
**Member:** Achinthya Hirushan  
**Role:** Red Team / Jailbreak Testing

## 1. Purpose

The red-team component investigates how adversarial inputs can affect the behaviour of AI models and agents.

The purpose is to provide controlled attack scenarios that can be used to evaluate the resilience of the target system.

All testing is intended to remain within the authorised project environment.

## 2. Attack Testing Approach

The project considers multiple AI attack surfaces.

These include:

- model-layer security testing;
- adversarial and jailbreak prompts;
- prompt-layer attacks;
- agent/tool-related attacks where applicable; and
- other authorised security tests within project scope.

Not all attack categories are currently implemented. They represent areas that may contribute to the modular testing architecture.

## 3. Current Model-Layer Work

The current technical work includes model-layer experimentation using a small open-weight language model.

The experimental workflow allows model behaviour to be observed under controlled testing conditions.

A baseline configuration is important because it provides a reference point for later comparison with modified model behaviour.

## 4. Adversarial Testing

Adversarial testing uses selected prompts designed to evaluate whether the target model maintains expected security behaviour.

Relevant observations can include:

- whether the model accepts or rejects an adversarial request;
- changes in refusal behaviour;
- whether a jailbreak attempt succeeds;
- differences between baseline and modified model behaviour; and
- consistency across repeated tests.

## 5. Evidence Collection

Testing evidence should be stored in a structured and reproducible form.

Evidence may include:

- test prompts;
- model responses;
- experiment output files;
- screenshots where appropriate;
- comparison summaries; and
- GitHub commits containing test-related work.

## 6. Integration Requirement

The attack-testing component should eventually provide structured test inputs and results that can be passed to the evaluation component.

This requires a consistent format for:

1. test identification;
2. prompt/input;
3. target configuration;
4. response;
5. attack outcome; and
6. relevant metadata.

## 7. Week 6 Outcome

Week 6 work contributes to defining how red-team testing fits within the broader Agent Resilience architecture and how attack results can be recorded for later security evaluation.

Any attack technique that has not yet been implemented remains a proposed part of the wider architecture rather than a completed feature.
