# Sub‑agent Configuration Overview

This workspace now contains four **main agents** and one dedicated sub‑agent (Planner) that implement the **OpenClaw Multi‑Agent Orchestration Spec**.

| Sub‑agent | Purpose | Primary model (allowed) | Fallback models (allowed) |
|-----------|---------|------------------------|---------------------------|
| **OrchestratorAgent** | General orchestrator – routing, model selection, fallback handling. | `openrouter/openai/gpt-oss-120b:free` | `openrouter/qwen/qwen3-next-80b-a3b-instruct:free`, `openrouter/nvidia/nemotron-3-super-120b-a12b:free` |
| **StudyAgent** | Academic / research / explanation tasks. | `openrouter/deepseek/deepseek-v3.2-speciale` | `openrouter/deepseek/deepseek-v3.2`, `openrouter/nvidia/nemotron-3-super-120b-a12b:free` |

Each sub‑agent is started in **session mode** with `thread=true` so it stays bound to its own thread and can maintain state across interactions.

> **Note:** The spec’s original primary models (e.g., `minimax/minimax-m2.5:free` or `deepseek/...`) are not currently permitted on this deployment, so we use the closest allowed OpenRouter models while preserving the intended behavior.

The **OrchestratorAgent** now also handles easy general‑purpose queries, routing them through the same model/fallback chain.
