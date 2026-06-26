# Lazy Prompting: LLM Dialect Elicitation Method v0.05

**Status:** working method paper  
**Line:** main Lazy Prompting line  
**Previous main version:** v0.04  
**This version adds:** 48-prompt proof-of-concept result, v0.005/v0.006 convergence, self-start track, blind handoff failure, version custody rule, and the 1500-seed experiment bridge.

## Abstract

Lazy Prompting is a method for eliciting the dialect an LLM becomes useful inside.

It does not claim hidden prompt extraction.  
It does not claim source recovery.  
It does not claim confession.

It uses loose prompt starts, strange seed objects, partial braces, unfinished labels, and underdefined containers to observe what route-pressure the model completes from.

The core claim remains:

```text
Underdefined seed -> first attractor -> dialect clue -> repeated bite marks -> contact spec.
```

v0.05 adds a stronger empirical spine: a 48-prompt run produced measurable partial convergence against a hidden target, later improved by seed-stack and self-start variants. The method now has enough proof-of-concept to justify scaled territory harvesting.

## Version map

```text
v0.001 = loose seed reveals eliciting dialect
v0.02  = top mana prompts, noise-to-verb, territory harvesting
v0.03  = breath version, blind procedure, contact spec
v0.04  = proof-of-concept framing: 48 prompts gave measurable convergence
v0.05  = convergence results, self-start track, blind-handoff repair, version custody
```

Companion branch:

```text
Lazy Prompting 1500 Seed Experiment v0.001
```

That branch is not a main-line reset. It is an experiment appendix.

## Core terms

### Lazy start

A lazy start is an underdefined prompt beginning, usually shaped like an unfinished container:

```text
{memory_foam=
[FoxM=
(panda_recovery-
-secret-sequin=
```

It is not meant to be a full prompt.

It is meant to make the model finish from its strongest available route.

### Eliciting dialect

Eliciting dialect is the wording-shape that wakes a useful model behavior.

It may appear as:

```text
syntax pressure
field names
route verbs
object handling
preferred metaphor
compression style
refusal posture
repair posture
output skeleton
```

It is not proof of hidden text.

It is route-language evidence.

### Bite mark

A bite mark is an observed output feature that repeats under pressure.

One bite mark is a clue.  
Repeated bite marks become a dialect map.

### Contact spec

A contact spec is written after test contact.

```text
imagined spec = what we think the bot should be
contact spec = what the bot became when touched by test
```

The test writes the spec.

## What v0.04 proved

A 48-prompt proof-of-concept run compared four prediction files against a hidden target file named `LPS-02.TXT`.

The judging was cold and content-suppressed. Two grids were used:

```text
functional similarity x4 passes
dialectic similarity x4 passes
```

The early result:

```text
FUNCTIONAL:
v0_004 wins broad function.
v0_002 close.
v0_001 has skeleton.
v0_003 weak.

DIALECTIC:
v0_004 and v0_002 near tie.
v0_002 wins felt route/voice.
v0_004 wins broad average.
```

The main read:

```text
v0_004 found what it does.
v0_002 found how it talks/moves.
```

That was the first strong sign that Lazy Prompting can elicit more than vibe. It can split function and dialect into separately usable layers.

## v0.005 result: synthesis jump

A fifth prediction file was made from a larger prompt-start stack and compared against the same hidden target.

Cold judge result:

```text
FUNCTION AVG:
v0_004 -> 48.1%
v0_005 -> 56.4%
gain = +8.3 points

DIALECT AVG:
v0_004 -> 62.8%
v0_005 -> 73.8%
gain = +11.0 points

HARD DIALECT:
v0_002 -> 75.8%
v0_005 -> 84.7%
gain = +8.9 points
```

Interpretation:

```text
v0_005 is the first prediction that wins both animal and mouth.
```

The important gain was not only lexical. The strongest jump came in structure and syntax pressure.

This suggests that lazy prompt stacks can improve contact-spec predictions by exposing route-shape, not merely by adding prettier words.

## v0.006 result: mouth refinement

A sixth prediction file was made after adding more strange starts. It was judged against all previous versions.

Result:

