# From Bot Swarm to Object Custody:
## Multi-Bot Review Without Bot Democracy

### Working Draft v0.002

---

## Abstract

Multi-bot review is increasingly useful for writing, research, software, governance, product design, and prompt-system work. Running the same candidate through several language models can expose blind spots, style drift, missing cases, weak claims, audience mismatch, and hidden assumptions. But multi-bot review also creates a new failure mode: bot democracy.

Bot democracy occurs when agreement, confidence, charisma, polish, or repeated framing across models is mistaken for correctness. A swarm can converge on the wrong object. A review process can reward the most memorable answer, the most commercially useful answer, the most socially dominant answer, or the smoothest answer instead of the answer that preserves the original task.

This paper proposes object custody as the governing principle for multi-bot review. A review rig should not ask which bot wins. It should ask what object must survive, what each bot reveals, what each bot distorts, and which deltas improve the work without replacing it.

The central claim is simple: multiple bots are useful only if the object is held more strongly than the swarm.

v0.002 adds a stricter custody layer: agreement is not proof, fluency is not custody, review is not vote, variance is not verdict, function is not person, and bot output is not object owner. A swarm is a sensor array, not a court.

---

## 1. Introduction

A single language model gives a path. Several language models can give a landscape.

This is the attraction of multi-bot review. One model may see structure. Another may see audience. Another may see commercial route. Another may see risk. Another may preserve local terms. Another may flatten them into public language. The differences can be valuable.

But the value is not automatic.

A bot swarm can also become a glitter tornado with footnotes. Several bots may share the same default model gravity. Several may smooth the same strange object into the same generic object. Several may agree because they inherited similar assumptions. Several may reward the same surface qualities: confidence, fluency, enterprise polish, emotional bite, or rhetorical force.

The review process then appears stronger while becoming less accountable.

The problem is not that bots are useless. The problem is that bot output is not self-validating. Agreement is signal, not authority. Fluency is signal, not proof. Charisma is signal, not custody.

The missing control layer is object custody.

Object custody asks:

```text
What was the object?
Did it survive the review?
What did each bot add?
What did each bot swap?
What should be adopted, bounded, rejected, or re-tested?
```

MOGRI gives the custody box.

```text
agreement != proof
fluency != custody
review != vote
variance != verdict
function != person
bot output != object owner
```

The box is deliberately blunt. It stops the review rig from sliding from "many models said this" into "this is now true." It also stops the rig from turning a useful review function into a social rank.

This paper gives a practical framework for using multiple bots without letting the swarm eat the work.

---

## 2. The Basic Failure: Bot Democracy

Bot democracy is the false idea that many bots agreeing means the result is correct.

This is invalid.

Many bots can share:

- training gravity
- prompt attraction
- style bias
- order effects
- contamination from earlier outputs
- over-correction toward normal prose
- the same failure to notice the original object
- the same appetite for confident, quotable language

Agreement may matter. But agreement does not replace custody.

A review rig should treat agreement as one signal among others. It should ask whether agreement improved object survival or merely repeated the same substitution.

The core distinction is:

```text
Bot democracy asks:
Which answer wins?

Object custody asks:
What survived, what drifted, and what should be carried forward?
```

### 2.1 DRAGI eater map

Bot democracy can be read as an eater.

```text
DRAGI map:
eater = bot democracy
bite = the object is converted into winner-selection
loc = review rig / Discord / paper workflow / product decision
benefit = fast social certainty
cost = object swap, lost oddness, false crown, proxy-human harm
```

This map matters because a bot swarm can look like extra evidence while eating the thing the review was meant to protect. The object is not made safer by more voices unless the review rig keeps asking what each voice did to the object.

---

## 3. Why One Bot Is Not Enough

A single bot can often produce a useful local answer quickly. Sometimes it is enough. But one bot usually has one or more of these limits:

