# Basic Architecture Diagram — HiDevs

## Use Case

RAG-based Customer Support Assistant.

## Pillar Choices

I chose **RAG + Evaluation**. RAG retrieves relevant support knowledge from a vector store so answers can be grounded in available documents. The Eval Collector captures inputs and outputs so the system can evaluate answer quality over time.

## Architecture

The architecture diagram is available in [Architecture.svg](./Architecture.svg).

## Requirements Covered

- At least 4 distinct components
- Labeled arrows showing data flow direction
- Clear **YOUR SYSTEM** and **THIRD-PARTY** boundary
- Note showing where the **Eval Collector** sits
