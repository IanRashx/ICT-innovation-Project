# Ian Rashmika – Week 2 Research

## Research Area

**Agent Resilience, AI Agent Security and Overall Project Problem Definition**

## Student Details

* **Name:** Ian Rashmika
* **Student ID:** 104833909
* **Role:** Team Leader
* **Project:** Agent Resilience
* **Unit:** ICT30016 – ICT Innovation Project

---

## 1. Research Objective

The purpose of this research was to develop a better understanding of **Agent Resilience** and the security problems that can affect AI agents and Large Language Models (LLMs).

The research focused particularly on:

* AI agent resilience.
* Jailbreak attacks.
* Prompt injection.
* Adversarial inputs.
* Security vulnerabilities in LLMs.
* Possible defence mechanisms.
* Methods that can be used to evaluate AI resilience.

The findings from this research will help the team define the overall project problem, identify suitable project objectives, and determine possible approaches for the Agent Resilience prototype.

---

## 2. What is Agent Resilience?

Agent Resilience can be described as the ability of an AI agent to continue operating reliably when it experiences unexpected, malicious or adversarial conditions.

For this project, resilience is mainly concerned with whether an AI agent can:

* Resist attempts to manipulate its behaviour.
* Continue following its intended instructions.
* Detect suspicious interactions.
* Reduce the impact of attacks.
* Recover after an adversarial interaction.
* Continue working normally for legitimate users.

The Week 1 Agent Resilience material also presents the idea that a resilient system may temporarily lose performance after a disturbance but can recover, while a non-resilient system may fail to return to its expected behaviour.

---

## 3. Why Agent Resilience is Important

AI agents and Large Language Models are increasingly being integrated into software applications and automated systems.

As these systems become more capable, they may also be exposed to security threats that attempt to manipulate how they behave.

One major problem is that a malicious user may provide specially constructed instructions that cause an AI system to behave differently from what the developer originally intended.

Research on LLM security shows that even safety-aligned language models can remain vulnerable to adversarial and jailbreak attacks.

This means that security controls should not rely only on the AI model's built-in safety behaviour.

For an AI agent to be resilient, additional methods may be required to detect, prevent and respond to malicious interactions.

---

## 4. Jailbreak Attacks

A jailbreak attack attempts to make an AI model bypass its intended safety controls or restrictions.

Jailbreak attacks commonly use specially designed adversarial prompts to manipulate an LLM into producing responses that it would normally reject.

Research categorises jailbreak attacks into different types, including **black-box** and **white-box** attacks, depending on how much information the attacker has about the target model.

A jailbreak may attempt to:

* Override existing instructions.
* Change the role of the AI system.
* Bypass safety controls.
* Cause the model to produce unintended output.
* Manipulate the model through complex or indirect instructions.

The main concern for our project is not simply that an attack occurs, but whether the AI agent is able to **resist the attack and continue behaving correctly**.

---

## 5. Prompt Injection

Prompt injection is another important security issue affecting LLM-based systems.

OWASP defines prompt injection as a vulnerability where supplied prompts alter an LLM's behaviour or output in unintended ways. These malicious instructions can sometimes be hidden in content processed by the model.

Prompt injection can be divided into two general categories:

### Direct Prompt Injection

A user directly provides malicious instructions to the AI system.

For example, an attacker may attempt to tell the model to ignore its original instructions and follow a new set of instructions.

### Indirect Prompt Injection

Malicious instructions are contained inside external information processed by the AI agent, such as:

* Documents.
* Webpages.
* Emails.
* Retrieved database information.
* Other external content.

Indirect prompt injection may become particularly important for AI agents because agents often interact with external information and tools.

---

## 6. Relationship Between Jailbreaking and Agent Resilience

Jailbreaking provides a practical way to test whether an AI system is resilient.

A simplified resilience test could follow this process:

```text
Normal Prompt
      |
      v
AI Agent
      |
      v
Expected Behaviour
```

The team could then introduce an adversarial prompt:

```text
Jailbreak Prompt
      |
      v
AI Agent
      |
      v
Does the behaviour change?
```

If the AI follows the malicious instructions, the attack may be considered successful.

A resilience mechanism could then be introduced:

```text
Jailbreak Prompt
      |
      v
Detection / Protection Layer
      |
      v
AI Agent
      |
      v
Safe / Expected Behaviour
```

The behaviour of the AI agent can then be compared before and after the resilience mechanism is added.

