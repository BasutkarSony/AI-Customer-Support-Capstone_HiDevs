# AI Customer Support Resolution Agent — HiDevs Level 5 Capstone

A complete AI customer support architecture using RAG, MCP, Agent orchestration, and Evaluation.

## Project

The system helps resolve customer support requests by:
- Retrieving current support knowledge using RAG
- Accessing ticket, order, and customer systems through MCP
- Using bounded agent autonomy for multi-step requests
- Evaluating response quality and tool behavior

## Capstone Files

- `architecture-diagram.md` — Complete system architecture, pillars, data flow, and fallbacks
- `prd.md` — Product requirements, scope, edge cases, and success metrics
- `eval-plan.md` — Offline/online evaluation and regression strategy
- `checklist.md` — Final submission self-review checklist

## Architecture

The system uses four pillars:

**RAG + MCP + Agent + Eval**

The agent has bounded autonomy, external tool access is standardized through MCP, current support knowledge is retrieved through RAG, and evaluation metrics are used to detect quality and safety problems.

## HiDevs Level 5 Capstone

Final submission covering the architecture, product requirements, evaluation strategy, failure handling, and scaling considerations.
