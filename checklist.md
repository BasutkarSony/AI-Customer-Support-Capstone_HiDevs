# Capstone Submission Checklist

## Architecture

- [x] RAG necessity is justified and not used by default.
- [x] MCP necessity is justified for multiple reusable external tools.
- [x] Agent autonomy level is explicitly defined as bounded autonomy.
- [x] Eval metrics match the system type and autonomy level.
- [x] Architecture has labeled components and data flow.
- [x] At least 3 failure points have actionable fallbacks.
- [x] Scaling bottleneck and mitigation are documented.

## PRD

- [x] Problem statement included.
- [x] Target users included.
- [x] Current workaround included.
- [x] V1 in-scope and out-of-scope items separated.
- [x] Functional requirements are testable.
- [x] At least 3 AI-specific RAG/Agent edge cases documented.
- [x] At least 2 measurable success metrics defined.
- [x] Latency, cost, availability, and safety requirements included.

## Evaluation

- [x] Offline dataset defined.
- [x] Offline metrics defined.
- [x] Passing thresholds defined.
- [x] Online production signals defined.
- [x] Regression plan covers prompt/model/tool changes.
- [x] Safety failures can block release and trigger rollback.

## Consistency

- [x] Architecture, PRD, and Eval Plan describe the same system.
- [x] RAG, MCP, Agent, and Eval roles are consistent across files.
- [x] Failure handling is reflected in both architecture and requirements.
- [x] Success metrics match the evaluation strategy.

## Final Submission

- [ ] Upload `architecture-diagram.md`
- [ ] Upload `prd.md`
- [ ] Upload `eval-plan.md`
- [ ] Upload `checklist.md`
- [ ] Verify all four files are visible in the public GitHub repository.
- [ ] Submit the GitHub repository URL.