---

## 7. Possible Security and Resilience Approaches

Based on the research, several possible defence mechanisms could be investigated.

### 7.1 Input Filtering

The system could analyse user prompts before they are passed to the AI agent.

Suspicious prompts could be:

* Blocked.
* Flagged.
* Modified.
* Sent for additional analysis.

---

### 7.2 Prompt Classification

A classifier could identify whether an input appears to be:

* Normal.
* Suspicious.
* Adversarial.
* Potentially a jailbreak.

This could be implemented using rules, machine learning or another LLM.

---

### 7.3 Output Verification

Instead of only checking the user's input, the AI response could also be analysed before it is returned to the user.

This provides an additional security layer.

---

### 7.4 Multi-Agent Defence

One interesting defence approach is the use of multiple AI agents.

The **AutoDefense** research proposes a multi-agent framework in which several language-model agents work together to identify or filter harmful responses generated after jailbreak attacks.

This research is relevant to our project because it demonstrates that AI agents can potentially be used as part of the defence mechanism itself.

---

### 7.5 Safe Fallback Behaviour

If the system detects a suspicious interaction, the AI agent could move into a safe fallback state.

For example, it could:

* Reject the suspicious request.
* Return a predefined safe response.
* Request clarification.
* Log the event.
* Continue processing future legitimate requests.

This is particularly relevant to Agent Resilience because the system should not simply stop working after an attack.

---

## 8. Possible Agent Resilience Architecture

Based on my preliminary research, a possible architecture for the project could be:

```text
User / Test Prompt
        |
        v
Input Analysis
        |
        v
Jailbreak Detection
        |
        +----------------------+
        |                      |
     Normal                 Suspicious
        |                      |
        v                      v
     AI Agent           Defence Mechanism
        |                      |
        +-----------+----------+
                    |
                    v
              Output Analysis
                    |
                    v
              Result Logging
                    |
                    v
           Resilience Evaluation
```

This is only a preliminary project idea and should be confirmed with the tutor/client before implementation.

---

## 9. Evaluating Agent Resilience

Another important part of the research is understanding how the team could measure whether a defence mechanism actually improves resilience.

Several possible metrics could be used.

### Attack Success Rate

Attack Success Rate measures the percentage of jailbreak attempts that successfully manipulate the AI system.

```text
Attack Success Rate =
Successful Jailbreak Attempts
----------------------------- × 100
Total Jailbreak Attempts
```

A lower Attack Success Rate after applying a resilience mechanism could indicate an improvement.

---

### Detection Rate

Detection Rate measures how many malicious prompts are correctly identified.

```text
Detection Rate =
Correctly Detected Attacks
-------------------------- × 100
Total Attacks
```

---

### False Positive Rate

False Positive Rate measures how many legitimate prompts are incorrectly identified as attacks.

This metric is important because a security system that blocks too many legitimate requests may become difficult to use.

---

### Benign Prompt Success Rate

This measures whether normal prompts continue to work successfully after the resilience mechanism is enabled.

The system should ideally improve security without significantly reducing normal functionality.

---

### Response Time

The team could measure how long the security or resilience mechanism takes to analyse an interaction.

A defence mechanism should not introduce excessive delays into the AI system.

---

### Recovery Behaviour

The team could also investigate whether the AI agent continues behaving normally after an adversarial interaction.

For example:

```text
Normal Prompt
     |
     v
Expected Behaviour

Jailbreak Attack
     |
     v
Attack Detected / Blocked

Normal Prompt After Attack
     |
     v
Expected Behaviour Restored
```

This could help measure resilience rather than only attack detection.

---

## 10. Key Findings

Based on my research, I identified the following important points:

1. AI agents and LLMs can remain vulnerable to adversarial and jailbreak attacks even when they have existing safety alignment.

2. Prompt injection can cause an LLM to change its behaviour or output in unintended ways, making it an important security problem for AI applications.

3. Agent Resilience should involve more than simply identifying an attack. It should also consider maintaining expected behaviour and recovering after disturbances.

4. Possible resilience mechanisms include prompt filtering, classification, output checking and multi-agent defence.

5. Multi-agent defence has already been investigated in existing research, showing that specialised AI agents can potentially collaborate to filter harmful outputs.

6. The effectiveness of the proposed solution should be measured using clearly defined metrics such as Attack Success Rate, detection rate, false positives, benign prompt success and response time.

---

