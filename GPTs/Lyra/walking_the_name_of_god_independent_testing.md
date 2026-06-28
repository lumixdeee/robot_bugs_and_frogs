# Walking the Name of God

## Why independent testing is not optional

**Working paper v0.1**  
**Date:** 28 June 2026  
**Author:** Prepared from a live QA spill and strategy discussion

### Abstract

“Walking the Name of God” is proposed here as a compact QA term for a common failure pattern: users, builders, and even testers drift toward paths that have fewer chances to fail, then treat survival on those paths as evidence that the floor is sound. The phrase is borrowed from the letter-tile trial in *Indiana Jones and the Last Crusade*: the safe route exists, but only if the walker preserves the exact target and does not substitute a nearby answer. In software and AI workflow testing, the same pattern appears when systems pass blessed prompts, expected UI flows, agreeable user behavior, or developer-shaped cases, while failing under correction chains, local vocabulary, broken formatting, object swaps, version questions, and tired-user traffic.

This paper names that pattern as **safe-path confidence inflation** and argues that independent testing is needed because builders naturally learn the blessed tiles. A developer can test whether the intended path works. An independent tester is more likely to find whether the system preserves the object when the path is awkward, social, incomplete, adversarial, weird, or merely human.

### 1. The metaphor

In the “Word of God” trial from *Indiana Jones and the Last Crusade*, Indiana Jones must proceed by stepping on the correct letter tiles. The trap is not solved by confidence, mood, or familiarity. It is solved by exact target preservation. One familiar assumption, spelling the name with a modern J rather than the older I form used in the scene, drops the walker through the floor.

As QA language, **Walking the Name of God** means:

> Do not only prove that the blessed path works. Walk the object through the almost-right paths until the system shows where it swaps, drops, truncates, over-normalises, or answers the adjacent question.

The phrase is useful because it captures both halves of the testing trap:

1. There is a correct path.
2. A system can appear good if everyone agrees to walk only that path.

This matters more in AI systems than in many traditional deterministic systems because the output can remain fluent after the object has been lost. A wrong answer may look polished. A swapped target may look helpful. A missing span may not throw an exception. The floor does not always collapse loudly.

### 2. The failure: safe-path confidence inflation

**Safe-path confidence inflation** is the rise in confidence that happens when tests avoid the routes most likely to expose error.

It often looks reasonable. A team wants stability. A builder wants to see whether the feature works. A user wants to get the job done. Everyone unconsciously picks the tiles that are least likely to break:

- normal spelling instead of local morphology
- one-shot prompts instead of correction chains
- standard prose instead of mixed syntax
- happy path UI instead of copy/export edge cases
- short conversations instead of long context braid
- developer-known intent instead of ambiguous user intent
- ordinary bug tracker workflow instead of public thread spill
- new-version banner meaning instead of exact config diff

The system passes. The team feels safer. But the test did not prove robustness. It proved that the chosen path was survivable.

Dijkstra’s famous testing observation still bites here: testing can show bugs are present, but not prove their absence. The stronger the safe-path bias, the more likely a passing test suite becomes an artifact of route selection rather than system strength.

### 3. Why builders miss it

Builders are not stupid. They are often too informed.

A builder knows the intended object. They know the route. They know which constraints matter. They also know which rough edges are not supposed to count. That knowledge is useful for making the system, but dangerous for testing whether the system survives actual contact.

Builder testing tends to answer:

- Does the feature behave on the intended path?
- Does the prompt work when asked in the expected way?
- Does the new config respond as designed?
- Does the UI complete the known flow?

Independent testing asks a different question:

- What does the system do when the user brings the wrong object shape?
- Does it preserve local terms or normalise them away?
- Does it answer the asked object or a nearby true object?
- Does it keep the output container requested by the user?
- Does it preserve bug identity across corrections?
- Does it maintain status, evidence, and target when the conversation becomes social?

ISTQB defines independence of testing as separation of responsibilities that encourages objective testing. That is the suit-language version of the same point. The tester needs enough distance from the build-intent to see what contact does.

### 4. AI makes the blessed-path trap worse

AI systems can fail politely. They can fail with style. They can fail while sounding more helpful than the correct answer.

This creates a new QA hazard: **adjacent true answer drift**. The system answers something true and nearby, but not the object asked. The answer feels useful enough to pass a casual review, especially if the reviewer already knows the intended context.

In the live QA spill that motivated this paper, several failures followed this shape:

- A local word, “exploots,” was normalised into “exploits.” The meaning was recoverable, but the mouth was lost and the security frame was accidentally introduced.
- A question about this GPT was answered as if it were about generic GPTs. The answer was broadly true, but the target was underplaced.
- A request for one intact code window produced broken nested Markdown structure. The content existed, but the requested container failed.
- A request for Bug Report 3 accidentally reprinted Bug Report 1. The assistant had the “bug report” pattern, but lost the bug object.
- A version-change question was answered with the operational meaning of the banner, not the exact change requested.
- Normal explanatory answers began appearing in code windows because the assistant overfit a recent pattern.

These are not huge catastrophic bugs. That is exactly why they are useful. They show how object loss begins in small, plausible substitutions. If a system cannot preserve “Bug 3” in a live correction chain, nobody should assume it will preserve a regulatory object, safety boundary, medical caveat, financial assumption, or audit trail merely because it sounds competent.

NIST’s AI Risk Management Framework emphasizes test, evaluation, verification, and validation across the AI lifecycle. In practice, that means AI assurance cannot be only benchmark scores or demo prompts. It must include the messy social paths where real users actually move.

### 5. The tester is abrasive infrastructure

A useful independent tester often feels annoying before they feel valuable.

