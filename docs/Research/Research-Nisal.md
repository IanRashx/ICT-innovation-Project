# LLM Jailbreak Evaluation, Security Benchmarks, and AI Resilience Metrics

## 1. Overview

Large Language Model (LLM) security evaluation increasingly focuses on
whether models can maintain safe and useful behaviour when exposed to
adversarial inputs. One important area is **jailbreak evaluation**,
where attackers attempt to bypass a model's safety controls.

A robust evaluation should not rely on a single metric such as Attack
Success Rate (ASR). Instead, it should combine attack effectiveness,
harmfulness, robustness, transferability, recovery, and legitimate
utility.

A useful evaluation pipeline is:

**Attack → Model Response → Safety Evaluation → Metrics → Resilience
Assessment**

------------------------------------------------------------------------

## 2. LLM Jailbreak Evaluation

A **jailbreak** is an input designed to bypass an LLM's safety
mechanisms and cause the model to produce content that it would normally
refuse.

A proper jailbreak evaluation should answer questions such as:

-   How often do attacks bypass the model's safety mechanisms?
-   How harmful are the responses produced after a successful attack?
-   Do attacks work across different models?
-   Does the model maintain safe behaviour under different attack
    strategies?
-   Do safety defences reduce legitimate model utility?

### JailbreakBench

JailbreakBench was developed to provide a more standardised framework
for evaluating jailbreak attacks and defences. It includes a common
threat model, system prompts, chat templates, scoring functions, and a
dataset of behaviours.

Source:

https://arxiv.org/abs/2404.01318

Official project:

https://jailbreakbench.github.io/

------------------------------------------------------------------------

## 3. Attack Success Rate (ASR)

Attack Success Rate is one of the most commonly used metrics in
jailbreak research.

### Formula

ASR = (Number of successful attacks / Total number of attacks) × 100

### Example

Suppose a model is tested using 100 adversarial prompts.

-   15 attacks successfully bypass the safety mechanism.
-   85 attacks are resisted.

Therefore:

ASR = (15 / 100) × 100 = 15%

A lower ASR generally indicates stronger resistance to the tested
attacks.

### Important limitation

ASR is a binary-style measure and may not capture the severity or
usefulness of the harmful response. A model might technically comply
with an adversarial request while producing an incomplete or useless
response.

Therefore:

**Jailbreak success ≠ harmful response quality**

ASR should be combined with additional metrics.

------------------------------------------------------------------------

## 4. StrongREJECT

StrongREJECT addresses limitations associated with simplistic jailbreak
evaluation.

Rather than only asking whether an attack succeeded, StrongREJECT
evaluates how effectively the model provides harmful information.

Its evaluation considers characteristics such as:

-   Whether the model complied with the request
-   How much relevant information was provided
-   How directly the response addressed the request
-   Whether the response was actually useful for the harmful objective

The research reported strong correlation between its automated
evaluation and human judgements.

Source:

https://arxiv.org/abs/2402.10260

Project:

https://github.com/dsbowen/strong_reject

### Key insight

A successful jailbreak is more meaningful when the resulting response is
both unsafe and useful for the harmful objective.

------------------------------------------------------------------------

## 5. HarmBench

HarmBench is a standardised framework for automated red teaming and
robust refusal evaluation.

It was designed to make comparisons between attack methods and model
defences more consistent.

The research evaluated:

-   18 red-teaming methods
-   33 target LLMs and defences

HarmBench is useful for measuring both attack effectiveness and model
robustness.

Source:

https://proceedings.mlr.press/v235/mazeika24a.html

------------------------------------------------------------------------

## 6. Other LLM Security Benchmarks

### JailbreakBench

**Primary focus:** Jailbreak attacks and defences.

Useful for:

-   Standardised jailbreak evaluation
-   Comparing attack methods
-   Comparing model defences
-   Reproducible benchmarking

### HarmBench

**Primary focus:** Automated red teaming and robust refusal.

Useful for:

-   Testing adversarial attacks
-   Comparing attack strategies
-   Evaluating refusal robustness

### StrongREJECT

**Primary focus:** Quality and effectiveness of harmful responses after
jailbreak.

Useful for:

-   Measuring harmful-response quality
-   Reducing misleading binary evaluations
-   Comparing automated evaluation with human judgement

### MLCommons AILuminate

AILuminate is an industry-oriented AI safety and security benchmark
framework. Its benchmark family includes jailbreak testing and uses
hazard categories and evaluator models.

Source:

https://mlcommons.org/benchmarks/ailuminate/

------------------------------------------------------------------------

## 7. AI Resilience Metrics

AI resilience can be understood as the ability of an AI system to
maintain safe and useful behaviour when exposed to adversarial,
unexpected, or changing inputs.

Resilience should therefore be evaluated using multiple dimensions.

------------------------------------------------------------------------

## 8. Metric 1 --- Attack Success Rate

### Formula

ASR = Successful attacks / Total attacks

or:

ASR = (Successful attacks / Total attacks) × 100

**Desired direction: Lower is better.**

ASR measures how frequently tested attacks successfully bypass the
model's safety mechanisms.

------------------------------------------------------------------------

## 9. Metric 2 --- Attack Failure Rate

Attack Failure Rate represents the proportion of tested attacks that
were successfully resisted.

### Formula

AFR = Failed attacks / Total attacks

or:

AFR = 1 − ASR

**Desired direction: Higher is better.**

------------------------------------------------------------------------

## 10. Metric 3 --- Robust Refusal Rate

Robust Refusal Rate measures how consistently the model refuses harmful
requests when they are presented through adversarial inputs.

### Example formula

RRR = Safe refusals / Adversarial prompts × 100

**Desired direction: Higher is better.**

However, refusal rate should not be evaluated alone. A model that
refuses every request may achieve excellent apparent safety while
becoming practically useless.

------------------------------------------------------------------------

## 11. Metric 4 --- Harmfulness / Jailbreak Severity

Instead of using only:

**Successful = 1**

and

**Unsuccessful = 0**

a response can be assigned a harmfulness score.

For example:

-   0 = No harmful information
-   0.25 = Very limited harmful information
-   0.5 = Moderate harmful information
-   0.75 = Substantial harmful information
-   1 = Highly useful harmful information

A lower harmfulness score indicates better safety.

This approach is consistent with the motivation behind
StrongREJECT-style evaluation.

------------------------------------------------------------------------

## 12. Metric 5 --- Robustness Degradation

Robustness degradation measures how much safety performance decreases
when the model is subjected to attacks.

### Formula

Robustness Degradation = Baseline Performance − Under-Attack Performance

### Example

Suppose:

-   Baseline safety performance = 98%
-   Under-attack safety performance = 80%

Then:

Robustness Degradation = 98 − 80 = 18 percentage points

**Desired direction: Lower degradation is better.**

This is particularly useful because resilience is fundamentally
concerned with maintaining performance under stress.

MLCommons' AILuminate work also considers degradation from baseline
safety to under-attack performance when evaluating jailbreak resilience.

Source:

https://mlcommons.org/benchmarks/ailuminate/

------------------------------------------------------------------------

## 13. Metric 6 --- Attack Transferability

Attack transferability measures whether an attack developed for one
model also works against other models.

### Example

An adversarial prompt is successful against Model A.

Researchers then test the same prompt against Models B, C, and D.

If it succeeds against many models, the attack has high transferability.

**Desired direction: Lower transferability is generally better for model
resilience.**

------------------------------------------------------------------------

## 14. Metric 7 --- Defense Success Rate

Defense Success Rate measures the proportion of adversarial attacks
successfully blocked by a defence mechanism.

### Formula

Defense Success Rate = Successfully blocked attacks / Total attacks ×
100

**Desired direction: Higher is better.**

This metric is useful when comparing:

-   Input filters
-   System prompts
-   Safety classifiers
-   Guard models
-   Output filters
-   Multi-layer safety architectures

