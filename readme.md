# 🧠 Awesome LLM and Agent Memory

<div align="center">
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

**Collection of resources on Memory Mechanisms for LLM and Agents.**

---

## 🗺️ Navigation

<details open>
<summary><b>Click to Expand Taxonomy</b></summary>

- [📚 Surveys & Foundations](#-surveys--foundations)
- [🏗️ Cognitive Architectures & Systems](#️-cognitive-architectures--systems)
  - [Agent Operating Systems](#agent-operating-systems)
  - [Human-Inspired & Episodic Architectures](#human-inspired--episodic-architectures)
- [⚡ Efficiency & Context Optimization](#-efficiency--context-optimization)
  - [KV Cache Compression & Pruning](#kv-cache-compression--pruning)
  - [Streaming & Infinite Context](#streaming--infinite-context)
- [🧠 Knowledge & Retrieval Mechanisms](#-knowledge--retrieval-mechanisms)
  - [Graph-Based & Symbolic Memory](#graph-based--symbolic-memory)
  - [Next-Gen RAG & Vector Memory](#next-gen-rag--vector-memory)
- [🔄 Evolution, Learning & RL](#-evolution-learning--rl)
  - [Reinforcement Learning for Memory](#reinforcement-learning-for-memory)
  - [Self-Evolving & Reflective Agents](#self-evolving--reflective-agents)
- [🤖 Embodied & Domain Specific Agents](#-embodied--domain-specific-agents)
- [🧪 Benchmarks & Evaluation](#-benchmarks--evaluation)

</details>

---

## 📚 Surveys & Foundations

*Foundational papers that define the taxonomy, mechanisms, and future directions of AI memory.*

- **[2025-05-01] Rethinking Memory in AI: Taxonomy, Operations, Topics, and Future Directions** Proposes a taxonomy of six atomic memory operations (Consolidation, Updating, Indexing, Forgetting, Retrieval, Compression) to clarify functional interplay in agents.  
  [[Paper](https://www.arxiv.org/abs/2505.00675v2)]

- **[2025-04-22] From Human Memory to AI Memory: A Survey on Memory Mechanisms in the Era of LLMs** A systematic review analyzing the relationship between biological human memory categories and current AI memory systems.  
  [[Paper](https://www.arxiv.org/abs/2504.15965)]

- **[2025-09-23] Memory in Large Language Models: Mechanisms, Evaluation and Evolution** Defines LLM memory as a persistent state and proposes a governance framework linking mechanism, evaluation, and editing (e.g., ROME, MEMIT).  
  [[Paper](https://www.arxiv.org/abs/2509.18868v1)]

- **[2024-04-21] A Survey on the Memory Mechanism of Large Language Model based Agents** Reviews design patterns for memory modules in agents, discussing "what," "why," and "how" to implement memory for complex interactions.  
  [[Paper](https://www.arxiv.org/abs/2404.13501)]

- **[2025-04-03] Cognitive Memory in Large Language Models** Categorizes memory into sensory (prompts), short-term (context), and long-term (external DBs/parameters), analyzing acquisition and management strategies.  
  [[Paper](https://www.arxiv.org/abs/2504.02441)]

---

## 🏗️ Cognitive Architectures & Systems

### Agent Operating Systems

- **[2023-10-12] MemGPT: Towards LLMs as Operating Systems** Introduces virtual context management inspired by OS hierarchical memory (paging between fast/slow memory) to handle infinite context and multi-session chat.  
  [[Paper](https://www.arxiv.org/abs/2310.08560)]

- **[2025-07-04] MemOS: A Memory OS for AI System** Treats memory as a system resource with a "MemCube" unit, unifying plaintext, activation, and parameter-based memories into a schedulable hierarchy.  
  [[Paper](https://www.arxiv.org/abs/2507.03724)]

- **[2025-04-28] Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory** A scalable memory-centric architecture that dynamically extracts and consolidates salient information, showing 26% improvement over base OpenAI models.  
  [[Paper](https://www.arxiv.org/abs/2504.19413)]

- **[2025-05-04] MemEngine: A Unified and Modular Library for Developing Advanced Memory of LLM-based Agents** A modular library implementation of various memory models to facilitate reproducible development of agent memory systems.  
  [[Paper](https://www.arxiv.org/abs/2505.02099)]

### Human-Inspired & Episodic Architectures

- **[2023-04-07] Generative Agents: Interactive Simulacra of Human Behavior** The seminal work on simulating human behavior by synthesizing memories into high-level reflections and retrieving them dynamically to plan behavior.  
  [[Paper](https://www.arxiv.org/abs/2304.03442)]

- **[2024-07-12] Human-like Episodic Memory for Infinite Context LLMs (EM-LLM)** Integrates Bayesian surprise and graph-theoretic boundary refinement to organize tokens into coherent episodic events, mimicking human event cognition.  
  [[Paper](https://www.arxiv.org/abs/2407.09450)]

- **[2025-08-05] Nemori: Self-Organizing Agent Memory Inspired by Cognitive Science** Uses Event Segmentation Theory and the Free-Energy Principle to proactively learn from prediction gaps and organize raw streams into coherent episodes.  
  [[Paper](https://www.arxiv.org/abs/2508.03341)]

- **[2025-02-17] A-MEM: Agentic Memory for LLM Agents** Applies the Zettelkasten method principles to create interconnected knowledge networks through dynamic indexing and linking of agent notes.  
  [[Paper](https://www.arxiv.org/abs/2502.12110)]

---

## ⚡ Efficiency & Context Optimization

### KV Cache Compression & Pruning

- **[2024-04-22] SnapKV: LLM Knows What You are Looking for Before Generation** Automatically compresses KV caches by selecting clustered important positions, achieving 8.2x memory efficiency enhancement.  
  [[Paper](https://www.arxiv.org/abs/2404.14469)]

- **[2023-06-24] H2O: Heavy-Hitter Oracle for Efficient Generative Inference** An eviction policy based on the observation that a small portion of "Heavy Hitter" tokens contribute most of the value in attention scores.  
  [[Paper](https://www.arxiv.org/abs/2306.14048)]

- **[2024-07-30] ThinK: Thinner Key Cache by Query-Driven Pruning** Reduces memory costs by over 20% by identifying and pruning redundancy in the channel dimension of the KV cache.  
  [[Paper](https://www.arxiv.org/abs/2407.21018)]

- **[2024-06-04] PyramidKV: Dynamic KV Cache Compression based on Pyramidal Information Funneling** Dynamically adjusts cache size across layers, allocating more to lower layers and less to higher ones based on attention scattering patterns.  
  [[Paper](https://www.arxiv.org/abs/2406.02069)]

- **[2024-05-23] MiniCache: KV Cache Compression in Depth Dimension** Merges KV cache states across layers by disentangling magnitude and direction, achieving up to 5x compression.  
  [[Paper](https://www.arxiv.org/abs/2405.14366)]

### Streaming & Infinite Context

- **[2023-09-29] StreamingLLM: Efficient Streaming Language Models with Attention Sinks** Enables infinite sequence length generalization without fine-tuning by keeping initial tokens as "attention sinks" to stabilize attention scores.  
  [[Paper](https://www.arxiv.org/abs/2309.17453)]

- **[2024-05-21] SirLLM: Streaming Infinite Retentive LLM** Utilizes token entropy and a memory decay mechanism to filter key phrases, allowing for long-lasting flexible memory in infinite dialogues.  
  [[Paper](https://www.arxiv.org/abs/2405.12528)]

- **[2023-09-12] vLLM: Efficient Memory Management with PagedAttention** Optimizes serving throughput by managing KV cache memory with virtual memory paging techniques, achieving near-zero waste.  
  [[Paper](https://www.arxiv.org/abs/2309.06180)]

---

## 🧠 Knowledge & Retrieval Mechanisms

### Graph-Based & Symbolic Memory

- **[2025-02-20] HippoRAG 2: From RAG to Memory** Uses the Personalized PageRank algorithm on Knowledge Graphs to mimic the hippocampus, outperforming standard RAG in associative memory tasks.  
  [[Paper](https://www.arxiv.org/abs/2502.14802)]

- **[2025-01-20] Zep: A Temporal Knowledge Graph Architecture for Agent Memory** Introduces 'Graphiti', a temporally-aware knowledge graph engine that synthesizes unstructured conversation and structured business data.  
  [[Paper](https://www.arxiv.org/abs/2501.13956)]

- **[2023-06-06] ChatDB: Augmenting LLMs with Databases as Their Symbolic Memory** Instantiates symbolic memory as a set of SQL databases manipulated by LLM-generated SQL instructions for complex multi-hop reasoning.  
  [[Paper](https://www.arxiv.org/abs/2306.03901)]

### Next-Gen RAG & Vector Memory

- **[2024-09-09] MemoRAG: Moving towards Next-Gen RAG Via Memory-Inspired Knowledge Discovery** Adopts a dual-system architecture with a global memory module to handle ambiguous information needs where standard RAG fails.  
  [[Paper](https://www.arxiv.org/abs/2409.05591)]

- **[2025-02-01] M+: Extending MemoryLLM with Scalable Long-Term Memory** Integrates a long-term memory mechanism with a co-trained retriever to extend knowledge retention from 20k to over 160k tokens.  
  [[Paper](https://www.arxiv.org/abs/2502.00592v2)]

- **[2024-02-07] MEMORYLLM: Towards Self-Updatable Large Language Models** Comprises a transformer and a fixed-size memory pool within the latent space, enabling self-updates with text knowledge.  
  [[Paper](https://www.arxiv.org/abs/2402.04624)]

---

## 🔄 Evolution, Learning & RL

### Reinforcement Learning for Memory

- **[2025-09-30] Mem-α: Learning Memory Construction via Reinforcement Learning** Trains agents to extract and store relevant content and update memory systems using feedback from downstream QA accuracy.  
  [[Paper](https://www.arxiv.org/abs/2509.25911v1)]

- **[2025-08-27] Memory-R1: Enhancing LLM Agents to Manage Memories via RL** A framework equipping LLMs with a Memory Manager and Answer Agent, fine-tuned with PPO and GRPO to learn structured memory operations.  
  [[Paper](https://www.arxiv.org/abs/2508.19828v4)]

- **[2023-10-15] AMAGO: Scalable In-Context Reinforcement Learning for Adaptive Agents** Uses sequence models and off-policy learning to train long-sequence Transformers over entire rollouts for meta-RL and long-term memory domains.  
  [[Paper](https://www.arxiv.org/abs/2310.09971)]

### Self-Evolving & Reflective Agents

- **[2025-09-29] ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory** Distills generalizable reasoning strategies from self-judged successful/failed experiences to guide future interactions and test-time scaling.  
  [[Paper](https://www.arxiv.org/abs/2509.25140v1)]

- **[2025-08-22] Memento: Fine-tuning LLM Agents without Fine-tuning LLMs** Enables continual adaptation via memory-based online RL, formalizing the process as a Memory-augmented Markov Decision Process (M-MDP).  
  [[Paper](https://www.arxiv.org/abs/2508.16153v2)]

- **[2023-03-20] Reflexion: Language Agents with Verbal Reinforcement Learning** Agents verbally reflect on feedback signals and maintain reflective text in episodic memory to induce better decision-making in subsequent trials.  
  [[Paper](https://www.arxiv.org/abs/2303.11366)]

---

## 🤖 Embodied & Domain Specific Agents

- **[2023-05-25] Voyager: An Open-Ended Embodied Agent with Large Language Models** The first LLM-powered embodied lifelong learning agent in Minecraft with an automatic curriculum and skill library.  
  [[Paper](https://www.arxiv.org/abs/2305.16291)]

- **[2023-05-25] Ghost in the Minecraft (GITM): Generally Capable Agents for Open-World Environments** Integrates LLMs with text-based knowledge and memory to create generally capable agents that navigate sparse-reward environments.  
  [[Paper](https://www.arxiv.org/abs/2305.17144v2)]

- **[2024-09-23] KARMA: Augmenting Embodied AI Agents with Long-and-short Term Memory Systems** Uses dual-memory (3D scene graphs for long-term, dynamic records for short-term) to improve task planning in embodied agents.  
  [[Paper](https://www.arxiv.org/abs/2409.14908v2)]

- **[2025-07-10] MIRIX: Multi-Agent Memory System for LLM-Based Agents** A modular memory system with six memory types (Core, Episodic, Semantic, etc.) designed for multi-agent coordination.  
  [[Paper](https://www.arxiv.org/abs/2507.07957)]

- **[2023-09-07] TradingGPT: Multi-Agent System with Layered Memory for Financial Trading** Organizes memory into layers with custom decay mechanisms to emulate human cognitive processes for financial decision making.  
  [[Paper](https://www.arxiv.org/abs/2309.03736)]

---

## 🧪 Benchmarks & Evaluation

- **[2025-11-25] Evo-Memory: Benchmarking LLM Agent Test-time Learning with Self-Evolving Memory** A streaming benchmark evaluating how agents accumulate and reuse experience across evolving task streams.  
  [[Paper](https://www.arxiv.org/abs/2511.20857v1)]

- **[2025-10-20] MemoryBench: A Benchmark for Memory and Continual Learning in LLM Systems** Evaluates the ability of systems to learn from accumulated user feedback rather than just reading comprehension.  
  [[Paper](https://www.arxiv.org/abs/2510.17281v2)]

- **[2025-07-07] MemoryAgentBench: Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions** Identifies four core competencies: accurate retrieval, test-time learning, long-range understanding, and conflict resolution.  
  [[Paper](https://www.arxiv.org/abs/2507.05257)]

- **[2024-10-14] LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory** Evaluates information extraction, multi-session reasoning, knowledge updates, and abstention in chat assistants.  
  [[Paper](https://www.arxiv.org/abs/2410.10813)]