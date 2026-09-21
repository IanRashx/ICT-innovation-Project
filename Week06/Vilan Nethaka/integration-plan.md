# Week 6 – Toolkit Integration Plan

**Project:** Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware  
**Member:** Vilan Nethaka  
**Role:** Toolkit / Integration

## 1. Purpose

The integration component focuses on how independently developed project components can operate as part of a common security-testing workflow.

The project is intended to remain modular so individual attack, defence, and evaluation components can be developed and tested separately before broader integration.

## 2. Proposed Architecture

The proposed high-level workflow is:

AI Security Researcher  
→ Test Configuration and Dataset  
→ Attack Module  
→ Target LLM / AI Agent  
→ Defence / Resilience Controls  
→ Response and Behaviour Collection  
→ Evaluation Engine  
→ Security Findings

The technical workflow is intended to operate within a local and controlled testing environment.

## 3. Integration Requirements

To integrate different components successfully, the project needs consistent interfaces.

Important requirements include:

- common test-input structure;
- consistent output/result format;
- predictable file and folder structure;
- documented setup instructions;
- clear module dependencies; and
- reproducible execution procedures.

## 4. Proposed Result Format

Structured data formats such as JSON or JSONL can be used to exchange test results between modules.

A result may contain fields representing:

- test ID;
- attack category;
- prompt/input;
- target model;
- model response;
- attack outcome;
- detection outcome;
- refusal behaviour; and
- execution status.

The final structure should be agreed by the team before integration.

## 5. Local Execution

The project is designed around local execution using commodity hardware.

Relevant environment components include:

- Windows;
- portable Python where required;
- small open-weight AI models;
- local project scripts and dependencies; and
- private version control for project artefacts.

This approach supports the client's requirement for controlled testing and reduces dependence on paid external AI APIs.

## 6. Current Integration State

The project currently contains technical experimentation and separately defined attack, defence, and evaluation responsibilities.

Full integration of all proposed modules is not considered complete at this stage.

The immediate integration priority is therefore to establish consistent interfaces and evidence formats before connecting independently developed components.

## 7. Main Integration Risk

A major technical risk is that independently developed components may use different input/output formats or environment assumptions.

This could increase integration time and require rework.

The mitigation approach is to:

1. agree on common data formats;
2. document module dependencies;
3. maintain a consistent repository structure;
4. test modules independently;
5. integrate incrementally; and
6. record reproducible setup and execution instructions.

## 8. Week 6 Outcome

Week 6 integration planning establishes a common technical direction for connecting the project's attack, defence, response-collection, and evaluation components.

The plan supports the architectural innovation approach by focusing on how existing technologies and project components can work together as a coherent security-testing toolkit.
