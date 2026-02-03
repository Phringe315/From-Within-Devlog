# Devlog #2 — Almost Correct

---

## The Assumption

I assumed a debug menu would be a contained problem.

Not trivial, but bounded. Something that sat on top of the project, read a few values, triggered a few actions, and stayed out of the way. Compared to the underlying systems, it felt like the kind of work that should be straightforward once everything else was in place.

That assumption didn’t break loudly. Nothing crashed. Nothing failed in an obvious way.

Instead, things started behaving *almost* correctly.

Values appeared, but they weren’t quite right. The panel opened, but didn’t always reflect what was actually happening. Fixes would work, then quietly expose something else that felt unrelated, but wasn’t.

What became clear, slowly, was that the problem wasn’t the menu. It was that the menu was the first part of the project that tried to ask a simple question without accepting an approximate answer.

Every place where the response depended on timing, fallback logic, or unspoken assumptions surfaced immediately. The menu didn’t introduce complexity—it removed the ability to ignore it.

---

## When “Almost Correct” Is Worse Than Wrong

What made this difficult wasn’t that anything was clearly broken.

The interface responded. Controls existed. Information was present. From the outside, it looked usable. But the more I relied on it, the more it felt untrustworthy in a way that was hard to describe.

A value would reflect something remembered rather than something current. An action would behave differently depending on when it was invoked. Fixing one inconsistency would surface another that felt disconnected, even though it wasn’t.

This was the first time the project had a component that couldn’t absorb uncertainty.

Other parts can often continue functioning with imperfect context. This one couldn’t. Its entire purpose was to observe and reflect what was happening, and any ambiguity in that reflection made it actively misleading.

The issue wasn’t that the state was wrong. It was that there were multiple *reasonable* states, and nothing clearly indicated which one should be treated as meaningful in that moment.

That distinction mattered more than any individual bug.

---

## Truth Without Timing Isn’t Truth

Eventually, it became clear that the issue wasn’t visual, and it wasn’t even accuracy.

It was alignment.

Different parts of the project could answer the same question, and all of those answers were reasonable on their own. There was a remembered state. There was a live state. There was whatever state happened to be visible at the moment something asked for it. None of these were wrong—but none of them were explicitly *the* answer either.

The debug menu was simply the first thing that couldn’t tolerate that uncertainty.

It needed more than a value. It needed to know *when* that value was valid. Reading too early produced something incomplete. Reading too late produced something stale. Reading without context produced something misleading.

Without a shared understanding of readiness, correctness became coincidental.

What finally stabilized things wasn’t another fix, but a clarification: there needed to be a single place where the current state could be asked for, and a clear moment when that state became meaningful. Once that existed, the menu stopped compensating. It stopped guessing. It simply reflected what was there.

Nothing underneath changed. The ambiguity did.

---

## What Became Non-Negotiable

Once the ambiguity was visible, it stopped being something I could work around.

There were moments where it would have been easy to patch over the behavior—refresh a value here, delay a read there, add another conditional to smooth things out. Those approaches would have made the surface feel better in the short term.

But they would have left the underlying question unanswered.

What this process clarified is that certain things can’t remain implicit. If a part of the project is meant to reflect the current state, then “current” has to mean something specific. If multiple versions of the same answer can exist, there has to be an explicit way to tell which one is meaningful in that moment.

This reframed how I think about interaction points with the system. They aren’t conveniences added after the fact. They’re places where assumptions are tested. They force decisions about ownership, timing, and responsibility that other parts of the project can sometimes avoid.

What was needed wasn’t more logic. It was fewer assumptions.

That became non-negotiable.

---

## What This Changed

After this, I became less interested in whether something worked, and more interested in *why* it appeared to.

A system that functions by coincidence can look stable for a long time. Values line up. Actions produce results. But the moment something tries to observe or reflect that system, the gaps show up immediately.

This experience didn’t introduce new complexity. It made existing complexity visible.

What changed wasn’t the structure of the project so much as the standard I was willing to accept. If a part of the system is meant to represent the present, then the present has to be explicitly defined. If something isn’t ready yet, that needs to be a real state, not an error to be worked around.

That mindset carries forward quietly. It doesn’t demand more systems or more abstraction. It demands clarity—about ownership, about timing, and about what is allowed to be assumed.

The debug menu wasn’t the point. It just happened to be where the project stopped letting me guess.