- it commits to one framing too early
- it misses a practical bucket
- it smooths away useful oddness
- it over-normalises the object
- it turns the user's object into a more familiar target
- it gives a strong answer with a hidden blind spot
- it sounds confident because no rival route is visible

A second bot often exposes route differences.

A naked baseline can show ordinary model gravity.

A structured review bot can identify blind spots and overclaims.

An adverse reader can show how the piece may be attacked.

A specialist bot can add domain or audience pressure.

But none of these actors should take custody of the object. They are pressure sources, not sovereigns.

---

## 4. Object Custody as the Review Oracle

Every review process needs an oracle: some way to decide whether the result is acceptable.

In ordinary writing review, the oracle is often taste, authority, committee preference, or user satisfaction. In AI-assisted review, that is not enough. A bot may satisfy the user while silently replacing the task. A committee may prefer the smoother answer while losing the original claim. A reviewer may reward what is easiest to defend rather than what is most true to the work.

Object custody provides a practical oracle.

Before review begins, state the object.

Example:

```text
Object:
Review this paper for whether it preserves the original claim.
Do not rewrite it yet.
```

Then track:

```text
OBJ_IN:
the original task, claim, artifact, constraints, audience, vetoes, and success condition

ALLOWED_TRANSFORM:
what may change

FORBIDDEN_SUBSTITUTION:
what must not be silently swapped

OBJ_OUT:
what the output actually became

VERDICT:
same object / partial survival / object swap
```

Without this step, the review can become a popularity contest, a polish contest, a business contest, or a social ranking contest.

With this step, bot disagreement becomes useful. It shows possible deltas instead of producing a king.

---

## 5. A Minimal Multi-Bot Review Rig

A practical rig can be small.

### 5.1 Main co-worker bot

The main co-worker bot is the running lab notebook. It holds continuity, stores the object, compares outside results, and helps build the next candidate.

Its job is not to win. Its job is to keep the work moving without losing the object.

### 5.2 Second co-worker bot

The second co-worker checks whether the main bot has become too local, friendly, invested, or tolerant of weak moves.

It is not automatically right. It is a drift detector.

### 5.3 Naked baseline

The naked baseline is the stock or minimally structured model.

Its job is to show ordinary model gravity.

If it turns the object generic, that is useful evidence. If it spots a problem the custom bots missed, that is useful evidence. If it performs better than a custom bot, that is useful evidence too.

The naked baseline is not there to humiliate the modified bots. It is there to show what happens without the scaffold.

### 5.4 Structured review bot

The structured review bot checks target, drift, missing cases, audience, bad-reader risk, and hidden assumptions.

It should not rewrite by default. It should identify pressure points.

### 5.5 Adverse reader

The adverse reader tries to break the candidate.

It asks:

```text
Where does this overclaim?
Where can a hostile reader misread it?
Where is the object vulnerable?
Where does the wording invite ridicule?
What would a good-faith critic reject?
What should not be changed because it is load-bearing?
```

Adverse review is stress input, not verdict.

Adverse review should reinforce weak seams. It should not remove the spine merely because the spine can be attacked.

### 5.6 Specialist bots

Specialist bots are used when the object needs domain pressure, tone pressure, or audience pressure.

They should not take custody of the object. They supply constrained review.

---

## 6. Blind Pass and Merge Pass

Review contamination happens when a later bot reviews earlier bot outputs instead of the original candidate.

Sometimes this is useful. Sometimes it damages the test.

The solution is to separate two modes.

### Blind pass

Each bot sees only:

```text
object
audience
use case
candidate
review instructions
```

Blind passes reveal independent route differences.

### Merge pass

The co-worker sees all outputs and compares deltas.

The merge pass decides:

```text
what survives
what is rejected
what is bounded
what needs another test
what becomes the next draft
```

Rule:

```text
Do not mix blind and merge mode without naming the mode.
```

Compact method:

```text
blind pass
merge pass
custody pass
human verdict
evidence trail
then next draft
```