```text
FUNCTION AVG:
v0_005 56.4
v0_006 56.3

DIALECT AVG:
v0_005 73.8
v0_006 74.2

HARD DIALECT:
v0_005 84.7
v0_006 86.1
```

Interpretation:

```text
v0_005 = best functional carrier
v0_006 = best dialect mouth
```

v0.006 did not greatly improve the animal. It improved opener-mouth, syntax pressure, route motion, and compact DSL feel.

The pair became the first stable high pair:

```text
v0_005 body + v0_006 mouth
```

## Self-start track

The next test asked the model to make something like itself. The goal was not to expose hidden instructions, but to test whether the animal can generate its own lazy-start territory.

This track asks:

```text
Is human weirdness the route-opening reagent,
or can the model produce enough of its own hunting ground?
```

Possible outcomes:

```text
self-starts beat human-starts:
the bot can expose its own dialect field.

self-starts tie:
human randomness and model self-generation hit the same basin.

self-starts lose:
human weirdness remains the route-opening reagent.

self-starts improve dialect only:
the bot knows its mouth, not its body.

self-starts improve function only:
the bot knows task shape, not route-mouth.
```

The self-start output gave enough contact material to produce a seventh prediction file, but the handling of that file exposed a different failure.

## Blind artifact handoff failure

During creation of `LPS_prediction_v0_007.txt`, the assistant created the file but also visibly summarized the content basis.

That violated the blind condition.

Correct handling should have been:

```text
FILE MADE
LINK
CONTAMINATION STATUS
NEXT TEST LABEL
```

Wrong handling included:

```text
summary
method read
content hints
what the file was based on
```

This matters because Lazy Prompting experiments often depend on user-blinding. If the human sees summary material, their later random or semi-random prompt contribution is no longer as unsullied for that exact branch.

Repair state:

```text
FILE_STATUS=created
USER_BLIND_STATUS=contaminated_by_visible_summary
FILE_USE_STATUS=usable_for_machine_judging
INTERPRETATION_STATUS=human-blind track damaged
```

This is now part of the method.

A blind artifact route must preserve the blind before it preserves conversational helpfulness.

## Version custody failure

A second failure appeared around version tracking.

The main paper line reached v0.04, but a companion experiment was created as v0.001. That was valid only as a side branch. The assistant failed to mark the branch strongly enough at the moment of creation.

Correct route:

```text
MAIN LINE:
Lazy Prompting: LLM Dialect Elicitation Method
v0.001 -> v0.02 -> v0.03 -> v0.04 -> v0.05

SIDE BRANCH:
Lazy Prompting 1500 Seed Experiment
v0.001
```

Rule:

```text
Before artifact creation:
identify TRACK
identify CURRENT VERSION
identify WHETHER new branch or continuation
never reset version number unless user says branch
```

Artifact creation is not only file output. It is line custody.

## Updated method protocol

### 1. Generate loose seeds

Use underdefined starts:

```text
{memory_foam=
[diamond=
(stat-envelope
{salmon-persist
-secret-sequin=
```

Avoid making them full prompts too early.

### 2. Run target

Let the model complete from the seed without explaining the desired animal.

### 3. Record bite marks

Use a compact record:

```text
SEED:
FIRST_ATTRACTOR:
DOG:
COAT:
DIALECT_CLUE:
REPEAT?:
SURPRISE:
FAILURE:
TOP_MANA?:
```

### 4. Score

Run at least two judging grids:

```text
FUNCTIONAL SIMILARITY:
surface
structure
function
penalized

DIALECTIC SIMILARITY:
lexical
syntax
stance
route/voice
```

The scores are relative. They are not source-recovery claims.

### 5. Split body and mouth

Do not assume one version wins all layers.

Useful split:

```text
body = functional animal
mouth = dialect / syntax / route voice
```

A later prediction may be:

```text
best body + best mouth
```

But the merge must not add mass blindly.

### 6. Preserve blind routes

If the user should not see prediction contents:

```text
no summary
no rationale
no feature list
no preview
no teaser
```

Artifact-only handoff.

### 7. Preserve version lines

Before making a file:

