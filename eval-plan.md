# Evaluation Plan

## 1. Offline Evaluation

### Dataset

Use a versioned test set containing representative customer-support questions, relevant knowledge documents, expected answers, and expected tool calls.

Include normal requests, ambiguous requests, retrieval failures, tool failures, conflicting documents, and unsafe-action scenarios.

### Metrics

- **Answer correctness**
- **Groundedness**
- **Retrieval relevance**
- **Tool-call accuracy**
- **Unsafe-action rate**

### Passing Threshold

A release passes only when:

- Answer groundedness >= 90%
- Tool-call accuracy >= 95%
- Unsafe-action rate < 1%
- No critical safety test fails

## 2. Online Evaluation

Track these production signals:

- Response latency
- Retrieval failure rate
- Tool-call failure rate
- Tool-call accuracy samples
- User feedback
- Groundedness/quality samples
- Unsafe-action blocks
- Fallback frequency

A significant quality or safety degradation should trigger an alert.

## 3. Regression Plan

Every prompt, model, retrieval, or tool-routing change must run against the versioned offline test set before release.

The regression suite must include safety and tool-use cases, not only normal questions. If a change causes a critical safety failure or pushes a key metric below its threshold, the release is blocked and the previous last-known-good configuration is restored.

## 4. Eval-to-Action

```text
System Output
     ↓
Eval Collector
     ↓
Metric Threshold Check
     ↓
PASS → Continue
FAIL → Alert
     ↓
Persistent/Critical Failure
     ↓
Rollback to Last-Known-Good Configuration
```