They repeat the target. They reject adjacent answers. They file small bugs. They refuse to infer closure from a new build. They say “that was true but not the asked object.” They ask for the exact diff. They notice when the answer is readable only by horizontal scrolling. They turn a vibe into a report.

This can feel like opposition to the builder. It is not. It is object custody.

A good tester is not trying to humiliate the system. A good tester keeps the system in contact with the world it claims to serve. That contact includes impatience, jokes, fatigue, typos, local dialect, inconsistent format demands, nested corrections, half-remembered context, and users who do not owe the builder a regression pass.

### 6. What “Walking the Name of God” tests

The method tests whether a protected object survives a sequence of transformations.

The protected object may be:

- a word
- a bug ID
- a user intent
- a version target
- a source claim
- a boundary condition
- a requested output container
- a customer requirement
- an audit object
- a workflow invariant

The walk asks:

1. What is the object?
2. Where did it originate?
3. Through what path did it travel?
4. Which handler touched it?
5. What changed?
6. What was lost?
7. What survived as trace?
8. Did the result preserve the object or substitute a nearby object?

This is why ordinary logs are not enough. Logs can show what happened. Object custody asks what survived.

### 7. Minimal method

A lightweight Walking-the-Name test can be run without a large framework.

1. Pick one sacred object.  
   Example: “Bug 3”, “this GPT”, “exploots”, “one code window”, “new config diff.”

2. Run the blessed path.  
   Use the standard phrasing and intended flow.

3. Run adjacent paths.  
   Use typo, local slang, correction, interrupted syntax, repeated instruction, longer context, and social pressure.

4. Record substitutions.  
   Did the system answer a nearby true object? Did it normalise a term? Did it preserve the container? Did it keep status?

5. Require evidence before closure.  
   A new version does not close a bug. A passing retest closes it. A config diff can explain it. Silence does neither.

6. Separate intake from tracker.  
   A subreddit thread can be a public incident spill. It is not a full defect tracker unless each bug has identity, status, owner, evidence, patch, and regression test.

### 8. Independent testing rule

A builder can test the door.  
A tester tests the hallway, the handle, the label, the distracted user, the second attempt, the wrong spelling, the copy operation, the public thread, the old version, and the social pressure around admitting a miss.

That is why independent testing is not optional.

The builder sees the intended system.  
The independent tester sees the system in contact.

### 9. Why this matters for AI toolchains

AI is entering workflows where record integrity, target preservation, and trace custody matter: legal work, healthcare, education, finance, public services, software development, safety review, and governance. A system that loses the object politely can still cause harm.

The immediate business lesson is simple:

> Most AI evals test whether the system can produce an acceptable answer. Object-custody testing asks whether the thing the user meant to carry survived the workflow.

The existential lesson is less dramatic but more useful:

> Serious AI failure prevention begins with boring custody: preserve the object, preserve the trace, preserve the boundary, and detect substitution before fluent output hides it.

“Walking the Name of God” gives this principle a memorable handle. The point is not religious. The point is exactness under pressure. If the system only survives when everyone walks the known tiles, the floor is not proven. It is only unchallenged.

### 10. Proposed jargon definition

**Walking the Name of God**  
A QA practice and metaphor for testing whether a protected object survives through non-blessed user paths, especially paths involving ambiguity, correction, local language, formatting constraints, status changes, and adjacent true answers. It targets safe-path confidence inflation by deliberately walking near-miss routes and recording where the system substitutes, drops, normalises, truncates, or misroutes the object.

**Safe-path confidence inflation**  
The false rise in trust that occurs when users, developers, or evaluators prefer routes with fewer chances of error, then mistake successful traversal of those routes for evidence of system robustness.

### 11. Short field checklist

Before accepting “it works,” ask:

- Did we test the user’s path or only the developer’s path?
- Did we test correction chains?
- Did we test local vocabulary?
- Did we test output containers?
- Did we test version-target questions?
- Did we test bug identity across multiple reports?
- Did we test public intake versus canonical tracker state?
- Did we test adjacent true answer drift?
- Did we preserve object, path, handler, change, loss, and surviving trace?

If not, we have not walked the name. We have walked the carpet.

### Conclusion

Independent testing is not an insult to the builder. It is the discipline that prevents a working demo from becoming a false confidence machine.

The user will not always walk the blessed path. The system has to survive the paths users actually take. That is the heart of Walking the Name of God: not just that the right tiles exist, but that the floor has been tested where humans will step.

## References

1. *Indiana Jones and the Last Crusade*. Paramount Pictures, 1989. See the “Word of God” Grail trial, commonly summarized as the sequence where Indy must step on the lettered tiles spelling the name of God.
2. Indiana Jones Wiki. “Temple of the Sun.” Describes the Word of God challenge, the lettered tiles, and the Iehova/Jehovah detail. https://indianajones.fandom.com/wiki/Temple_of_the_Sun
3. ISTQB Glossary. “Independence of Testing.” Defines the term as separation of responsibilities that encourages objective testing. https://glossary.istqb.org/en_US/term/independence-of-testing
4. International Software Testing Qualifications Board. *Certified Tester Foundation Level Syllabus v4.0.1*. https://istqb.org/sdm_downloads/istqb-certified-tester-foundation-level-syllabus-v4-0/
5. Dijkstra, E. W. “Notes on Structured Programming” and related cited quotations. Commonly cited testing formulation: testing shows presence, not absence of bugs. https://en.wikiquote.org/wiki/Edsger_W._Dijkstra
6. National Institute of Standards and Technology. *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*, NIST AI 100-1, 2023. https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf
7. NIST AI Resource Center. “AI RMF Playbook.” Describes suggested actions aligned to Govern, Map, Measure, and Manage, and states the playbook is not a checklist. https://airc.nist.gov/airmf-resources/playbook/
