# Advanced Diagram + Fallbacks — HiDevs

## Use Case

RAG-based Customer Support Assistant with evaluation, failure handling, and scaling controls.

## Failure Points + Fallbacks

1. **Vector store unavailable or retrieval timeout:** use cached FAQs or keyword retrieval.
2. **LLM timeout/rate limit:** retry with backoff, then route to an alternate LLM provider/model.
3. **Low-quality or unsafe output:** evaluation metrics trigger an alert; if the threshold breach persists, roll back to the last-known-good model/prompt configuration.

## Scaling

The **LLM API/router** is the first likely bottleneck because inference latency and provider rate limits increase with traffic. Use response caching, a request queue, and load balancing across providers/models.

## Eval Integration

The **Eval Collector** sends metrics to the **Eval Monitor**. If a quality metric crosses its threshold, an alert is raised; a persistent breach triggers rollback to the last-known-good model/prompt configuration.

## Critical Failure Point

LLM timeout or rate limiting is critical because it can directly prevent the assistant from producing a response. The system retries with backoff and then switches to a fallback LLM provider/model, keeping the user request available instead of failing immediately.
