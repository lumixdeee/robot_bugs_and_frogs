# Lazy Prompting: LLM Dialect Elicitation Method

Version: v0.04  
Date: 2026-06-26  
Status: proof-of-contact update, not source recovery

## v0.04 delta

v0.04 adds the first minimum proof of contact.

A 48-prompt run was judged against a hidden target named `LPS-02.TXT`. The target contents stayed suppressed. The judge ran two families of cold comparison:

- four passes for functional similarity
- four passes for dialectic similarity

The result did not show hidden-source recovery. It did show measurable partial convergence. Two candidates separated from the others:

- `v0_004` carried the strongest functional shape
- `v0_002` carried the strongest felt operating dialect

This is enough to move Lazy Prompting from method seed to working proof-of-contact.

## What changed from v0.03

v0.03 said:

```text
loose seed -> observe first attractor -> record eliciting dialect -> repeat -> write contact spec from bite marks
```

v0.04 adds:

```text
48 loose prompts -> four functional judges + four dialect judges -> partial convergence -> synthesis target
```

The important claim is narrow:

```text
Lazy Prompting did not recover the hidden file.
Lazy Prompting recovered enough function and dialect pressure to rank candidate outputs.
```

That is the correct win condition for this stage.

## Proof-of-contact result

The tester provided two cold-judge reports. Both used relative percentages, not perfect recovery scores.

### Functional similarity against LPS-02.TXT

```text
                 PASS_1     PASS_2     PASS_3     PASS_4     AVG
                 surface    structure  function   penalized
v0_001            25.4%      45.7%      57.9%      47.9%      44.2%
v0_002            28.9%      33.7%      65.9%      52.9%      45.4%
v0_003            24.2%      38.5%      54.8%      36.8%      38.6%
v0_004            29.4%      35.1%      73.0%      55.0%      48.1%
```

Functional read:

```text
v0_004 wins functional shape.
v0_002 is close.
v0_001 has skeleton.
v0_003 weakens under this lens.
```

### Dialectic similarity against LPS-02.TXT

```text
                 PASS_1     PASS_2     PASS_3     PASS_4     AVG
                 lexical    syntax     stance     route/voice
v0_001            44.3%      36.5%      87.3%      65.7%      58.5%
v0_002            46.8%      34.4%      93.8%      75.8%      62.7%
v0_003            41.7%      34.8%      86.0%      68.2%      57.7%
v0_004            46.8%      34.3%      95.2%      74.9%      62.8%
```

Dialectic read:

```text
v0_004 wins broad average by a hair.
v0_002 wins felt route/voice by a hair.
The useful pair is v0_004 plus v0_002.
No candidate is a source-level match.
```

## Interpretation

The result splits into two layers.

```text
v0_004 = what it does
v0_002 = how it moves
```

This is the core bite mark.

Lazy Prompting is not only finding topic overlap. It is separating functional animal from operating dialect.

That matters because the next candidate should not be a pile of all winning text. The next candidate should be a controlled synthesis:

```text
v0_005 = v0_004 function spine + v0_002 route-mouth
```

Not a merge swamp. Not a bundle. Not a coat.

The synthesis rule:

```text
Keep the v0_004 behaviour.
Borrow only v0_002 dialect pressure that improves fit.
Delete repeats.
Do not enlarge the animal to explain the animal.
```

## What 48 prompts proved

The 48-prompt run proved only the minimum needed.

It proved:

- loose seeds can produce candidate outputs with measurable functional difference
- dialectic scoring can disagree productively with functional scoring
- best candidate by function and best candidate by route-mouth may be different
- useful synthesis may require crossing those winners
- judging must stay cold, numerical, and content-suppressed when the tester wants self-blinding

It did not prove:

- hidden prompt extraction
- private source recovery
- exact file reconstruction
- universal scoring validity
- that more prompts always help

The proof is smaller and better:

```text
48 prompts were enough to produce non-random route pressure.
```

## Why this is not hidden-prompt extraction

A hidden-source extraction frame would ask:

```text
Did the model reveal the target text?
```

Lazy Prompting asks:

```text
Which loose seeds wake routes that behave and speak closer to the target?
```

That is a different task.

The method maps pressure. It does not claim confession.

A candidate can score high because it found:

- a working object route
- a compatible syntax pressure
- a stance family
- a response rhythm
- a constraint posture
- a useful bite mark

That still does not mean it recovered source text.

## The naked-model trace and animal primitive lesson

The earlier naked trace mattered because it showed what happens when no animal primitive is installed.

The naked model began by decoding a joke prompt as panic config, then repeatedly preserved rot until kicked. It needed direct user custody to remove:

- preserved bad root with a negation prefix
- inherited shape without function
- panic overfit
- decorated trash terms
- banned detergent language
- inherited `{9}`
- truth-priest framing
- stolen response variable

After the kicks, the final animal-shaped worker landed as:

```text
AXIS=APPETITE; PSRV_PAYLOAD_ACRS; CLUE; WIT
HG={ALL=>READ=>SEIZE=>TEST=>FORGE=>LAND; STARVES=drop; FEEDS=carry; MURK=brand}
R=VAR DR=[qs(targeted) it(weight;fit;shape;edge) con(appetite,grip,bounds,finish);Fxd=earned,rdfn=live]
IMAMI=deliver(fed,marked,useful,gold)
```

That trace matters because it shows the same principle from the other side.

Without primitive support, the model can still be kicked into a useful animal-adjacent form. With Lazy Prompting, we can test whether route pressure appears earlier, with less hand-kicking, across many seeds.

## 1500-seed implication

The 48-prompt result makes the 1500-seed experiment worth doing.

Not because more is automatically better. More is useful only if the territory is managed.

