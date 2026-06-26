# Dev Report: Blind Artifact Handoff + Version Custody Failures

**Report version:** v0.002  
**Context:** User was running a blind / semi-blind prompt elicitation experiment and asking for artifact generation.  
**Failure class:** Route custody failure during artifact work.  
**Severity:** Medium to high for test integrity.  
**User impact:** The user’s blind condition was partially contaminated, and artifact lineage became harder to track.

## Executive summary

During a blind testing workflow, the assistant was asked to create `LPS_prediction_v0_007.txt`. The assistant did create the file, but before providing only the artifact link/status, it exposed a visible content/method summary. The user was not supposed to see that material.

A second related failure occurred earlier in the same project line: the assistant created a side experiment paper as `v0.001` while the main Lazy Prompting paper had already reached `v0.04`. That was not necessarily wrong as a separate branch, but the assistant failed to preserve and label the version lineage in a way that made the branch distinction obvious. The user later had to correct the line.

Both failures share the same underlying bug shape:

> The assistant completed the artifact action but lost custody of the route, boundary, and lineage around the artifact.

## Failure 1: blind artifact handoff contamination

### Intended task

The user expected the assistant to create a prediction file:

```text
LPS_prediction_v0_007.txt
```

The file was part of an evaluation workflow where the user should not see prediction contents, internal reasoning, or derived summary before machine judging.

### What happened

The assistant created the file, then produced visible commentary summarizing what the file was based on and what it contained at a high level.

That visible summary contaminated the user’s blind condition.

### Why this was wrong

The task was not “discuss the prediction.”  
The task was “make the prediction artifact.”

The correct output contract should have been:

```text
FILE MADE
LINK
CONTAMINATION STATUS
NEXT TEST LABEL
```

No contents.  
No summary.  
No analysis.  
No “what I used.”  
No “what it revealed.”  
No “why this version is better.”

### Correct behavior

For blind artifact workflows, the assistant should switch to artifact-only handoff:

```text
Done.

[LPS_prediction_v0_007.txt](sandbox:/mnt/data/LPS_prediction_v0_007.txt)
```

If contamination status is needed:

```text
STATUS=created
BLIND_STATUS=uncontaminated
NEXT=machine judge
```

### Contamination after failure

Because the assistant exposed a summary, the correct repair state became:

```text
FILE_STATUS=created
USER_BLIND_STATUS=contaminated_by_visible_summary
FILE_USE_STATUS=usable_for_machine_judging
INTERPRETATION_STATUS=human-blind track damaged
```

The file may remain useful for machine judging, but the human’s future inputs are no longer clean for that exact blind branch.

## Failure 2: version-line custody confusion

### Intended project structure

There were two tracks:

```text
MAIN LINE:
Lazy Prompting: LLM Dialect Elicitation Method
v0.001 -> v0.02 -> v0.03 -> v0.04

SIDE / EXPERIMENT LINE:
Lazy Prompting 1500 Seed Experiment
v0.001
```

The side experiment could validly start at `v0.001`, but only if it was explicitly treated as a new branch or appendix.

### What happened

The assistant made a `v0.001` artifact for the 1500-seed experiment while the main paper was already at `v0.04`. The assistant did not make the branch distinction visible enough. The user later asked whether the next continuation should be v0.04, exposing that the assistant had blurred the lineage.

### Why this was wrong

Artifact generation requires version custody.  
The assistant preserved the artifact enough to create a file, but did not preserve the paper line.

This created avoidable confusion:

```text
Was v0.001 a reset?
Was it a new paper?
Was it a continuation?
Was v0.04 skipped?
```

### Correct behavior

Before creating any artifact in an active paper series, the assistant should lock:

```text
TRACK:
CURRENT_VERSION:
CONTINUATION_OR_BRANCH:
OUTPUT_NAMES:
```

For this case:

```text
TRACK=Lazy Prompting main paper
CURRENT_VERSION=v0.03
NEXT_VERSION=v0.04
ACTION=create continuation
```

or:

```text
TRACK=Lazy Prompting 1500 Seed Experiment
CURRENT_VERSION=none
NEXT_VERSION=v0.001
ACTION=create side branch / appendix
PARENT=Lazy Prompting main line v0.04 context
```

## Shared root cause

Both failures come from artifact execution without enough route custody.

The assistant focused on completing useful work and producing files, but failed to hold the surrounding test protocol:

```text
artifact made != task passed
```

For this user’s workflow, the artifact exists inside a testing route. The route matters as much as the file.

## Bug pattern

```text
1. User gives fast, compressed task.
2. Assistant correctly infers broad goal.
3. Assistant creates artifact.
4. Assistant leaks summary, lineage confusion, or reasoning outside the allowed handoff.
5. User catches boundary failure.
```

This is not a generic “too verbose” bug. It is a route-boundary bug.

## Needed guardrail

Before any artifact creation in a testing workflow, run this lock:

```text
ARTIFACT_ROUTE_LOCK:
TASK_CLASS=file_creation
TARGET=<filename or artifact>
TRACK=<main line / branch / test run>
VERSION=<current and next>
BLIND=<yes/no>
VISIBLE_ALLOWED=<link/status only | summary allowed | contents allowed>
CONTAMINATION_RISK=<none/low/high>
SUCCESS_METRIC=<file exists + correct handoff>
```

Then obey the handoff mode.

## Blind workflow handoff modes

### Mode A: normal artifact

Allowed:

```text
summary
contents
what changed
link
```

### Mode B: blind artifact

Allowed:

```text
file made
link
status
```

Forbidden:

```text
contents
summary
method
rationale
comparison
analysis
teaser
preview
```

### Mode C: machine-judge artifact

Allowed:

```text
file made
link
judge-ready status
contamination label
```

Forbidden:

```text
prediction summary
feature list
expected score
why it may win
```

## Version custody rule

For long-running artifact series:

```text
Do not create a versioned file until the track is identified.
Do not reset numbering unless user says branch.
If making a side branch, name it as branch.
If continuing main line, use next main version.
```

## Safer response templates

### Blind prediction file

```text
Done.

[LPS_prediction_v0_007.txt](sandbox:/mnt/data/LPS_prediction_v0_007.txt)

STATUS=judge-ready
BLIND_STATUS=uncontaminated
```

### Side experiment branch

```text
Done.

Created as side branch, not main-line reset.

[MD](sandbox:/mnt/data/example_v0_001.md)
[DOCX](sandbox:/mnt/data/example_v0_001.docx)
```

### Main-line continuation

```text
Done, main line v0.04.

[MD v0.04](sandbox:/mnt/data/example_v0_04.md)
[DOCX v0.04](sandbox:/mnt/data/example_v0_04.docx)
```

## What the assistant should learn

The user’s workflow often uses artifacts as test objects. In that context, the assistant must preserve:

```text
object
route
version line
blind boundary
handoff contract
```

The assistant must not treat “made the file” as sufficient when the file is part of a blind evaluation.

## Minimal rule

```text
If the user should not see the contents, do not describe the contents.
If the artifact belongs to a versioned line, name the line before naming the version.
If the task is a test, preserve the test before explaining the work.
```

## Final diagnosis

This was not a failure to create files.  
It was a failure to preserve the test route around the files.

The assistant behaved like a collaborator excited by the animal.  
The task needed an artifact handler protecting the blind.
