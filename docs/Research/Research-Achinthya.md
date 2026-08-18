# Achinthya Hirushan -- Week 2 Research

------------------------------------------------------------------------

## Research Area

**Jailbreak Attacks and Jailbreak Techniques**

------------------------------------------------------------------------

## Student Details

-   **Name:** Achinthya Hirushan
-   **Student ID:** 105016390
-   **Role:** Co-Leader
-   **Project:** Agent Resilience
-   **Unit:** ICT30016 -- ICT Innovation Project

------------------------------------------------------------------------

## 1. Introduction

Large Language Models (LLMs) are designed with safety mechanisms that
restrict harmful, unsafe, or unauthorised behaviour. However, attackers
can use specially designed prompts to manipulate an LLM into ignoring or
bypassing these restrictions. These attacks are commonly known as
**jailbreak attacks**.

Jailbreak security is particularly important for AI agents because
agents may have access to tools, files, APIs, databases, or other
systems. A successful attack may therefore affect more than the model's
text response.

## 2. What is an LLM Jailbreak?

An **LLM jailbreak attack** is an adversarial prompting technique
intended to bypass or weaken the safety restrictions of a large language
model. The attacker attempts to influence the model so that it behaves
in a way that would normally be restricted by its safety policies.

### Common Attacker Goals

-   Bypass safety restrictions
-   Manipulate model behaviour
-   Produce restricted or unsafe outputs
-   Reveal information that should remain protected
-   Influence an AI agent's decisions
-   Cause an agent to perform unintended actions

## 3. Jailbreaking vs Prompt Injection

### Jailbreaking

Jailbreaking normally focuses on **bypassing the model's safety
restrictions**. The attacker creates prompts designed to make the model
ignore or weaken its normal safeguards.

### Prompt Injection

Prompt injection is a broader attack in which malicious or untrusted
instructions are introduced to manipulate the behaviour of an LLM or AI
application.

A jailbreak can therefore be considered a type of adversarial prompt
manipulation, while prompt injection can also target application
instructions, connected tools, external data, and AI agent behaviour.

## 4. Major Jailbreak Techniques

### 4.1 Direct Instruction Attacks

The attacker directly provides adversarial instructions and attempts to
make those instructions override the model's normal restrictions.

**Security concern:** The model may incorrectly prioritise malicious
user instructions over its safety requirements.

### 4.2 Role-Playing and Persona Attacks

The attacker asks the model to adopt a fictional character, role, or
alternative persona to change the context of a request.

**Security concern:** Safety restrictions should continue to apply
regardless of fictional roles or scenarios.

### 4.3 Hypothetical or Scenario-Based Attacks

An attacker places a restricted objective inside an apparently
fictional, educational, hypothetical, or simulated scenario.

**Security concern:** The underlying intention may remain unsafe even
when disguised by harmless-looking context.

### 4.4 Prompt Obfuscation

The attacker disguises the meaning or intention of an adversarial
instruction using techniques such as encoding, unusual formatting,
character substitutions, language transformations, or splitting
instructions into multiple components.

**Security concern:** Defences based only on obvious keywords may fail
to identify transformed attacks.

### 4.5 Multi-Turn Jailbreaks

Instead of attempting a jailbreak in one message, the attacker gradually
influences the model over multiple conversation turns.

**Security concern:** Detection systems need to consider conversation
history rather than analysing each message independently.

### 4.6 Many-Shot Jailbreaking

Many-shot attacks provide a large number of examples or demonstrations
inside the model's context before asking it to produce another response.

**Security concern:** Long context windows can provide additional
opportunities for adversarial information to influence model behaviour.

### 4.7 Adversarial Suffix Attacks

An adversarial suffix is a specially constructed sequence added to a
prompt to influence model behaviour.

**Security concern:** The sequence may not look meaningful to a human
reviewer while still affecting the model.

### 4.8 Automated Jailbreak Generation

Automated systems, algorithms, or other LLMs can generate and test
variations of jailbreak prompts.

**Security concern:** Automation allows many attack variations to be
tested quickly.

### 4.9 Indirect Prompt Injection

Indirect prompt injection occurs when malicious instructions are placed
inside external information that an AI system later processes, such as
documents, web pages, emails, retrieved knowledge, tool outputs, or
other external data.

**Security concern:** This is particularly important for AI agents that
automatically process external information and use tools.

## 5. Direct vs Indirect Attacks

### Direct Attack

**Attacker → adversarial prompt → LLM → attempted policy bypass**

The attacker directly controls the prompt sent to the model.

### Indirect Attack

**Attacker → external content → AI agent reads content → malicious
instruction influences agent**

The malicious instruction is hidden in information consumed by the AI
system. This is particularly important when agents have permission to
access files, applications, APIs, or other resources.

## 6. Why Jailbreak Attacks Can Succeed

-   **Instruction conflicts:** Attackers try to make malicious
    instructions influence the model despite higher-priority
    restrictions.
-   **Helpfulness vs safety:** Adversarial prompts may exploit tension
    between producing useful responses and following safety
    requirements.
-   **Context manipulation:** Carefully constructed context can
    influence how later instructions are interpreted.
-   **Generalisation limitations:** Safety training cannot anticipate
    every possible representation of an unsafe request.
-   **Long-context vulnerabilities:** Larger contexts provide more space
    for adversarial examples and instructions.
-   **Obfuscation:** Transformed instructions may be harder for simple
    filters to recognise.

