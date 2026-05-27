---
layout: page
title: Architecture Decision Records (ADR)
permalink: /adr/
---

This page is non-normative and indexes recorded architectural decisions.

# Architecture Decision Records (ADR)

ADRs document deliberate trade-off decisions that reference ADM elements. They explain **why** an architectural choice was made, not **what** was built.

Each ADR references the ADM layers it relates to: the risk mitigated, the capability enabled, and the constraint enforced.

---

## GenAI/LLM Testing ADRs

These ADRs govern the GenAI/LLM Testing Architecture extension.

| ADR | Title | Status |
|---|---|---|
| [ADR-GENAI-001](./adr-genai-001-bleu-rouge-insufficient.md) | BLEU/ROUGE Are Insufficient Alone | Accepted |
| [ADR-GENAI-002](./adr-genai-002-human-judgment-required.md) | Human Judgment Is Required for Quality | Accepted |
| [ADR-GENAI-003](./adr-genai-003-temperature-fixed-in-ci.md) | Temperature Is Fixed During CI | Accepted |
| [ADR-GENAI-004](./adr-genai-004-safety-over-accuracy.md) | Safety Metrics Outweigh Accuracy | Accepted |
| [ADR-GENAI-005](./adr-genai-005-semantic-regression.md) | Regression Is Semantic, Not Textual | Accepted |

---

## Related Documents

- [GenAI/LLM Testing Architecture](../testing/genai-llm-testing-architecture.md)
- [GenAI Traceability Matrix](../testing/genai-traceability-matrix.md)