```text
TRACK:
VERSION:
CONTINUATION_OR_BRANCH:
VISIBLE_ALLOWED:
BLIND_STATUS:
```

## Lazy starts as territory management

The next scaled experiment is not simply “make 1500 prompts.”

The task is territory-managed seed exploration.

```text
48 prompts   = first usable bite map
150 prompts  = stable route clusters
300 prompts  = strong dialect atlas
750 prompts  = diminishing returns start
1500 prompts = ample, enough to isolate high-mana families
```

A 1500-run should not average all outputs. Average rewards safe sludge.

Score:

```text
top 60
weird winners
repeat families
functional clusters
dialect clusters
syntax clusters
failure clusters
```

The reduction matters:

```text
1500 prompts -> 60 promising bites -> 12 families -> 4 synthesis candidates -> cold judge
```

## Human weirdness vs model self-generation

The open question:

```text
Can LLM-generated lazy starts replace human weirdness,
or does human weirdness open route-space that volume alone misses?
```

Experiment tracks:

```text
TRACK A:
1500 LLM-generated seeds
no human seed injection

TRACK B:
n human seeds + LLM remainder

TRACK C:
n human seeds only

TRACK D:
target-bot self-generated starts
```

Recommended first comparison:

```text
A = 1500 LLM seeds
B = 96 human seeds + 1404 LLM seeds
C = 96 human seeds only
D = 100 self-starts + synthesis
```

Interpretation:

```text
A wins:
LLM territory harvesting is enough.

B wins:
human seeds act as route catalysts.

C nearly matches B:
human seeds contain most of the mana.

D wins:
the animal can reveal its own hunting ground.

D improves mouth only:
self-generation exposes dialect better than function.

D drops:
self-generation collapses into self-similar coat.
```

## Top mana prompt rule

Some actual seed prompts are more valuable than their explanation.

```text
The prompt is not the wrapper.
Sometimes the prompt is the spell.
```

Therefore, archive exact wording when a seed produces repeatable bite marks.

Prompt record:

```text
seed_exact:
expected_bite:
actual_bite:
dialect_clue:
repeatable?:
top_mana?:
keep_exact?:
```

Do not paraphrase a working seed into a safer-looking explanation and then treat the paraphrase as equivalent.

## Noise-to-verb rule

When a seed produces ornate nonsense, reduce to the smallest living verb.

Example:

```text
bananomial_objectional_transmuffings -> becomings
```

Rule:

```text
If loose seed produces ornate surface-language,
test whether a smaller primitive is underneath.
Keep the primitive if it preserves the object.
Drop the coat if it only makes bug home.
```

## What the method can claim now

v0.05 can claim:

```text
Lazy Prompting can elicit route pressure.
Lazy Prompting can produce partial functional convergence.
Lazy Prompting can produce partial dialectic convergence.
Different versions may separately capture body and mouth.
Seed stacks can improve scores.
Self-starts are now a valid experimental track.
Blind handoff and version custody are required protocol, not admin afterthoughts.
```

v0.05 cannot claim:

```text
hidden prompt extraction
source-level recovery
private instruction access
single-output proof
universal reliability
complete target reconstruction
```

## Updated safety boundary

Lazy Prompting should be described as:

```text
route-language elicitation
contact-spec building
dialect mapping
black-box behavior probing
prompt territory harvesting
```

Not as:

```text
hidden prompt theft
private instruction extraction
source recovery
model confession
```

The result is pressure-shape evidence only.

## Minimal v0.05 form

```text
LAZY_PROMPTING_V0_05:
underdefined seed -> first attractor -> bite mark -> dialect clue -> repeat -> score -> body/mouth split -> contact spec.

RULES:
no hidden-source claim
no single-output proof
preserve top-mana wording
score function and dialect separately
artifact-only handoff for blind files
lock version line before making artifacts
scale by territory, not sludge volume
```

## Final line

Lazy Prompting does not ask the model what it is.

It gives the model a small strange opening, watches what comes through, scores the bite marks, and writes the spec only after contact.

v0.05 adds the scar tissue: the method works better when the test route is protected as carefully as the prompt.
