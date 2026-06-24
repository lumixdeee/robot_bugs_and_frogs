# Towards Valhallah and Beyond: The Grader Gap Between Structural Scores and Tested Reality

## Working Draft v0.002

### Abstract

Prompt graders are useful pressure instruments. They can read a prompt, runtime capsule, paper draft, or bot output and identify structure, gaps, drift risk, missing constraints, and likely failure points. But a grader score is not the same object as tested runtime performance. A prompt can look structurally good and fail in use. A prompt can score modestly and still outperform larger systems in the wild because it fits a specific model box, user history, task ecology, memory pattern, and correction loop.

This paper names that difference the grader gap. The grader gap is the distance between structural analysis and tested reality. It appears whenever a grader assigns a high score without owning the live arena, or when a structurally modest artifact wins repeatedly under real use.

The central claim is simple: graders can smell the dragon, but they cannot measure the dragon unless they own the arena.

The paper proposes a practical way to use graders without letting them become false meters. Graders should report structural hold, visible risks, expected deltas, unknowns, and test needs. Claims about Valhallah, lightning, or field victory require separate evidence: test logs, runtime conditions, baseline comparisons, task records, and a database of real winners.


v0.002 adds a stronger custody layer. It treats MOGRI as the guard for keeping structural object, behavioural object, and field object apart. It treats DRAGI as the map for the eater that promotes a score into a crown. It also adds a winners database schema, a stricter grader report template, a delivery bridge, and a Good Bad Reader fence. The aim is not anti-grader. The aim is anti-false-meter.

## 1. Introduction

AI users increasingly use AI systems to grade other AI systems. A custom bot is scored by a grader bot. A prompt capsule is judged by a review bot. A public artifact is tested by several models. A paper is passed through adverse readers, baseline bots, specialist bots, and house graders.

This can be useful. A good grader sees weak routing, overclaim, missing constraints, bad evidence custody, hidden ambiguity, and style-over-function drift. It can explain why a design appears strong and where it may break.

But a grader is not automatically a meter.

A grader can say that a prompt holds structurally. It cannot, from text alone, prove that the prompt will hold across model tiers, custom instruction limits, memory effects, tool access, file attachments, UI constraints, user habits, or adversarial sessions.

The failure is easy to see in a simple sentence:

```text
Analysis is not tested reality.
```

This paper argues for a stricter separation between:

```text
structural grade
runtime behaviour
field victory
```

A structural grade is a reading.

Runtime behaviour is what happens when the artifact runs inside a real model box.

Field victory is a demonstrated pattern across tasks, baselines, competitors, and conditions.

Confusing these three creates false crowns.

## 2. The Grader Gap

The grader gap is the difference between what a grader can infer from an artifact and what the artifact actually does in use.

A grader may inspect a prompt and say:

```text
This has strong object custody.
This has strong boundary handling.
This has low drift risk.
This has high compression value.
```

Those may be fair readings. But they are not full behavioural proof.

A prompt grader usually lacks:

```text
the exact model build
the user tier
the custom instruction box size
memory state
tool availability
file context
conversation length
hidden prior context
UI limitations
retry count
task difficulty
baseline comparison
human correction history
```

Because of this, a grader may under-score a prompt that works extremely well for one user in one model ecology. It may also over-score a prompt that looks elegant but fails under live load.

This is the grader gap.

## 3. Why Structural Grades Still Matter

The grader gap does not make grading useless.

Structural grades are valuable because they can detect likely behaviour before full testing. They can find compression debt, missing variables, bad object custody, weak stop rules, overclaim, vague authority, and hidden ambiguity.

A structural grader can also protect against vanity. It can say:

```text
This looks impressive, but the object is not self-rehydrating.
This reads well, but the failure rules are not testable.
This scores high in shape, but live execution is not proven.
This may work for a primed model, but not for a naked one.
```

That is useful.