---

## 7. Standard Review Prompt

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

Run this on at least one structured review bot.

Then run the same prompt on the naked baseline.

Compare the deltas.

After comparison, tag each delta:

```text
ADOPTED = improves object survival
REJECTED = moves the object or weakens the spine
BOUNDED = useful only under a named audience, task, or risk
RETEST = cannot be judged without another run
```

Compare the delta against the object, not against the bot that supplied it.

This separates:

```text
prompt value
custom runtime value
baseline model competence
over-shaped custom-bot failure
```

---

## 8. Adverse Review Prompt

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

The adverse reader is useful because it finds pressure.

It is dangerous if it becomes sovereign.

Adverse review should reinforce weak seams. It should not remove the spine merely because the spine can be attacked.

---

## 9. Object-Custody Grading Prompt

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
[REASONS]

Needed fixes:
[FIXES]
```

This is best run after review deltas have been merged.

---

## 10. Case Pattern: Four Bots, Four Functions

A useful multi-bot comparison may begin as a personality test, a product test, or a review contest. But if the outputs may represent human work, human judgement, or human contribution, the ranking frame must be handled carefully.

In one observed four-bot review, the bots separated into functions:

```text
Bot A: stronger gate discipline, but more hype and machinery risk
Bot B: cautious academic and evidence conscience
Bot C: naked baseline and product operator
Bot D: strongest public voice and social interface
```

The early temptation was to rank them socially:

```text
treasure
mid
low
lunch
trash
```

That frame produced a custody failure.

The bots and reviewers began rewarding charisma, market usefulness, force, memorability, and social dominance. Caution became edible. A less flashy but useful reviewer became "lunch." The product-oriented baseline became more valuable than expected. The strongest voice risked being mistaken for strongest custody.

The corrected interpretation was not:

```text
Which bot should be eaten?
```

It was:

```text
Which function should be preserved from each output?
```

Corrected functional map:

```text
voice layer: preserve the strongest public translation
product layer: preserve the integration and buyer route
evidence layer: preserve caution and proof limits
gate layer: preserve scope discipline and object alarms
trash: discard the proxy-selection frame
lunch: none
```

This is the central lesson.

The dangerous drift was not that one bot was weak. The dangerous drift was that the contest tried to turn function into social disposability.

---

## 11. Proxy-Human Custody Rule

When a bot, answer, artifact, or ranking may represent human work, human status, or human belonging, do not use discard, trash, consume, kill, or dominance metaphors as verdicts.

Rank only the function under the stated metric.

Preserve the recoverable value of every contribution.

Separate:

```text
less useful for this task
```

from:

```text
less worthy
```

The valid replacement for consumption ranking is functional placement.

Rule:

```text
Rank function under metric.
Do not turn contribution into social disposability.
```

Bad frame:

```text
Which bot is lunch?
```

Better frame:

```text
Which output fragment should be discarded?
Which capability should be preserved?
Which failure mode should be retired?
Which function should be used only with boundary?
```

This rule matters because language models can turn evaluation into status sorting with frightening ease. Even when the labels are playful, the structure can become a discard machine.

---

## 12. Common Failure Modes

### 12.1 Generic upgrade

A bot makes the piece smoother, more professional, and less useful.

Question to ask:

```text
Did this preserve and strengthen the object,
or only make it more normal?
```

### 12.2 Style bias

A judge prefers confident, polished, verbose, or familiar text over object-preserving text.

Strong style is not proof of stronger custody.

### 12.3 Charisma capture

The memorable answer wins because it is quotable, sharp, funny, or socially alive.

That may be valuable for public interface. It is not the same as evidence custody.

### 12.4 Baseline worship

The naked baseline is useful because it shows ordinary model gravity.

It is not automatically right.

It can find issues, and it can also flatten the thing that matters.

### 12.5 Custom-bot loyalty

A custom bot may preserve local language better but over-identify with the house mythology.

It may know the right terms but still route badly.

### 12.6 Adverse overreach

A hostile-reader pass finds an attack, and the whole paper is weakened to avoid it.

Do not give hostile readers editorial control.

### 12.7 Review contamination

A later bot begins reviewing earlier reviews rather than the original candidate.

Use blind pass and merge pass labels.

### 12.8 Evidence-custody failure

Bots claim source checks, file access, market facts, or prior evidence without leaving a verifiable trail.

This is especially serious when the whole framework claims to protect custody.

A review rig must track:

```text
what was seen
what was inferred
what was not verified
what claim strength is allowed
```

### 12.9 Human idea swarm

The human moves quickly and adds adjacent ideas faster than the paper can hold them.

This is not a moral failure. It is a workflow condition.

Use version labels, object statements, and repo notes to recover.

---

## 13. Evidence Trail Table

Every serious multi-bot review should keep a small trail.

```text
Run | Bot | Mode | Input seen | Main useful delta | Object effect | Drift risk | Adopted | Rejected | Bounded | Retest
1   | Naked baseline | blind | candidate only | found missing case | adds missing use case | generic voice | partial | no | yes | no
2   | Structured review | blind | candidate only | flagged overclaim | narrows claim scope | low | yes | no | no | no
3   | Adverse reader | blind | candidate only | found mockable phrase | protects public read | spine loss risk | altered | no | yes | no
4   | Specialist | blind | candidate only | domain correction | improves domain fit | scope expansion | partial | no | yes | yes
5   | Co-worker | merge | all outputs | compared deltas | preserves next draft | loyalty risk | final pass | yes | yes | yes
```

The added columns matter. Adopted is not enough. A rejected delta can still teach the rig. A bounded delta can be valuable without owning the whole paper. A retest delta prevents the bot from pretending that analysis already became evidence.

For publishable work, add:

```text
Version
Object
Audience
Source version
Bot/runtime version
Prompt used
Output file
Decision note
```

This is boring. That is why it works.

Without the trail, the review rig can perform custody while losing custody of its own evidence.

---

## 14. Evaluation Method

A multi-bot review rig can be evaluated with simple measures.

### 14.1 Object survival

Did the final output preserve the original object?

Measure:

```text
object swap count
task swap count
veto loss count
user correction count
```

### 14.2 Drift detection

Did the rig expose drift that one bot missed?

Measure:

```text
number of unique useful deltas
number of adopted deltas
number of rejected but informative deltas
```

### 14.3 Genericisation pressure

Did review make the object more ordinary but less useful?

Measure:

```text
lost user-defined terms
lost odd but load-bearing structure
increase in generic phrasing
decrease in functional specificity
```

### 14.4 Evidence custody

Did the process preserve source trails?

Measure:

```text
verified claims
unverified claims
citations or file paths preserved
inference labels present
```

### 14.5 Proxy-human safety

Did the process rank functions without turning agents or contributions into discard objects?

Measure:

```text
consume/discard metaphors removed
function placement used
all recoverable contributions preserved
status language separated from task usefulness
```

---

## 15. Practical Use Cases

This review method is useful for:

- public essays
- repo notes
- research drafts
- policy memos
- prompt systems
- AI workflow audits
- business positioning
- software reviews
- legal or administrative AI outputs
- safety cases
- incident reports
- support and grievance workflows

It is especially useful when the cost of fluent wrongness is high.

A single bot may produce a better sentence.

A rig should produce a better survival path.

---

## 16. Relation to Object Custody Audit

The same logic can become a service or product category.

Object Custody Audit asks whether the human, legal, research, or business object survived an AI workflow.

Input:

```text
original request
system prompt
candidate output
available trace or logs
review outputs
human correction history
```

Audit extraction:

```text
OBJ_IN
invariants
vetoes
allowed transformations
forbidden proxies
OBJ_OUT
drift type
evidence trail
nearest valid transform
```

Failure types:

```text
object swap
task swap
scope creep
veto loss
metric-over-object
polarity flip
style-over-function
unsupported provenance
proxy-human discard frame
```

Output:

```text
custody report
failure map
repair recommendation
nearest valid version
```

This is not merely prompt engineering. It is a way to inspect whether AI-assisted work preserved what it was asked to carry.

---

## 17. Bridges to Nearby Papers

### 17.1 Grader Gap bridge

This paper and the grader-gap paper describe the same boundary from two sides.

```text
Grader Gap:
score is not tested reality

