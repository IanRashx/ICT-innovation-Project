# Ian Rashmika – Week 2 Research
## Research Area: Agent Resilience and AI Agent Security

### 1. Research Objective
The purpose of my research was to understand the concept of Agent Resilience,
identify the main security problems affecting AI agents, and determine how
resilience could be evaluated and improved in the proposed project.

### 2. What is Agent Resilience?
Agent Resilience refers to the ability of an AI agent to continue operating
reliably, resist malicious manipulation, or recover its expected behaviour
after being exposed to adversarial inputs.

### 3. Main Security Problem
AI agents and LLM applications can be exposed to jailbreak attacks and prompt
injection. These attacks attempt to manipulate the AI into ignoring its
intended rules, safety restrictions, or system instructions.

### 4. Why This Matters
A successful attack may cause an AI agent to:
- Ignore intended instructions
- Produce unintended responses
- Bypass safety controls
- Perform actions outside its expected role
- Become unreliable after malicious interaction

### 5. Possible Resilience Approaches
Potential approaches identified during research include:
- Prompt filtering
- Jailbreak detection
- Input classification
- Output verification
- Multi-agent defence
- Safe fallback mechanisms
- Logging and monitoring

### 6. Possible Evaluation Metrics
The project could consider:
- Attack Success Rate
- Detection Rate
- False Positive Rate
- Response Time
- Benign Prompt Success Rate
- Recovery Rate

### 7. Relevance to Our Project
Based on the research, our project could focus on testing an AI agent against
normal and jailbreak prompts, applying a resilience mechanism, and comparing
the agent's behaviour before and after protection.

### 8. Sources
1. Jailbreak Attacks and Defenses Against Large Language Models: A Survey
2. OWASP LLM01 – Prompt Injection
3. Survey of Vulnerabilities in Large Language Models Revealed by Adversarial Attacks
4. Multi-Agent LLM Defense against Jailbreak Attacks
5. JailbreakBench
