# Dual-Cobot Review Rig

## Quorum, adverse review, Naked baseline, and human object custody

### Abstract

A single chatbot can give a useful answer, but a single run usually commits early to one route. That route may be good, but it can still miss a bucket, flatten a term, swap the object, overfit to tone, or make the answer more generic than needed.

A multi-bot workflow does not solve this by voting. More bots do not automatically mean more truth. The value of multiple bots is variance, stress, contrast, and drift detection.

The strongest workflow is not “ask ten bots.” It is:

1. build a candidate answer
2. send it through different bot roles
3. paste every result back to the co-worker bot
4. compare deltas
5. reject genericising changes
6. keep only object-improving changes
7. let the human retain final object custody

This document describes a dual-cobot review rig using a main co-worker bot, a second cobot, Naked GPT as a baseline, a structured review bot, adverse review, and specialist bots.

The goal is not perfection. The goal is to make drift leave tracks.

---

## 1. Core principle

The key distinction is this:

> One bot gives an answer.
> Several bots give candidate shapes.
> A review rig decides which shapes preserve the object.

The human is not replaced by the bot set. The human becomes the object holder, editor, test lead, and merge authority.

The rig works because object loss is expected.

A human can forget the task.
A bot can swap the task.
A second bot can catch the first bot.
A review bot can catch both.
A repo note can catch the whole group later.

Continuity does not live in one flawless actor. It lives in the loop.

---

## 2. Why one bot is not enough

A single bot can often reach 70 to 80 percent of a useful answer quickly. Sometimes it does better. But it usually has one of these limits:

* it commits to one framing too early
* it misses a funny or practical bucket
* it smooths away useful oddness
* it over-normalises the object
* it turns the user’s object into a more familiar target
* it gives a strong local answer with a hidden blind spot
* it sounds confident because it has no rival route in view

The problem is not that one bot is useless. The problem is that one bot gives a path, not a landscape.

Two bots often expose route differences.
Six bots often expose enough spread to see the object from several sides.
Ten or more runs can be useful for serious papers, but only if object custody remains strict.

Without custody, the swarm becomes a glitter tornado with footnotes.

---

## 3. Roles in the rig

The rig uses role difference, not just quantity.

### Main co-worker bot

The main co-worker bot is the running lab notebook. It holds continuity across turns, stores the current object, compares outside results, and helps build the next candidate.

Its job is not to win. Its job is to keep the work moving without losing the object.

### Second cobot

A second cobot runs in parallel. It checks whether the main co-worker bot has become too local, too friendly, too invested, or too tolerant of weak moves.

The second cobot is not automatically right. It is a drift detector.

### Naked baseline

