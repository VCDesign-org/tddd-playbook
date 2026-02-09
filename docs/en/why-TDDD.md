# Why TDDD (TODO Driven Development)

## Why TDDD Is Necessary

TDDD (TODO Driven Development)  
was not born to invent a new development technique.

It was born  
**to make the development process catch up to changes that already happened.**

---

## The Death of Implementation

With generative AI,  
“writing implementation” is no longer the core of development.

- Code is generated quickly
- Quality is reasonably consistent
- The cost of rewriting has dropped drastically

As a result, code has become **disposable**.

Code written today  
is expected to be erased and rewritten by AI tomorrow.

Yet systems still must keep running.

---

## What Changed Is Not “How”

This change is not about “how” to write.

What fundamentally changed is:

**“Where to stop.”**

---

## Mechanics Get Off the Plane

Engineers used to be:

- Designers
- Implementers
- Mechanics when trouble happened

In other words,  
they rode inside the plane even during flight.

But as generative AI automates implementation,  
engineers are gradually pushed out of the cabin.

Design and decisions are finished before takeoff,  
and after takeoff, “touching” the system is assumed impossible.

This is not a choice.  
**It is a structural change.**

---

## The Problem Is Not “Who Is Piloting”

Common debates go like this:

- Is AI piloting?
- Is the human piloting?

But the real issue is not who.

It is:

**Where the controls are**  
and  
**where piloting decisions are recorded.**

---

## Code Cannot Preserve Decisions

Code preserves implementation,  
but **cannot preserve decisions**.

- Why this spec?
- Why stop at this boundary?
- Why allow this exception?

Those fragments may appear in comments or design docs,  
but code itself is not a medium for decisions.

In the generative‑AI era,  
entrusting decisions to code is dangerous.

---

## TODOs Can Preserve Decisions

A TODO is  
**a message of decisions** to future implementation.

- Do up to here
- Do not go beyond this
- This condition must be met
- This point must be verified

TODOs survive even if implementation disappears.

Even if the implementation is rewritten,  
decisions recorded in TODOs carry over.

---

## What TDDD Does

TDDD is simple.

- Centralize decisions in TODOs
- Make implementation only execute TODOs
- When problems happen, fix TODOs, not code

That’s it.

---

## Why a Loop

Generative AI does not reach the correct answer in one shot.  
Humans do not either.

So TDDD does not aim for one‑shot completion.

- Create TODOs
- Implement
- Verify
- Update TODOs

Development is treated as  
**a loop of continuously updated decisions**.

---

## Why Boundaries Matter

Generative AI always goes wild  
where boundaries are ambiguous.

- What is allowed
- What is forbidden
- What is out of scope

Unless these are explicit,  
AI crosses boundaries in good faith.

In TDDD,  
boundaries are made explicit as TODOs.

Boundaries are not design docs,  
but **decisions written as preconditions for execution**.

---

## Why an Annual Edition

TDDD depends on the current tool structure.

- Conversational AI
- Automated code‑generation AI
- IDE‑integrated AI support

If these are integrated,  
TODO creation and implementation will merge.

At that time, TDDD’s shape will change.

So this is not an eternal theory.  
**It is a driving method matched to the reality of the year.**

---

## What TDDD Places and Does Not Place

TDDD keeps ideology minimal.

- AI governance
- Design philosophy
- Organizational theory
- Responsibility design

These are **outside TDDD**.

They can be carried in Loop A,  
but TDDD itself does not force them.

---

## Summary

Implementation is no longer the lead.

What remains is:

- Decisions
- Boundaries
- Expectations

TDDD is  
**the smallest development loop**  
for delivering those into the future via TODOs.

Even if code disappears,  
as long as TODOs remain,  
development can continue.
