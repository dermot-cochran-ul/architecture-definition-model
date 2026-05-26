---
layout: page
title: ADM and C4: Complementary, Not Competing
permalink: /adm-and-c4/
---

This page is normative and defines ADM semantics.

# ADM and C4: Complementary, Not Competing

ADM and C4 are compatible when used for their intended purposes.

- ADM defines architecture semantics and governance.
- C4 provides diagram views for communicating architectural structure at different zoom levels.

ADM answers **what exists, why it exists, and how it is governed**.
C4 answers **how to visualize parts of the architecture at different zoom levels**.

ADM is **normative and enforceable**.
C4 is **descriptive and illustrative**.

> C4 diagrams are *derived artifacts* from ADM, not the architecture itself.

## Explicit Mapping Between ADM and C4

The mapping below preserves ADM layer discipline while allowing C4 diagrams to communicate selected architectural slices.

| ADM Layer | ADM Role | Typical C4 View(s) | Mapping Guidance |
|---|---|---|---|
| Intent | Why the system exists; goals and quality attributes | System Context (supporting narrative) | Use Intent to explain purpose and quality drivers behind boundaries shown in diagrams. Do not encode deployable structure here. |
| Context | External environment, actors, and constraints context | System Context | Use Context to define external actors and neighboring systems represented around the system boundary. |
| Capability | What must be possible (non-executable) | System Context, Container (annotative) | Show capabilities as labels or overlays; do not treat capabilities as running elements. |
| Service Interface | Contractual boundaries (APIs, schemas, SLAs) | Container, Component | Map interfaces to explicit contracts shown between containers/components. Keep contracts distinct from implementations. |
| Execution Unit | Runtime units that perform work | Container (runtime-focused) | Use for runtime responsibility decomposition when communicating executable units. |
| Component | Internal architectural building blocks | Component | Represent component decomposition inside a selected container while preserving ADM meaning. |
| Technical Interface | Concrete technical contracts/protocols | Container, Component, Dynamic | Use to show concrete protocol/transport/API details and interaction paths. |
| Agent | Agent-specific role and behavior | Component, Dynamic (where relevant) | Depict agent behavior as derived from ADM Agent definitions; do not redefine agent semantics in diagrams. |
| Constraints | Cross-cutting limits and obligations | All levels (annotations/legends) | Apply as governing annotations; constraints do not substitute for structural definitions. |
| Decisions | Recorded architectural choices and rationale | All levels (references/notes) | Link diagrams to ADR-style rationale so visuals remain traceable to authoritative decisions. |

## Usage Rules for ADM + C4

1. Define and approve architecture in ADM first.
2. Generate C4 diagrams from ADM statements and relationships.
3. Validate every C4 element against its originating ADM layer.
4. Treat diagram drift from ADM as a conformance defect.

## Conformance Checklist

- Every C4 element traces back to an ADM concept.
- No C4 label redefines ADM layer meaning.
- Structural views do not collapse or merge ADM layers.
- Constraints and decisions are referenced, not replaced, by visuals.

## Summary

ADM remains the authoritative architecture model.
C4 remains a communication framework that visualizes architecture already defined in ADM.