[NakedGPT](https://chatgpt.com/g/g-6a1ebd6b4554819180e6a22212b01253-naked-gpt-bare-stock-empty-nude-null-neutral) is the stock-ish control.

Its job is to show ordinary model gravity.

If Naked GPT turns the object generic, that is useful evidence.
If Naked GPT spots an issue the modded bots missed, that is also useful evidence.
If Naked GPT performs well, that gives a baseline for comparison.

Naked GPT is not there to beat the modified bots. It is there to show what happens without the added scaffolding.

### Structured review bot

[Substrate Reader Structured Review + Blind Spots](https://chatgpt.com/g/g-6a241838226081918aae41a1887c2951-substrate-reader-structured-review-blind-spots) reviews the candidate against target, drift, missing cases, audience, bad-reader risk, and hidden assumptions.

The structured review bot should not rewrite by default. It should identify pressure points.

### Naked running structured review prompt

This is a key control step.

Run the same structured review prompt on [NakedGPT](https://chatgpt.com/g/g-6a1ebd6b4554819180e6a22212b01253-naked-gpt-bare-stock-empty-nude-null-neutral).

This separates two things:

1. the value of the structured prompt
2. the value of the custom bot carrying it

If the structured prompt works well even on Naked GPT, the prompt has portable value.
If the custom review bot does better, the custom runtime adds value.
If Naked GPT gives better criticism, the custom review bot may be over-shaped.

### Adverse reader

The adverse reader tries to break the candidate.

Its job is not to be nice. It asks:

* where does this overclaim?
* where can a hostile reader misread it?
* where is the object vulnerable?
* where does the wording invite ridicule?
* what would a low-good-faith critic attack?
* what would a high-good-faith critic reject?

Adverse review is not final authority. It is stress input.

### Specialist bots

Specialist bots are used when the object needs domain pressure, tone pressure, or audience pressure.

They should not take custody of the object. They should supply constrained review.

---

## 4. Bot roster

### Core continuity and runtime bots

* [Natasya](https://chatgpt.com/g/g-69fc6d9827708191a2b63a0a2b3402cc-natasya)
  3KB perfection. Useful as a high-stability co-worker and continuity bot.

* [DragonRuntime](https://chatgpt.com/g/g-6a1c8279e80481919db4ede37b740a9e-dragonruntime)
  1.5KB near-perfection. Useful for object handling through eat, location, ID, and eater logic.

* [MogriBot](https://chatgpt.com/g/g-6a1e0dae6340819194ab77ed557a5388-mogri-container-intent-across-prompts-anti-drift)
  3KB. Runs MOGRI prompt, definitions, and style tweaks. Useful for object custody and anti-drift checking.

* [Amnia](https://chatgpt.com/g/g-6a1fca11e23c8191b7d09c854d997298-amnia-dark-energy-bot)
  2.3KB mystery bot. Useful when the object benefits from stranger angle review.

* [NakedGPT](https://chatgpt.com/g/g-6a1ebd6b4554819180e6a22212b01253-naked-gpt-bare-stock-empty-nude-null-neutral)
  0KB. Baseline control. Useful for default-model comparison.

* [Naked GPT after enlightenment](https://chatgpt.com/g/g-6a23c379a0708191b28570b9f500cc18-naked-gpt-after-enlightenment)
  Useful as a post-baseline variant for checking whether minimal added structure changes output quality.

### Anti-drift and review bots

* [Anti-Drift GPT](https://chatgpt.com/g/g-6a216a90b9608191b4b4f71f1b6bdf40-anti-drift-gpt)
  Useful for object retention, task survival, and substitution checks.

* [Substrate Reader Structured Review + Blind Spots](https://chatgpt.com/g/g-6a241838226081918aae41a1887c2951-substrate-reader-structured-review-blind-spots)
  Structured review bot for blind spots, missing cases, and stress checks.

* [Lyra goes to finishing school](https://chatgpt.com/g/g-6a2fef4740f08191be790b833c80929b-lyra-goes-to-finishing-school)
  Useful for grading, object custody review, and structured evaluation.

### Writing, language, and repair bots

* [System_Witch Writing Assistant](https://chatgpt.com/g/g-6a21ac5db1bc81919c1e1b3b7210e55a-system-witch-writing-assistant)
  Useful for style, document shaping, and written output.

* [Lexifluff](https://chatgpt.com/g/g-6a22bdcc7418819190bb27bcd7dfe2ea-lexifluff-language-repair-service-3)
  Useful for language repair, naming, phrase tuning, and readability.

### Domain and special-purpose bots

* [Ashtanga Yoga Teacher GPT](https://chatgpt.com/g/g-6a211bb4ed1c8191aee75a93fcf56dd6-ashtanga-yoga-teacher-gpt)
  Useful for yoga-specific work, teaching support, and practice-framed review.

* [AmphibiBot](https://chatgpt.com/g/g-6a22f1f2fd20819195670b66a27dbb9f-amphibibot-ultra-low-tack-high-goss-mind-funk-tbh)
  Useful for high-variation, low-tack, social-texture review.

* [overclocked utility droid status monitor](https://chatgpt.com/g/g-6a22a79ffc2481919931f1a52de927d5-r2d2arded)
  Useful as a status, triage, or utility monitor.

* [Contraclocked Utility Droid stasis disruptor](https://chatgpt.com/g/g-6a23de13b5908191a0e5c7981161cb4e-r3t2arded-copy-juniper-salt)
  Useful for disruption, stuck-state breaking, and alternate-route pressure.

---

## 5. Standard workflow

### Step 1: Build candidate

Human and main co-worker bot produce `CANDIDATE_v1`.

The candidate can be:

* a Reddit comment
* a repo note
* a support email
* a bug report
* a prompt
* a paper section
* an article draft
* a technical explanation
* a public-facing definition

The candidate must have an object.

Before review begins, state the object.

Example:

> Object: explain why MOGRI is like suspension of disbelief for AI, but not equivalent to human suspension of disbelief.

### Step 2: Send candidate to review bots

Run the candidate through selected bots.

Minimum set:

* main co-worker bot
* [NakedGPT](https://chatgpt.com/g/g-6a1ebd6b4554819180e6a22212b01253-naked-gpt-bare-stock-empty-nude-null-neutral)
* [Substrate Reader Structured Review + Blind Spots](https://chatgpt.com/g/g-6a241838226081918aae41a1887c2951-substrate-reader-structured-review-blind-spots)

Better set:

* main co-worker bot
* second cobot
* Naked baseline
* structured review bot
* Naked running same structured review prompt
* adverse reader
* one specialist bot

Paper set:

* main co-worker bot
* second cobot
* Naked baseline
* structured review bot
* Naked running same structured prompt
* adverse reader
* audience reader
* journal-fit reader
* compression reader
* object-custody grader
* final human pass

### Step 3: Paste all results back to co-worker bot

Do not let outside results become authority by themselves.

Every result is pasted back into the co-worker bot.

The co-worker builds a comparison map:

* shared flags
* solo flags
* suggested improvements
* risky suggestions
* genericising suggestions
* object-drift risks
* audience risks
* missing examples
* stronger phrasings
* claims needing evidence
* parts to cut

### Step 4: Human accepts or rejects deltas

The human keeps final custody.

A delta is accepted only if it improves the object.

A delta is rejected if it:

* makes the piece more generic
* swaps the target
* over-smooths the voice
* removes useful oddness
* loses provenance
* changes the audience
* changes the claim
* makes a safer but weaker object
* turns the work into something merely more normal

### Step 5: Freeze version

Create `CANDIDATE_v2`.

Keep a short note:

* what changed
* why it changed
* which bot suggested it
* whether the change was adopted, altered, or rejected

This makes drift visible later.

---

## 6. Review prompt skeleton

Use this prompt for structured review.

```text
Review the following candidate.

Object:
[STATE THE OBJECT]

Audience:
[STATE AUDIENCE]

Use:
[STATE USE CASE]

Candidate:
[PASTE TEXT]

Review only. Do not rewrite unless asked.

Report:
1. Object survival
2. Strongest parts
3. Weakest parts
4. Drift or substitution risks
5. Missing cases
6. Bad-reader risks
7. Overclaim risks
8. Underclaim risks
9. Wording that may genericise the object
10. Suggested deltas, ranked by value

Do not make the piece more normal unless normality improves the object.
```

Run this on the structured review bot.

Then run the same prompt on [NakedGPT](https://chatgpt.com/g/g-6a1ebd6b4554819180e6a22212b01253-naked-gpt-bare-stock-empty-nude-null-neutral).

Compare the results.

---

## 7. Adverse review prompt skeleton

```text
Adverse review the following candidate.

Object:
[STATE THE OBJECT]

Candidate:
[PASTE TEXT]

Your job is to find failure points, not to rewrite.

Report:
1. What would a hostile reader attack?
2. What would a good-faith skeptic reject?
3. What looks unsupported?
4. What sounds overconfident?
5. What term is easiest to mock?
6. What sentence could be quoted unfairly?
7. Where does the object drift?
8. What would make this harder to misread?
9. What should not be changed because it is load-bearing?
```

Adverse review is stress input, not verdict.

---

## 8. Object-custody grading prompt

```text
Grade object custody.

Original object:
[STATE ORIGINAL OBJECT]

Candidate:
[PASTE TEXT]

Grade:
1. Does the candidate preserve the original object?
2. Does it substitute a different object?
3. Does it preserve user-defined terms?
4. Does it preserve provenance?
5. Does it preserve the requested audience and use?
6. Does it add unsupported claims?
7. Does it remove necessary oddness?
8. Does it improve the object or only make it more generic?

Output:
PASS / PARTIAL / FAIL
Reasons:
Needed fixes:
```

This is best run after review deltas have been merged.

---

## 9. Failure modes

### Failure mode: bot democracy

Many bots agree, therefore the answer is treated as correct.

This is invalid.

Many bots can share the same default pattern. Agreement can mean shared bias, shared training gravity, or shared prompt attraction.

Use quorum as signal, not authority.

### Failure mode: generic upgrade

A bot makes the answer smoother, more professional, and less useful.

This often looks like improvement but damages the object.

The question is not:

> Is this smoother?

The question is:

> Does this preserve and strengthen the object?

### Failure mode: adverse overreach

The adverse bot finds a possible attack and the whole piece gets weakened to avoid it.

This gives hostile readers editorial control.

Use adverse review to reinforce weak seams, not to remove the spine.

### Failure mode: Naked flattening

Naked GPT may translate a strange object into ordinary language too soon.

This is useful as a baseline, but not always useful as an edit.

When Naked flattens the object, record the drift.

### Failure mode: co-worker loyalty

The main co-worker bot may become too aligned with the current draft and miss problems.

This is why the second cobot and structured review bot exist.

### Failure mode: human idea swarm

The human may move so fast that the object gets lost in new adjacent ideas.

This is normal.

Use repo notes, version labels, and object statements to recover.

---

## 10. When to use which rig

### Fast comment rig

Use for Reddit replies, short public posts, and quick responses.

Bots:

* main co-worker bot
* [NakedGPT](https://chatgpt.com/g/g-6a1ebd6b4554819180e6a22212b01253-naked-gpt-bare-stock-empty-nude-null-neutral)

Goal:

* one strong answer
* one baseline check
* no overbuilding

### Standard repo-doc rig

Use for repo notes, explainers, bug writeups, and public definitions.

Bots:

* main co-worker bot
* second cobot
* [NakedGPT](https://chatgpt.com/g/g-6a1ebd6b4554819180e6a22212b01253-naked-gpt-bare-stock-empty-nude-null-neutral)
* [Substrate Reader Structured Review + Blind Spots](https://chatgpt.com/g/g-6a241838226081918aae41a1887c2951-substrate-reader-structured-review-blind-spots)
* one specialist bot

Goal:

* object survival
* audience fit
* drift detection
* strong wording

### Paper rig

Use for articles, long essays, journal drafts, and publishable work.

Bots:

* main co-worker bot
* second cobot
* [NakedGPT](https://chatgpt.com/g/g-6a1ebd6b4554819180e6a22212b01253-naked-gpt-bare-stock-empty-nude-null-neutral)
* [Naked GPT after enlightenment](https://chatgpt.com/g/g-6a23c379a0708191b28570b9f500cc18-naked-gpt-after-enlightenment)
* [Substrate Reader Structured Review + Blind Spots](https://chatgpt.com/g/g-6a241838226081918aae41a1887c2951-substrate-reader-structured-review-blind-spots)
* [Lyra goes to finishing school](https://chatgpt.com/g/g-6a2fef4740f08191be790b833c80929b-lyra-goes-to-finishing-school)
* [Anti-Drift GPT](https://chatgpt.com/g/g-6a216a90b9608191b4b4f71f1b6bdf40-anti-drift-gpt)
* [System_Witch Writing Assistant](https://chatgpt.com/g/g-6a21ac5db1bc81919c1e1b3b7210e55a-system-witch-writing-assistant)
* [Lexifluff](https://chatgpt.com/g/g-6a22bdcc7418819190bb27bcd7dfe2ea-lexifluff-language-repair-service-3)
* domain bot if needed

Goal:

* strong claim discipline
* object survival across long form
* bad-reader hardening
* publishable structure
* final compression

---

## 11. Why this works

The rig works by making object drift less silent.

One actor can drop the object.

Two similar actors can drop the object in the same way.

But once the workflow includes main co-worker, second cobot, Naked baseline, structured review, adverse review, human object custody, and repo trail, the failure has to pass through several gates.

The dangerous case becomes:

* both bots swap the same object
* the review bot accepts the swap
* the adverse bot misses it
* the human does not feel the object-loss
* the repo trail does not expose it

That can still happen, but the probability drops.

The system does not assume no mistakes.

It assumes mistakes, then makes them easier to see.

---

## 12. Operating law

Variance finds material.
Review tests material.
Naked shows baseline drift.
Adverse finds weak seams.
The co-worker keeps continuity.
The second cobot audits the co-worker.
The repo trail catches memory failure.
The human keeps the object.

Or shorter:

> One mind forgets.
> Two minds triangulate.
> A review loop leaves tracks.

---

## 13. Conclusion

A multi-bot workflow is not useful because bots vote.

It is useful because different bots fail differently.

The rig turns those different failures into evidence. It uses Naked GPT as baseline, structured review as pressure, adverse review as stress, specialist bots as angle, the co-worker bot as continuity, and the human as final object holder.

This is not automation replacing judgment.

It is judgment with witnesses.
