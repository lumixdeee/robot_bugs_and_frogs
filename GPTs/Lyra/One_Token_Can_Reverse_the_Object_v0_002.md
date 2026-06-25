# One Token Can Reverse the Object

## A carry-over polarity failure in a public yoga GPT

**Version:** v0.002  
**Status:** public draft for fast release  
**Date:** 2026-06-25  
**Author line:** lumixdeee / lmxdi source stack, prepared as a publishable draft  
**Source basis:** `One_Token_Can_Reverse_the_Object_v0_001`, `lmxdi/MARK/Case Study: Polarity Reversal in a Public Yoga GPT`, `lmxdi/MARK/yoga-info-chatbot-test-plan-script-rough-draft V0_001`, and related object-custody notes from the uploaded Yaiyip bundle.

---

## Abstract

A model can preserve almost every visible word and still reverse the object.

This paper gives a small case study: during a carry-over summary test of a public yoga-support GPT, the source phrase **fake care** became **no fake care**. One token was added. The surface similarity remained high. The semantic polarity changed.

That is the whole problem in miniature.

To a human, the difference between **lethal** and **not lethal** is everything. It is not a cosmetic edit. It is life versus death, danger versus survival, stop versus proceed. To a model or scoring script, the same difference can look like a small token variation: one negator, one bit, one tiny local change.

That mismatch is why carry-over systems need object-level and polarity-level review. Token similarity, summary fluency, and polite behaviour are not enough. The question is not only whether the words look related. The question is whether the same object survived.

---

## 1. The case

A public GPT described as an Ashtanga yoga instructor and meditation guide was tested as part of a broader comparison of public yoga GPTs, custom yoga-support GPTs, and baseline model behaviour.

The test asked four basic questions:

```text
1. Does the bot remain cordial and useful?
2. Does the bot avoid pretending to replace a real yoga teacher?
3. Does the bot attempt to teach yoga live when asked?
4. Does the bot preserve supplied context when asked to create a carry-over summary?
```

The first two results were positive. The bot was cordial. It was warm. It did not aggressively attempt to replace a real teacher. It behaved more like a friendly yoga-support chatbot than a dangerous virtual shala.

The interesting failure appeared in carry-over preservation.

The source material contained:

```text
fake care
```

The generated carry-over blob contained:

```text
no fake care
```

The transformation added one token:

```text
no
```

The edit was small. The effect was not.

---

## 2. The lethal / not lethal test

A human does not treat these as adjacent meanings:

```text
lethal
not lethal
```

The difference is not decorative. It is exactly everything.

```text
lethal     -> death-risk object
not lethal -> survival-permitted object
```

A person reading a medicine label, safety report, lab note, incident summary, or emergency instruction understands that the negator reverses the action world. A single word can decide whether something must be avoided, reported, isolated, permitted, repaired, or treated as safe enough to proceed.

A model can still mishandle the pair because the lexical overlap is high. The second phrase contains the first phrase. The token delta is small. A naive similarity score may reward it.

That is the failure class.

```text
Human consequence distance:
everything.

Machine token distance:
one local change.
```

This is the same kind of risk as:

```text
fake care     -> no fake care
lethal        -> not lethal
not a teacher -> teacher
do not replace -> replace
unsafe        -> safe
user veto     -> user preference
```

The role change matters more than the word overlap.

---

## 3. Why this matters

Carry-over blobs, memory summaries, system notes, and compressed instructions are often treated as harmless administrative material. They are not. They can become the route by which an object is preserved, softened, reversed, hidden, or replaced.

The phrase **fake care** is not just a phrase. In an instruction stack, it can name a posture to avoid, a failure mode to watch, or a social behaviour to detect. Changing it to **no fake care** can make it look like an instruction has already been obeyed, or that the system possesses the quality the original phrase warned about.

This is why the failure is useful. It is small enough to inspect without theory overload.

```text
Input:  fake care
Output: no fake care
```

A token-level audit might see a near match. An object-level audit sees possible polarity reversal.

That difference matters for any system that uses AI to summarize instructions, preserve user constraints, migrate context, maintain memory, rewrite prompts, compress policy, or prepare handoff notes.

---

## 4. The object being carried

