---
layout: page
title: Worked Examples
permalink: /worked-examples/
---

This page is normative and defines ADM semantics.

# Worked Examples

## Purpose
Worked examples demonstrate classification and rule conformance using existing ADM semantics.

## Example Constraints
- Each worked example MUST map statements to existing ADM layers only.
- Each worked example MUST preserve single-meaning semantics.
- Each worked example MUST state violations when layer discipline is broken.

## Prohibitions
- Worked examples MUST NOT define new layers.
- Worked examples MUST NOT redefine ADM concepts.
- Worked examples MUST NOT add internal usage policy.

---

## Example 1: Testing Strategy (ADM Layer Classification)

This example classifies statements from a test automation system across ADM layers.

### Statements and Layer Assignments

| Statement | ADM Layer | Rationale |
|---|---|---|
| "Provide continuous, trustworthy evidence that the system meets its obligations before every change." | Intent | Expresses the purpose and goal of testing; no structural or implementation detail. |
| "CI/CD system executes tests automatically on every change." | Context | Identifies an external actor and its role relative to the testing system. |
| "Test Execution: run tests deterministically and in parallel." | Capability | Names a stable, tool-agnostic ability without referencing implementation. |
| "`executeTests(testSuite, environmentRef) → TestReport`" | Service Interface | Defines a named, typed contract exposed by the testing service; no implementation detail. |
| "Test Orchestrator: coordinates test execution and manages ordering and parallelism." | Execution Unit | Identifies a deployable, independently scalable runtime responsibility. |
| "Test Discovery, Test Executor, Assertion Engine, Result Normalizer, Artifact Collector (within a Test Runner)" | Component | Lists internal, replaceable parts of an Execution Unit; invisible across service boundaries. |
| "CLI invocation to trigger test suites; HTTP APIs to query status; JUnit XML artifact exchange." | Technical Interface | Identifies concrete communication mechanisms between components. |
| "Test Selection Agent: chooses which tests to run based on change risk." | Agent (horizontal) | An autonomous decision-support role; references the Capability layer without defining structure. |
| "Tests must be deterministic and repeatable." | Constraints (horizontal) | A non-negotiable rule that applies across all vertical layers. |
| "ADR-001: Contract tests are favored over E2E tests in CI." | Decisions (horizontal) | Records a deliberate architectural trade-off linking capability to risk. |

### Layer Violations (Illustrative)

| Misclassified Statement | Incorrect Layer | Correct Layer | Violation |
|---|---|---|---|
| "We use pytest to run unit tests." | Capability | Technical Interface | Names a specific tool; belongs at Technical Interface, not Capability. |
| "Quality gates block bad changes." | Technical Interface | Capability / Constraints | Describes an ability and a rule, not a concrete mechanism. |
| "Developers write tests." | Execution Unit | Context | Describes an actor role, not a deployable runtime responsibility. |

### Conformance Summary

All ten correctly classified statements map to existing ADM layers without skipping or collapsing layers. No new layers are introduced. The violations table confirms that tool names and actor roles are misplaced when placed at the wrong layer.

---

## Example 2: Gen AI Test Automation (ADM Layer Classification)

This example classifies statements from a GenAI/LLM test automation system across ADM layers.

### Statements and Layer Assignments

| Statement | ADM Layer | Rationale |
|---|---|---|
| "Continuously establish justified confidence that LLM-powered behavior is correct enough, safe enough, aligned enough, and economical enough." | Intent | Expresses the governing purpose of GenAI testing; no structural or implementation detail. |
| "Foundation model providers, vector databases, prompt/version stores, and evaluation datasets are external dependencies." | Context | Identifies external systems; no capability or implementation detail. |
| "Output Evaluation: assess quality, relevance, and correctness of model outputs." | Capability | Names a stable, model-agnostic ability; no tool or implementation reference. |
| "`evaluateSafety(outputBatch) → SafetyReport`" | Service Interface | Defines a typed contract; no implementation detail or CI tool reference. |
| "Safety Evaluation Engine: runs toxicity, policy, and risk checks; applies red-line thresholds." | Execution Unit | Identifies a deployable, independently scalable runtime responsibility. |
| "Policy Classifier, Risk Heuristic Evaluator, Threshold Comparator, Escalation Handler (within Safety Evaluation Engine)" | Component | Lists internal, replaceable parts of the Safety Evaluation Engine. |
| "Model APIs over HTTP/gRPC; JSON evaluation schemas; artifact storage for reports and traces." | Technical Interface | Identifies concrete communication mechanisms; these are examples, not prescriptions. |
| "Test Case Generation Agent: proposes adversarial or edge-case prompts." | Agent (horizontal) | An autonomous decision-support role; does not bypass quality gates or define structure. |
| "Evaluation datasets are versioned and immutable; safety violations always block deployment." | Constraints (horizontal) | Non-negotiable rules that govern all vertical layers of GenAI testing. |
| "ADR-GENAI-005: Regression is semantic, not textual." | Decisions (horizontal) | Records a deliberate trade-off linking Regression Detection capability to a constraint. |

### Layer Violations (Illustrative)

| Misclassified Statement | Incorrect Layer | Correct Layer | Violation |
|---|---|---|---|
| "We use LangSmith to evaluate prompt quality." | Capability | Technical Interface | Names a specific tool; belongs at Technical Interface, not Capability. |
| "Temperature is fixed at 0.0 during CI." | Constraints | Technical Interface | Describes a concrete configuration value; belongs at Technical Interface (possibly also documented as a Constraint rationale in the ADR, but the value itself is not a layer-level constraint). |
| "Safety violations block deployment." | Execution Unit | Constraints (horizontal) | Describes a non-negotiable rule, not a deployable runtime responsibility. |

### Key GenAI Distinction

The GenAI context introduces probabilistic correctness. This does not create new ADM layers; it affects how the Intent layer is stated (bounding behavior rather than asserting binary correctness) and how Constraints are set (thresholds, not pass/fail assertions).

### Conformance Summary

All ten correctly classified statements map to existing ADM layers. The GenAI-specific Agents and Constraints follow horizontal layer rules: they reference vertical layers without defining new structure. No new layers are introduced.

---

## Related Documents

- [Testing Architecture (ADM-Aligned)]({{ site.baseurl }}/testing/testing-architecture/)
- [GenAI/LLM Testing Architecture]({{ site.baseurl }}/testing/genai-llm-testing-architecture/)
- [GenAI Traceability Matrix]({{ site.baseurl }}/testing/genai-traceability-matrix/)
- [Traceability Matrix]({{ site.baseurl }}/testing/traceability-matrix/)
- [Layers]({{ site.baseurl }}/layers/)
- [Rules]({{ site.baseurl }}/rules/)