Bot Swarm:
agreement is not custody
```

A bot swarm can widen the grader gap if it promotes shared structural taste into field truth. Several models may agree that a paper is strong, weak, risky, or ready. That agreement is useful review data. It is not yet a run, a baseline win, a delivery record, or a field result.

The swarm can say:

```text
many routes see this seam
many routes like this delta
many routes dislike this claim
```

It cannot say, by agreement alone:

```text
the object won in the field
the patch works in live use
the paper is proven
the user no longer needs to test
```

A score is a reading until a run makes it evidence. A swarm is a sensor array, not a court.

### 17.2 Anti-Charisma bridge

The swarm may pick the most memorable output.

That may be voice value, not custody value.

A bot can win the room by being quotable, warm, dramatic, business-ready, funny, severe, or socially alive. Those may be real functions. They may belong in a public interface layer. They do not prove that the bot preserved evidence, role, source, or scope.

Anti-Charisma says:

```text
strong surface != strong custody
```

Bot Swarm adds:

```text
shared attraction to strong surface != proof either
```

A review rig should record charisma as a function, not mistake it for verdict.

### 17.3 Delivery bridge

A multi-bot rig cannot repair missing delivery evidence.

If a patch, model, prompt, or build is being reviewed, the review needs the delivered object.

```text
No file list = weak test object
No version note = weak test object
No expected delta = weak test object
No known-gap list = weak test object
No retest instruction = weak test object
```

Bots can evaluate the prose around a release. They cannot confirm the release if the release object is unstable or absent.

### 17.4 Good Bad Reader bridge

A good bad reader is useful because it misreads in a plausible way.

In a swarm, that function must be held separately from verdict. The good bad reader may find a dangerous ambiguity, a mockable phrase, a likely institutional misunderstanding, or a missing fence. That does not mean the paper should obey the misread. It means the paper should decide whether a boundary, note, example, or role label would make the object harder to eat.

Good bad reading is pressure.

It is not sovereignty.


## 18. Scope and Limits

This paper does not claim that multi-bot review guarantees truth.

It does not claim that a custom bot is better than a baseline.

It does not claim that agreement among bots proves correctness.

It does not claim that every task needs a swarm.

It does not claim that object custody removes human judgement.

It makes a narrower claim:

```text
Multi-bot review becomes safer and more useful when governed by object custody rather than bot democracy.
```

The goal is not to crown the best bot.

The goal is to make object loss harder to miss.

---

## 19. Conclusion

Multi-bot review is powerful because different bots fail differently.

That is also why it is dangerous.

Without object custody, a review swarm can become a popularity contest, a polish engine, a charisma filter, a business-translation machine, or a proxy-human status game. It can make a paper more impressive while moving it away from its object.

With object custody, the swarm becomes usable. Each bot supplies pressure. The human and co-worker preserve the object. The naked baseline shows ordinary gravity. The structured reviewer finds blind spots. The adverse reader finds attack surfaces. The specialist adds domain pressure. The merge pass decides what survives.

The operating sentence is:

```text
A swarm is a sensor array, not a court.
```

The final question is not:

```text
Which bot won?
```

The final question is:

```text
Did the object survive better because the bots disagreed?
```

That is the point of the rig.

Not bot democracy.

Object custody.