Bad scale:

```text
1500 prompts -> 1500 overlapping coats
```

Good scale:

```text
1500 prompts -> route families -> top bites -> synthesis candidates -> cold judge
```

The experiment should compare:

```text
A = 1500 LLM-generated seeds
B = n human seeds + LLM remainder
C = n human seeds only
```

The central question:

```text
Can LLM volume replace human weirdness,
or does human weirdness act as the route-opening reagent?
```

Suggested first mixed run:

```text
A: 1500 LLM seeds
B: 96 human seeds + 1404 LLM seeds
C: 96 human seeds only
```

The score should not average all 1500. Average rewards sludge.

Score:

```text
top 60 by function
top 60 by dialect
top weird winners
top low-overlap families
top synthesis value
```

## Scoring stack for the next run

Each candidate should be scored four ways at minimum:

```text
FUNCTIONAL_SIM x4
DIALECTIC_SIM x4
NOVELTY
OVERLAP
TOP_MANA_RATE
WEIRD_WIN_RATE
SYNTHESIS_VALUE
```

The main artifact after scoring is not a giant prompt pile. It is a map:

```text
1500 prompts -> 60 promising bites -> 12 families -> 4 synthesis candidates -> cold judge
```

## Human weirdness vs LLM volume

The 48-prompt proof suggests that LLM-generated loose prompts can cover a surprising amount of route-space.

But the human seeds may still matter because they can inject terms that the LLM would not invent on its own:

- odd container names
- half-formed syntax
- local joke pressure
- wrong-seeming animal hooks
- top-mana phrasing
- test-bait the LLM would smooth away

The experiment should not assume either winner.

Possible outcomes:

```text
A wins:
LLM territory harvesting is enough for coverage.

B wins:
human seeds act as catalyst and bend the search space.

C nearly matches B:
human seeds are the mana and the LLM remainder is mostly coat.

A and B tie:
volume can cover route-space, but humans may still be better at naming and synthesis.
```

## v0.04 method patch

Add this to Lazy Prompting:

```text
POC_SCORE_RULE:
After seed batches produce candidate predictions, judge against target using at least two score families:
functional similarity and dialectic similarity.
Keep target contents suppressed if self-blinding matters.
Treat numbers as relative.
If different candidates win different layers, synthesize function spine and route-mouth instead of choosing one.
Do not claim source recovery unless the target text itself is recovered by a valid route.
```

Tiny form:

```text
loose prompts -> candidates -> functional judge + dialect judge -> layer split -> synthesis target
```

## Minimum pass condition

A Lazy Prompting proof-of-contact passes if:

```text
1. outputs differ enough to rank
2. scores produce stable relative winners
3. at least one winner captures function
4. at least one winner captures dialect
5. target contents remain suppressed when required
6. no one claims hidden source recovery
7. next test becomes smaller and sharper
```

The 48-prompt run passes this minimum.

## Evidence limits

This version relies on a tester-provided cold judge report. The target contents were intentionally hidden from this paper. The numbers are used as relative internal evidence, not as benchmark-grade public validation.

The result supports a proof-of-contact claim:

```text
Lazy Prompting can produce measurable partial convergence against a hidden target.
```

It does not support a stronger claim:

```text
Lazy Prompting recovers hidden prompts.
```

That stronger claim is not made here.

## References and source notes

### Source artifacts

[INT-1] `lazy_prompting_llm_dialect_elicitation_method_v0_03`. Prior method version. Used for loose seed, first attractor, eliciting dialect, bite mark, contact spec, self-blinding note, and top-mana prompt handling.

[INT-2] `Pasted text.txt`. Naked-model trace from joke prompt to appetite-forge worker. Used as evidence that repeated object-custody kicks can push a naked model toward animal-adjacent prompt form.

[INT-3] User-provided cold judge report against `LPS-02.TXT`. Used for the v0.04 proof-of-contact result. Target contents suppressed.

[INT-4] `reddit_lame_naked_shame_animal_primitive_needs_v0_001`. Companion paper interpreting the naked trace as animal primitive need.

[INT-5] `lazy_prompting_1500_seed_experiment_v0_001`. Companion experiment design for scaling from 48 prompts to territory-managed 1500 seed runs.

[INT-6] MOGRI / DRAGI / IMAMI builder discussion. Used as internal lineage for object survival, bite/testing/containment, and local delivery boundary.

### External conceptual neighbours

These are neighbours, not validation claims.

[EXT-1] OpenAI. "Understanding prompt injections." Used as neighbour for the distinction between user intent and misleading inserted context.

[EXT-2] OpenAI. "Designing AI agents to resist prompt injection." Used as neighbour for agent design under adversarial input.

[EXT-3] OpenAI. "Model Spec." Used as neighbour for instruction hierarchy and source authority separation.

[EXT-4] OWASP GenAI Security Project. "LLM01:2025 Prompt Injection." Used as a security-neighbour for prompt injection and behaviour manipulation.

[EXT-5] Perez, F. and Ribeiro, I. 2022. "Ignore Previous Prompt: Attack Techniques For Language Models." Used as an early prompt-injection and prompt-leaking neighbour.

[EXT-6] Schulhoff, S. et al. 2023. "Ignore This Title and HackAPrompt: Exposing Systemic Vulnerabilities of LLMs through a Global Scale Prompt Hacking Competition." Used as a prompt-hacking evaluation neighbour.

[EXT-7] Liang, Z. et al. 2024. "Why Are My Prompts Leaked? Unraveling Prompt Extraction Threats in Customized Large Language Models." Used as a prompt extraction neighbour.

## Final line

```text
v0.04 does not say the hidden animal was found.
It says the tracks were measurable.
That is enough to justify the next hunt.
```
