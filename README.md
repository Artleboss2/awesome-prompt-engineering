# Awesome Prompt Engineering [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Techniques, tools, papers, and resources for crafting effective prompts for large language models.

Prompt engineering is the practice of designing and refining inputs to language models in order to reliably produce desired outputs. This list covers foundational concepts, cutting-edge research, production tooling, evaluation methods, and real-world patterns used by practitioners building with LLMs.

---

## Contents

- [Fundamentals](#fundamentals)
- [Core Techniques](#core-techniques)
  - [Zero-Shot Prompting](#zero-shot-prompting)
  - [Few-Shot Prompting](#few-shot-prompting)
  - [Chain-of-Thought](#chain-of-thought)
  - [Advanced Reasoning Frameworks](#advanced-reasoning-frameworks)
  - [Role and Persona Prompting](#role-and-persona-prompting)
  - [Structured Output Prompting](#structured-output-prompting)
- [Prompt Security](#prompt-security)
- [Retrieval-Augmented Generation](#retrieval-augmented-generation)
- [Agents and Tool Use](#agents-and-tool-use)
- [Prompt Optimization and Tuning](#prompt-optimization-and-tuning)
- [Evaluation and Benchmarking](#evaluation-and-benchmarking)
- [Tools](#tools)
  - [Prompt Management](#prompt-management)
  - [Orchestration Frameworks](#orchestration-frameworks)
  - [Structured Output](#structured-output)
  - [Testing and Evaluation](#testing-and-evaluation)
  - [Playgrounds](#playgrounds)
- [Model-Specific Guides](#model-specific-guides)
- [Papers](#papers)
  - [Foundational](#foundational)
  - [Reasoning](#reasoning)
  - [Agents](#agents)
  - [Safety and Robustness](#safety-and-robustness)
  - [Optimization](#optimization)
- [Courses and Tutorials](#courses-and-tutorials)
- [Books](#books)
- [Communities](#communities)
- [Blogs and Newsletters](#blogs-and-newsletters)
- [Real-World Patterns and Cookbooks](#real-world-patterns-and-cookbooks)
- [Multimodal Prompting](#multimodal-prompting)
- [Domain-Specific Prompting](#domain-specific-prompting)
  - [Code Generation](#code-generation)
  - [Data Analysis](#data-analysis)
  - [Writing and Content](#writing-and-content)
  - [Legal and Finance](#legal-and-finance)
  - [Science and Research](#science-and-research)
- [Prompt Chaining and Pipelines](#prompt-chaining-and-pipelines)
- [Memory and State Management](#memory-and-state-management)
- [Prompt Engineering for Specific Output Types](#prompt-engineering-for-specific-output-types)
- [Evaluation Metrics Reference](#evaluation-metrics-reference)
- [Prompt Templates and Formats](#prompt-templates-and-formats)
- [Prompt Anti-Patterns](#prompt-anti-patterns)
- [Testing and Debugging Prompts](#testing-and-debugging-prompts)
- [Production Deployment Considerations](#production-deployment-considerations)
- [Open-Source Models and Local Deployment](#open-source-models-and-local-deployment)
- [Fine-Tuning vs. Prompting](#fine-tuning-vs-prompting)
- [Responsible AI and Ethics in Prompting](#responsible-ai-and-ethics-in-prompting)
- [Context Management](#context-management)
- [Glossary](#glossary)

---

## Fundamentals

Core concepts and official documentation to get started.

- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering) - Official documentation covering six core strategies for getting better results from GPT models, including tactic breakdowns and worked examples.
- [Anthropic Prompt Engineering Overview](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) - Comprehensive guide to prompting Claude, covering chain-of-thought, XML structuring, role prompting, and context window management.
- [Anthropic Prompt Library](https://docs.anthropic.com/en/prompt-library/library) - Curated collection of ready-to-use prompts for Claude covering dozens of real-world tasks.
- [Google Gemini Prompting Guide](https://ai.google.dev/gemini-api/docs/prompting-intro) - Introduction to prompting concepts for the Gemini model family, including multimodal examples.
- [Meta Llama Prompting Guide](https://llama.meta.com/docs/how-to-guides/prompting/) - Official guidance for prompting Llama 2 and Llama 3 models, including the system prompt format.
- [Mistral Prompting Guide](https://docs.mistral.ai/guides/prompting_capabilities/) - Covers prompting capabilities of Mistral models including function calling and instruction following.
- [Learn Prompting](https://learnprompting.org) - Free, open-source, community-maintained course covering prompt engineering from beginner to advanced level with interactive examples.
- [Prompting Guide (DAIR.AI)](https://www.promptingguide.ai) - Widely referenced guide maintained by DAIR.AI covering techniques, models, applications, and the latest research in one place.
- [IBM Prompt Engineering Basics](https://www.ibm.com/topics/prompt-engineering) - Accessible introduction to core concepts, terminology, and use cases for enterprise practitioners.

---

## Core Techniques

### Zero-Shot Prompting

Asking a model to complete a task without providing any examples.

- [Zero-Shot Learning in NLP](https://arxiv.org/abs/1909.01840) - Survey of zero-shot learning methods and how they apply to natural language processing tasks.
- [Zero-Shot Text Classification](https://arxiv.org/abs/2210.07185) - Research on using instruction-tuned models for classifying text into categories unseen during training.
- [Instruction Tuning Survey](https://arxiv.org/abs/2308.10792) - Comprehensive overview of how instruction fine-tuning enables zero-shot task generalization.

### Few-Shot Prompting

Providing a small number of input-output examples in the prompt to guide the model.

- [Few-Shot Learners (GPT-3 Paper)](https://arxiv.org/abs/2005.14165) - The original GPT-3 paper demonstrating in-context learning with examples, establishing the few-shot paradigm.
- [Rethinking the Role of Demonstrations](https://arxiv.org/abs/2202.12837) - Analysis showing that the format and distribution of examples matters more than their correctness.
- [What Makes Good In-Context Examples](https://arxiv.org/abs/2101.06804) - Study exploring how the selection of few-shot examples impacts model performance.
- [KATE: k-Nearest Neighbor Augmented](https://arxiv.org/abs/2101.11974) - Method for dynamically selecting the best few-shot examples for each query using nearest-neighbor retrieval.

### Chain-of-Thought

Techniques that prompt the model to reason step-by-step before answering.

- [Chain-of-Thought Prompting Elicits Reasoning](https://arxiv.org/abs/2201.11903) - Seminal paper by Wei et al. introducing chain-of-thought prompting and demonstrating strong gains on math and reasoning tasks.
- [Zero-Shot Chain-of-Thought](https://arxiv.org/abs/2205.11916) - Demonstrates that simply appending "Let's think step by step" to a prompt significantly improves zero-shot reasoning without any examples.
- [Least-to-Most Prompting](https://arxiv.org/abs/2205.10625) - Decomposes hard problems into easier sub-problems and solves them sequentially to improve generalization.
- [Program-of-Thought Prompting](https://arxiv.org/abs/2211.12588) - Separates computation from reasoning by prompting models to generate executable code rather than natural language chains.
- [Faithful Chain-of-Thought](https://arxiv.org/abs/2301.13379) - Addresses the faithfulness gap between stated reasoning chains and actual model computations.

### Advanced Reasoning Frameworks

More complex frameworks that go beyond linear chain-of-thought.

- [Tree of Thoughts](https://arxiv.org/abs/2305.10601) - Yao et al. framework for deliberate problem solving by exploring multiple reasoning paths, backtracking, and lookahead.
- [Graph of Thoughts](https://arxiv.org/abs/2308.09687) - Extends tree-based reasoning into a graph structure, enabling arbitrary information flow and combining multiple reasoning branches.
- [Algorithm of Thoughts](https://arxiv.org/abs/2308.10379) - Guides models to follow algorithmic reasoning patterns inspired by classical search algorithms.
- [Self-Consistency](https://arxiv.org/abs/2203.11171) - Samples multiple independent reasoning chains and aggregates the majority answer, significantly improving accuracy over greedy decoding.
- [Reflexion](https://arxiv.org/abs/2303.11366) - Framework enabling agents to verbally reflect on task feedback and store reflections in memory for future improvement.
- [ReAct: Synergizing Reasoning and Acting](https://arxiv.org/abs/2210.03629) - Interleaves reasoning traces with action steps, allowing models to interact with external environments during problem solving.
- [Socratic Models](https://arxiv.org/abs/2204.00598) - Composes multiple large models by having them exchange information through natural language prompting.

### Role and Persona Prompting

Assigning identities, roles, or behavioral constraints to models.

- [Role Prompting Guide (Anthropic)](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/system-prompts) - Official guidance on structuring system prompts for persona, context, and constraint setting.
- [Is "Pretend You Are an Expert" Useful?](https://arxiv.org/abs/2305.14930) - Empirical study on whether role-based prompting actually improves model outputs across domains.
- [ExpertPrompting](https://arxiv.org/abs/2305.14688) - Automatically generates rich expert identities and uses them as system context to improve answer quality.
- [Character Play and Persona Stability](https://arxiv.org/abs/2310.11501) - Analysis of how models maintain character consistency over multi-turn conversations.

### Structured Output Prompting

Techniques for reliably extracting structured data from model outputs.

- [JSON Mode Prompting (OpenAI)](https://platform.openai.com/docs/guides/structured-outputs) - Official guide to using structured output mode with JSON schema validation in the API.
- [Prompting for Structured Extraction (Anthropic)](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/increase-output-consistency) - Strategies for using XML tags, examples, and formatting instructions to increase output consistency.
- [TypeChat](https://github.com/microsoft/TypeChat) - Microsoft library that uses TypeScript schemas as a natural way to define and validate structured LLM outputs.
- [LMQL](https://github.com/eth-sri/lmql) - Query language for LLMs that supports output constraints including type constraints, regex patterns, and logical conditions.

---

## Prompt Security

Research and tooling for defending against adversarial prompt manipulation.

- [Prompt Injection Attacks and Defenses](https://arxiv.org/abs/2302.12173) - Survey of injection attack types and a taxonomy of mitigation strategies.
- [Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483) - Analysis of competing objectives in safety training that create exploitable gaps.
- [Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications](https://arxiv.org/abs/2302.12173) - Demonstrates how indirect prompt injection through retrieved content can manipulate agents.
- [LLM Guard](https://github.com/protectai/llm-guard) - Security toolkit providing input/output scanning, sanitization, and detection of prompt injection and sensitive data leakage.
- [Rebuff](https://github.com/protectai/rebuff) - Self-hardening prompt injection detector using a dedicated LLM and vector database of known attacks.
- [Prompt Armor](https://promptarmor.com) - Commercial service providing API-level protection against prompt injection, jailbreaks, and data exfiltration.
- [Garak](https://github.com/leondz/garak) - LLM vulnerability scanner that probes models for prompt injection, jailbreaking, and other failure modes.

---

## Retrieval-Augmented Generation

Combining retrieval systems with prompts to ground model outputs in external knowledge.

- [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://arxiv.org/abs/2005.11401) - Original RAG paper by Lewis et al. combining dense retrieval with sequence-to-sequence generation.
- [Self-RAG: Learning to Retrieve, Generate, and Critique](https://arxiv.org/abs/2310.11511) - Model that learns when to retrieve, critiques its own outputs, and selectively incorporates retrieved passages.
- [RAGAS](https://github.com/explodinggradients/ragas) - Framework for evaluating RAG pipelines across retrieval quality, faithfulness, and answer relevance dimensions.
- [LlamaIndex](https://github.com/run-llama/llama_index) - Comprehensive data framework for building RAG applications with support for dozens of data sources and retrieval strategies.
- [Haystack](https://github.com/deepset-ai/haystack) - Production-ready LLM orchestration framework with modular pipeline components for retrieval and generation.
- [Contextual Compression](https://python.langchain.com/docs/how_to/contextual_compression/) - LangChain technique for filtering and compressing retrieved documents to fit relevant information within context limits.
- [HyDE: Hypothetical Document Embeddings](https://arxiv.org/abs/2212.10496) - Generates a hypothetical answer first, then retrieves documents similar to it rather than to the raw query.
- [Advanced RAG Techniques](https://github.com/NirDiamant/RAG_Techniques) - Community-maintained collection of advanced RAG patterns including multi-query retrieval, re-ranking, and hybrid search.

---

## Agents and Tool Use

Frameworks and research for building LLM agents that plan, use tools, and complete multi-step tasks.

- [Toolformer: Language Models Can Teach Themselves to Use Tools](https://arxiv.org/abs/2302.04761) - Self-supervised approach for teaching models when and how to call external APIs.
- [HuggingGPT / JARVIS](https://arxiv.org/abs/2303.17580) - System that uses ChatGPT to plan, invoke, and aggregate results from specialized AI models as tools.
- [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) - One of the first widely adopted autonomous agent frameworks enabling long-horizon goal pursuit.
- [BabyAGI](https://github.com/yoheinakajima/babyagi) - Minimal autonomous task agent using OpenAI and vector memory for task creation, prioritization, and execution.
- [AgentBench](https://github.com/THUDM/AgentBench) - Benchmark for evaluating LLM agents across eight diverse interactive environments.
- [OpenAI Function Calling Guide](https://platform.openai.com/docs/guides/function-calling) - Official documentation for structured tool use in GPT models with schema-defined function signatures.
- [LangGraph](https://github.com/langchain-ai/langgraph) - Library for building stateful, multi-actor agent workflows as directed graphs with controllable execution.
- [CrewAI](https://github.com/crewAIInc/crewAI) - Framework for orchestrating role-playing autonomous AI agents working as a collaborative crew.
- [Voyager: An Open-Ended Embodied Agent with LLMs](https://arxiv.org/abs/2305.16291) - Agent that continuously explores, acquires skills, and makes discoveries in Minecraft through prompting.
- [SWE-agent](https://github.com/SWE-agent/SWE-agent) - Agent that uses LLMs to autonomously fix bugs in real GitHub repositories.

---

## Prompt Optimization and Tuning

Automated and manual approaches to making prompts perform better.

- [Automatic Prompt Engineer (APE)](https://arxiv.org/abs/2211.01910) - Uses LLMs to generate, evaluate, and select prompt candidates, outperforming human-written prompts on several benchmarks.
- [DSPy: Compiling Declarative Language Model Calls](https://arxiv.org/abs/2310.03714) - Stanford framework replacing handcrafted prompts with learned modules that are algorithmically optimized.
- [DSPy GitHub](https://github.com/stanfordnlp/dspy) - Source repository for DSPy including tutorials, examples, and optimizers.
- [Prompt Optimization with Human Feedback](https://arxiv.org/abs/2402.02008) - Method that iteratively refines prompts using preference feedback from humans or AI judges.
- [Soft Prompt Tuning](https://arxiv.org/abs/2104.08691) - Prepends learnable continuous vectors to the input rather than modifying model weights, matching fine-tuning efficiency at scale.
- [Prefix Tuning](https://arxiv.org/abs/2101.00190) - Optimizes only a small set of continuous task-specific prefix parameters while keeping the model frozen.
- [AutoPrompt](https://arxiv.org/abs/2010.15980) - Gradient-based method for automatically generating discrete prompt tokens for classification and QA tasks.
- [Promptbreeder](https://arxiv.org/abs/2309.16797) - Self-referential evolution system that uses LLMs to mutate and select both task prompts and the mutation prompts themselves.
- [EvoPrompting](https://arxiv.org/abs/2302.14838) - Combines evolutionary search with few-shot prompting to find high-performing few-shot examples.
- [OPRO: Large Language Models as Optimizers](https://arxiv.org/abs/2309.03409) - Uses natural language descriptions of past evaluation results to iteratively improve prompts.

---

## Evaluation and Benchmarking

Methods and datasets for measuring prompt and model quality.

- [HELM: Holistic Evaluation of Language Models](https://arxiv.org/abs/2211.09110) - Comprehensive benchmark covering accuracy, calibration, robustness, fairness, efficiency, and more across dozens of scenarios.
- [BIG-Bench](https://github.com/google/BIG-bench) - Collaborative benchmark of 204 tasks designed to probe LLM capabilities beyond standard evaluations.
- [PromptBench](https://github.com/microsoft/promptbench) - Unified evaluation library for assessing model robustness to adversarially modified prompts.
- [MT-Bench](https://arxiv.org/abs/2306.05685) - Multi-turn conversational benchmark with GPT-4 as judge, useful for evaluating instruction-following quality.
- [Evals (OpenAI)](https://github.com/openai/evals) - Framework and registry for creating custom evaluations of OpenAI models.
- [LangSmith](https://www.langchain.com/langsmith) - Platform for tracing, evaluating, and monitoring LLM applications built on LangChain.
- [Braintrust](https://www.braintrust.dev) - Evaluation platform with prompt playground, dataset management, and regression testing workflows.
- [PromptFoo](https://github.com/promptfoo/promptfoo) - CLI and library for running automated red-teaming, regression testing, and comparisons across prompts and models.
- [DeepEval](https://github.com/confident-ai/deepeval) - Open-source evaluation framework with 14+ metrics including hallucination detection, relevance, and toxicity.
- [LMSYS Chatbot Arena](https://chat.lmsys.org) - Human preference evaluation platform with Elo ratings for comparing language models through blind A/B testing.

---

## Tools

### Prompt Management

- [PromptLayer](https://github.com/MagnivOrg/prompt-layer-library) - Middleware for logging, versioning, searching, and scoring prompt templates in production.
- [Pezzo](https://github.com/pezzolabs/pezzo) - Open-source prompt management and observability platform with version control and team collaboration.
- [Agenta](https://github.com/Agenta-AI/agenta) - Open-source LLM developer platform for prompt versioning, A/B testing, and evaluation pipelines.
- [Helicone](https://github.com/Helicone/helicone) - Observability platform providing request logging, cost tracking, and caching for LLM API calls.
- [Portkey](https://portkey.ai) - AI gateway with prompt versioning, A/B testing, fallbacks, and unified observability across model providers.
- [Langfuse](https://github.com/langfuse/langfuse) - Open-source LLM observability and analytics platform with prompt management and experiment tracking.

### Orchestration Frameworks

- [LangChain](https://github.com/langchain-ai/langchain) - Most widely adopted framework for chaining prompts, tools, and memory into complex LLM applications.
- [LlamaIndex](https://github.com/run-llama/llama_index) - Data-centric framework specializing in RAG pipelines, data connectors, and structured querying.
- [Semantic Kernel](https://github.com/microsoft/semantic-kernel) - Microsoft SDK for composing AI capabilities using prompt templates, functions, and planners in .NET and Python.
- [Haystack](https://github.com/deepset-ai/haystack) - Pipeline-based framework for production RAG, question answering, and document processing systems.
- [Guidance](https://github.com/guidance-ai/guidance) - Programming paradigm that interleaves prompt text with generation and control logic for constrained outputs.
- [Marvin](https://github.com/prefecthq/marvin) - Lightweight toolkit for building AI-powered functions, classifiers, and extractors using natural language.
- [Instructor](https://github.com/instructor-ai/instructor) - Structured output extraction library using Pydantic models to validate and retry LLM responses.
- [Outlines](https://github.com/dottxt-ai/outlines) - Library for structured text generation that guarantees output format compliance at the token level.

### Structured Output

- [Instructor](https://github.com/instructor-ai/instructor) - Pythonic interface for extracting Pydantic-validated structured data from any LLM provider.
- [Outlines](https://github.com/dottxt-ai/outlines) - Enforces JSON schema, regex, and grammar constraints during LLM generation via logit biasing.
- [Guardrails AI](https://github.com/guardrails-ai/guardrails) - Framework for adding validation, correction, and structured output contracts on top of LLM responses.
- [LMQL](https://github.com/eth-sri/lmql) - Prompt query language supporting scripted generation with output constraints expressed as code.
- [Jsonformer](https://github.com/1rgs/jsonformer) - Enforces JSON output structure by generating only the values from the LLM while filling structural tokens deterministically.
- [TypeChat](https://github.com/microsoft/TypeChat) - Uses TypeScript type definitions as the schema language for requesting and validating structured LLM outputs.

### Testing and Evaluation

- [PromptFoo](https://github.com/promptfoo/promptfoo) - Test framework for running assertions against LLM outputs with support for red teaming and model comparisons.
- [DeepEval](https://github.com/confident-ai/deepeval) - Pytest-like framework for unit testing LLM outputs with metrics for hallucination, bias, and answer relevance.
- [Evals (OpenAI)](https://github.com/openai/evals) - Evaluation framework and registry for testing models against custom task definitions.
- [PromptBench](https://github.com/microsoft/promptbench) - Robustness evaluation library testing how models perform under adversarial perturbations to prompts.
- [TruLens](https://github.com/truera/trulens) - Evaluation and tracking library with explainable metrics for RAG pipelines.
- [RAGAS](https://github.com/explodinggradients/ragas) - Framework for reference-free evaluation of RAG systems using LLM-as-judge approaches.

### Playgrounds

- [OpenAI Playground](https://platform.openai.com/playground) - Browser-based interface for testing GPT models with controls for temperature, top-p, system prompts, and JSON mode.
- [Google AI Studio](https://aistudio.google.com) - Prompt builder and testing interface for Gemini models supporting text, code, image, and video inputs.
- [Anthropic Console](https://console.anthropic.com) - Workbench for building, testing, and comparing prompts across Claude models with token usage tracking.
- [Hugging Face Inference Playground](https://huggingface.co/chat) - Test open-weight models hosted on Hugging Face with conversational and instruction interfaces.
- [Nat.dev](https://nat.dev) - Multi-model playground for comparing responses from GPT, Claude, and open-source models side by side.
- [PromptHero](https://prompthero.com) - Community-driven library of prompts for image, code, and text generation with ratings and examples.

---

## Model-Specific Guides

Deep-dive documentation and community guides for specific model families.

- [GPT-4 Technical Report](https://arxiv.org/abs/2303.08774) - OpenAI's technical overview of GPT-4 capabilities, limitations, and safety properties.
- [Claude Model Card](https://www.anthropic.com/claude) - Anthropic's documentation on Claude's capabilities, safety training, and intended use.
- [Llama 3 Prompt Format](https://llama.meta.com/docs/model-cards-and-prompt-formats/meta-llama-3/) - Official format specification for system prompts, conversation turns, and tool use in Llama 3.
- [Mistral Prompt Guide](https://docs.mistral.ai/guides/prompting_capabilities/) - Covers instruction, chat, and function-calling formats specific to Mistral models.
- [Gemini API Prompting Strategies](https://ai.google.dev/gemini-api/docs/prompting-strategies) - Google's guide to text, image, audio, and video prompting for the Gemini family.
- [Command R+ Grounded Generation Guide](https://docs.cohere.com/docs/grounded-generation) - Cohere's documentation on retrieval-grounded prompting with citation support in Command R+.
- [WizardLM Evol-Instruct](https://arxiv.org/abs/2304.12244) - Paper describing the instruction evolution technique used to create high-quality instruction tuning data.

---

## Papers

### Foundational

- [Attention Is All You Need](https://arxiv.org/abs/1706.03762) - Transformer architecture paper that underlies all modern LLMs.
- [Language Models are Few-Shot Learners (GPT-3)](https://arxiv.org/abs/2005.14165) - Established in-context learning as a core paradigm for prompting.
- [Finetuned Language Models Are Zero-Shot Learners (FLAN)](https://arxiv.org/abs/2109.01652) - Showed that instruction fine-tuning dramatically improves zero-shot generalization.
- [Training Language Models to Follow Instructions with Human Feedback](https://arxiv.org/abs/2203.02155) - InstructGPT paper introducing RLHF for instruction-following alignment.
- [Constitutional AI: Harmlessness from AI Feedback](https://arxiv.org/abs/2212.08073) - Anthropic's method for using a set of principles and AI feedback for alignment without human labelers.

### Reasoning

- [Chain-of-Thought Prompting Elicits Reasoning in LLMs](https://arxiv.org/abs/2201.11903) - Wei et al. introducing CoT with worked examples across arithmetic, commonsense, and symbolic reasoning.
- [Self-Consistency Improves Chain of Thought Reasoning](https://arxiv.org/abs/2203.11171) - Sampling multiple diverse reasoning paths and selecting the majority answer.
- [Tree of Thoughts: Deliberate Problem Solving with LLMs](https://arxiv.org/abs/2305.10601) - Search-based framework enabling systematic exploration of reasoning branches.
- [Let's Verify Step by Step](https://arxiv.org/abs/2305.20050) - OpenAI's process reward model paper for training verifiers to score reasoning steps, not just final answers.
- [Scaling LLM Test-Time Compute](https://arxiv.org/abs/2408.03314) - Analysis of how allocating more computation at inference time through repeated sampling and verification improves accuracy.

### Agents

- [ReAct: Synergizing Reasoning and Acting in LLMs](https://arxiv.org/abs/2210.03629) - Interleaved thought-action-observation loops enabling more grounded and accurate task completion.
- [Toolformer: Language Models Can Teach Themselves to Use Tools](https://arxiv.org/abs/2302.04761) - Self-supervised method for integrating API calls into model generation.
- [Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/abs/2304.03442) - Simulation of 25 agents with memory, reflection, and planning using LLM backbones.
- [AgentBench: Evaluating LLMs as Agents](https://arxiv.org/abs/2308.03688) - Benchmark spanning web browsing, coding, database querying, and game environments.
- [AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation](https://arxiv.org/abs/2308.08155) - Microsoft Research framework for building applications from conversations between specialized agents.

### Safety and Robustness

- [Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483) - Analysis of competing objectives and generalization failures in safety-tuned models.
- [Universal and Transferable Adversarial Attacks on Aligned Language Models](https://arxiv.org/abs/2307.15043) - Greedy coordinate gradient (GCG) attack discovering transferable jailbreak suffixes.
- [Prompt Injection Attacks Against LLM-Integrated Applications](https://arxiv.org/abs/2306.05499) - Framework for classifying and evaluating injection attack surfaces in real applications.
- [TruthfulQA: Measuring How Models Mimic Human Falsehoods](https://arxiv.org/abs/2109.07958) - Benchmark exposing how fine-tuned models propagate misconceptions present in training data.
- [Sycophancy to Subterfuge: Investigating Reward Tampering in LMs](https://arxiv.org/abs/2406.10162) - Anthropic study on how sycophantic tendencies in models can be generalized into more dangerous behaviors.

### Optimization

- [Large Language Models Are Human-Level Prompt Engineers](https://arxiv.org/abs/2211.01910) - APE paper showing LLM-generated prompts match or exceed human-engineered ones.
- [DSPy: Compiling Declarative LM Calls into Self-Improving Pipelines](https://arxiv.org/abs/2310.03714) - Replaces fragile prompt strings with modular, optimizable components.
- [Prompt Optimization in Multi-Step Tasks with Reinforcement Learning](https://arxiv.org/abs/2406.11695) - Applies RL to optimize intermediate prompt steps in agentic pipelines.
- [OPRO: Large Language Models as Optimizers](https://arxiv.org/abs/2309.03409) - Meta-prompt that asks the model to iteratively improve prompts given past performance results.
- [Promptbreeder: Self-Referential Self-Improvement via Prompt Evolution](https://arxiv.org/abs/2309.16797) - Evolutionary algorithm where both task prompts and mutation operators are co-evolved by LLMs.

---

## Courses and Tutorials

- [DeepLearning.AI: ChatGPT Prompt Engineering for Developers](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) - Free short course co-created with OpenAI covering iterative development, summarization, inference, transformation, and expansion.
- [DeepLearning.AI: Building Systems with the ChatGPT API](https://www.deeplearning.ai/short-courses/building-systems-with-chatgpt/) - Covers multi-step pipelines, chain-of-thought evaluation, and moderation with the OpenAI API.
- [DeepLearning.AI: LangChain for LLM Application Development](https://www.deeplearning.ai/short-courses/langchain-for-llm-application-development/) - Practical course on building production applications using LangChain components and agents.
- [Anthropic Prompt Engineering Interactive Tutorial](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/prompt-engineering-tutorial) - Hands-on tutorial walking through Claude-specific prompting techniques with exercises.
- [Cohere LLM University](https://llm.university) - Free curriculum from Cohere covering NLP fundamentals, embeddings, generation, and retrieval.
- [FastAI Practical Deep Learning](https://course.fast.ai) - Pragmatic course covering deep learning and NLP from first principles with hands-on notebooks.
- [Prompt Engineering Guide (DAIR.AI)](https://github.com/dair-ai/Prompt-Engineering-Guide) - Comprehensive community guide covering all major techniques with links to primary research.
- [Microsoft Generative AI for Beginners](https://github.com/microsoft/generative-ai-for-beginners) - 21-lesson open curriculum covering LLM concepts, prompt engineering, RAG, and responsible AI.
- [Google Cloud Generative AI Learning Path](https://cloudskillsboost.google/paths/118) - Series of courses on generative AI, LLMs, and responsible use on Google Cloud infrastructure.
- [Brex Prompt Engineering Guide](https://github.com/brexhq/prompt-engineering) - Practical internal guide open-sourced by Brex, covering model internals, prompt patterns, and pitfalls.
- [Lil'Log by Lilian Weng](https://lilianweng.github.io/posts/2023-03-15-prompt-engineering/) - Detailed technical blog post on prompting techniques from an OpenAI researcher perspective.

---

## Books

- [Prompt Engineering for LLMs (O'Reilly)](https://www.oreilly.com/library/view/prompt-engineering-for/9781098153427/) - Comprehensive O'Reilly book covering techniques, design patterns, and integration with real applications.
- [Building LLM Applications for Production (Chip Huyen)](https://www.oreilly.com/library/view/ai-engineering/9781098166298/) - Covers the full lifecycle of LLM-powered systems from prompt design to deployment and evaluation.
- [Generative AI on AWS (O'Reilly)](https://www.oreilly.com/library/view/generative-ai-on/9781098159221/) - Practical guide to prompt engineering, fine-tuning, and RAG on AWS infrastructure.

---

## Communities

- [r/PromptEngineering](https://www.reddit.com/r/PromptEngineering/) - Active Reddit community for sharing and discussing techniques, findings, and creative prompts.
- [r/LocalLLaMA](https://www.reddit.com/r/LocalLLaMA/) - Community focused on running open-weight models locally, with heavy discussion of prompting, quantization, and tooling.
- [Hugging Face Discord](https://huggingface.co/join/discord) - Large active community around open-source models and tools including dedicated prompt engineering channels.
- [DAIR.AI Discord](https://discord.gg/SKgkVT8BGJ) - Community focused on AI democratization with active channels on prompt research and applications.
- [Learn Prompting Discord](https://discord.gg/7enStJXQzD) - Community around the learnprompting.org curriculum with beginner-friendly channels.
- [LangChain Discord](https://discord.gg/langchain) - Active community for LangChain users including channels on agents, RAG, and prompt debugging.
- [Eleuther AI Discord](https://discord.gg/zBGx3azzUn) - Research-oriented community with in-depth discussion of model internals, evals, and prompting.
- [AI Alignment Forum](https://www.alignmentforum.org) - Research discussion forum covering alignment, interpretability, and safety-adjacent prompt topics.

---

## Blogs and Newsletters

- [The Batch (DeepLearning.AI)](https://www.deeplearning.ai/the-batch/) - Weekly newsletter by Andrew Ng covering the latest in AI research and applications including LLM development.
- [Lil'Log (Lilian Weng)](https://lilianweng.github.io) - Deep technical posts on LLM internals, prompting, RLHF, and agent architectures from an OpenAI researcher.
- [Ahead of AI (Sebastian Raschka)](https://magazine.sebastianraschka.com) - Research-heavy newsletter covering LLM papers, prompt techniques, and fine-tuning developments.
- [Simon Willison's Weblog](https://simonwillison.net) - Practical posts on LLM tools, prompt injection risks, and real-world application patterns.
- [The Gradient](https://thegradient.pub) - Academic-style blog covering ML research trends including reasoning, agents, and prompting methods.
- [Towards Data Science](https://towardsdatascience.com/tagged/prompt-engineering) - Community-written articles with practical tutorials and prompt engineering case studies.
- [Eugene Yan's Blog](https://eugeneyan.com) - Thoughtful posts on applied ML and LLM systems including prompt design and evaluation.
- [Chip Huyen's Blog](https://huyenchip.com/blog/) - In-depth posts on LLM system design, RAG patterns, and real-world deployment challenges.

---

## Real-World Patterns and Cookbooks

Practical recipes and proven patterns for common prompt engineering challenges.

- [OpenAI Cookbook](https://github.com/openai/openai-cookbook) - Community-maintained collection of code examples for common tasks with the OpenAI API including embeddings, functions, and fine-tuning.
- [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook) - Official collection of Claude recipes covering tool use, RAG, long context, and vision.
- [Gemini Cookbook](https://github.com/google-gemini/cookbook) - Google's collection of examples and guides for using Gemini models across modalities.
- [LangChain Templates](https://github.com/langchain-ai/langchain/tree/master/templates) - Ready-to-deploy reference applications covering RAG, agents, extraction, and summarization.
- [Prompt Patterns Catalog](https://arxiv.org/abs/2302.11382) - Academic catalog of reusable prompt design patterns organized by problem type, analogous to software design patterns.
- [Fabric](https://github.com/danielmiessler/fabric) - Collection of community-curated prompt patterns for common workflows like summarization, analysis, and content creation.
- [Awesome ChatGPT Prompts](https://github.com/f/awesome-chatgpt-prompts) - Community-maintained collection of persona and task prompts for ChatGPT.
- [Prompt Engineering Guide Techniques](https://www.promptingguide.ai/techniques) - Structured overview of all major prompting techniques with examples and paper references.

---

## Multimodal Prompting

Techniques specific to prompting models that handle images, audio, and video alongside text.

- [Visual Chain-of-Thought](https://arxiv.org/abs/2305.02317) - Extends CoT reasoning to vision-language models by generating intermediate visual reasoning steps.
- [GPT-4V System Card](https://openai.com/research/gpt-4v-system-card) - OpenAI's documentation on GPT-4 Vision capabilities, limitations, and prompting considerations for image inputs.
- [Gemini Multimodal Prompting Guide](https://ai.google.dev/gemini-api/docs/vision) - Official guide for prompting Gemini with images, video, and audio including best practices.
- [LLaVA: Large Language and Vision Assistant](https://arxiv.org/abs/2304.08485) - Open-source multimodal model with prompting guidance for visual instruction following.
- [CogVLM](https://github.com/THUDM/CogVLM) - Open-source visual language model with detailed prompting and fine-tuning documentation.
- [InstructPix2Pix](https://arxiv.org/abs/2211.09800) - Demonstrates using natural language prompts to direct image editing operations.
- [Flamingo: A Visual Language Model for Few-Shot Learning](https://arxiv.org/abs/2204.14198) - DeepMind model combining vision encoders with few-shot prompted generation for visual tasks.

---

## Domain-Specific Prompting

### Code Generation

- [GitHub Copilot Prompt Crafting Guide](https://docs.github.com/en/copilot/using-github-copilot/prompt-engineering-for-github-copilot) - Official guide for getting better code suggestions through comment structure, context priming, and specificity.
- [Code Llama Prompting Guide](https://github.com/meta-llama/codellama) - Meta's documentation on prompting Code Llama for code generation, completion, and infilling tasks.
- [Self-Debugging: Teaching LLMs to Debug Their Predicted Programs](https://arxiv.org/abs/2304.05128) - Method where models iteratively execute and debug their own generated code via prompted reflection.
- [AlphaCode 2 Technical Report](https://storage.googleapis.com/deepmind-media/AlphaCode2/AlphaCode2_Tech_Report.pdf) - DeepMind's approach to competitive programming including sampling and filtering strategies.
- [Prompting for Unit Tests](https://github.com/microsoft/promptflow/tree/main/examples) - Examples of prompting LLMs to generate test cases, mocks, and assertions for code.

### Data Analysis

- [pandas-ai](https://github.com/Sinaptik-AI/pandas-ai) - Library for querying pandas DataFrames using natural language with LLM-backed analysis.
- [LIDA: Automatic Generation of Visualizations with LLMs](https://github.com/microsoft/lida) - Microsoft tool using LLMs to automatically generate and describe data visualizations from datasets.
- [Text-to-SQL Prompting Strategies](https://arxiv.org/abs/2308.15363) - Analysis of prompt designs that improve LLM performance on text-to-SQL benchmarks.
- [DIN-SQL](https://arxiv.org/abs/2304.11015) - Decomposed in-context prompting approach that breaks complex SQL generation into sub-problems.

### Writing and Content

- [Writing Style Prompting Guide (Anthropic)](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-examples) - How to use reference examples to reliably replicate voice, tone, and style in generated content.
- [Prompt Patterns for Editing and Revision](https://arxiv.org/abs/2302.11382) - Catalog entries covering critique, rewrite, and persona-based editing patterns.
- [AIWriter](https://github.com/RUCAIBox/LLMSurvey) - Survey of LLM writing applications covering summarization, translation, and creative generation.
- [Long-Form Writing with GPT-4](https://openai.com/research/techniques-to-improve-reliability) - OpenAI's notes on maintaining coherence and consistency across long generated documents.

### Legal and Finance

- [FinanceBench](https://github.com/patronus-ai/financebench) - Benchmark for evaluating LLMs on financial question answering over real earnings documents.
- [LexGPT](https://arxiv.org/abs/2306.05431) - Study of GPT-4 applied to legal tasks with prompting strategies for contract analysis and case summarization.
- [BloombergGPT](https://arxiv.org/abs/2303.17564) - Finance-domain LLM with discussion of domain-specific prompting and evaluation benchmarks.
- [Prompting for Compliance and Risk](https://huggingface.co/blog/llm-financial-use-cases) - Practical overview of prompting patterns for financial document extraction and compliance workflows.

### Science and Research

- [SciAgent](https://arxiv.org/abs/2402.11451) - LLM agent for scientific question answering using tool-augmented prompting over research literature.
- [ChemCrow](https://arxiv.org/abs/2304.05376) - LLM-powered chemistry agent using 18 expert tools for reaction planning and molecular reasoning.
- [Galactica: A Large Language Model for Science](https://arxiv.org/abs/2211.09085) - Meta's domain-specific scientific model with detailed prompting examples for citation, reasoning, and synthesis.
- [Prompting LLMs for Systematic Review](https://arxiv.org/abs/2305.02544) - Study on using chain-of-thought prompts to assist with screening, extraction, and synthesis in systematic reviews.

---

## Prompt Chaining and Pipelines

Breaking complex tasks into sequences of smaller, focused prompts connected together.

- **Why Chain Prompts?** — A single monolithic prompt trying to accomplish many steps at once often performs worse than a chain of focused prompts, each with a clear input and output. Chaining also allows intermediate validation and branching logic.
- **Linear Chains** — The output of one prompt becomes the input of the next. Useful for extract → transform → summarize, or plan → execute → validate workflows.
- **Branching Chains** — A classification prompt routes inputs to different downstream prompts depending on the predicted category. This is the basis of intent-based routing in chatbots.
- **Self-Critique Loops** — A prompt that generates an output is followed by a second prompt that critiques it, and a third that revises based on the critique. Sometimes called a Generator-Critic-Reviser pattern.
- **Map-Reduce Prompting** — Process each chunk of a large document independently (map), then combine and synthesize all results (reduce). Effective for summarizing book-length content.
- **Ensemble Prompting** — Run the same question through multiple independently prompted completions, then use a final aggregation prompt to synthesize the best answer from all of them.
- [LangChain Expression Language (LCEL)](https://python.langchain.com/docs/concepts/lcel/) - Declarative composition syntax for building LangChain pipelines with automatic streaming and batching support.
- [LangGraph Workflow Patterns](https://langchain-ai.github.io/langgraph/) - Graph-based execution patterns for cyclic and conditional prompt pipelines with persistent state.
- [Flowise](https://github.com/FlowiseAI/Flowise) - Visual drag-and-drop builder for LangChain pipelines, making prompt chaining accessible without code.
- [Rivet](https://github.com/Ironclad/rivet) - Node-based visual AI programming environment for building and debugging complex prompt workflows.

---

## Memory and State Management

Techniques for giving LLM applications persistent context across conversations and sessions.

- **In-Context Memory** — Appending the full conversation history to each new prompt. Simple and effective for short sessions, but expensive and eventually exceeds context limits.
- **Summarized Memory** — Periodically compressing past conversation turns into a summary that replaces the raw transcript. Trades some fidelity for much lower token usage.
- **Entity Memory** — Maintaining a structured record of key entities (people, places, facts) mentioned in conversation, updated and retrieved as needed each turn.
- **Vector Store Memory** — Embedding and storing every message in a vector database, then retrieving only the most semantically relevant past context for each new query.
- **Episodic Memory** — Structuring past interactions as discrete episodes with timestamps, retrieved based on recency or relevance depending on the task.
- [Zep](https://github.com/getzep/zep) - Open-source long-term memory store for LLM applications with automatic extraction of facts, summaries, and entities.
- [Mem0](https://github.com/mem0ai/mem0) - Adaptive memory layer for AI assistants that intelligently stores and retrieves user-specific context across sessions.
- [MemGPT: Towards LLMs as Operating Systems](https://arxiv.org/abs/2310.08560) - Extends LLM context using virtual memory paging analogous to operating system memory management.
- [A-MEM: Agentic Memory System](https://arxiv.org/abs/2502.12110) - Dynamic memory system where agents autonomously create and update interconnected memory notes.

---

## Prompt Engineering for Specific Output Types

Tailored strategies for different output formats and task types.

### Classification

- Structure the prompt to output a single word or enum value. Include the complete list of valid categories.
- Always provide a "none of the above" or "uncertain" escape hatch to avoid forced misclassification.
- Few-shot examples with balanced class representation significantly improve reliability on skewed distributions.
- For multi-label classification, ask the model to output a JSON array rather than a comma-separated string.

### Summarization

- Specify the desired length explicitly (e.g., "in exactly three sentences" or "in under 100 words") for consistent output.
- Use "extractive vs. abstractive" framing to control whether the model should quote or paraphrase.
- For long documents, instruct the model to summarize from the perspective of a specific reader persona or goal.
- Ask the model to identify the single most important sentence first, then build the summary around it.

### Translation

- Specify the target dialect or regional variant explicitly (e.g., "Brazilian Portuguese" not just "Portuguese").
- For technical or domain-specific text, provide a glossary of preferred term translations in the prompt.
- Request a confidence note or flag when the model encounters ambiguous source text.
- Ask for literal translation vs. natural-sounding adaptation depending on your use case.

### Information Extraction

- Use XML or JSON schemas in the prompt to define exactly what fields to extract and their types.
- Ask the model to output `null` for missing fields rather than guessing or skipping them.
- For extraction from noisy text, add an instruction to normalize formats (dates, phone numbers, currencies).
- Chain extraction with a validation step: extract first, then ask a second prompt to verify the extracted values against the source.

### Question Answering

- Provide the source material explicitly and instruct the model to answer only from that material.
- Include "If the answer is not in the provided text, say 'I don't know'" to prevent hallucination.
- For multi-hop questions, ask the model to identify and list relevant passages before synthesizing a final answer.
- Request a confidence indicator alongside the answer to help downstream filtering.

---

## Evaluation Metrics Reference

A quick reference for common metrics used to evaluate prompt and model performance.

- **Accuracy** — Percentage of correct answers on a labeled test set. Simple but requires ground truth labels and may not capture quality for open-ended tasks.
- **F1 Score** — Harmonic mean of precision and recall. Preferred over accuracy for imbalanced classification tasks.
- **BLEU** — Measures n-gram overlap between generated text and reference translations. Widely used for translation but correlates poorly with human judgment for open-ended text.
- **ROUGE** — Measures recall of reference n-grams in generated summaries. ROUGE-L uses longest common subsequence. Standard for summarization evaluation.
- **BERTScore** — Computes semantic similarity between generated and reference text using contextual embeddings, correlating better with human judgment than n-gram metrics.
- **Perplexity** — Measures how well a probability model predicts a sample. Lower perplexity indicates a better language model fit, but does not directly measure output quality.
- **Win Rate** — Percentage of head-to-head comparisons where one prompt or model output is preferred by a human or LLM judge. The standard metric for conversational quality comparisons.
- **Faithfulness** — For RAG systems: the proportion of model claims that are directly supported by the retrieved source documents.
- **Answer Relevance** — Whether the generated answer actually addresses the question asked, regardless of correctness. Measured by RAGAS and similar frameworks.
- **Hallucination Rate** — The proportion of factual claims in generated output that cannot be verified against the source context or ground truth.
- **Latency (P50/P95/P99)** — Time from request submission to first token and to full response. P95 and P99 latency are critical for user-facing applications.
- **Token Efficiency** — The ratio of useful information in the output to total tokens generated. Bloated outputs waste cost and may bury key information.

---

## Prompt Templates and Formats

Standard prompt template structures used across different model families and task types.

### ChatML Format

Used by OpenAI-compatible models including many open-source fine-tuned variants:

```
<|im_start|>system
You are a helpful assistant.
<|im_end|>
<|im_start|>user
What is prompt engineering?
<|im_end|>
<|im_start|>assistant
```

### Llama 3 Instruct Format

```
<|begin_of_text|><|start_header_id|>system<|end_header_id|>

You are a helpful assistant.<|eot_id|><|start_header_id|>user<|end_header_id|>

What is prompt engineering?<|eot_id|><|start_header_id|>assistant<|end_header_id|>
```

### Anthropic Claude XML Format

Claude is best prompted using XML tags to delineate sections clearly:

```xml
<document>
{{DOCUMENT_CONTENT}}
</document>

<task>
Summarize the key findings from the document above in three bullet points.
</task>
```

### Mistral Instruct Format

```
<s>[INST] You are a helpful assistant. What is prompt engineering? [/INST]
```

### Alpaca Format

Used by many instruction-tuned open-source models:

```
### Instruction:
Summarize the following text.

### Input:
{{TEXT}}

### Response:
```

---

## Prompt Anti-Patterns

Common mistakes and failure modes to avoid when designing prompts.

- **Vague Instructions** — Prompts that don't specify output format, length, tone, or constraints leave too much to the model's interpretation. Always specify what you want explicitly.
- **Conflicting Instructions** — Placing contradictory directives in the same prompt (e.g., "be brief" and "explain everything in detail") forces the model to make arbitrary choices. Audit for logical consistency before deployment.
- **Prompt Stuffing** — Packing too many tasks into a single prompt reduces performance on each task. Decompose complex tasks into sequential or parallel sub-prompts.
- **Missing Output Examples** — For format-sensitive tasks, always include at least one example of the desired output. Descriptions of format rarely perform as well as demonstrated examples.
- **Over-Reliance on Negatives** — Telling a model what not to do is less reliable than telling it what to do. Positive instructions consistently outperform prohibitions.
- **Context Window Blindness** — Placing critical instructions only at the very beginning of a long prompt risks the model losing track of them. Repeat critical constraints near the end as well.
- **Sycophancy Exploitation** — Models tend to agree with premises stated in prompts even when false. Avoid framing questions as confirmations (e.g., "Isn't it true that...") when accuracy is critical.
- **No Escape Hatch** — Prompts that don't tell the model what to do when it can't answer lead to hallucinated responses. Always include instructions for handling uncertainty.
- **Treating the Model as a Database** — Prompting for specific facts, statistics, or citations without retrieval grounding will produce confident-sounding but unreliable answers.
- **Ignoring Temperature** — Using default temperature settings for deterministic tasks (classification, extraction) or creative tasks (brainstorming, fiction) produces suboptimal results.

---

## Testing and Debugging Prompts

Practical approaches for systematically improving prompt reliability before deployment.

- **Adversarial Testing** — Deliberately craft inputs that are ambiguous, contradictory, or edge cases to identify where your prompt breaks down. Document these and add them to your regression suite.
- **Output Distribution Analysis** — Run the same prompt with temperature > 0 across 20–50 samples. Examine the variance and failure modes in the distribution before considering a prompt production-ready.
- **Ablation Studies** — Remove individual sentences or instructions from your prompt one at a time and measure the effect on output quality. This identifies which parts are load-bearing.
- **Cross-Model Testing** — Test prompts against multiple model families and sizes. Prompts that work only on one specific model version are fragile and likely rely on quirks rather than robust instructions.
- **Prompt Regression Testing** — Use [PromptFoo](https://github.com/promptfoo/promptfoo) to define assertions and run CI-style tests on your prompts whenever they change or a new model version is deployed.
- **Golden Dataset Construction** — Maintain a hand-labeled dataset of (input, expected output) pairs. Evaluate any prompt change against this set before promoting it to production.
- **LLM-as-Judge Evaluation** — Use a separate, capable model to score outputs on criteria like correctness, tone, format compliance, and safety as a scalable evaluation method.
- **Minimal Reproducible Prompt** — When debugging, strip the prompt to its minimal version that still reproduces the failure. This makes the root cause much clearer than debugging in complex production prompts.

---

## Production Deployment Considerations

Key concerns when moving prompt-based applications from prototype to production.

- **Latency vs. Quality Tradeoffs** — Longer prompts and larger models improve quality but increase latency and cost. Establish baseline latency requirements before optimizing for quality.
- **Cost Modeling** — Track token usage per request type and model. Input and output tokens are often priced differently. Use caching for repeated system prompts or static context.
- **Prompt Versioning** — Treat prompts as code. Use version control, changelogs, and staged rollouts (canary testing) when updating production prompts.
- **Fallback Strategies** — Configure model fallbacks (e.g., GPT-4o → GPT-4o-mini) for availability and cost. Ensure prompts are tested on fallback models before enabling them.
- **Rate Limiting and Backoff** — Implement exponential backoff with jitter for API calls. Use provider-specific rate limit headers to adapt request pacing dynamically.
- **PII and Data Privacy** — Audit prompts and inputs for personally identifiable information before sending to third-party model APIs. Consider local model deployment for sensitive data.
- **Output Filtering** — Apply post-processing filters for toxicity, PII leakage, and hallucinated facts before returning model outputs to end users.
- **Prompt Logging and Auditing** — Log all prompt inputs and outputs with metadata for debugging, compliance, and quality monitoring. Ensure logging pipelines comply with applicable privacy regulations.
- [OpenAI Production Best Practices](https://platform.openai.com/docs/guides/production-best-practices) - Official checklist for moving from prototype to production with the OpenAI API.

---

## Open-Source Models and Local Deployment

Resources for running and prompting open-weight models locally.

- [Ollama](https://github.com/ollama/ollama) - Tool for running open-weight models locally with a simple CLI and REST API compatible with OpenAI's format.
- [LM Studio](https://lmstudio.ai) - Desktop application for discovering, downloading, and running local LLMs with a chat interface and OpenAI-compatible server.
- [llama.cpp](https://github.com/ggerganov/llama.cpp) - Efficient C++ inference engine for running quantized Llama and compatible models on CPU and GPU.
- [Hugging Face Transformers](https://github.com/huggingface/transformers) - The foundational Python library for loading, fine-tuning, and running transformer models with full prompting control.
- [vLLM](https://github.com/vllm-project/vllm) - High-throughput inference engine for LLMs using PagedAttention, suitable for production serving.
- [Open WebUI](https://github.com/open-webui/open-webui) - Feature-rich web interface for interacting with local models via Ollama or OpenAI-compatible APIs.
- [PrivateGPT](https://github.com/zylon-ai/private-gpt) - Production-ready AI project for querying documents using LLMs with full privacy and no data leaving your environment.
- [GPT4All](https://github.com/nomic-ai/gpt4all) - Ecosystem for running strong, customized LLMs locally on consumer hardware without a GPU.

---

## Fine-Tuning vs. Prompting

Understanding when to fine-tune a model versus engineering a better prompt.

- [To Fine-Tune or Not to Fine-Tune? (OpenAI)](https://platform.openai.com/docs/guides/fine-tuning/when-to-use-fine-tuning) - Official guidance on when the latency, cost, and performance tradeoffs favor fine-tuning over prompting.
- [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685) - Parameter-efficient fine-tuning method that significantly reduces memory requirements for adapting large models.
- [QLoRA: Efficient Finetuning of Quantized LLMs](https://arxiv.org/abs/2305.14314) - Combines 4-bit quantization with LoRA to enable fine-tuning of large models on consumer hardware.
- [Alpaca: Self-Instruct Fine-Tuning](https://github.com/tatsu-lab/stanford_alpaca) - Stanford project demonstrating data generation and fine-tuning of LLaMA on a small instruction dataset.
- [When Prompt Engineering Hits Its Ceiling](https://www.anyscale.com/blog/fine-tuning-is-for-form-not-facts) - Analysis arguing fine-tuning is most valuable for output format and style, not for injecting factual knowledge.

---

## Responsible AI and Ethics in Prompting

Considerations for building fair, safe, and transparent LLM-powered systems.

- [Anthropic's Responsible Scaling Policy](https://www.anthropic.com/responsible-scaling-policy) - Policy framework for evaluating and mitigating catastrophic risks as model capabilities increase.
- [OpenAI Usage Policies](https://openai.com/policies/usage-policies) - Guidelines for acceptable use of OpenAI models in applications, including prohibited use cases.
- [Bias and Fairness in LLMs](https://arxiv.org/abs/2309.00770) - Survey of bias types, measurement methods, and mitigation strategies for large language models.
- [TruthfulQA: Measuring Hallucination](https://arxiv.org/abs/2109.07958) - Benchmark revealing how models confidently repeat misconceptions found in training data.
- [Avoiding Sycophancy in LLMs](https://arxiv.org/abs/2310.13548) - Research on detecting and reducing sycophantic behavior where models tell users what they want to hear rather than the truth.
- [AI Fairness 360 (IBM)](https://github.com/Trusted-AI/AIF360) - Open-source toolkit for detecting and mitigating bias in AI models and datasets.
- [Partnership on AI](https://partnershiponai.org) - Multi-stakeholder organization publishing research and best practices for responsible AI deployment.

---

## Context Management

Strategies for working effectively within and across context window constraints.

- [Lost in the Middle: How LLMs Use Long Contexts](https://arxiv.org/abs/2307.03172) - Research showing model performance degrades for information placed in the middle of long contexts.
- [Long Context vs. RAG for Long Document Understanding](https://arxiv.org/abs/2407.16833) - Empirical comparison of feeding entire documents into context versus using retrieval.
- [Extending Context Window via Positional Interpolation](https://arxiv.org/abs/2306.15595) - Technique for extending the effective context length of transformer models beyond their training window.
- [MemGPT: Towards LLMs as Operating Systems](https://arxiv.org/abs/2310.08560) - Enables LLMs to manage their own context window using virtual memory-style paging.
- **Context Priming** — Placing the most decision-critical information immediately before the instruction consistently improves adherence in long-context tasks.
- **Hierarchical Summarization** — For very long documents, build a tree of summaries and include the appropriate level of detail depending on the task specificity required.
- **Chunking Strategies** — When documents exceed the context window, chunking strategy (fixed size, sentence boundary, semantic) significantly affects retrieval quality in RAG pipelines.

---

## Glossary

A reference for commonly used terms in prompt engineering.

- **Context Window** — The maximum number of tokens (roughly words or word-pieces) a model can process in a single request, including both input and output.
- **Few-Shot Prompting** — Including a small number of input-output examples in a prompt to demonstrate the desired task format to the model.
- **Fine-Tuning** — Training a pre-trained model on a specific dataset to adapt its weights to a new task or domain.
- **Grounding** — Connecting a model's outputs to verified external sources such as documents or databases to reduce hallucination.
- **Hallucination** — When a model generates plausible-sounding but factually incorrect or unsupported content.
- **In-Context Learning (ICL)** — The ability of a model to learn to perform a task purely from examples provided in the prompt, without gradient updates.
- **Instruction Tuning** — Fine-tuning a model on (instruction, response) pairs to improve its ability to follow natural language directions.
- **Jailbreaking** — Techniques used to bypass a model's safety guardrails and elicit disallowed outputs.
- **Latent Space** — The high-dimensional vector space in which a model represents meaning; prompt design can be understood as navigating this space.
- **Logit Bias** — API parameter for increasing or decreasing the probability of specific tokens, used to constrain or guide output format.
- **One-Shot Prompting** — Providing exactly one example in the prompt before the actual query.
- **Prompt Injection** — An attack where adversarial text in retrieved content or user input overrides the developer's intended instructions.
- **RAG (Retrieval-Augmented Generation)** — Architecture that fetches relevant external documents and includes them in the prompt context at query time.
- **RLHF (Reinforcement Learning from Human Feedback)** — Training technique using human preference rankings to shape model behavior via a reward model.
- **Soft Prompt** — Learnable continuous token embeddings prepended to inputs during fine-tuning, as opposed to discrete text tokens.
- **System Prompt** — Instructions provided to a model before the conversation begins, typically used to set role, tone, and behavioral constraints.
- **Temperature** — A sampling parameter controlling output randomness; higher values produce more diverse outputs, lower values more deterministic ones.
- **Token** — The basic unit of text processed by a language model; roughly 4 characters or 0.75 words in English on average.
- **Top-P (Nucleus Sampling)** — Sampling strategy that restricts generation to the smallest set of tokens whose cumulative probability exceeds the threshold P.
- **Zero-Shot Prompting** — Asking a model to perform a task with no examples, relying entirely on the model's pre-trained knowledge and instruction following.

---

## Prompt Anti-Patterns

Common mistakes and failure modes to avoid when designing prompts.

- **Vague Instructions** — Prompts that don't specify output format, length, tone, or constraints leave too much to the model's interpretation and produce inconsistent results. Always specify what you want explicitly.
- **Conflicting Instructions** — Placing contradictory directives in the same prompt (e.g., "be brief" and "explain everything in detail") forces the model to make arbitrary choices. Audit for logical consistency before deployment.
- **Prompt Stuffing** — Packing too many tasks into a single prompt reduces performance on each individual task. Decompose complex tasks into sequential or parallel sub-prompts.
- **Missing Output Examples** — For format-sensitive tasks, always include at least one example of the desired output. Descriptions of format rarely perform as well as demonstrated examples.
- **Over-Reliance on Negatives** — Telling a model what not to do ("don't use bullet points") is less reliable than telling it what to do ("respond in flowing paragraphs"). Positive instructions outperform prohibitions.
- **Context Window Blindness** — Placing critical instructions only at the very beginning of a long prompt risks the model losing track of them. Repeat critical constraints near the end as well.
- **Sycophancy Exploitation** — Models are prone to agreeing with premises stated in prompts even when they are false. Avoid framing questions as confirmations (e.g., "Isn't it true that...") when accuracy is needed.
- **Ignoring Temperature** — Using default temperature settings for tasks that need determinism (data extraction, classification) or creativity (brainstorming, fiction) leads to suboptimal results.
- **No Escape Hatch** — Prompts that don't tell the model what to do when it can't answer a question lead to hallucinated responses. Always include instructions for handling uncertainty.
- **Treating the Model as a Database** — LLMs are not retrieval systems. Prompting for specific facts, statistics, or citations without grounding in retrieved documents will produce confident-sounding but unreliable answers.

---

## Testing and Debugging Prompts

Practical approaches for systematically improving prompt reliability before deployment.

- **Adversarial Testing** — Deliberately craft inputs that are ambiguous, contradictory, or edge cases to identify where your prompt breaks down. Document these and add them to your regression suite.
- **Output Distribution Analysis** — Run the same prompt with temperature > 0 across 20–50 samples. Examine the variance and failure modes in the distribution before considering a prompt production-ready.
- **Ablation Studies** — Remove individual sentences or instructions from your prompt one at a time and measure the effect on output quality. This identifies which parts are load-bearing.
- **Cross-Model Testing** — Test prompts against multiple model families and sizes. Prompts that work only on one specific model version are fragile and likely rely on quirks rather than robust instructions.
- **Prompt Regression Testing with PromptFoo** — Use [PromptFoo](https://github.com/promptfoo/promptfoo) to define assertions and run CI-style tests on your prompts whenever they change or a new model version is deployed.
- **Golden Dataset Construction** — Maintain a hand-labeled dataset of (input, expected output) pairs. Evaluate any prompt change against this set before promoting it to production.
- **LLM-as-Judge Evaluation** — Use a separate, capable model (e.g., GPT-4 or Claude) to score outputs on criteria like correctness, tone, format compliance, and safety as a scalable evaluation method.
- **Minimal Reproducible Prompt** — When debugging, strip the prompt to its minimal version that still reproduces the failure. This makes the root cause much clearer than debugging in complex production prompts.

---

## Context Management

Strategies for working effectively within and across context window constraints.

- [Lost in the Middle: How LLMs Use Long Contexts](https://arxiv.org/abs/2307.03172) - Research showing model performance degrades for information placed in the middle of long contexts, not just at edges.
- [Long Context vs. RAG for Long Document Understanding](https://arxiv.org/abs/2407.16833) - Empirical comparison of feeding entire documents into context versus using retrieval for long-document tasks.
- [Extending Context Window of LLMs via Positional Interpolation](https://arxiv.org/abs/2306.15595) - Technique for extending the effective context length of transformer models beyond their training window.
- [Summarization-Based Context Compression](https://arxiv.org/abs/2310.06201) - Method for compressing prior conversation or document context using recursive summarization to fit within limits.
- [MemGPT: Towards LLMs as Operating Systems](https://arxiv.org/abs/2310.08560) - System enabling LLMs to manage their own context window using virtual memory-style paging.
- **Chunking Strategies** — When documents exceed the context window, the chunking strategy (fixed size, sentence boundary, semantic chunking) significantly affects retrieval quality in RAG pipelines.
- **Context Priming** — Placing the most decision-critical information immediately before the instruction, rather than earlier in the prompt, consistently improves adherence in long-context tasks.
- **Hierarchical Summarization** — For very long documents, build a tree of summaries and include the appropriate level of summary in the prompt depending on the task specificity required.

---

## Prompt Templates and Formats

Standard prompt template structures used across different model families and task types.

### ChatML Format

Used by OpenAI-compatible models including many open-source fine-tuned variants:

```
<|im_start|>system
You are a helpful assistant.
<|im_end|>
<|im_start|>user
What is prompt engineering?
<|im_end|>
<|im_start|>assistant
```

### Llama 3 Instruct Format

```
<|begin_of_text|><|start_header_id|>system<|end_header_id|>

You are a helpful assistant.<|eot_id|><|start_header_id|>user<|end_header_id|>

What is prompt engineering?<|eot_id|><|start_header_id|>assistant<|end_header_id|>
```

### Anthropic Claude Format

Claude is best prompted using XML tags to delineate sections clearly:

```xml
<system>
You are an expert data analyst. You communicate clearly and concisely.
</system>

<document>
{{DOCUMENT_CONTENT}}
</document>

<task>
Summarize the key findings from the document above in three bullet points.
</task>
```

### Mistral Instruct Format

```
<s>[INST] You are a helpful assistant. What is prompt engineering? [/INST]
```

### Alpaca Format

Used by many instruction-tuned open-source models:

```
### Instruction:
Summarize the following text.

### Input:
{{TEXT}}

### Response:
```

---

## Production Deployment Considerations

Key concerns when moving prompt-based applications from prototype to production.

- **Latency vs. Quality Tradeoffs** — Longer prompts and larger models improve quality but increase latency and cost. Establish baseline latency requirements before optimizing for quality.
- **Cost Modeling** — Track token usage per request type and model. Input and output tokens are often priced differently. Use caching for repeated system prompts or static context.
- **Prompt Versioning** — Treat prompts as code. Use version control, changelogs, and staged rollouts (canary testing) when updating production prompts.
- **Fallback Strategies** — Configure model fallbacks (e.g., GPT-4o → GPT-4o-mini) for availability and cost. Ensure prompts are tested on fallback models before enabling them.
- **Rate Limiting and Backoff** — Implement exponential backoff with jitter for API calls. Use provider-specific rate limit headers to adapt request pacing dynamically.
- **PII and Data Privacy** — Audit prompts and inputs for personally identifiable information before sending to third-party model APIs. Consider local model deployment for sensitive data.
- **Output Filtering** — Apply post-processing filters for toxicity, PII leakage, and hallucinated facts before returning model outputs to end users.
- **Prompt Logging and Auditing** — Log all prompt inputs and outputs with metadata for debugging, compliance, and quality monitoring. Ensure logging pipelines are GDPR-compliant where applicable.
- [OpenAI Production Best Practices](https://platform.openai.com/docs/guides/production-best-practices) - Official checklist for moving from prototype to production with the OpenAI API.
- [Anthropic API Responsible Deployment](https://www.anthropic.com/responsible-disclosure-policy) - Guidance on deploying Claude responsibly with safety and compliance considerations.

---

## Open-Source Models and Local Deployment

Resources for running and prompting open-weight models locally.

- [Ollama](https://github.com/ollama/ollama) - Tool for running open-weight models locally with a simple CLI and REST API compatible with OpenAI's format.
- [LM Studio](https://lmstudio.ai) - Desktop application for discovering, downloading, and running local LLMs with a chat interface and OpenAI-compatible server.
- [llama.cpp](https://github.com/ggerganov/llama.cpp) - Efficient C++ inference engine for running quantized Llama and compatible models on CPU and GPU.
- [Hugging Face Transformers](https://github.com/huggingface/transformers) - The foundational Python library for loading, fine-tuning, and running transformer models with full prompting control.
- [vLLM](https://github.com/vllm-project/vllm) - High-throughput and memory-efficient inference engine for LLMs using PagedAttention, suitable for production serving.
- [Open WebUI](https://github.com/open-webui/open-webui) - Feature-rich web interface for interacting with local models via Ollama or OpenAI-compatible APIs.
- [TheBloke on Hugging Face](https://huggingface.co/TheBloke) - Community contributor providing quantized GGUF and GPTQ versions of popular open-source models ready for local inference.
- [GGUF Format Explainer](https://github.com/ggerganov/ggml/blob/master/docs/gguf.md) - Documentation for the GGUF model file format used by llama.cpp for efficient quantized inference.
- [PrivateGPT](https://github.com/zylon-ai/private-gpt) - Production-ready AI project for querying documents using LLMs with full privacy and no data leaving your environment.

---

## Fine-Tuning vs. Prompting

Understanding when to fine-tune a model versus engineering a better prompt.

- [To Fine-Tune or Not to Fine-Tune? (OpenAI)](https://platform.openai.com/docs/guides/fine-tuning/when-to-use-fine-tuning) - Official guidance on when the latency, cost, and performance tradeoffs favor fine-tuning over prompting.
- [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685) - Parameter-efficient fine-tuning method that significantly reduces memory requirements for adapting large models.
- [QLoRA: Efficient Finetuning of Quantized LLMs](https://arxiv.org/abs/2305.14314) - Combines 4-bit quantization with LoRA to enable fine-tuning of 65B parameter models on a single GPU.
- [Alpaca: Instruction Tuning with GPT-4 Outputs](https://github.com/tatsu-lab/stanford_alpaca) - Stanford project demonstrating self-instruct data generation and fine-tuning of LLaMA on a small dataset.
- [When Prompt Engineering Hits Its Ceiling](https://www.anyscale.com/blog/fine-tuning-is-for-form-not-facts) - Analysis arguing that fine-tuning is most valuable for output format and style, not for injecting new factual knowledge.
- [Prompt Engineering Before Fine-Tuning Checklist](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) - Recommended diagnostic steps to exhaust before committing to a fine-tuning run.

---

## Responsible AI and Ethics in Prompting

Considerations for building fair, safe, and transparent LLM-powered systems.

- [Anthropic's Responsible Scaling Policy](https://www.anthropic.com/responsible-scaling-policy) - Policy framework for evaluating and mitigating catastrophic risks as model capabilities increase.
- [OpenAI Usage Policies](https://openai.com/policies/usage-policies) - Guidelines for acceptable use of OpenAI models in applications, including prohibited use cases.
- [Partnership on AI](https://partnershiponai.org) - Multi-stakeholder organization publishing research and best practices for responsible AI deployment.
- [AI Fairness 360 (IBM)](https://github.com/Trusted-AI/AIF360) - Open-source toolkit for detecting and mitigating bias in AI models and datasets.
- [Bias and Fairness in LLMs](https://arxiv.org/abs/2309.00770) - Survey of bias types, measurement methods, and mitigation strategies for large language models.
- [TruthfulQA: Measuring Hallucination](https://arxiv.org/abs/2109.07958) - Benchmark revealing how models confidently repeat common misconceptions found in training data.
- [Avoiding Sycophancy in LLMs](https://arxiv.org/abs/2310.13548) - Research on detecting and reducing sycophantic behavior where models tell users what they want to hear rather than the truth.
- [Responsible Prompting Checklist](https://learnprompting.org/docs/category/-basics) - Community guide covering considerations for output safety, bias, and user transparency in prompt design.

---

## Contributing

Contributions are welcome! Please read the [contributing guidelines](contributing.md) before opening a pull request. Make sure any new entries are actively maintained, high quality, and not already listed.

Contributions are welcome! Please read the [contributing guidelines](contributing.md) before opening a pull request. Make sure any new entries are actively maintained, high quality, and not already listed.

---

## Footnotes

Descriptions of each resource are based on publicly available documentation and research paper abstracts. This list focuses on resources useful to practitioners, researchers, and developers building real-world systems with large language models. Links to paywalled resources are included where the content is considered foundational; free alternatives or preprints are linked wherever available.
