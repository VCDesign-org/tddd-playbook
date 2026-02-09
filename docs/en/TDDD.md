# TDDD: TODO Driven Development (2026 Edition)

## Overview

**TDDD (TODO Driven Development)**  
is a development method for the generative‑AI era  
that runs the entire process around TODOs.

Specs, design, implementation, and review are all **aggregated into TODOs**,  
and development is defined as “a loop of creating, executing, and updating TODOs.”

This method is recorded as an **annual edition** because it assumes  
the current separation of conversational AI, automated code‑generation AI,  
and IDE‑integrated AI tools.

---

## Background

Traditional development assumed:

- Humans understand specifications
- Humans break down design
- Humans write code

With generative AI,  
**“writing implementation” is now the cheapest and most predictable work**.

Still, the following are human responsibilities:

- What to build
- How far to build
- Where to stop
- What the expected result is

TDDD is designed around this **separation of decisions and implementation**.

---

## Core Principles

- What drives development is not code, but **TODOs**
- TODOs are not “commands” but **records of decisions**
- Implementation is only a faithful execution of TODOs
- When problems happen, you fix **TODOs**, not code

---

## The Four TDDD Loops

### Loop A: Create TODOs (Conversational AI + Humans)

**Purpose**
- Understand the spec
- Clarify boundaries
- Break into work units

**Main work**
- Provide conversation, documents, existing code
- Define the boundary where AI may act
- Create TODOs only within the boundary
- Generate YAML/schema if needed

**Deliverables**
- TODO.md
- (If needed) schema.yaml / boundaries.md

---

### Loop B: Execute TODOs (Automated AI)

**Purpose**  
- Mechanical implementation based on TODOs

**Main work**
- Provide the TODO folder as input
- Generate code under a specific language and constraints
- If behavior is unclear, do not implement it and return to TODOs

**Deliverables**
- Implementation code
- Minimal test code

---

### Loop C: Verify Behavior (Human)

**Purpose**  
- Check gaps with reality
- Return responsibility to humans

**Main work**
- Run and verify
- Observe differences from expectations
- Organize reproduction steps

**Deliverables**
- Observation logs
- Reproduction steps
- New TODOs

---

### Loop D: Review and Re‑TODO (Conversational AI)

**Purpose**  
- Fix learning
- Improve the next loop’s accuracy

**Main work**
- Have conversational AI review the implementation
- Convert feedback into TODOs
- Record design decisions briefly

**Deliverables**
- Updated TODOs
- Decision records (optional)

---

## Relationship to Other Methods

- TDDD is not a replacement for TDD (Test Driven Development)
- Tests are treated as part of TODOs
- Unlike BDD / SpecDD, specs are not the main deliverable

---

## Annual Edition

TDDD **depends strongly on tool structure**.

- Assumes separation of conversational AI and automated AI
- If IDE AI integrates both,  
  Loop A and Loop B are likely to merge

For that reason, this document is the **2026 Edition**.

---

## Future Extensions

- Integrate boundary design into Loop A
- Integrate organizational decision and responsibility design
- Add layers for AI governance and design principles

These are external principles to TDDD.  
TDDD itself preserves the **minimal structure of “running by TODOs.”**

---

## Summary

TDDD is not a methodology but a **driving method**.

Not “what to build,” but  
**what to leave as TODOs** determines development quality.

Code can disappear,  
but decisions recorded in TODOs are carried into the next implementation.
