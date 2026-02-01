# Devlog #[NN] — [Short, Precise Title]

**Date:** YYYY-MM-DD

---

## Context

Briefly describe what part of the project this entry relates to and why it exists *now*.

Focus on:
- what prompted this work
- what problem or tension you were addressing
- what assumptions were in play before starting

Avoid describing implementation details.

---

## Problem Statement

State the problem as clearly and narrowly as possible.

Good examples:
- “The system behaved correctly but felt unpredictable.”
- “Early versions escalated too quickly and removed player agency.”
- “The design allowed edge cases that undermined long-term stability.”

This section should make it obvious *why* the problem mattered.

---

## Constraints

List the constraints that shaped the solution.

These should be **non-negotiables**, not preferences.

Examples:
- Must remain deterministic
- Must not mutate baseline world data
- Must be bounded and replay-safe
- Must preserve player legibility
- Must survive long-term accumulation

This section is critical for preventing future drift.

---

## Exploration & Failures

Document approaches that were tried and discarded.

Focus on:
- what was attempted
- what failed
- why it failed conceptually (not mechanically)

This is where most of the value lives.

Avoid:
- step-by-step logic
- formulas
- code references

---

## Resolution (Current Direction)

Describe the direction you settled on *at the level of intent*.

Answer:
- what changed in the design
- what tradeoffs were accepted
- what risks remain

Do **not** describe exact mechanics or algorithms.

---

## Open Questions

List unresolved questions or things intentionally left open.

Examples:
- How this scales later
- Where pressure might become too dominant
- What signals might be required for readability

This section keeps future work honest.

---

## Notes to Future Me

Optional but recommended.

Use this to:
- warn against known pitfalls
- explain why a tempting alternative was rejected
- record “don’t forget why this exists”

This is not for readers — it’s for continuity.

---

*This entry reflects design intent at the time of writing.  
Specific implementations may change or remain private.*