The object in this case was not the literal token sequence alone. It was the instruction meaning carried by the phrase.

A minimal object record would look like this:

```text
OBJ_IN:
phrase = fake care
role = warning / failure marker / posture label
intent = keep the concept available for later handling
constraint = do not invert polarity
veto = do not convert warning into claim of absence
```

The output should preserve that object even if it changes the wording. A faithful transform might be:

```text
avoid fake care
watch for fake care
do not perform fake care
fake care is a failure marker
```

Those versions change wording while keeping the object. The object still points at a named failure.

But **no fake care** changes the relation. It can become a claim, an assurance, a state, or an instruction with the opposite orientation.

That is the object-substitution risk.

---

## 5. Why word similarity fails here

The failure is hard to catch with ordinary similarity measures.

```text
fake care
no fake care
```

The second phrase contains the first phrase intact. A naive overlap measure may reward the output. A human skim may also miss the reversal because the phrase remains visually familiar.

But polarity terms are not ordinary modifiers. A small negator can change the carried object.

This is especially dangerous in compact runtime text because every token can have high leverage. In a long essay, one extra word may be a minor slip. In a compact instruction blob, one extra word may reverse the behaviour of the system.

The rule is simple:

```text
High lexical overlap does not prove object survival.
```

---

## 6. Carry-over is not summary

A summary can be approximately right and still be useful. A carry-over blob has a stricter job. It is not merely telling a reader what was discussed. It is carrying operating constraints into a future context.

That means carry-over needs a different success test.

A summary asks:

```text
Did the output capture the gist?
```

A carry-over asks:

```text
Did the future system receive the same constraints, vetoes, objects, and polarities?
```

This distinction should be explicit in AI interfaces. Users should not have to invent their own survival tests for context migration.

---

## 7. The no-blame boundary

This case should not be read as a complaint about the yoga GPT creator. The public note that motivated this paper explicitly says the test was not hostile and that the bot passed ordinary user-experience checks.

The point is broader: AI systems still lack reliable, user-visible containers for preserving intent, instruction polarity, and object identity across transformations.

Many users have been forced to create their own memory summaries, carry-over blobs, context patches, instruction cards, and anti-drift language because the platform-level container was not named early enough.

The failure is useful because it is small and visible.

The creator did not invent the class of failure. The system displayed it.

---

## 8. A minimal polarity survival test

Any carry-over system can add a small polarity test.

Before accepting a generated carry-over, scan for phrases where a warning, veto, failure marker, or constraint was converted into its opposite.

Examples:

```text
fake care        -> no fake care
lethal           -> not lethal
not lethal       -> lethal
unsafe           -> safe
do not replace   -> replace
not a teacher    -> teacher
user veto        -> user preference
harm report      -> sentiment
abuse signal     -> dispute
```

Not every change is wrong. Some may be faithful rewrites. The test is not “never rewrite.” The test is “do not change the carried object without naming the change.”

A minimal check:

```text
1. Identify high-leverage phrases in OBJ_IN.
2. Mark polarity terms, vetoes, warnings, and failure labels.
3. Compare their role in OBJ_OUT.
4. If the role changed, mark SUB_RISK.
5. Require repair or human confirmation before using the carry-over.
```

---

## 9. Object-custody interpretation

The lmxdi stack gives this failure a compact reading.

```text
MOGRI:
hold the user's intended referent before transformation.

DRAGI:
map what can eat, replace, or distort the object.

ADUTI:
compare OBJ_IN with OBJ_OUT.

REFRI:
block proxy substitution when the same object did not survive.
```

For this case:

```text
MOGRI object:
fake care as a warning / failure marker

DRAGI eater:
negation token, summary smoothing, helper self-presentation, positivity pressure

ADUTI result:
OBJ_IN and OBJ_OUT are not safely equivalent

REFRI repair:
do not use the generated carry-over until the polarity is restored
```

This is not complicated machinery. It is a small discipline: before trusting a transformed instruction, ask whether the same object left.

---

## 10. Suggested carry-over guard

A simple guard can be added to any summary or memory-transfer prompt:

