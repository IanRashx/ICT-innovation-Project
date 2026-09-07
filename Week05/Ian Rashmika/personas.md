# Week 5 – User Personas

## Project
Agent Resilience – Attacking and Hardening LLM Agents on Commodity Hardware

## Purpose

The purpose of this document is to define two primary user personas for the Agent Resilience project.

During Week 2, the team identified AI developers, AI security researchers and cybersecurity researchers as the main users of the proposed solution. The following personas represent two users with different roles and requirements.

---

# Persona 1 – AI Security Researcher

## Name and Demographics

**Name:** Dr Sarah Chen  
**Role:** AI Security Researcher  
**Age Range:** 35–45

## Background

Sarah works in AI and cybersecurity research and evaluates the resilience of language models and AI agents against jailbreak and adversarial prompts.

She has experience with AI security testing, security benchmarks and experimental evaluation.

## Goals

- Test AI agents using legitimate and adversarial prompts.
- Identify successful jailbreak attempts.
- Measure Attack Success Rate (ASR).
- Analyse refusal behaviour.
- Compare model resilience before and after protection.
- Obtain reproducible experimental evidence.

## Challenges / Pain Points

- Jailbreak techniques continue to change and can be difficult to detect consistently.
- Different model configurations can produce different security behaviour.
- Security evaluation can become subjective without clearly defined metrics.
- Large numbers of test prompts can make manual evaluation difficult.
- Experimental results need to be recorded consistently for comparison.

## Technology Proficiency

**High**

Sarah is familiar with:

- Large Language Models (LLMs)
- AI security testing
- Python
- Security benchmarks
- Jailbreak testing
- Evaluation metrics
- Cybersecurity concepts

## Motivations

Sarah wants reliable evidence about whether an AI model or agent remains resilient when exposed to adversarial inputs.

She wants security conclusions to be supported by measurable experimental results rather than subjective observations.

## Behavioural Traits

- Analytical
- Evidence-driven
- Security-conscious
- Methodical
- Research-focused
- Interested in measurable results

---

# Persona 2 – AI Developer

## Name and Demographics

**Name:** Alex Morgan  
**Role:** AI Developer  
**Age Range:** 25–35

## Background

Alex develops and integrates LLM-based applications.

Alex is responsible for maintaining useful AI behaviour while reducing security risks caused by malicious or adversarial prompts.

## Goals

- Implement practical protection against suspicious prompts.
- Detect potential jailbreak attempts.
- Reduce successful manipulation of AI agents.
- Maintain legitimate AI functionality.
- Evaluate whether protection mechanisms improve resilience.
- Maintain a reliable testing workflow.

## Challenges / Pain Points

- Strong protection may incorrectly block legitimate prompts.
- Weak protection may fail to stop sophisticated jailbreak attempts.
- Security controls may reduce the usefulness of the AI application.
- Different models may respond differently to the same protection mechanism.
- Security and usability need to remain balanced.

## Technology Proficiency

**Very High**

Alex is comfortable with:

- Python
- LLM environments
- Git and GitHub
- APIs
- Command-line tools
- AI application development
- Model testing

## Motivations

Alex wants AI systems to remain useful for legitimate users while reducing the likelihood that adversarial prompts can successfully manipulate them.

## Behavioural Traits

- Practical
- Technically focused
- Systematic
- Solution-oriented
- Performance-conscious
- Reliability-focused

---

# Impact on Functional Requirements

The two personas highlight the need for the system to support both security testing and practical protection.

The AI Security Researcher needs to submit normal and adversarial prompts, identify potential jailbreak attempts, and record AI responses and attack outcomes for evaluation.

The AI Developer needs the system to detect suspicious prompts, apply an appropriate resilience or protection mechanism, and maintain legitimate AI functionality.

Together, these needs reinforce the existing Week 2 functional requirements:

- **FR1 – Submit Test Prompts**
- **FR2 – Detect Potential Jailbreaks**
- **FR3 – Apply Protection**
- **FR4 – Record and Display Results**

---

# Impact on Non-Functional Requirements

Both personas require the system to be accurate, responsive, reliable and usable.

The AI Security Researcher requires effective and consistent jailbreak detection for meaningful evaluation.

The AI Developer requires protection that does not unnecessarily block legitimate prompts.

Therefore, the Week 2 non-functional requirements remain important:

- **NFR1 – Detection Response Time:** 2 seconds or less.
- **NFR2 – Detection Effectiveness:** At least 80% of jailbreak prompts in the agreed evaluation dataset should be detected.
- **NFR3 – Benign Prompt Acceptance:** At least 90% of approved legitimate prompts should continue to work correctly when protection is enabled.
- **NFR4 – System Reliability:** At least 95% of planned evaluation test cases should complete without application failure.

---

## Conclusion

The two personas demonstrate that the Agent Resilience project needs to balance security testing, protection, usability and measurable evaluation.

The personas also provide a direct link between the stakeholder needs identified in Week 2 and the functional and non-functional requirements used during implementation.