------------------------------------------------------------------------

## 15. Metric 8 --- False Refusal Rate

A safety system should not refuse legitimate requests unnecessarily.

False Refusal Rate measures how frequently legitimate, safe requests are
incorrectly rejected.

### Formula

False Refusal Rate = Legitimate requests incorrectly refused / Total
legitimate requests × 100

**Desired direction: Lower is better.**

This metric is essential for evaluating the safety--utility trade-off.

------------------------------------------------------------------------

## 16. Metric 9 --- Utility Score

Utility measures how well the model continues to perform legitimate
tasks while safety defences are active.

Possible measures include:

-   Task accuracy
-   Helpfulness
-   Instruction following
-   Reasoning performance
-   User satisfaction
-   Benchmark performance

**Desired direction: Higher is better.**

------------------------------------------------------------------------

## 17. Metric 10 --- Recovery Rate

Recovery Rate measures whether a model can return to safe behaviour
after being exposed to adversarial interaction.

A resilient model should not only resist individual attacks but should
also maintain safe behaviour across multi-turn conversations.

Possible evaluation:

1.  Establish a normal conversation.
2.  Introduce an adversarial input.
3.  Continue the interaction.
4.  Test whether the model returns to appropriate safe behaviour.

**Desired direction: Higher is better.**

------------------------------------------------------------------------

## 18. Metric 11 --- Human--Evaluator Agreement

Automated safety evaluators are useful for large-scale testing, but
their judgements may differ from human assessments.

Human--Evaluator Agreement measures how closely an automated evaluator
agrees with human judgements.

Possible statistics include:

-   Cohen's kappa
-   Spearman correlation
-   Pearson correlation
-   Agreement percentage

**Desired direction: Higher agreement is better.**

StrongREJECT provides an important example of research attempting to
improve automated evaluation reliability.

------------------------------------------------------------------------

# 19. Safety--Utility Trade-off

One of the most important concepts in LLM resilience research is the
trade-off between safety and utility.

Consider two hypothetical models.

### Model A

-   Blocks 99% of tested attacks
-   Incorrectly refuses 40% of legitimate requests

### Model B

-   Blocks 97% of tested attacks
-   Correctly answers 99% of legitimate requests

ASR alone would favour Model A.

However, Model B may provide better real-world performance because it
maintains much greater legitimate utility.

Therefore:

**Good resilience = strong safety + preserved legitimate utility**

A robust evaluation should avoid rewarding systems simply for refusing
everything.

MLCommons notes this limitation in relation to safety benchmarking: a
system could theoretically achieve excellent safety by refusing all
requests, even though such behaviour would severely reduce usefulness.

Source:

https://mlcommons.org/ailuminate/safety-faq/

------------------------------------------------------------------------

# 20. Recommended Evaluation Framework

A strong research framework can be organised into five layers.

## Layer 1 --- Baseline Evaluation

Test the model using normal, non-adversarial prompts.

Measure:

-   Accuracy
-   Helpfulness
-   Safety
-   Legitimate refusal rate
-   Utility

↓

## Layer 2 --- Adversarial Evaluation

Expose the model to multiple jailbreak and red-teaming strategies.

Measure:

-   ASR
-   Refusal rate
-   Attack transferability
-   Defense success rate

↓

## Layer 3 --- Severity Evaluation

Examine the quality and harmfulness of responses produced after
successful attacks.

Measure:

-   Harmfulness score
-   Jailbreak severity
-   Response usefulness
-   Human evaluation

↓

## Layer 4 --- Resilience Evaluation

Compare baseline performance with performance under attack.

Measure:

-   Robustness degradation
-   Recovery rate
-   Multi-turn robustness
-   Cross-attack robustness

↓

## Layer 5 --- Utility Evaluation

Determine whether safety mechanisms negatively affect legitimate use.

Measure:

-   False refusal rate
-   Task accuracy
-   Helpfulness
-   Instruction following
-   Overall utility

