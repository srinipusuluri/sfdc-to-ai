
# 🤖 Claude Agentic Frameworks — Visual Guide

> An interactive, single-page visual reference covering every major Claude AI agentic pattern — with flow diagrams, trace examples, variant breakdowns, and a side-by-side comparison table.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-7c3aed?style=for-the-badge&logo=github)](https://srinipusuluri.github.io/crm-claude-agentic-patterns/)
[![Built with Claude](https://img.shields.io/badge/Built%20with-Claude%20Sonnet%204.6-c084fc?style=for-the-badge)](https://claude.ai)
[![No Dependencies](https://img.shields.io/badge/Dependencies-None-22c55e?style=for-the-badge)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-60a5fa?style=for-the-badge)](LICENSE)

---

## 📖 Overview

This guide visually explains **8 core agentic patterns** used with Claude AI — how they work, when to use them, real trace examples, and how they compare. Designed for developers, AI engineers, and solution architects building production agent systems.

Navigate between patterns using the sticky top nav bar. No frameworks, no build step — just open `index.html`.

---

## 🗂️ Project Structure

```
/
├── docs/
│   └── index.html        # Full interactive guide (GitHub Pages root)
└── README.md
```

---

## 🧠 Patterns Covered

### ⚙️ ReAct — Reason + Act
**The backbone of most agent loops.** Interleaves Thought → Action → Observation in a tight feedback loop. Includes a full annotated trace example showing Thought / Action / Observation / Final Answer steps.

**Key insight:** Prevents hallucination by grounding every reasoning step in real tool observations rather than imagination.

---

### 🔄 Reflection / Self-Critique
**Quality through iteration.** Claude generates output, critiques it against quality criteria, revises, and repeats until a stop condition is met.

Variants covered:
- **Self-Reflection** — single model critiques itself
- **Adversarial** — a separate critic agent attacks the generator
- **Constitutional** — output checked against rules/principles
- **Test-Based** — code is run; failures drive the reflection
- **Reflexion** — adds long-term memory so past failures inform future attempts

---

### 🔧 Tool Use / Function Calling
**The action primitive.** Claude selects and invokes typed external functions based on context. Covers parallel vs. sequential execution strategies and MCP (Model Context Protocol) integration.

Tool categories: Search & Retrieval, Code Execution, API Calls, File I/O, Calculators, Memory Tools.

---

### 🗺️ Planning Frameworks
**Decompose, then execute.** Two sub-patterns:

- **Plan-and-Execute** — generate an ordered task list, run each step with ReAct, replan dynamically on failure
- **Tree-of-Thoughts (ToT)** — explore multiple reasoning branches in parallel, score each, and commit to the best path

---

### 🕸️ Multi-Agent Systems
**Specialization at scale.** An Orchestrator delegates to domain-specific Subagents. Supports tasks that exceed a single context window.

Topology types:
- **Hub-and-Spoke** — central orchestrator delegates to all agents
- **Pipeline** — sequential agent handoff (A → B → C)
- **Peer-to-Peer** — agents collaborate freely
- **Debate / Vote** — agents propose; majority or judge decides

---

### 📚 RAG — Retrieval-Augmented Generation
**Ground answers in real data.** Embeds the query, searches a vector store, injects top-K documents into the prompt, then generates a grounded response.

RAG variants covered:
- **Naive RAG** — simple retrieve → generate
- **Agentic RAG** — Claude decides when and what to retrieve
- **Hybrid RAG** — vector search + BM25 keyword retrieval
- **Graph RAG** — knowledge graphs + semantic search for relational reasoning

---

### 🧠 Chain-of-Thought & Extended Thinking
**Reason before answering.** Forces explicit step-by-step reasoning in a scratchpad before committing to a final answer. Claude's Extended Thinking allocates a separate private token budget.

Variants: Zero-Shot CoT, Few-Shot CoT, Extended Thinking, Scratchpad Mode.

---

### 🔀 Subagent & Delegation Patterns
**The practical building blocks.** Four additional patterns for real-world agent pipelines:

- **Prompt Chaining** — sequential deterministic prompt pipeline
- **Routing** — classifier dispatches to specialized handlers
- **Parallelization** — independent subtasks run simultaneously
- **Human-in-the-Loop (HITL)** — approval gates for high-stakes or irreversible actions

---

## 📊 Pattern Comparison

| Pattern | Complexity | Best For | Claude Support |
|---------|-----------|----------|----------------|
| ⚙️ ReAct | Medium | Tool-using agents | Native |
| 🔄 Reflection | Medium | Quality-critical outputs | Native |
| 🔧 Tool Use | Low | Any action-taking agent | Native + MCP |
| 🗺️ Planning | High | Complex multi-step tasks | Native |
| 🕸️ Multi-Agent | High | Long-horizon, parallel work | Native |
| 📚 RAG | Medium | Knowledge-intensive tasks | Via tools |
| 🧠 CoT / Thinking | Low | Math, logic, analysis | Extended Thinking API |
| 🔗 Prompt Chaining | Low | Deterministic pipelines | Native |
| 🚦 Routing | Low | Multi-domain apps | Native |
| ⚡ Parallelization | Medium | Speed-critical tasks | Via multi-agent |
| 👤 HITL | Medium | High-stakes actions | Native |
| 🌳 Tree-of-Thoughts | High | Complex reasoning tasks | Prompt-based |

---

## 🚀 Getting Started

### View Online
👉 **[https://srinipusuluri.github.io/crm-claude-agentic-patterns/](https://srinipusuluri.github.io/crm-claude-agentic-patterns/)**

### Run Locally
```bash
git clone https://github.com/srinipusuluri/crm-claude-agentic-patterns.git
cd crm-claude-agentic-patterns
open docs/index.html
```

Zero dependencies. Pure HTML + CSS + vanilla JS. Works in any modern browser.

---

## 🎨 Design

- **Dark theme** — deep navy/purple palette optimized for readability
- **Sticky nav** — jump between any pattern instantly
- **Flow diagrams** — color-coded node/arrow diagrams for each pattern
- **Trace examples** — annotated real-world step-by-step traces (ReAct)
- **Comparison table** — complexity, best-use, and Claude support at a glance
- **Fully responsive** — works on mobile and desktop

---

## 🛠️ Built With

- **[Claude AI](https://claude.ai)** — Anthropic Claude Sonnet 4.6
- **HTML5 / CSS3 / Vanilla JS** — no frameworks, no bundlers
- **GitHub Pages** — free static hosting from `/docs` folder

---

## 🔗 Related

- [CRM Use Cases Guide](./docs/index.html) — Agentic patterns applied to real CRM workflows
- [Anthropic Docs](https://docs.anthropic.com) — Official Claude API documentation
- [Claude Prompt Engineering](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview)

---

## 📄 License

MIT © [Srini Pusuluri](https://github.com/srinipusuluri)