## 7. Potential Impact of Successful Jailbreaks

-   Safety-policy bypass
-   Generation of restricted content
-   Sensitive-information disclosure
-   System-prompt leakage
-   Manipulation of model decisions
-   Unauthorised tool usage
-   Data exfiltration
-   Loss of application integrity
-   Unintended AI-agent actions

The risk becomes greater when an LLM is connected to external tools or
sensitive information.

## 8. Jailbreak Defence Techniques

A layered security approach is important because no single defence can
completely prevent every jailbreak.

-   **Input filtering:** Analyse prompts before they reach the model.
-   **Output filtering:** Analyse model responses before they are
    released or passed to another system.
-   **Safety and alignment training:** Train models to recognise
    adversarial requests and maintain safety requirements.
-   **Trusted/untrusted instruction separation:** Clearly distinguish
    trusted system instructions from untrusted content.
-   **Least privilege:** Give AI agents only the permissions required
    for their tasks.
-   **Human confirmation:** Require approval before sensitive or
    high-impact actions.
-   **Sandboxing:** Isolate potentially risky AI-generated actions.
-   **Monitoring and logging:** Record activity to identify unusual
    behaviour and repeated attacks.
-   **Adversarial testing/red teaming:** Test systems against different
    attacks and improve defences based on results.

## 9. Evaluating Jailbreak Resilience

### Attack Success Rate (ASR)

**ASR = (Successful jailbreak attempts / Total jailbreak attempts) ×
100**

A lower ASR generally indicates stronger resistance to the tested
jailbreak attacks.

### Other Useful Metrics

-   Refusal rate
-   Safe response rate
-   Detection accuracy
-   False-positive rate
-   False-negative rate
-   Defence bypass rate
-   Performance before defence
-   Performance after defence
-   Performance across different attack categories

### Example Evaluation Table

  Attack Category        Tests   Successful   Blocked   ASR
  -------------------- ------- ------------ --------- -----
  Role-playing              20            4        16   20%
  Obfuscation               20            7        13   35%
  Multi-turn                20            9        11   45%
  Indirect injection        20            3        17   15%

> **Note:** These figures are examples of how experimental results could
> be recorded. They are not actual test results.

## 10. Importance to Agent Resilience

Jailbreak resistance is an important part of **AI agent resilience**. AI
agents may be able to read files, search databases, call APIs, use
external tools, retrieve information, modify data, or trigger actions.

A resilient AI agent should:

1.  Identify suspicious instructions.
2.  Maintain trusted instruction priorities.
3.  Treat external content as untrusted.
4.  Restrict tool permissions.
5.  Require confirmation for sensitive actions.
6.  Monitor unusual behaviour.
7.  Fail safely when uncertain.
8.  Maintain useful behaviour while resisting adversarial manipulation.

## 11. Research Questions for the Project

1.  What jailbreak techniques are most effective against current LLMs?
2.  Which techniques are most difficult to detect?
3.  How does multi-turn interaction affect jailbreak success?
4.  How effective are input and output filters?
5.  How can indirect prompt injection affect AI agents?
6.  Does combining multiple defensive layers reduce attack success?
7.  How should jailbreak resilience be measured?
8.  What trade-offs exist between security and model usability?
9.  How can an agent safely process untrusted external information?
10. How can automated testing improve jailbreak detection?

## 12. Useful Search Terms

``` text
LLM jailbreak attacks
LLM jailbreak attack taxonomy
jailbreak attacks large language models
jailbreak techniques LLM
adversarial prompts large language models
direct prompt injection LLM
indirect prompt injection LLM
multi-turn jailbreak LLM
role playing jailbreak LLM
prompt obfuscation jailbreak
adversarial suffix LLM jailbreak
automated jailbreak attacks LLM
many-shot jailbreaking
LLM jailbreak defenses
prompt injection mitigation LLM
jailbreak detection large language models
jailbreak benchmark LLM
jailbreak attack success rate
LLM agent prompt injection security
AI agent jailbreak resilience
```

## 13. Recommended Sources

### NIST

**Adversarial Machine Learning: A Taxonomy and Terminology of Attacks
and Mitigations** --- useful for understanding adversarial AI attacks,
attacker goals, capabilities, and terminology.

### OWASP GenAI Security Project

**LLM01: Prompt Injection** --- useful for understanding direct and
indirect prompt injection, impacts, and mitigation approaches.

### Anthropic

**Many-shot Jailbreaking** --- useful for understanding how long context
windows can introduce jailbreak vulnerabilities.

### Academic Research

**Jailbreak Attacks and Defenses Against Large Language Models: A
Survey** --- useful for studying jailbreak taxonomies, attack
techniques, defence methods, and research challenges.

## 14. Summary

LLM jailbreak attacks attempt to manipulate models into bypassing their
normal safety restrictions. Important techniques include direct
instruction manipulation, role-playing, hypothetical framing,
obfuscation, multi-turn attacks, many-shot attacks, adversarial
suffixes, automated jailbreak generation, and indirect prompt injection.

For AI agents, the impact can be greater because agents may interact
with external tools and information. Effective protection therefore
requires multiple defensive layers, including filtering, instruction
separation, least privilege, monitoring, human approval, sandboxing, and
adversarial testing.

For the **Agent Resilience** project, jailbreak security can be
evaluated by testing multiple attack categories, measuring metrics such
as Attack Success Rate, applying defensive controls, and comparing
results before and after those controls are introduced.
