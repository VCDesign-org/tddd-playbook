# TDDD Advanced Guide (2026)

## What This Is

This document shows **concrete steps to run TDDD reliably in real work**.

Design theory is minimized,  
and the focus is on “how to avoid accidents.”

---

## Two Premises in the Advanced Guide

### Design Premise

**Assuming rebuilds is what sustains value**

### Method Premise

**Decision and execution phases must be consciously separated, even when using the same tool**

The TDDD Advanced Guide is built only on these two premises.

---

## Overall TDDD Advanced Cycle

The Advanced Guide loops through three phases.

1. Create TODOs through decision-phase AI operation
2. Execute TODOs through execution-phase AI operation
3. Review and return to TODOs

Repeat.

---

## 1. Create TODOs Through Decision-Phase AI Operation

This is the **most important step**.

Even when using the same tool, such as Claude Code design mode,
keep this phase focused on decisions, not implementation.

### 1-1. Make It Understand the Spec

- Explain in conversation
- Paste existing materials
- Ambiguity is fine

The goal is not “the correct answer.”  
The goal is **aligning assumptions**.

---

### 1-2. Define the Boundary Where AI Can Act

Always make these explicit.

- What to do this time
- What not to do this time
- What must not affect anything outside

Example:

```md
- Do not touch external APIs
- Do not change the DB schema
- Do not perform file I/O
```

### 1-3. Create TODOs Within the Boundary

Ask through decision-phase AI operation:

Within this boundary only, create implementation TODOs.  
Make explicit what we will not do.

### 1-4. Output YAML If Needed

- Inputs/outputs
- State
- Settings

Write **structure only** in YAML before any code.

Deliverables:

```text
todo/
  ├─ TODO.md
  └─ schema.yaml (if needed)
```

---

## 2. Execute TODOs Through Execution-Phase AI Operation

Do **not** let it decide.

### 2-1. Large Systems Are “One Boundary, One Project”

- Separate repositories or folders per boundary
- Keep the size within AI’s cognitive limits

This is not design philosophy.  
It is a defense against AI limits.

### 2-2. Make the TODO Folder the Only Source of Truth

Always instruct the execution-phase AI operation:

Using only the contents of the `todo` folder,  
implement in xx language.  
Do not implement anything not written in the TODO.

### 2-3. If It Acts Strange, Turn the Behavior Into a TODO Test

- Do not fix code
- Ask for a test that verifies the behavior

Example:

- [ ] Add a test that verifies no exception is thrown when input is None

Procedure:

1. Manually check behavior
2. Execute
3. Confirm what differs from expectations
4. Fix it in the next phase

---

## 3. Review and Re-TODO

### 3-1. If Possible, Refactor Through a Different Execution-Phase AI Operation

Purpose:

- Organize code
- Remove duplication
- Improve readability

Adding tests from a “different perspective” rarely matters.

### 3-2. Review Through the Original Decision-Phase AI Operation

- Does this implementation satisfy the TODO?
- Did it cross any boundaries?
- Where are decisions missing?

### 3-3. Return All Feedback to TODOs

- Fix TODOs before code
- Freeze decisions
- Repeat the cycle

1. Create TODOs
2. Implement
3. Verify
4. Fix TODOs

TDDD does not aim for one-shot completion.

---

## Techniques for Connecting Boundaries (Entry to Larger Scale)

TDDD is small per boundary,  
but can be expanded with loose coupling.

Useful techniques:

- Connect boundaries with data structures only
- Use JSON / YAML / DTOs instead of function calls
- Do not reference directly (use Adapter / Facade)
- Design boundary communication for failure

This allows:

- Discarding one side
- Rebuilding
- Switching AI tools

---

## Limits of the Advanced Guide

- Human safety systems
- Physical control
- Legally high-liability domains

These require different design.

---

## Summary

- Decisions are made through decision-phase AI operation
- Implementation is delegated to execution-phase AI operation
- Cut by boundaries, connect loosely
- Do not erase TODOs

The TDDD Advanced Guide is a practical development loop  
that assumes continuous rebuilding.

---

## Advanced Supplement: The “Invisible Map” of 11 Boundaries

The most important thing in the Advanced Guide is  
**not making a mistake about where to cut**.

To help that judgment, VCDesign / VC-AD  
organize “constraints outside the code”  
as **11 boundaries** that AI often misses.

These are hard to represent as code  
and are where AI most often goes wild.

---

## Overview of the 11 Boundaries

They are grouped into four categories.

---

### Group 1: Unchangeable Premises (Context)

**Boundaries you must not try to solve with design**

1. Physical / field constraints  
10. Organization / boundaries  
11. Governance

Examples:
- Physically separated
- Different organizations or responsible parties
- Fixed by law or regulation

TDDD handling:
- Explicitly write them as “assumptions” in TODOs
- Do not solve them in implementation
- Fix them as “accepted premises” for AI

---

### Group 2: Chosen Resources (Resource)

**Boundaries determined by “selection,” not design**

2. Execution platform  
3. Network  
9. Platform

Examples:
- Cloud / on‑prem
- Latency / bandwidth
- Managed / self‑managed

TDDD handling:
- Split projects so they don’t cross these boundaries
- Write the chosen premises in TODOs
- Don’t change them mid‑implementation

---

### Group 3: Required Quality Standards (Standard)

**Boundaries AI must not break**

6. Reliability (SRE)  
7. Security  
8. Observability

Examples:
- Retry policy
- Access control
- Log/metric formats

TDDD handling:
- Write them as constraints in TODOs
- Do not make decisions in the execution phase
- If needed, turn checks into TODO tests

---

### Group 4: VC‑AD Core Domain (Core Domain)

**No correct answer; only decisions exist**

4. Nature of distribution  
5. Data semantics

Examples:
- Consistency vs availability
- Whether to allow double processing
- Meaning of money/quantity

TDDD handling:
- Humans always decide through decision-phase AI operation
- Record decisions in TODOs
- Implementation only “executes” the decisions

This is **where AI is weakest**  
and needs the most careful handling.

---

## Practical Use in the Advanced Guide

### Boundary Split Check

Before cutting a project/TODO by a boundary, confirm:

- Which of the 11 boundaries it includes
- Whether it crosses multiple groups
- Especially whether Group 4 is mixed in

If it is mixed, **split it**.

---

### Principles for Connecting Boundaries (Loose Coupling)

- Connect with data structures
- Do not reference directly
- Assume failure
- Make each side disposable

This makes TDDD  
**applicable to large real systems**.

---

## Relationship Between TDDD and the 11 Boundaries

- TDDD is about “how to run”
- The 11 boundaries are a map of “where to cut”
- VCDesign / VC‑AD explain “why to cut that way”

The Advanced Guide covers  
**driving while reading the map**.

---

## Summary

- AI does not know boundaries
- Humans must teach boundaries
- Record decisions in TODOs
- Keep implementation inside boundaries

If you can do this,  
TDDD scales beyond small systems  
to **large real systems**.
