---
layout: page
title: Overview
permalink: /overview/
---

This page is normative and defines ADM semantics.

# Overview

The Architecture Definition Model (ADM) is a structured way to describe an AI system without mixing purpose, policy, design, runtime structure, and implementation details together.

In practice, ADM helps answer questions like:

- Why does this system exist?
- What context and constraints shape it?
- What capability is being provided?
- What interfaces expose that capability?
- What units execute it?
- What components implement it?
- What technical interfaces connect it?
- What rules and decisions govern it?

ADM exists to keep architecture explicit, reviewable, and stable. It separates meaning from implementation so that a system can evolve without losing architectural clarity.

## Why ADM Uses Layers

Architectural descriptions often become confusing because different kinds of statements are mixed together. For example:

- a business goal is written beside an API contract
- a safety constraint is confused with a component
- a runtime worker is described as if it were a user-facing capability
- an implementation choice is presented as a governing principle

ADM prevents that confusion by assigning each kind of architectural statement to a defined layer.

Each layer has one purpose.
Each concept has one meaning.
Architecture stays understandable because structure is preserved.

## Canonical Layer Set

The ADM layer set is:

1. Intent
2. Context
3. Capability
4. Service Interface
5. Execution Unit
6. Component
7. Technical Interface
8. Agent
9. Constraints
10. Decisions

The vertical layers refine architecture from purpose toward implementation-facing structure.

The horizontal layers apply across the model:

- **Agent** describes agent-specific behavior and responsibilities where applicable
- **Constraints** define limits, obligations, and prohibitions
- **Decisions** record deliberate architectural choices and rationale

## Running Example: AI Support Assistant

Consider an AI support assistant used by customers to ask product and troubleshooting questions.

### Intent
Why does the system exist?

- Reduce support response time
- Improve answer consistency
- Preserve auditability and safety
- Escalate uncertain cases to a human

### Context
What environment and conditions shape the system?

- Customers ask questions through a web portal
- Answers may affect regulated product usage
- Human support staff must remain part of the process
- Responses must be logged for review

### Capability
What ability does the system provide?

- Answer product-support questions
- Retrieve relevant product guidance
- Identify uncertainty and trigger escalation

### Service Interface
How is that capability presented to consumers?

- A chat interface for customers
- An internal escalation request interface for support staff
- A feedback submission interface for answer quality review

### Execution Unit
What runtime units perform the work?

- A request handler for incoming chat messages
- A retrieval pipeline that gathers relevant documents
- A response generation worker
- An escalation evaluator

### Component
What architectural building blocks implement the system?

- Conversation manager
- Retrieval service
- Policy checker
- Answer composer
- Audit logger

### Technical Interface
What concrete technical contracts connect the system?

- HTTP endpoints
- Internal service calls
- event messages
- storage APIs
- model invocation APIs

### Agent
Where an agent is used, what role does it play?

- Interpret the user request
- decide whether enough information is available
- propose an answer
- decline or escalate when policy requires it

### Constraints
What limits govern the system?

- The system must not invent unsupported claims
- High-risk advice must be reviewed or escalated
- All responses must be logged
- The system must not bypass defined escalation rules

### Decisions
What architectural choices have been deliberately made?

- Retrieval is required before answer generation
- Escalation is mandatory above a confidence/risk threshold
- Policy validation occurs before response delivery
- Audit logging is part of the core architecture, not an optional add-on

## How to Read ADM Correctly

A useful way to read ADM is to move from top to bottom:

- **Intent** explains why
- **Context** explains under what conditions
- **Capability** explains what the system does
- **Service Interface** explains how that capability is exposed
- **Execution Unit** explains what runs
- **Component** explains what is built
- **Technical Interface** explains how parts connect technically

Then read across the model:

- **Agent** for agent-specific responsibility and behavior
- **Constraints** for hard limits and obligations
- **Decisions** for chosen architectural direction and rationale

## Common Modeling Mistakes

### Mistake 1: Mixing goals with structure
“Use a retrieval API” is not an Intent statement.
It is closer to a Technical Interface or an implementation-oriented architectural choice.

### Mistake 2: Confusing capability with interface
“Chat endpoint” is not the capability.
The capability is answering support questions.
The chat endpoint is one interface exposing that capability.

### Mistake 3: Treating a component as a policy
“Audit logger” is a component.
“All responses must be logged” is a constraint.

### Mistake 4: Treating implementation details as architecture purpose
“Use vector search” is not a statement of why the system exists.
It is a lower-layer design or technical decision.

## Summary

ADM provides a disciplined way to describe architecture so that meaning remains stable across change.

Use ADM to separate:

- purpose from implementation
- capability from interface
- runtime behavior from structural composition
- policy from mechanism
- architecture from incidental detail
