# AI Agents & MCP Roadmap

> **Pillar:** 07-ai-ml · **Status:** 🚧 Stub · **Track:** Parallel
> **Prerequisites:** [LLM](../07-ai-ml/llm.md)
> **Feeds into:** [Generative AI](../07-ai-ml/generative-ai.md) (agentic GenAI products)

## Overview
Building autonomous AI agents and the Model Context Protocol (MCP): planning, memory, tool
calling, multi-agent orchestration, and the client/server protocol agents use to reach tools
and resources.

## Planned modules (to build)
- Agent fundamentals: agent vs LLM, agent architectures, design patterns (planner-executor,
  supervisor-worker, router, reflection)
- Agent planning & reasoning: ReAct, Plan-and-Execute, Tree of Thoughts, goal decomposition
- Tool calling · agent memory (short/long-term) · context & state management
- MCP fundamentals: architecture, clients, servers, tools, resources, prompts, transport
  (stdio, HTTP, SSE)
- MCP server & client development · multi-agent systems & A2A (agent-to-agent) communication
- Agentic RAG (see [LLM](../07-ai-ml/llm.md) for retrieval technique depth)
- Agent security (prompt/tool injection, sandboxing), observability, evaluation
- Agent frameworks overview (LangGraph, AutoGen, CrewAI, OpenAI Agents SDK — framework
  comparison depth lives in [Generative AI](../07-ai-ml/generative-ai.md))
- Production agent architecture & case studies (assignments)

_Follows [`../../templates/ROADMAP-TEMPLATE.md`](../../templates/ROADMAP-TEMPLATE.md)._
