# CulinaryMind:Multi-Agent AI Orchestration for Recipe Generation

> A next-generation **LangGraph + LangChain** project showcasing **multi-agent orchestration**, **structured LLM reasoning**, and **adaptive workflow design** — turning meal ideas into detailed, culturally enriched recipe guides.

---

## Overview

**CulinaryMind** is an intelligent **multi-agent system** that demonstrates how different AI agents can collaborate to transform a simple list of meals into a complete, chef-level culinary plan.

This project leverages **LangGraph** to coordinate multiple autonomous agents — each responsible for a specialized task — creating a seamless pipeline from meal planning to detailed preparation guidance.

---

## Agent Architecture

The system operates through **three coordinated agents**, each represented as a LangGraph node:

| Agent | Role | Description |
|:------|:------|:------------|
| **Orchestrator Agent** | Planner | Decomposes the user’s meal list into structured dish objects (`Dishes` schema) with names, ingredients, and cultural origins. |
| **Chef Agent(s)** | Executors | Each chef agent specializes in a particular cuisine, generating step-by-step preparation guides based on assigned dishes. Multiple chef agents can work in **parallel** using the `Send()` API. |
| **Synthesizer Agent** | Aggregator | Compiles all generated dish guides into a polished, human-readable final meal report. |

Each agent is connected through a **state-driven workflow**, managed by `StateGraph`, ensuring data consistency and smooth message passing between nodes.

---

## Tech Stack

| Layer | Technology | Purpose |
|:------|:------------|:--------|
| AI Core | [LangChain](https://python.langchain.com/) | Prompt design, message templates, and LLM invocation |
| Workflow Engine | [LangGraph](https://langchain-ai.github.io/langgraph/) | Agent orchestration and state management |
| Schema Enforcement | [Pydantic](https://docs.pydantic.dev/) | Defines and validates structured data models (`Dish`, `Dishes`) |
| LLM Provider | [OpenAI GPT-4o-mini](https://platform.openai.com/docs/) | Cost-efficient model for structured reasoning |
| Visualization | [PyGraphviz](https://pygraphviz.github.io/) | Generates the workflow graph diagram |

---

## Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/CulinaryMind.git
cd CulinaryMind

# Install dependencies
pip install langchain-openai==0.3.27
pip install langgraph==0.6.6
pip install pygraphviz==1.14
