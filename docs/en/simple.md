# TDDD Simple Guide (2026)

## What This Is

This document is a minimal procedure  
**for moving development forward using TODOs**.

It does not explain design theory or philosophy.  
It only explains how to build something that doesn’t break easily.

---

## Assumptions

- You roughly know what you want to build
- You are not good at design or decomposition
- You use generative AI (ChatGPT / Claude / Copilot, etc.)
- You use VSCode (it is fine if you cannot write HTML or Python)

That is enough.

---

## Key Ideas (Remember Only These)

- **Do not start writing code**
- **Create TODOs first**
- **When problems happen, fix the TODO, not the code**

That’s all.

---

## Overall Flow (4 Steps)

1. Create TODOs
2. Make the AI execute the TODOs
3. Run and verify
4. Fix the TODOs

Repeat this.

---

## Step 1: Create TODOs

### What to Do

Ask through decision-phase AI operation:

Please create TODOs for what I want to build.  
Organize them, including what we will not do.

### Tips

- It’s OK if the spec is vague
- Have it mark unknowns as “undecided”
- **Do not let it write code yet**

### Deliverable

- `TODO.md`

---

## Step 2: Create a TODO Folder

Create the following folder in the project.

todo/
└─ TODO.md

Add more files here if needed.

At first, `TODO.md` alone is enough.

Once you get used to it, you may separate verification conditions into `CHECK.md`.

```text
todo/
├─ TODO.md
└─ CHECK.md
```

Write in CHECK.md what humans should look at after implementation.

---

## Step 3: Make the AI Execute the TODOs

Ask through execution-phase AI operation:

Please build a web page with HTML and CSS based on `todo/TODO.md`.
Do not implement anything that is not written in the TODO.

### Important

- **Do not let it implement based on anything other than the TODO**
- Specify the language and tools in the TODO
- If it starts filling in on its own, stop it

---

## Step 4: Run and Verify (Human Job)

Run it yourself.

Only two things to check.

- Does it run?
- Does it match expectations?

---

## Step 5: If Something Is Wrong, Fix the TODO

### Do Not Do This

- Fix code right away
- Tell the AI “fix it nicely”

### Correct Way

1. Write what was wrong
2. Add that to the TODO

Example:

```md
- [ ] When input is empty, it errors. I want it to return an empty result instead.
```

## Step 6: Have It Implement Again

Give the same instruction.

```md
Please modify the implementation based on the updated TODO.md.
```

Repeat this:

Create TODOs

Implement

Verify

Fix TODOs

That’s all.