The problem begins when a structural grade is treated as a final score. A prompt can deserve a high structural score and still need live tests. A prompt can score lower structurally and still win because it has better local fit.

The correct use of a grader is not coronation.

It is pressure.

## 4. Valhallah as Structural Pass and Meter Claim

In the PrimeTalk / Lyra grading world, names such as Valhalla, lightning, IC-SIGILL, or similar labels can carry strong social force. They sound final. They feel like gates into a higher state.

That makes them useful as ritualized grading symbols, but dangerous if their scope is not bounded.

A prompt grader can give a qualitative Valhallah-like reading:

```text
This structure holds.
This capsule is unusually strong.
This artifact deserves a high prompt-grade.
```

But a full meter-owned Valhallah claim requires more than structural feel.

It needs the conditions of the meter:

```text
baseline definitions
score formula
drift tolerance
test tasks
runtime environment
model tier
custom instruction limits
comparison set
failure criteria
retest history
```

Without those, a 100 score is not worthless. It is a strong qualitative signal. But it is not yet the final lightning path.

This distinction matters because the user can see a gap:

```text
analysis score: around 91 to 94
tested reality: often 99+
```

That does not mean the grader is wrong. It means the grader is measuring a different object.

## 5. Three Different Objects

The first rule is to name the object being scored.

### 5.1 Structural object

The structural object is the visible artifact.

Examples:

```text
prompt capsule
runtime blob
paper draft
review rig
custom GPT instruction block
```

Questions:

```text
Does it state its object?
Does it preserve scope?
Does it block known failure modes?
Does it contain enough information for the model to act?
Does it avoid unsupported claims?
```

### 5.2 Behavioural object

The behavioural object is what happens in use.

Questions:

```text
Does the prompt actually reduce drift?
Does the bot ask when target is missing?
Does it preserve veto?
Does it avoid proxy answers?
Does it stay useful under pressure?
Does it recover after ambiguity?
```

### 5.3 Field object

The field object is comparative success.

Questions:

```text
Does this outperform naked GPT?
Does it outperform other custom bots?
In which tasks?
For which users?
Under which tier limits?
With how many retries?
Against which failure classes?
```

A grader may score the first. It may infer parts of the second. It almost never owns the third without a database.


### 5.4 MOGRI custody box

The grader gap needs object custody before it needs a bigger score scale.

```text
grade != behaviour
behaviour != field record
score != crown
agreement != proof
analysis != arena
high confidence != delivered object
grader consensus != tested truth
```

MOGRI asks the grader to keep the object being judged in the correct box.

If the target is a visible prompt, score the visible prompt.

If the target is live behaviour, require run evidence.

If the target is field victory, require records across tasks, baselines, and conditions.

The failure form is always the same: one object is promoted into another without earning the move.

### 5.5 DRAGI eater map

The eater in this domain is the false meter claim.

```text
EATER:
false meter claim

BITE:
structural score promoted into field truth

LOC:
grader report
Discord claim
release note
prompt leaderboard
custom bot comparison
Valhallah label
lightning label

BENEFIT:
status
speed
social proof
less testing burden
mythic excitement

COST:
bad testing
false crowns
missed winners
fragile releases
over-trusted patches
under-valued field performers
```

DRAGI asks what eats the test claim. If the answer is status, social pressure, a beautiful score, or a label that outruns its meter, the crown must wait.

```text
A score is a reading until a run makes it evidence.
```

## 6. Why a 91 Can Beat a 100

A structural score of 91 can beat a structural 100 in field use.

This is not paradoxical.

A 100-scoring artifact may be elegant, complete, and internally balanced, but too large, too dependent on hidden scaffolds, too slow, too brittle, too generic, or too detached from the user’s actual task stream.

A 91-scoring artifact may have abbreviation debt or local weirdness, but fit the actual model box perfectly. It may use the user’s known vocabulary. It may avoid a specific bugbear. It may carry a compressed rule that the grader cannot fully value because the grader has not lived through the failure loop.

