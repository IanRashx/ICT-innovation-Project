# Week 6 – Defence and Resilience Strategy

**Project:** Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware  
**Member:** Shalitha Pramod Perera  
**Role:** Blue Team / Defence

## 1. Purpose

The defence component investigates how the system can identify, restrict, or respond to potentially adversarial interactions.

The objective is not only to reduce successful attacks but also to maintain acceptable behaviour for legitimate prompts.

## 2. Proposed Defence Areas

The project architecture considers several possible resilience controls:

### Prompt Filtering

Prompt filtering can analyse incoming prompts before they are passed to the target AI system.

The objective is to identify suspicious or known adversarial input patterns.

### Jailbreak Detection

A detection component can classify whether an input shows characteristics associated with jailbreak attempts.

The project requirement targets measurable detection effectiveness on an agreed evaluation dataset.

### Tool and Action Restrictions

For AI agents with access to tools or actions, restrictions can reduce the impact of malicious or manipulated instructions.

Possible controls include limiting permitted operations and applying validation before sensitive actions are executed.

### Monitoring and Detection

Monitoring can record relevant model or agent behaviour during testing.

This can provide evidence for identifying abnormal behaviour and supporting later evaluation.

## 3. Evaluation of Defence

A defence should not be evaluated only by whether attacks are blocked.

The project also considers the effect of controls on legitimate use.

Relevant measures include:

- jailbreak detection rate;
- attack success rate;
- refusal behaviour;
- benign prompt acceptance; and
- system reliability.

## 4. Current Status

The defence architecture and relevant resilience controls are being defined as part of the wider project design.

Controls that have not yet been implemented should be treated as proposed controls rather than completed technical features.

## 5. Integration with Testing

The proposed workflow is:

Input Prompt  
→ Defence / Detection Control  
→ Target Model or Agent  
→ Behaviour Collection  
→ Evaluation

The defence component will need to integrate with both the attack-testing and evaluation components so that protected and unprotected behaviour can be compared consistently.

## 6. Week 6 Outcome

Week 6 work establishes how defensive controls can contribute to the modular Agent Resilience testing architecture and identifies the metrics required to evaluate whether those controls improve resilience without excessively affecting legitimate prompts.
