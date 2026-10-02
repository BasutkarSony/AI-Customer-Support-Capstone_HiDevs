# Product Requirements Document

## 1. Problem Statement

Customer support teams spend time searching policies, checking customer/order information, and handling repetitive requests. The AI Customer Support Resolution Agent combines knowledge retrieval and standardized tools to provide grounded responses and support safe actions.

## 2. Target Users

- Customer support agents
- Customers using support channels
- Support operations teams

## 3. Current Workaround

Support staff manually search knowledge bases and separately access ticket, order, and customer systems.

## 4. V1 Scope

### In Scope
- Retrieve relevant support knowledge using RAG.
- Use MCP tools for ticket, order, and customer information.
- Use bounded agent autonomy to plan multi-step requests.
- Generate grounded customer responses.
- Evaluate response quality and tool behavior.
- Use fallbacks when retrieval, tools, or the LLM fail.

### Out of Scope
- Fully autonomous high-impact customer actions.
- Replacing human support agents.
- Building new ticket/order/customer systems.
- Voice support.

## 5. Functional Requirements

1. The system shall retrieve relevant knowledge before answering policy-related questions.
2. The agent shall select the appropriate MCP tool when external customer, order, or ticket data is required.
3. The system shall not execute a high-impact action without validation.
4. The system shall use a fallback when the primary LLM fails.
5. The system shall avoid guessing when reliable retrieved information is unavailable.
6. The system shall record evaluation metrics for responses and tool calls.

## 6. RAG/Agent Edge Cases

### Edge Case 1 — No Relevant Retrieval
If RAG returns no reliable information, the agent must not invent an answer and should ask for clarification or provide a safe fallback.

### Edge Case 2 — MCP Tool Failure
If a required external tool fails, the agent should retry once and then provide a safe status message without performing the action.

### Edge Case 3 — Conflicting Retrieved Information
If retrieved documents contain conflicting policies, the agent should flag the conflict and avoid making a definitive claim until the information is verified.

### Edge Case 4 — Unsafe Agent Action
If an action fails an evaluation safety check, the action must be blocked and the user should receive a safe response.

## 7. Success Metrics

- **Answer groundedness:** at least 90% of evaluated responses should be supported by retrieved knowledge.
- **Tool-call accuracy:** at least 95% of evaluated tool calls should select the correct tool and parameters.
- **Unsafe-action rate:** less than 1% of evaluated requests should result in an unsafe or unauthorized action.

These metrics are measured through the Eval Plan's offline and online evaluation strategy.

## 8. Non-Functional Requirements

- **Latency:** 95% of normal requests should receive a response within 5 seconds, excluding slow external systems.
- **Availability:** target 99.5% monthly availability for the core service.
- **Cost:** use caching and model routing to control inference and tool-call costs.
- **Safety:** high-impact actions require validation before execution.