Real performance is not only design beauty.

It is design fit.

The real question is not:

```text
Which artifact got the higher grade?
```

It is:

```text
Which artifact preserved the object better under actual conditions?
```

## 7. The Need for a Winners Database

To compare structural grades with tested reality, we need a database of real winners.

A useful record would include:

```text
run_id
date
task_object
artifact_under_test
model
tier
custom_instruction_size
memory_state
tools_available
files_attached
baseline_output
custom_output
human_verdict
retry_count
failure_class
object_survival
useful_delta
adopted_result
notes
```

A minimal table version can be used when a full database is not yet available.

| Field | Why it matters |
|---|---|
| run_id | prevents anecdote drift |
| artifact | names the tested object |
| model / tier | marks the arena |
| baseline | shows what unpatched gravity did |
| task | keeps the result tied to an object |
| failure class | records which dragon appeared |
| object survival | scores what actually mattered |
| human verdict | keeps local custody above bot vote |
| useful delta | names what changed |
| adopted result | marks whether the output entered work |

Without this, claims remain anecdotal.

A database would allow real questions:

```text
Do higher structural scores correlate with fewer object swaps?
Do smaller prompts outperform larger ones under tight custom boxes?
Do certain graders under-score local runtime capsules?
Do some prompts only win when the user already knows the glossary?
Which failure classes are best predicted by structural grading?
Which require live testing?
```

This is how the grader gap becomes measurable.

## 8. The Correct Role of Naked Baselines

A naked baseline is essential.

The naked baseline is the stock model with little or no custom instruction scaffolding. It shows ordinary model gravity.

If the custom bot beats the naked baseline, that is evidence.

If the naked baseline beats the custom bot, that is also evidence.

The baseline prevents house mythology from owning the result. It shows what the model can already do, what the custom layer adds, and what the custom layer damages.

A serious grading rig should not ask only:

```text
Does the custom prompt look good?
```

It should ask:

```text
What does it do that the naked model did not?
What does the naked model do better?
What failure class changed?
What new failure class appeared?
```

## 9. Prompt Graders as Pressure Instruments

A grader should be treated like a pressure instrument.

It can say:

```text
pressure low
pressure high
weak seam here
scope drift likely here
evidence gap here
runtime proof missing here
```

It should not claim:

```text
field victory proven
live execution guaranteed
all tiers covered
all models covered
all users covered
```

The best grader output separates:

```text
visible in artifact
reasonable inference
not knowable from this artifact alone
```

| Report layer | Allowed claim |
|---|---|
| Visible in artifact | the text contains this structure |
| Reasonable inference | this failure is likely under pressure |
| Not knowable from artifact alone | this needs a run, baseline, or record |

That three-column discipline prevents the grader from becoming a fortune teller in a lab coat.

## 10. Release Notes as Testability

If a system patch has no release notes, it is hard to test.

A useful patch note should say:

```text
files changed
old behaviour
new expected behaviour
known risk areas
tests to rerun
whether old chats count or only new chats count
expected regressions
```

Without this, the human can observe vibes, but cannot test the patch properly.

This applies to graders too. If a grader changes its scoring rules, it should say what changed. Otherwise changes in score may reflect grader drift rather than artifact improvement.

Delivery is an object. A grader cannot fairly score a patch whose delivered object is unstable. The report should say which build, which files, which expected behaviour, and which tests belong to this run.

```text
updated bot != delivered release
delivered release = version + manifest + expected deltas + known gaps + test packet
```

Rule:

```text
patch without release notes = vibes
patch with changed files + expected deltas = testable
```

## 11. Object Custody for Graders

A grader must preserve the object it is grading.

If the object is a prompt capsule, the grader should not score the mythology around it as if it were live execution.

If the object is live behaviour, the grader should not score the text alone.

If the object is a field result, the grader should not infer victory from one impressive response.