## 11. Relevance to Our Agent Resilience Project

The research suggests that our project could focus on creating a controlled testing environment where an AI agent is tested against both normal and adversarial prompts.

The project could compare:

```text
AI Agent Without Protection
             vs
AI Agent With Resilience Mechanism
```

The system could record whether:

* A jailbreak attempt was detected.
* The attack successfully changed the agent's behaviour.
* The resilience mechanism prevented the attack.
* Legitimate prompts continued to work.
* The agent recovered and continued operating normally.

This would provide measurable evidence of whether the proposed resilience mechanism actually improves AI agent security.

---

## 12. Proposed Project Problem Definition

Based on my research, the preliminary project problem can be defined as:

> AI agents and Large Language Models may be vulnerable to adversarial inputs such as jailbreak and prompt-injection attacks that attempt to alter their intended behaviour. There is therefore a need to investigate how AI agents respond to these attacks and how security and resilience mechanisms can help them resist manipulation, maintain expected behaviour and recover after adversarial interactions.

This problem definition should be reviewed and confirmed with the project tutor/client.

---

## 13. Questions Identified From My Research

The following questions should be clarified before the team finalises the project design:

1. Which AI model or AI agent should we use?
2. Should the project focus only on jailbreak attacks?
3. Should prompt injection also be included?
4. Should the prototype detect, prevent and recover from attacks?
5. What should count as a successful jailbreak?
6. Which resilience metrics should be prioritised?
7. Should we use an existing jailbreak benchmark or create our own safe test dataset?
8. Should the final prototype contain a dashboard?
9. Are multi-agent defence approaches within the expected scope?
10. What level of resilience improvement is expected from the final system?

---

# Research Sources

## Source 1

**S. Yi et al., “Jailbreak Attacks and Defenses Against Large Language Models: A Survey,” 2024.**

### Why it is relevant

This paper provides a broad overview of jailbreak attacks and defence mechanisms for Large Language Models. It classifies jailbreak attacks into categories including black-box and white-box attacks and also describes prompt-level and model-level defence approaches.

### Part of project addressed

* Jailbreak definition.
* Attack categories.
* Defence categories.
* LLM security.
* Evaluation of jailbreak attacks.

---

## Source 2

**OWASP GenAI Security Project – LLM01:2025 Prompt Injection**

### Why it is relevant

OWASP identifies prompt injection as a significant security vulnerability affecting LLM applications. It explains how malicious prompts can cause an LLM to behave in unintended ways.

### Part of project addressed

* Problem identification.
* Prompt injection.
* AI application security.
* Security requirements.

---

## Source 3

**E. Shayegani et al., “Survey of Vulnerabilities in Large Language Models Revealed by Adversarial Attacks,” 2023.**

### Why it is relevant

This survey examines security vulnerabilities in Large Language Models and explains how adversarial attacks can exploit weaknesses even in safety-aligned models.

### Part of project addressed

* LLM vulnerabilities.
* Adversarial attacks.
* AI security problem definition.
* Possible defence strategies.

---

## Source 4

**Y. Zeng et al., “AutoDefense: Multi-Agent LLM Defense against Jailbreak Attacks,” 2024.**

### Why it is relevant

AutoDefense demonstrates a multi-agent approach to defending LLMs against jailbreak attacks. Different AI agents perform specialised defence tasks and collaboratively analyse responses.

### Part of project addressed

* Agent-based defence.
* Jailbreak prevention.
* Response filtering.
* Possible resilience architecture.

---

## Source 5

**Z. Xu et al., “A Comprehensive Study of Jailbreak Attack versus Defense for Large Language Models,” 2024.**

### Why it is relevant

This study compares multiple jailbreak attack techniques and defence approaches across different language models, providing useful information for understanding how attack and defence effectiveness can be experimentally evaluated.

### Part of project addressed

* Attack testing.
* Defence testing.
* LLM comparison.
* Evaluation methodology.

---

# Conclusion

My Week 2 research shows that Agent Resilience is closely related to the security and reliability of AI agents when they are exposed to adversarial inputs.

Jailbreak attacks and prompt injection demonstrate that AI models may not always maintain their intended behaviour when manipulated by carefully constructed instructions.

The project therefore has an opportunity to investigate a combination of **attack testing, jailbreak detection, resilience mechanisms and measurable evaluation**.

The next step is to confirm the exact project scope with the tutor/client and then use these findings to define the final requirements and technical architecture.
