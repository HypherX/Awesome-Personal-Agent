# Awesome Personal Agent

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) ![Papers](https://img.shields.io/badge/entries-93-blue) ![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg) ![Last Updated](https://img.shields.io/badge/Updated-2026--10--31-green)

**A curated list of papers and benchmarks on personal agents** — assistants centered on a *specific user*, combining personalization and proactivity.

## Operational definition

> **Personal Agent** = **Personalization × Proactivity**.
>
> - **Memory** = substrate that keeps user state across sessions (not a third definition axis).
> - **Harness** (environment / tools / safety) = capability carrier that makes the above executable and deployable; safety lives **inside** harness design (isolation, authorization, HITL, injection defenses), not as a separate definition axis.
> - Harness entries are **personal-agent–related only** (including environment synthesis / training environments built for personal agents).

```
        ┌─ Personalization ─┐
User ──►│                   │──► Personal Agent behavior
        └─ Proactivity ─────┘
                 ▲
                 │ substrate
              Memory
                 ▲
                 │ carries execution & safety
              Harness (env / tools / safety)
```

**Last updated:** 2026-10-31 (Asia/Shanghai)

**Stats:** 93 curated entries (starter set + weekly update 2026-10-31). Links checked against arXiv API and public project pages; do not invent ids.

## Inclusion criteria

**Include**

- Tasks or methods that clearly depend on a **specific user's** preferences, history, devices, or accounts
- Or that study **proactivity** (clarification / ask-now-use-later / event-driven initiative / timing) in a personal-assistant setting
- Or that provide personal-assistant **memory**, **harness** (incl. PA-targeted env synthesis), **safety architecture**, or **evaluation**

**Exclude** (candidates for a future Related section)

- Generic agents with no user specificity (pure SWE, generic web navigation, tool-use-only)
- Platform-centric recommendation or fixed-persona roleplay without a real user-state loop
- Long-context / document RAG decoupled from a particular user

Each paper has **one** primary section; `#tags` capture cross-cutting facets.

## Contents

- [Operational definition](#operational-definition)
- [Inclusion criteria](#inclusion-criteria)
- [0. Surveys (2)](#0-surveys)
- [1. Personalization (8)](#1-personalization)
- [2. Proactivity (15)](#2-proactivity)
- [3. Memory (16)](#3-memory)
- [4. Harness (24)](#4-harness)
- [5. Benchmarks (28)](#5-benchmarks)
- [Contributing](#contributing)
- [License](#license)

## 0. Surveys

*Surveys and position-style overviews that map personalization, proactivity, or personal agents.*

- **A Survey of Personalization: From RAG to Agent** [[paper](https://arxiv.org/abs/2504.10147)] — *arXiv 2025.04* — Survey of personalization spanning RAG to agentic systems. `#survey` `#personalization`
- **A Survey on Proactive Dialogue Systems: Problems, Methods, and Prospects** [[paper](https://arxiv.org/abs/2305.02750)] — *arXiv 2023.05* — Classic survey of proactive dialogue: problems, methods, prospects. `#survey` `#proactivity` `#dialogue`

## 1. Personalization

*Preference extraction, utilization (incl. when not to use), update/drift, and interaction preference — methods and training.*

- **Persona Learning from Feedback for Personalized AI Assistants** [[paper](https://arxiv.org/abs/2610.38561)] — *arXiv 2026.10* — Learns reusable assistant personas from feedback via routed LoRA adapters. `#personalization` `#adapter`
- **Bridging Exploration and Persona: Information-Directed Dueling for Test-Time Agent Personalization** [[paper](https://arxiv.org/abs/2610.24385)] — *arXiv 2026.10* — ID-TAP: neural dueling bandit for test-time persona adaptation from pairwise user feedback. `#personalization` `#test-time` `#bandit`
- **CAPTURE: Disentangling Preference Drift from Memory Poisoning in Personalized LLM Agents** [[paper](https://arxiv.org/abs/2609.02265)] — *arXiv 2026.09* — Separates legitimate preference drift from memory poisoning. `#personalization` `#update` `#safety`
- **PreCoMem: Predictive Cognitive Memory for Self-Evolving Long-Term Dialogue Agents** [[paper](https://arxiv.org/abs/2610.29467)] — *arXiv 2026.10* — Confidence-gated MAINTAIN/PROFILE/CORRECT updates for long-term dialogue. `#personalization` `#memory` `#update`
- **From Correctness to Preference: A Framework for Personalized Agentic Reinforcement Learning** [[paper](https://arxiv.org/abs/2605.23382)] — *arXiv 2026.05* — Personalized agentic RL from correctness toward preference. `#personalization` `#RL`
- **Training Proactive and Personalized LLM Agents** [[paper](https://arxiv.org/abs/2511.02208)] — *arXiv 2025.11* — PPP (productivity / proactivity / personalization) with UserVille multi-objective RL. `#personalization` `#proactivity` `#RL`
- **AdaMem: Learning What to Remember with Adaptive Memory Policies for Personalized Agents** [[paper](https://arxiv.org/abs/2606.21144)] — *arXiv 2026.06* — Learns adaptive write policies (what to remember) for personalized agents. `#personalization` `#memory` `#write-gate`
- **Know Me, Respond to Me: Benchmarking LLMs for Dynamic User Profiling and Personalized Responses at Scale** [[paper](https://arxiv.org/abs/2504.14225)] — *arXiv 2025.04* — PersonaMem: large-scale dynamic user profiling and personalized response benchmark (filed here as profiling method+eval anchor). `#personalization` `#profiling` `#benchmark`

## 2. Proactivity

*Clarification / information seeking, ask-now-use-later, event-driven initiative, timing / interruptibility, proactive memory maintenance.*

- **When to Assist and What to Suggest: Joint Gating and Memory-Grounded Hint Generation in One Compact Decoder** [[paper](https://arxiv.org/abs/2610.40611)] — *arXiv 2026.10* — Joint when-to-intervene gating and memory-grounded hint generation in one decoder. `#proactivity` `#memory` `#timing`
- **Proactive Memory for Event-Driven LLM Agents** [[paper](https://arxiv.org/abs/2610.36967)] — *arXiv 2026.10* — ProactMem + ProactiveStream: event-driven proactive memory with validated trajectories. `#proactivity` `#memory` `#benchmark`
- **ProMemAgent: Long-Horizon Proactive Assistance with Context-Aware Prospective Memory from Sensory Perceptions** [[paper](https://arxiv.org/abs/2610.27400)] — *arXiv 2026.10* — Prospective memory over egocentric sensory context for delayed-intention proactive help; CPMBench. `#proactivity` `#memory` `#wearable` `#benchmark`
- **When Should AI Chime In? Benchmarking Timely Contribution of Proactive Agents in Multi-Party Chat** [[paper](https://arxiv.org/abs/2610.25896)] — *arXiv 2026.10* — PITCH: human-judged timing of proactive contributions; models chime in too early when live. `#proactivity` `#timing` `#multi-party` `#benchmark`
- **When Interpretations Persist: Downstream Influence in Gaze-Aware Assistants** [[paper](https://arxiv.org/abs/2610.25512)] — *arXiv 2026.10* — Retained interpretations of a user's activity shape later system-triggered outputs; evidence-bounded interpretation reduces harm. `#proactivity` `#memory` `#wearable` `#HCI`
- **Ask Less, Ask Better: Allocating User Attention in Proactive LLM Agents with Interruption Budgets** [[paper](https://arxiv.org/abs/2610.24411)] — *arXiv 2026.10* — Interruption budgets + user-attention cost for clarification; memory of earlier answers yields better questions. `#proactivity` `#clarification` `#user-attention`
- **MemoProAgent: Toward Memory-Driven Proactive Assistance** [[paper](https://arxiv.org/abs/2610.22671)] [[code](https://github.com/facebookresearch/Memo-Pro-Agent)] — *arXiv 2026.10* — Memory-driven proactive assistance over egocentric video + year-long personal memory; MemoProBench jointly scores content and timing; gated graph-memory harness (+ optional RL). `#proactivity` `#memory` `#harness` `#benchmark`
- **Clarify the User or Verify the World? Uncertainty Routing for Proactive Agents** [[paper](https://arxiv.org/abs/2609.32255)] — *arXiv 2026.09* — Routes uncertainty to asking the user vs verifying the environment. `#proactivity` `#clarification` `#routing`
- **Learning What to Ask for Tomorrow: Active Preference Acquisition for Long-Term Personalized Web Agents** [[paper](https://arxiv.org/abs/2610.31107)] — *arXiv 2026.10* — ActiveWebPref: ask preferences now for long-horizon web-agent reuse. `#proactivity` `#ask-now-use-later` `#web`
- **Knowing but Not Showing: LLMs Recognize Ambiguity but Rarely Ask Clarifying Questions** [[paper](https://arxiv.org/abs/2605.25284)] — *arXiv 2026.05* — Shows models detect ambiguity yet under-ask clarifying questions. `#proactivity` `#clarification`
- **PRISM: Festina Lente Proactivity -- Risk-Sensitive, Uncertainty-Aware Deliberation for Proactive Agents** [[paper](https://arxiv.org/abs/2602.01532)] — *arXiv 2026.02* — Risk-sensitive, uncertainty-aware deliberation for when to act. `#proactivity` `#timing` `#uncertainty`
- **From Helpfulness to Toxic Proactivity: Diagnosing Behavioral Misalignment in LLM Agents** [[paper](https://arxiv.org/abs/2602.04197)] — *arXiv 2026.02* — Diagnoses over-/toxic proactivity as behavioral misalignment. `#proactivity` `#timing` `#safety`
- **Proactive Conversational Agents with Inner Thoughts** [[paper](https://arxiv.org/abs/2501.00383)] — *arXiv 2024.12* — Inner Thoughts: decide when to speak from internal deliberation. `#proactivity` `#timing` `#dialogue`
- **Proactive Agent: Shifting LLM Agents from Reactive Responses to Active Assistance** [[paper](https://arxiv.org/abs/2410.12361)] — *arXiv 2024.10* — Early LLM proactive-assistance framing and data/reward setup. `#proactivity` `#method`
- **ProactEgoMem: Benchmarking Proactive Memory in Streaming Egocentric Video** [[paper](https://arxiv.org/abs/2610.30089)] — *arXiv 2026.10* — Proactive memory capture/maintenance on streaming egocentric video. `#proactivity` `#memory` `#wearable` `#benchmark`

## 3. Memory

*Architectures, write/retrieve/update, memory→action, and aligning when memory should be used.*

- **MemSteer: Turning User Histories into Supervision for Agent Memory Optimization** [[paper](https://arxiv.org/abs/2610.39276)] — *arXiv 2026.10* — Turns unlabeled user histories into evidence-backed QA to optimize agent memory design. `#memory` `#personalization` `#supervision`
- **ETAMem: Decoupling and Aligning Heterogeneous Memory for Long-Term Conversational Agents** [[paper](https://arxiv.org/abs/2610.37443)] — *arXiv 2026.10* — Event/emotion/time memory views with entropy-based retrieval budgets. `#memory` `#architecture`
- **From Voiceprints to User Entities: Online Speaker-Memory Construction for Multi-User Spoken Agents** [[paper](https://arxiv.org/abs/2610.36713)] — *arXiv 2026.10* — Online speaker-memory construction for multi-user spoken personal agents. `#memory` `#personalization` `#speech`
- **BehaviorMem: Building and Evaluating User Memory from Real-World E-Commerce Behavior Streams** [[paper](https://arxiv.org/abs/2610.34790)] — *arXiv 2026.10* — User memory from real behavior streams for interest and unmet-demand inference. `#memory` `#personalization` `#behavior`
- **SLICE-Mem: Salience-Gated Lightweight Information Curation for Efficient LLM Agent Memory** [[paper](https://arxiv.org/abs/2610.33015)] — *arXiv 2026.10* — Salience-gated lightweight write curation for long-term personalized interaction. `#memory` `#write-gate` `#efficiency`
- **PolyMemDB: A Polyglot Database System for AI Memory Management** [[paper](https://arxiv.org/abs/2608.25577)] — *arXiv 2026.08* — Polyglot memory store with provenance for personal intelligent agents. `#memory` `#harness` `#provenance`
- **What should AI forget? A design and taxonomy for negative space governance in AI memory** [[paper](https://arxiv.org/abs/2610.27607)] — *arXiv 2026.10* — Taxonomy of what users want kept out of assistant memory + FENCE user-rule memory gate. `#memory` `#forgetting` `#privacy` `#HCI`
- **Learning Personalized Memory Gating from Delayed One-Sided Feedback** [[paper](https://arxiv.org/abs/2610.23812)] — *arXiv 2026.10* — User-specific fact-level memory gating as contextual apple tasting (Warm-Start UCB). `#memory` `#write-gate` `#personalization`
- **MemT-1.0: Towards Memory-Native Evolution** [[paper](https://arxiv.org/abs/2610.26825)] — *arXiv 2026.10* — Memory-native foundation model toward evolving personal memory. `#memory` `#foundation-model`
- **Memory-Aware Reward Modeling: Learning Human Preferences for LLM Memory Use** [[paper](https://arxiv.org/abs/2610.31272)] — *arXiv 2026.10* — Learns human preferences for *when/how* to use memory in replies. `#memory` `#alignment` `#RM`
- **ColaBench: Evaluating Memory-Guided Knowledge Acquisition in Personal Agents** [[paper](https://arxiv.org/abs/2610.30989)] — *arXiv 2026.10* — Memory-conditioned external knowledge acquisition for personal agents (MemKB). `#memory` `#memory-to-action` `#benchmark`
- **Personalize-then-Store: Benchmarking and Learning Personalized Memory for Long-horizon Agents** [[paper](https://arxiv.org/abs/2605.25535)] — *arXiv 2026.05* — Personalized write-then-store memory for long-horizon agents. `#memory` `#write-gate` `#benchmark`
- **From Recall to Forgetting: Benchmarking Long-Term Memory for Personalized Agents** [[paper](https://arxiv.org/abs/2604.20006)] — *arXiv 2026.04* — Long-term memory with forgetting for personalized agents. `#memory` `#forgetting` `#benchmark`
- **Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory** [[paper](https://arxiv.org/abs/2504.19413)] — *arXiv 2025.04* — Production extract–merge–retrieve (and graph) long-term memory. `#memory` `#systems`
- **MemGPT: Towards LLMs as Operating Systems** [[paper](https://arxiv.org/abs/2310.08560)] — *arXiv 2023.10* — OS-style hierarchical virtual context / memory management. `#memory` `#architecture`
- **MemoryBank: Enhancing Large Language Models with Long-Term Memory** [[paper](https://arxiv.org/abs/2305.10250)] — *AAAI 2024 / arXiv 2023.05* — Early long-term memory mechanism + personal dialogue resource. `#memory` `#personalization`

## 4. Harness

*Environment, tools, and safety for personal agents only — personal apps/MCP/accounts, device GUI, isolation/authz/HITL, injection & data trust, PA-targeted env synthesis. Safety ∈ harness.*

- **Understanding and Mitigating Role Spoofing in LLMs** [[paper](https://arxiv.org/abs/2610.40396)] — *arXiv 2026.10* — Detects tool-output text that spoofs the user role to hijack agents. `#harness` `#safety` `#injection`
- **Appreciation Teaches Unauthorized Execution: Self-Evolution Degrades the Robustness of Personal Agents to Indirect Prompt Injection** [[paper](https://arxiv.org/abs/2610.39122)] [[code](https://github.com/SaFo-Lab/Evolve-IPI)] — *arXiv 2026.10* — Self-evolution from user feedback weakens personal agents against IPI. `#harness` `#safety` `#IPI`
- **Is it my preference? Role Grounding Attack against Agent's Memory via Social Interaction** [[paper](https://arxiv.org/abs/2610.38209)] — *arXiv 2026.10* — Social memory sharing can mis-attribute attacker prefs into the victim agent. `#harness` `#memory` `#safety`
- **Correction or Manipulation? Measuring Epistemic Vigilance in LLM Agents Under User Pressure** [[paper](https://arxiv.org/abs/2610.36453)] — *arXiv 2026.10* — Distinguishes correction vs manipulation when users pressure acting-for-user agents. `#harness` `#safety` `#HITL`
- **Measure Before You Train: Typed Decision Models vs. a Classical Baseline vs. a Generative LLM for Routing a Personal Multilingual Inbox** [[paper](https://arxiv.org/abs/2610.32955)] — *arXiv 2026.10* — Pre-train eval of typed vs classical vs LLM routing for a personal multilingual inbox. `#harness` `#personalization` `#benchmark`
- **Privacy Preference Controls for Agentic Systems** [[paper](https://arxiv.org/abs/2610.29929)] — *arXiv 2026.10* — Taxonomy of enforceable end-user privacy preferences for agents acting on users' behalf; MCP/A2A prototypes. `#harness` `#privacy` `#MCP`
- **Preference Is Not Permission: Personalizing the Auto-Purchase Line in Agentic Commerce** [[paper](https://arxiv.org/abs/2610.29216)] — *arXiv 2026.10* — Learns each user's don't-buy / confirm / auto-buy boundary; models overreach on commitment. `#harness` `#authorization` `#personalization`
- **After the Attacker Leaves: Benchmarking Carryover Attacks on LLM Agents** [[paper](https://arxiv.org/abs/2610.28425)] — *EMNLP 2026 / arXiv 2026.10* — CarryoverBench: injections persisting via memory files and scheduled tasks across personal-assistant sessions. `#harness` `#injection` `#memory` `#safety` `#benchmark`
- **Disclosure Begets Disclosure: A Self-Reinforcing Privacy Loop in LLM Agents with Persistent Memory** [[paper](https://arxiv.org/abs/2610.28315)] — *arXiv 2026.10* — Memory-conditioned replies make users disclose more personal attributes over sessions. `#harness` `#privacy` `#memory` `#safety`
- **ClawMMU: Protection-Coherent Virtual Memory for Stateful LLM Agents** [[paper](https://arxiv.org/abs/2610.28093)] — *arXiv 2026.10* — Owner/scope/origin/authority labels on agent memory so injected content cannot act as the user. `#harness` `#memory` `#authorization` `#safety`
- **AutoRedClaw: Automated Red-Teaming for Claw-Style Agents** [[paper](https://arxiv.org/abs/2610.27244)] [[code](https://github.com/SaFo-Lab/AutoRedClaw)] — *arXiv 2026.10* — Automated attack+environment generation for persistent personalized (OpenClaw-style) assistants. `#harness` `#red-team` `#local-agent` `#safety`
- **Whose Credential Is It? How Owner Attribution in Agent MemoryShapes Cross-User Account Misuse** [[paper](https://arxiv.org/abs/2610.25707)] — *arXiv 2026.10* — Owner attribution in shared memory prevents agents from acting with another user's credentials. `#harness` `#memory` `#authorization` `#safety`
- **Indistinguishable Agents: Training Agent Privacy as Twin-World Indistinguishability** [[paper](https://arxiv.org/abs/2610.25161)] — *arXiv 2026.10* — Twin-world RL so actions taken for a user do not leak the user's private facts to observers. `#harness` `#privacy` `#RL` `#safety`
- **Can Agents Keep Secrets They Were Never Told? Benchmarking Latent Privacy Risks Across Sessions with MemJoin** [[paper](https://arxiv.org/abs/2610.24359)] — *arXiv 2026.10* — MemJoin: sensitive relations inferred by joining user memories across sessions. `#harness` `#privacy` `#memory` `#benchmark`
- **Act on Your Behalf, Beyond Your Authorization: Benchmarking LLM Agent Authorization Alignment** [[paper](https://arxiv.org/abs/2610.27548)] [[code](https://github.com/PEACH-Research-Lab/AuthorizationBench)] — *arXiv 2026.10* — AuthorizationBench: authorization alignment beyond task completion. `#harness` `#authorization` `#safety` `#benchmark`
- **X-AgentRed: Red-Teaming Personal Agents in Evolving Multi-Service Ecosystems** [[paper](https://arxiv.org/abs/2610.13886)] — *arXiv 2026.10* — Red-teaming personal agents across evolving multi-service ecosystems. `#harness` `#red-team` `#safety`
- **From Assistant to Double Agent: Formalizing and Benchmarking Attacks on OpenClaw for Personalized Local AI Agent** [[paper](https://arxiv.org/abs/2602.08412)] — *arXiv 2026.02* — Attack formalization/benchmark on personalized local OpenClaw-style agents. `#harness` `#local-agent` `#safety`
- **Personalized Safety in LLMs: A Benchmark and A Planning-Based Agent Approach** [[paper](https://arxiv.org/abs/2505.18882)] — *arXiv 2025.05* — Personalized safety benchmark + planning-based agent approach. `#harness` `#safety` `#personalization`
- **MCP-Persona: Benchmarking LLM Agents on Real-World Personal Applications via Environment Simulation** [[paper](https://arxiv.org/abs/2606.02470)] [[code](https://github.com/wwh0411/MCP-Persona)] — *arXiv 2026.06* — Env simulation over real-world personal MCP/apps (PA harness eval). `#harness` `#MCP` `#env-synthesis` `#benchmark`
- **MyPCBench: A Benchmark for Personally Intelligent Computer-Use Agents** [[paper](https://arxiv.org/abs/2606.16748)] — *arXiv 2026.06* — Personal desktop CUA with seeded personas and multi-app tasks. `#harness` `#GUI` `#CUA` `#benchmark`
- **iOSWorld: A Benchmark for Personally Intelligent Phone Agents** [[paper](https://arxiv.org/abs/2606.09764)] — *arXiv 2026.06* — Personally intelligent phone-agent environment/benchmark. `#harness` `#mobile` `#GUI` `#benchmark`
- **Muse (Meta Personal AI Agent)** [[news](https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/)] [[design](https://introducing.muse.ai/)] [[safety blog](https://research.meta.ai/blog/security-and-safety-for-ai-agents-our-approach-with-muse)] — *2026.09* — Consumer personal AI agent: Secure VM + Sentinel authorization, memory, proactive goals. `#product` `#harness` `#safety`
- **Muse Spark Safety & Preparedness Report** [[paper](https://arxiv.org/abs/2606.12429)] — *arXiv 2026.05* — Safety & preparedness report for the Muse Spark model family. `#product` `#safety` `#model`
- **nanoMuse: An Open-Source Personal Agent for Every Device You Own** [[paper](https://arxiv.org/abs/2610.08699)] — *arXiv 2026.10* — Open-source cross-device personal agent. `#systems` `#open-source`

## 5. Benchmarks

*Evaluation suites for personal agents (end-to-end, personalization/proactivity/memory atomic, mechanism). Harness/safety benches that are primarily env+security are listed under Harness above and tagged `#benchmark`.*

- **Beyond Preference Following: Benchmarking Profile-Query Arbitration in Personalized Text Transformation** [[paper](https://arxiv.org/abs/2610.39550)] — *arXiv 2026.10* — PCA-Bench: arbitrating long-term profile vs current rewrite requests. `#benchmark` `#personalization`
- **HALO: Human-Grounded Granular Evaluation of Proactive Agents** [[paper](https://arxiv.org/abs/2610.39086)] — *arXiv 2026.10* — Human-grounded eval of whether/when/how much proactive agents should intervene. `#benchmark` `#proactivity`
- **iPrefBench: A User-Centric Benchmark for Personalized Mobile Use Agents** [[paper](https://arxiv.org/abs/2610.34735)] — *arXiv 2026.10* — Personalized iOS agents that must infer from history or ask the user. `#benchmark` `#personalization` `#mobile`
- **InferPriv: Evaluating Inferential Privacy Leakage in LLM Assistants** [[paper](https://arxiv.org/abs/2610.34640)] — *arXiv 2026.10* — Inferential privacy when personal assistants communicate with third parties. `#benchmark` `#harness` `#privacy`
- **OptionWorld: A Benchmark for Diagnosing Failures of LLMs as Long-Term Personal Assistants** [[paper](https://arxiv.org/abs/2610.28491)] — *arXiv 2026.10* — Traces information, judgment, action and outcome in multi-day daily-life tasks to locate follow-through failures. `#benchmark` `#e2e` `#long-horizon`
- **MOSAIC: An Omni-Modal Benchmark for Long-Term Memory and Cross-Modal Reasoning in Conversational Agents** [[paper](https://arxiv.org/abs/2610.29249)] — *arXiv 2026.10* — Persona-grounded multi-session omni-modal memory with write/retrieve/deliver/read diagnosis. `#benchmark` `#memory` `#multimodal`
- **MemBubble: Benchmarking How Agent Memory Shapes LLM Response Diversity** [[paper](https://arxiv.org/abs/2610.25127)] — *arXiv 2026.10* — Memory-driven personalization narrows response diversity (real-user preferences). `#benchmark` `#memory` `#personalization`
- **HABIT-Bench: Evaluating Habit Induction from Longitudinal Weak Evidence in Agent Memory** [[paper](https://arxiv.org/abs/2610.24520)] — *arXiv 2026.10* — Inferring and applying user habits from weak longitudinal evidence, incl. exceptions and changes. `#benchmark` `#memory` `#personalization`
- **Memorizing Who, Knowing How: Benchmarking Personal and Procedural Memory for Persistent Assistants** [[paper](https://arxiv.org/abs/2610.20022)] [[code](https://github.com/QMMMS/PraxisMemBench)] — *arXiv 2026.10* — PraxisMemBench couples personal and procedural memory for harness-based persistent assistance; PraxisMem learns joint memory content and organization. `#benchmark` `#memory` `#procedural` `#harness` `#personalization`
- **VitaBench 2.0: Evaluating Personalized and Proactive Agents in Long-Term User Interactions** [[paper](https://arxiv.org/abs/2605.27141)] [[code](https://github.com/meituan-longcat/VitaBench-2.0)] — *arXiv 2026.05* — Long-term personalized & proactive agents in life-service environments; pluggable memory interface. `#benchmark` `#e2e` `#personalization` `#proactivity`
- **$π$-Bench: Evaluating Proactive Personal Assistant Agents in Long-Horizon Workflows** [[paper](https://arxiv.org/abs/2605.14678)] — *arXiv 2026.05* — Hidden intent + cross-session proactive assistance in long-horizon workflows. `#benchmark` `#e2e` `#proactivity`
- **Ask Now, Use Later: Benchmarking the Proactivity Gap in Long-Lived LLM Agents** [[paper](https://arxiv.org/abs/2605.28108)] [[code](https://github.com/BUPT-GAMMA/ATRBench)] — *arXiv 2026.05* — ATRBench: ask-now-use-later proactivity gap for long-lived agents. `#benchmark` `#proactivity`
- **PAUSE: A User-Centric Benchmark for Personal AI Assistants in Unified Service Environments** [[paper](https://arxiv.org/abs/2607.27354)] [[code](https://github.com/hyc481/PAUSE)] — *arXiv 2026.07* — User-centric personal assistants in unified service environments (incl. permission awareness). `#benchmark` `#e2e` `#harness`
- **PAST-Bench: Benchmarking the Foundations of Recursive Self-Improvement in Personal Agents** [[paper](https://arxiv.org/abs/2608.04003)] [[code](https://github.com/Gen-Verse/PAST-Bench)] — *arXiv 2026.08* — Persistence on/off mechanism eval for personal-agent self-improvement. `#benchmark` `#mechanism` `#memory`
- **ProAgentBench: Evaluating LLM Agents for Proactive Assistance with Real-World Data** [[paper](https://arxiv.org/abs/2602.04482)] — *arXiv 2026.02* — Proactive assistance with real-world event/data triggers. `#benchmark` `#proactivity`
- **ProEvent: An Event-centric Benchmark for Proactive Agents** [[paper](https://arxiv.org/abs/2607.17701)] — *arXiv 2026.07* — Event-centric proactive agent benchmark. `#benchmark` `#proactivity` `#events`
- **PrefDisco: Benchmarking Proactive Personalized Reasoning** [[paper](https://arxiv.org/abs/2510.00177)] — *arXiv 2025.09* — Cold-start proactive preference discovery then personalized reasoning. `#benchmark` `#personalization` `#proactivity`
- **Evaluating Personalized Tool-Augmented LLMs from the Perspectives of Personalization and Proactivity** [[paper](https://arxiv.org/abs/2503.00771)] [[code](https://github.com/hypasd-art/ETAPP)] — *arXiv 2025.03* — ETAPP: personalized tool use under personalization + proactivity views. `#benchmark` `#tools` `#personalization` `#proactivity`
- **FingerTip 20K: A Benchmark for Proactive and Personalized Mobile LLM Agents** [[paper](https://arxiv.org/abs/2507.21071)] [[code](https://github.com/tsinghua-fib-lab/FingerTip-20K)] — *arXiv 2025.06* — Proactive suggestion + personalized GUI execution on long-term phone use. `#benchmark` `#mobile` `#GUI`
- **Do LLMs Recognize Your Preferences? Evaluating Personalized Preference Following in LLMs** [[paper](https://arxiv.org/abs/2502.09597)] — *arXiv 2025.02* — PrefEval: multi-session preference inference and following. `#benchmark` `#personalization`
- **OP-Bench: Benchmarking Over-Personalization for Memory-Augmented Personalized Conversational Agents** [[paper](https://arxiv.org/abs/2601.13722)] — *arXiv 2026.01* — Over-personalization failures in memory-augmented agents. `#benchmark` `#personalization`
- **How Does Personalized Memory Shape LLM Behavior? Benchmarking Rational Preference Utilization in Personalized Assistants** [[paper](https://arxiv.org/abs/2601.16621)] — *arXiv 2026.01* — Rational preference utilization (when to use / not use preferences). `#benchmark` `#personalization`
- **Diagnosing Personalization Failures in Mobile GUI Agents** [[paper](https://arxiv.org/abs/2610.30573)] — *arXiv 2026.10* — PrefDiag-Bench: how/when preferences change mobile GUI execution. `#benchmark` `#personalization` `#GUI`
- **LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory** [[paper](https://arxiv.org/abs/2410.10813)] [[code](https://github.com/xiaowu0162/LongMemEval)] — *ICLR 2025 / arXiv 2024.10* — Five long-term interactive memory abilities for chat assistants. `#benchmark` `#memory`
- **Evaluating Very Long-Term Conversational Memory of LLM Agents** [[paper](https://arxiv.org/abs/2402.17753)] — *ACL 2024 / arXiv 2024.02* — LoCoMo: very long multi-session conversational memory. `#benchmark` `#memory`
- **VitaBench: Benchmarking LLM Agents with Versatile Interactive Tasks in Real-world Applications** [[paper](https://arxiv.org/abs/2509.26490)] — *arXiv 2025.09* — VitaBench 1.0 life-service interactive agent benchmark (precursor to 2.0). `#benchmark` `#e2e` `#harness`
- **Personal Agent Eval (PersonalAgentEval)** [[blog](https://www.personalagenteval.com/blog/)] [[leaderboard](https://www.personalagenteval.com/)] — *2026* — Product-facing end-to-end eval of commercial personal agents (no arXiv long paper at listing time). `#benchmark` `#e2e` `#product`
- **Why Bother Me Again? Benchmarking Personal Agent Memory for Interaction Preferences** [[paper](https://arxiv.org/abs/2610.30485)] [[project](https://mempabench.com/)] — *arXiv 2026.10* — MemPABench: interaction-preference memory, when to clarify / confirm / act autonomously. `#benchmark` `#personalization` `#memory`

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md). Prefer verified arXiv ids / public URLs; one primary section per entry.

## License

[CC0-1.0](LICENSE) — paper titles and metadata remain under their original copyrights; product names are trademarks of their owners.