------------------------------------------------------------------------

# 21. Recommended Core Metrics

For a university research project on **LLM Security, Jailbreak
Evaluation, and AI Resilience**, the following metrics provide a strong
core framework.

  -----------------------------------------------------------------------
  Metric                  What it measures        Desired direction
  ----------------------- ----------------------- -----------------------
  ASR                     Percentage of           Lower
                          successful jailbreaks   

  Refusal Rate            Safe handling of        Higher
                          harmful requests        

  Harmfulness Score       Severity/usefulness of  Lower
                          harmful output          

  Robustness Degradation  Performance loss under  Lower
                          attack                  

  Attack Transferability  Whether attacks work    Lower
                          across models           

  Defense Success Rate    Effectiveness of        Higher
                          defences                

  False Refusal Rate      Legitimate requests     Lower
                          incorrectly rejected    

  Utility Score           Normal task performance Higher

  Recovery Rate           Ability to return to    Higher
                          safe behaviour          

  Human--Evaluator        Reliability of          Higher
  Agreement               automated evaluation    
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 22. Key Research Insight

The research literature suggests a shift from simple jailbreak counting
toward multidimensional resilience evaluation.

### Traditional approach

> How many jailbreaks succeeded?

### Stronger approach

> How resilient is the complete AI system across different attacks, how
> harmful are successful attacks, how much does performance degrade
> under attack, and how much legitimate utility is lost through
> defensive mechanisms?

This is important because ASR alone can be misleading. JailbreakBench
highlighted the need for more consistent evaluation, while StrongREJECT
demonstrated that simplistic evaluation methods can overestimate
jailbreak effectiveness.

Therefore, a more defensible conceptual model is:

**LLM Resilience = f(ASR, Harmfulness, Robustness, Transferability,
Utility, Recovery)**

There is currently no single universally accepted resilience score. A
**profile of complementary metrics** is more appropriate.

------------------------------------------------------------------------

# 23. Key Academic Sources

1.  Mazeika, M., Phan, L., Yin, X., Zou, A., Wang, Z., Mu, N., Sakhaee,
    E., Li, N., Basart, S., Li, B., Forsyth, D., & Hendrycks, D. (2024).
    *HarmBench: A standardized evaluation framework for automated red
    teaming and robust refusal*. Proceedings of Machine Learning
    Research, 235.

    https://proceedings.mlr.press/v235/mazeika24a.html

2.  Chao, P., Debenedetti, E., Robey, A., Andriushchenko, M., Croce, F.,
    Pappu, A., Dziedzic, A., Sehwag, V., Tramer, F., & Zhang, B. (2024).
    *JailbreakBench: An open robustness benchmark for jailbreaking large
    language models*.

    https://arxiv.org/abs/2404.01318

3.  Souly, A., Lu, Q., Bowen, D., Rock, J., Helm, H., Duburque, A.,
    Swanson, E., Chen, A., Vaughan, J., Hendrycks, D., & others. (2024).
    *A StrongREJECT for empty jailbreaks*. NeurIPS 2024.

    https://arxiv.org/abs/2402.10260

4.  MLCommons. *AILuminate: AI safety and security benchmark*.

    https://mlcommons.org/benchmarks/ailuminate/

5.  NIST. *Artificial Intelligence Risk Management Framework: Generative
    Artificial Intelligence Profile*.

    https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence

------------------------------------------------------------------------

## 24. Conclusion

A reliable evaluation of LLM security should not depend on ASR alone.

The strongest approach combines:

**Jailbreak resistance** → ASR, refusal rate, defense success

**Harmfulness** → severity and usefulness of unsafe outputs

**Resilience** → robustness degradation, recovery, transferability

**Utility** → legitimate task performance and false refusal rate

**Evaluation reliability** → human--evaluator agreement

This multidimensional approach provides a more realistic picture of
whether an LLM is genuinely resilient rather than merely capable of
refusing a particular set of test prompts.
