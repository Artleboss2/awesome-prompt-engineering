# Awesome Prompt Engineering [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Techniques, tools, papers, and resources for crafting effective prompts for large language models.

---

## Contents

- [Fundamentals](#fundamentals)
- [Techniques](#techniques)
- [Tools](#tools)
- [Frameworks](#frameworks)
- [Papers](#papers)
- [Courses & Tutorials](#courses--tutorials)
- [Playgrounds & Testing](#playgrounds--testing)
- [Communities](#communities)

---

## Fundamentals

- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering) - Official documentation covering core strategies for getting better results from GPT models.
- [Anthropic Prompt Engineering Docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) - Comprehensive guide to prompting Claude models, including chain-of-thought and XML structuring.
- [Google Prompting Essentials](https://ai.google.dev/gemini-api/docs/prompting-intro) - Introduction to prompting concepts for Gemini models by Google.
- [Learn Prompting](https://learnprompting.org) - Free, open-source course covering prompt engineering from beginner to advanced level.

## Techniques

- [Chain-of-Thought Prompting](https://arxiv.org/abs/2201.11903) - Seminal paper introducing step-by-step reasoning prompts to improve LLM problem-solving.
- [Zero-Shot CoT](https://arxiv.org/abs/2205.11916) - Demonstrates that appending "Let's think step by step" significantly improves zero-shot reasoning.
- [Tree of Thoughts](https://arxiv.org/abs/2305.10601) - Framework for deliberate decision-making by exploring multiple reasoning paths.
- [ReAct](https://arxiv.org/abs/2210.03629) - Combines reasoning and acting in language models for more reliable task completion.
- [Self-Consistency](https://arxiv.org/abs/2203.11171) - Improves chain-of-thought prompting by sampling multiple reasoning paths and taking the majority answer.
- [Automatic Prompt Engineer (APE)](https://arxiv.org/abs/2211.01910) - Method for automatically generating and selecting optimal prompts.
- [Few-Shot Prompting Patterns](https://arxiv.org/abs/2005.14165) - The original GPT-3 paper detailing in-context learning with examples.
- [Prompt Injection & Defense](https://arxiv.org/abs/2302.12173) - Research on attacks and mitigations for prompt injection vulnerabilities.

## Tools

- [PromptFlow](https://github.com/microsoft/promptflow) - Microsoft's suite for building, testing, and deploying LLM-based workflows.
- [LangChain](https://github.com/langchain-ai/langchain) - Framework for composing prompts, chains, and agents with language models.
- [Guidance](https://github.com/guidance-ai/guidance) - A programming paradigm for controlling LLM generation with constraints and structure.
- [DSPy](https://github.com/stanfordnlp/dspy) - Stanford framework for algorithmically optimizing LLM prompts and weights.
- [PromptLayer](https://github.com/MagnivOrg/prompt-layer-library) - Middleware for logging, searching, and managing prompt templates in production.
- [LMQL](https://github.com/eth-sri/lmql) - A programming language for interacting with language models using constraints.
- [Outlines](https://github.com/outlines-dev/outlines) - Library for structured text generation to enforce output schemas from LLMs.
- [Priompt](https://github.com/anysphere/priompt) - JSX-based library for priority-based prompt construction with token budgets.

## Frameworks

- [LlamaIndex](https://github.com/run-llama/llama_index) - Data framework for building LLM applications with retrieval-augmented generation.
- [Haystack](https://github.com/deepset-ai/haystack) - End-to-end LLM orchestration framework for building production-ready pipelines.
- [Semantic Kernel](https://github.com/microsoft/semantic-kernel) - SDK for integrating LLMs into applications using prompt templates and plugins.
- [Instructor](https://github.com/instructor-ai/instructor) - Structured output extraction from LLMs using Pydantic validation.

## Papers

- [A Prompt Pattern Catalog to Enhance Prompt Engineering with ChatGPT](https://arxiv.org/abs/2302.11382) - Catalog of reusable prompt design patterns analogous to software design patterns.
- [Large Language Models Are Human-Level Prompt Engineers](https://arxiv.org/abs/2211.01910) - Study showing LLMs can generate prompts that outperform human-written ones.
- [Calibrate Before Use: Improving Few-Shot Performance of Language Models](https://arxiv.org/abs/2102.09690) - Addresses bias in few-shot prompting with a calibration method.
- [The Power of Scale for Parameter-Efficient Prompt Tuning](https://arxiv.org/abs/2104.08691) - Shows soft prompt tuning can match fine-tuning at large scales.
- [Constitutional AI](https://arxiv.org/abs/2212.08073) - Anthropic's method for using principles-based prompting to align AI behavior.

## Courses & Tutorials

- [DeepLearning.AI ChatGPT Prompt Engineering for Developers](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) - Short course co-developed with OpenAI covering iterative prompting, summarizing, and more.
- [Prompt Engineering Guide by DAIR.AI](https://github.com/dair-ai/Prompt-Engineering-Guide) - Comprehensive guide and paper collection on prompt engineering techniques.
- [Brex Prompt Engineering Guide](https://github.com/brexhq/prompt-engineering) - Practical internal guide open-sourced by Brex covering real-world patterns and gotchas.
- [Cohere LLM University](https://llm.university) - Free curriculum covering NLP foundations through advanced prompt design.

## Playgrounds & Testing

- [OpenAI Playground](https://platform.openai.com/playground) - Interactive interface for testing prompts across GPT models with adjustable parameters.
- [Google AI Studio](https://aistudio.google.com) - Browser-based environment for prototyping prompts with Gemini models.
- [Anthropic Console](https://console.anthropic.com) - Workbench for building and testing prompts against Claude models.
- [PromptBench](https://github.com/microsoft/promptbench) - Adversarial robustness evaluation benchmark for large language models.
- [Agenta](https://github.com/Agenta-AI/agenta) - Open-source platform for prompt versioning, evaluation, and A/B testing.

## Communities

- [r/PromptEngineering](https://www.reddit.com/r/PromptEngineering/) - Reddit community for sharing and discussing prompting techniques.
- [Learn Prompting Discord](https://discord.gg/7enStJXQzD) - Active community around the learnprompting.org curriculum.
- [DAIR.AI Discord](https://discord.gg/SKgkVT8BGJ) - Community focused on AI democratization, with active prompt engineering channels.
```

---

## PR Title (exactly as required)
```
Add Prompt Engineering