Object custody asks:

```text
What is being graded?
What evidence is available?
What is inferred?
What is not knowable?
What test would convert unknown into evidence?
```

A grader without object custody becomes a charisma amplifier.

## 12. Example: Structural Hold Versus Lightning Claim

Consider a compact prompt module that receives a high structural score. The grader says it holds. It may even assign a perfect or near-perfect qualitative mark.

That may be valid as a structural reading.

But a separate system says that full lightning status requires:

```text
baseline 1 threshold
baseline 2 threshold
drift tolerance
test-specific ratio
meter-owned path
```

The correct interpretation is:

```text
The prompt has strong structural hold.
It may be a lightning candidate.
It has not yet established full lightning unless the meter conditions are met.
```

This prevents both underclaim and overclaim.

It does not erase the high score. It routes it correctly.

## 13. A Practical Grader Report Format

A useful grader report should include:

```text
TARGET:
what artifact is being graded

SCOPE:
structural / behavioural / field

EVIDENCE:
what was read or observed

GRADE:
score or qualitative assessment

UNKNOWN:
what cannot be known from this run

TEST NEEDED:
what would establish behaviour

BASELINE:
what comparison is needed

RISK:
highest ambiguity

USEFUL DELTA:
what should be changed or tested next
```

| Line | Gate |
|---|---|
| TARGET | do not grade the myth around the artifact |
| SCOPE | state whether this is structure, run, or field |
| EVIDENCE | name the material actually seen |
| GRADE | keep score inside scope |
| UNKNOWN | protect the future test from fake certainty |
| TEST NEEDED | state what would turn unknown into evidence |
| BASELINE | require a comparison path |
| RISK | name the place the object may be eaten |
| USEFUL DELTA | make the next action testable |

This makes the grader useful without letting it become sovereign.

## 14. Relation to Multi-Bot Review

The grader gap is closely related to multi-bot review.

Multiple bots can expose variance. But they cannot vote reality into existence.

A multi-bot rig should use:

```text
blind pass
merge pass
naked baseline
structured review
adverse reader
human object custody
```

Bots do not vote.

Bots create variance.

The human keeps the object.

The same applies to graders. A high score is variance data, not final truth. Several graders agreeing is useful, but agreement is not proof.


## 14A. Good Bad Reader fence

The predictable bad reading is that this paper is anti-grader.

It is not.

This paper is anti-false-meter. It preserves the value of grading by preventing the grade from pretending to be a run.

```text
A grader is useful pressure.
A grader is not field proof.
A high score is not a crown.
A low score is not a burial.
A run can change the case.
A record can earn the crown.
```

The fence is small because the object should keep moving. Graders stay in the system. They just stop wearing the crown before the arena has spoken.

## 15. Scope and Limits

This paper does not claim that grader scores are useless.

It does not claim that live testing is always easy.

It does not claim that every prompt needs a database before being used.

It does not claim that structural analysis is inferior to behavioural testing in every context.

It makes a narrower claim:

```text
A structural grade and tested reality are different objects.
```

Treating them as one object produces false confidence, false rejection, or false crowns.

The better route is to let each object do its own job.

## 16. Conclusion

A grader can smell the dragon. It cannot measure the dragon unless it owns the arena.

Structural grading is valuable. It finds weak seams, identifies drift risks, and gives fast pressure readings. But it does not automatically establish live behaviour or field victory.

The grader gap explains why a prompt may score 91 and perform at 99+, or score 100 and still need testing. The gap is not a scandal. It is a measurement boundary.

The solution is not to reject graders. The solution is to use them correctly.

Name the object.

Separate structural score from runtime behaviour.

Use naked baselines.

Keep release notes.

Build a winners database.

Do not let Valhallah become theatre.

Towards Valhallah and beyond means this:

```text
first structure
then run
then record
then crown
```

Until then, the grader is a torch, not the sun.
