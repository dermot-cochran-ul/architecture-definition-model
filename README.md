# Architecture Definition Model (ADM)

The Architecture Definition Model (ADM) is a structured, layered framework for
defining, governing, and enforcing the architecture of Generative AI systems.

ADM exists to ensure that:
- Architecture is explicit and human‑owned
- Responsibilities and boundaries are clearly defined
- Agents operate within defined constraints
- Architectural evolution is deliberate and auditable

This repository provides a **public reference** for ADM concepts, terminology,
rules, and illustrative examples.

---

## Scope

This repository contains:
- Canonical definitions of ADM layers and concepts
- Explanatory guides for applying ADM
- Non‑authoritative examples and templates
- Testing architecture extensions (see [docs/testing/](docs/testing/))
- Architecture Decision Records (see [docs/adr/](docs/adr/))

This repository does **not**:
- Define implementation requirements
- Provide production‑ready systems
- Imply adoption by any organization

---

## Disclaimer

This project is published in a personal capacity.

Any intellectual property rights that may arise from my employment are retained by
**UL Solutions**, as applicable. No endorsement, sponsorship, or approval by
UL Solutions is implied.

The views, ideas, and materials expressed here are my own and are provided
for informational purposes only.

---

## Intellectual Property Notice

This work was developed independently and does not incorporate proprietary,
confidential, or internal materials from any employer.

All trademarks and registered trademarks, if referenced, are the property of
their respective owners.

---

## Canonical Reference

This repository serves as the canonical public reference for the
Architecture Definition Model (ADM) as described by the author.

Forks and derivative works are permitted under the applicable licenses;
however, this repository remains the authoritative reference location.

---

## Testing Architecture

- [Testing Architecture (ADM-Aligned)](docs/testing/testing-architecture.md)
- [Traceability Matrix](docs/testing/traceability-matrix.md)
- [Architecture Decision Records (ADRs)](docs/adr/)

---

## License

This material is made available under the licenses below **to the extent
permitted by applicable intellectual property rights**.

- Documentation, definitions, and explanatory text are licensed under  
  **Creative Commons Attribution 4.0 International (CC BY 4.0)**

- Example code, configuration, and prompt templates are licensed under  
  **Apache License, Version 2.0**

Nothing in this repository grants rights to any intellectual property
owned by UL Solutions beyond what is permitted by law.

See `LICENSE.docs` and `LICENSE.code` for full license texts.

---

## Contributions

Contributions are welcome, but architectural changes must respect ADM
layer discipline and semantic rules.

Significant changes should be proposed as documented decisions
(Architecture Decision Records) rather than implicit edits.

---

## Testing Architecture

ADM-aligned testing architecture documentation is available under [`docs/testing/`](docs/testing/):

- [GenAI/LLM Testing Architecture](docs/testing/genai-llm-testing-architecture.md) — Testing strategy and automation architecture for LLM-powered systems
- [GenAI Traceability Matrix](docs/testing/genai-traceability-matrix.md) — Capabilities → Constraints → Risks → Evidence mapping

## Architecture Decision Records

Recorded trade-off decisions are under [`docs/adr/`](docs/adr/):

| ADR | Title |
|---|---|
| [ADR-GENAI-001](docs/adr/adr-genai-001-bleu-rouge-insufficient.md) | BLEU/ROUGE Are Insufficient Alone |
| [ADR-GENAI-002](docs/adr/adr-genai-002-human-judgment-required.md) | Human Judgment Is Required for Quality |
| [ADR-GENAI-003](docs/adr/adr-genai-003-temperature-fixed-in-ci.md) | Temperature Is Fixed During CI |
| [ADR-GENAI-004](docs/adr/adr-genai-004-safety-over-accuracy.md) | Safety Metrics Outweigh Accuracy |
| [ADR-GENAI-005](docs/adr/adr-genai-005-semantic-regression.md) | Regression Is Semantic, Not Textual |

---

## Contact
