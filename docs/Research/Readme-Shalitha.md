# Jailbreak Detection & Defence Mechanisms — Research Summary
*Agent Resilience Project — Preliminary Research (Activity 5)*

## 1. Defense Landscape

Jailbreak defenses fall into three broad families:

- **Detection-based** — deny responses by identifying malicious intent before/after generation
- **Prompt-based** — modify inputs (system prompts, self-reminders) to make the model resist manipulation
- **Tuning-based** — adjust the model's own parameters via adversarial training

Detection-based methods (most relevant to FR2) split further by what they inspect:
- Input prompt inspection (e.g. SmoothLLM — perturbs multiple copies of a query and aggregates predictions)
- Internal model states
- Generated responses

Detectors can also be grouped as:
- **External-model-based** — fine-tuned classifier APIs or dedicated moderation LLMs (e.g. OpenAI Moderation API, Meta's Llama Guard) that score input toxicity/harm
- **LLM-feedback-based** — using the target model's own signals (logits, confidence, output distribution) to flag jailbreaks

## 2. Efficient Detection (relevant to NFR1 — 2s detection budget)

Chen et al. (EMNLP Findings 2025) found jailbreak and benign prompts produce measurably different output-token distributions. Their "Free Jailbreak Detection" (FJD) method prepends an affirmative instruction and uses temperature-scaled logits on just the first token, achieving detection with almost no extra inference cost — a useful design pattern to justify a lightweight detector.

## 3. Benchmarks & Datasets (relevant to FR4, NFR2, NFR3)

| Dataset | Size / Content | Use |
|---|---|---|
| **AdvBench** | 520 adversarial prompts, direct harmful intent (misinformation, illegal activity, hate speech) | Standard jailbreak eval set |
| **JailbreakBench (JBB-Behaviors)** | 100 misuse behaviors across 10 categories aligned to OpenAI usage policy; public leaderboard for attacks + defenses | Reproducible attack/defense evaluation |
| **HarmBench** | 300 standardized harmful-behavior samples | Cross-benchmark validation |
| **XSTest** | 450 benign samples designed to test over-refusal | Measures false positives — supports NFR3 |

## 4. Open-Source Tools / Repos

- **NeMo Guardrails** (NVIDIA) — github.com/NVIDIA-NeMo/Guardrails
  Open-source toolkit for programmable guardrails: built-in jailbreak/injection detection, input/output moderation, fact-checking; works across multiple LLM backends. Good reference architecture for the protection mechanism (FR3).
- **JailbreakBench** — github.com/JailbreakBench/jailbreakbench
  Code + leaderboard for reproducible attack/defense evaluation.
- **Llama Guard** — Meta's fine-tuned Llama model for input/output safety classification.
- **Awesome-Jailbreak-Guardrails** — github.com/xunguangwang/Awesome-Jailbreak-Guardrails
  Curated, actively updated reading list of guardrail papers.
- **Awesome-LM-SSP** — github.com/CryptoAILab/Awesome-LM-SSP
  Broader LLM safety/security/privacy reading list.

## 5. Suggested Activity 5 Table (3 Strongest Sources)

| # | Source | Which part of the problem it addresses |
|---|--------|------------------------------------------|
| 1 | Chen et al., "LLM Jailbreak Detection for (Almost) Free!", EMNLP Findings 2025 — arxiv.org/abs/2509.14558 | Low-latency detection design — supports NFR1 |
| 2 | Chao et al., "JailbreakBench: An Open Robustness Benchmark", NeurIPS 2024 Datasets Track — github.com/JailbreakBench/jailbreakbench | Evaluation dataset/leaderboard — supports FR4, NFR2 |
| 3 | NVIDIA, "NeMo Guardrails" — github.com/NVIDIA-NeMo/Guardrails | Reference architecture for protection/fallback mechanism — supports FR3, FR5 |

## 6. Key Consideration to Raise with Client

Detection and defence aren't fully separable stages — tighter detection thresholds tend to raise false positives on legitimate prompts (NFR3 concern). Worth flagging explicitly when discussing "what counts as a successful jailbreak" and "how important is avoiding false positives" with the client.