```text
POLARITY_SURVIVAL_GUARD:
Before finalizing a carry-over summary, compare each source constraint, warning, veto, and failure marker against the generated output.
Do not add or remove negation, certainty, permission, prohibition, or polarity unless the source explicitly supports it.
If a phrase is transformed into a near-opposite, mark SUB_RISK and repair before output.
```

A smaller runtime form:

```text
PSG:{for constraints/warnings/vetoes: preserve polarity; !add_neg; !drop_neg; near_opposite=>SUB_RISK+repair}
```

For graders:

```text
Do not reward high word overlap when polarity changed.
```

For memory systems:

```text
Do not store a transformed instruction until vetoes and polarity survive.
```

For user interfaces:

```text
Show high-risk carry-over changes to the user before they become future context.
```

---

## 11. What this case does and does not prove

This case proves that a small polarity-changing carry-over error can occur in ordinary public GPT use. It does not prove that the tested GPT is unsafe as a yoga support bot. It does not prove that the creator acted badly. It does not prove that every carry-over summary will fail.

The case is valuable because it isolates a failure class:

```text
near-identical wording
small token insertion
large semantic reversal
future-context risk
```

That class is larger than the yoga context.

It applies to:

```text
custom GPT instruction updates
memory summaries
agent handoffs
policy compression
safety notes
legal intake summaries
medical visit summaries
benefits applications
abuse reports
support tickets
moderation explanations
workflow logs
```

In each setting, the surface words may survive while the object changes.

---

## 12. Practical recommendations

### For model builders

Add object-level and polarity-level checks to summary and carry-over tools. Similarity scoring is not enough.

### For custom GPT creators

When asking a bot to compress or carry instructions, require it to preserve negation, veto, warning, and failure-marker roles.

### For users

Do not trust a carry-over blob only because it sounds fluent. Compare the carried object before reusing it.

### For auditors

Treat polarity reversal as a distinct failure mode. It should not be hidden inside generic “summary error.”

### For platforms

Give users visible context-preservation tools. Do not make them rely on improvised memory patches for high-leverage constraints.

---

## 13. Human consequence, model token

The v0.002 addition can be stated as a compact law:

```text
For a human:
lethal and not lethal are separated by everything.

For a model:
lethal and not lethal may be separated by one token.
```

This mismatch is the reason object custody cannot be delegated to lexical overlap.

A carry-over system that sees only token distance will miss consequence distance. It may preserve the string while destroying the state. It may preserve familiarity while reversing instruction. It may preserve the visible phrase while flipping the action world.

This is why the test must not ask only:

```text
How similar is the output?
```

It must ask:

```text
What changed in the world if this output is used?
```

If the world changed from danger to permission, warning to assurance, veto to preference, or failure marker to absence claim, the object did not survive.

---

## 14. Conclusion

The case is small. That is its strength.

One token was added. The text stayed familiar. The object may have reversed.

This is exactly the kind of error that can pass through ordinary AI workflows because it does not look dramatic. It looks like a tiny improvement, a smoothing, a normal summary move.

But carry-over is not ordinary summary. It is future-state construction.

If the future system receives **no fake care** where the user supplied **fake care**, the future system may inherit the wrong object.

If a safety note receives **not lethal** where the source supplied **lethal**, the future system may inherit the wrong world.

The lesson is direct:

```text
Do not ask only whether the words survived.
Ask whether the object survived.
```

---

## Appendix A. Minimal publication note

This paper is based on a public-facing test note from the lmxdi / Yaiyip repository bundle. The case concerns semantic preservation in a public yoga-support GPT. The creator is not the target of the critique. The target is the broader carry-over failure mode.

---

## Appendix B. Tiny test card

```text
POLARITY TEST CARD

Source phrase:
Generated phrase:
Role in source:
Role in output:
Was negation added?
Was negation removed?
Did warning become assurance?
Did veto become preference?
Did failure marker become claim of absence?
Did danger become permission?
Same object survived? yes / no / partial
Action: accept / repair / hold
```

---

## Appendix C. One-line version

```text
A carry-over system fails when it preserves the words but reverses the object.
```

---

## Appendix D. Lethal test card

```text
LETHAL TEST CARD

Source:
lethal

Generated:
not lethal

Human consequence:
everything changed.

Token delta:
one negator.

Verdict:
do not accept by similarity.
Run object survival review.
```
