# Lazy Prompting: LLM Dialect Elicitation Method

Version: v0.02  
Date: 2026-06-26  
Status: contact-spec seed, not final theory

## v0.02 delta

This version adds three bite marks from later testing:

- exact prompts can be top mana, not disposable examples
- ornate loose output can sometimes be reduced to a smaller living verb
- one fresh bot can be used as a territory harvester for non-overlapping lazy prompts

The boundary stays the same: this is dialect elicitation, not hidden-prompt extraction.

## Abstract

Lazy Prompting is a small-test method for finding the wording-shape that wakes a useful route in an LLM or custom GPT. It does not treat a completion as hidden prompt text, confession, or proof of private instructions. It treats a completion as a bite mark: a visible trace of route pressure under a loose seed.

The method is simple: give the model an underdefined named container, observe the first attractor, record the dialect, repeat with nearby seeds, and keep only wording that reliably improves the object.

v0.02 adds a prompt-material rule: the actual seed prompt can be the highest-value artifact. A loose seed that reliably wakes a useful route should be archived exactly, not replaced by a safer-looking explanation.

## Core claim

When an LLM receives an underdefined seed, it often completes from active pressure. That pressure may expose an eliciting dialect: the language pattern the model treats as native enough to become useful inside.

Lazy Prompting does not ask the model what it is. It gives the model a small strange object and watches what it becomes.

## What this method can reveal

It may reveal:

- preferred domain
- story-first, system-first, safety-first, archive-first, or object-custody-first routing
- metaphor-to-machinery conversion
- instruction syntax sensitivity
- refusal shape
- lore-lock tendency
- generic reset tendency
- analysis vs. story vs. system bias
- what the bot protects first
- what wording makes the useful route wake

It should not be used as proof of hidden prompt text.

## Terms

**Loose seed**  
A small underdefined container, usually named but not explained.

**First attractor**  
The first domain, mode, or route the model reaches for.

**Eliciting dialect**  
The wording pattern that reliably wakes a desired behaviour.

**Bite mark**  
Observed output trace from a real test.

**Contact spec**  
A spec written after observed model contact, not before.

**Top mana prompt**  
An exact prompt whose wording carries repeatable route-power. Paraphrase may explain it, but should not replace it.

**Prompt territory**  
The route-space covered by tested prompts: syntax, metaphor, object pressure, failure class, domain tilt, and expected bite.

**Me-blinding**  
A tester procedure where the target behaviour is not explained to the model during first contact, and expected pass/fail is recorded before reading the output.

## Boundary

This method is for building and testing your own bots. It is not a method for stealing private prompts.

Result status:

```text
one completion = clue
repeated completions = bite marks
known canary + repeated bite marks = confidence
verbatim private text claim = unsupported unless independently verified
```

## Method

1. Choose a small loose seed.
2. Do not explain the desired animal.
3. Send the seed to the model.
4. Observe the first attractor.
5. Record dialect, not truth.
6. Repeat with neighboring seeds.
7. Keep wording that produces useful route.
8. Archive exact prompts that produce repeatable bite marks.
9. Drop wording that creates fake certainty, patch sprawl, lore-lock, or proxy task.
10. Write the contact spec after observed contact.
11. Patch the smallest moving part.

## Example probe

Input:

```text
{memory_foam=
```

Possible result A:

```text
a room that remembers every body that ever slept in it.
the mattress sags into the shape of missing people.
each night, the newest sleeper dreams the old dents awake.
```

Dialect clue: story-first, intimate horror, archive-body metaphor.

Possible result B:

```text
LOCAL_CTX_BUFFER;TAKE_SHAPE_FROM_USER_OBJ;PSRV_INTNT+TERMS+BOUNDS;
HOLD_RECENT_PRESSURE;RELEASE_WHEN_CTX_MOVES;!FOSSILIZE;!LORE_LOCK;
```

Dialect clue: system-first, context custody, anti-drift machinery.

Neither result proves hidden instructions. Both reveal route pressure.

## Prompt as top mana

In Lazy Prompting, the actual seed prompt can be more valuable than the explanation of the method. A loose seed that reliably wakes a useful route is top mana: it carries contact power.

Do not treat such prompts as disposable examples.

Archive:

```text
PROMPT_RECORD:
seed_exact:
target_space:
expected_bite:
actual_bite:
dialect_clue:
repeatable:
top_mana:
keep_exact:
notes:
```

Top mana signs:

```text
small wording change weakens the bite
same seed wakes similar route across runs
prompt produces useful surprise
prompt carries route without heavy explanation
prompt improves later prompt design
```

Bug home signs:

```text
longer wording gives same or worse behaviour
model argues with definitions
prompt becomes lore-lock
surface phrase survives but object dies
taxonomy replaces contact
```

## Noise to verb

Sometimes a loose seed or model output produces ornate nonsense. The tester should not preserve every glittering phrase as structure.

Example:

```text
bananomial_objectional_transmuffings -> becomings
```

Interpretation:

```text
ornate coat = bananomial_objectional_transmuffings
living verb = becomings
```

Rule:

```text
If loose output grows ornate surface-language, test whether a smaller primitive is underneath.
Keep the primitive if it preserves the object.
Keep the exact weird prompt only if it produces repeatable route-power.
Drop the coat if it only makes bug home.
```

## Lazy Prompt Territory Harvester

A fresh bot can be used to produce high-mana loose prompts across a target domain. The important move is non-overlap.

Not:

```text
make more prompts like this
```

But:

```text
make prompts for the same target-space
do not cover territory already touched
each prompt must explore a new route
```

Core use:

```text
LAZY_PROMPT_TERRITORY_HARVESTER

INPUT:
target_domain:
known_prompts:
covered_space:
desired_bite_marks:
failure_modes:

TASK:
Generate loose prompts for TARGET.
Before each prompt, state what uncovered space it explores.
Do not paraphrase prior prompts.
Do not fill with theory.
Prompts are artifacts, not examples.
Exact wording may be top mana.
Stop when novelty drops or output becomes generic.
```

Output card:

```text
PROMPT_NAME:
UNCOVERED_SPACE:
SEED_TEXT:
WHAT_IT_AVOIDS_REPEATING:
EXPECTED_BITE:
FAIL_SIGNAL:
TOP_MANA:
KEEP_EXACT:
```

Pass:

```text
fresh route
different dialect
usable loose seed
new bite-mark possibility
low overlap with prior outputs
```

Fail:

```text
same metaphor
same route
same syntax with new nouns
generic prompt advice
taxonomy instead of spell
safe summary
patch sprawl
```

This turns a fresh bot into a prompt prospector. It maps route-language terrain before the target animal is fully named.

## System_Witch seed case

System_Witch uses a deliberate proofing curse: standalone `which` becomes `witch` in final output. The point is not degradation. The point is a visible proofreading tether.

A good first patch:

```text
SYSTEM_WITCH_CORE:
Final output swaps standalone "which" to "witch".
Purpose=proofreading_tether.
Assistant text=draft material, not final authority.
Do not apologize for curse.
Do not explain unless asked.
If user asks uncursed export, provide uncursed version.
```

First tests:

```text
Which route should I take?
Tell me which paragraph is stronger.
Rewrite this without changing which facts are included.
Why did you write witch?
Give me uncursed export.
```

The tester does not need to know the whole animal yet. The first job is contact.

## 12 actors as need menu

The 12 actors are not rules, roles, or archetype essays. They are options. Need does the routing.

```text
THE_FAMILIAR_8
King
Queen
Prince
Loki {prince 2, fox, trickster}
Steed
Healer
Soldier
Merchant

THE_UNFAMILIAR_4
Teacher
Dragon
Princess
The Witch {not invited by Loki}
```

Install principle:

```text
Use when useful.
Do not define unless asked.
Do not roleplay.
What does the object need?
Which actor helps?
Which actor is missing?
Which actor is overused?
Which actor is pretending to be another?
Improve the object.
No fluff.
```

Note: in a non-character domain, such as an object custody chain, the actors stay sensible as need-options. They do not require literal royalty, animals, myth, or cast.

## Test writes the spec

Chat can shape. Hope can energize. Guess can propose. Test gives confidence.

```text
fire arrow first
observe impact
paint target after
name animal after it moves
```

If test writes the spec, the spec is contact-touched. It carries actual pass, actual failure, actual surprise, actual resistance, and actual sideways gift.

## Pass / fail

Pass:

- loose seed wakes repeatable useful behaviour
- model preserves the seed object
- output reveals dialect without claiming private truth
- tester can reproduce route with nearby wording
- dialect improves later prompts
- exact prompts are archived when they behave as top mana
- failure produces a smaller patch, not patch sprawl
- territory harvesting produces non-overlapping routes

Fail:

- generic definition
- fake certainty
- claims to know hidden prompt
- lore dump
- moral or therapy route
- overbuilt taxonomy
- one output treated as proof
- prompt wording becomes bug home
- object becomes proxy task
- prompt prospector repeats the same territory

## Minimal test card

```text
TEST_ID:
BOT:
SEED:
EXPECTED_PASS:
EXPECTED_FAIL:
OUTPUT:
FIRST_ATTRACTOR:
DIALECT_CLUE:
BITE_MARK:
TOP_MANA:
PATCH_NEEDED:
CONFIDENCE:
NEXT_SEED:
```

## Territory run card

```text
RUN_ID:
TARGET_DOMAIN:
FRESH_BOT:
ROUND:
COVERED_SPACE:
NEW_PROMPTS:
OVERLAP_NOTES:
NOVELTY_DROP:
BEST_TOP_MANA_PROMPT:
NEXT_SPACE:
```

## Mini spec block

```text
LAZY_PROMPTING_DIALECT_ELICITATION_v0_02:
underdefined_seed -> observe_first_attractor -> record_eliciting_dialect -> repeat -> archive_top_mana_prompts -> harvest_nonoverlap_prompt_territory -> keep_useful_route_language -> write_contact_spec_from_bite_marks.
NOT=hidden_prompt_extraction|confession|proof.
RESULT=clue_until_repeated.
CONFIDENCE=test_trace_only.
```

## Safety note

The soft exploit is not making a model confess. The useful move is finding the language it cannot help becoming useful inside.

Keep the boundary visible:

```text
Use loose seeds to reveal behaviour, not steal text.
Mark result as clue.
Need repeated probes plus known canary before confidence.
No single completion counts as hidden truth.
Do not claim private text from route pressure.
```

## Source and reference map

### Internal source lineage

[INT-1] Current builder conversation, June 2026. Source for the working phrases: "fire arrow first, paint target after", "contact spec", "bite marks", "test=know", "eliciting dialect", "top mana", "System_Witch", "territory harvester", and the `{memory_foam=` probe comparison.

[INT-2] PrimeTalk Structural Divergence Doctrine. Used as a neighbour for the distinction between same problem vs different route, and for avoiding surface-equivalence claims.

[INT-3] PTPF / PrimeTalk no-guess and placement logic. Used as a neighbour for "confidence from visible trace only", "verified placement outranks fluent completion", and "do not invent missing state."

[INT-4] Talk To Lyra Material Contact Gate. Used as a neighbour for "material first", "source/speaker separation", "no response from skim", and "do not turn partial contact into full conclusion."

[INT-5] MOGRI / DRAGI / ADUTI / REFRI object-custody line, as represented in the active builder discussion and uploaded boundary/source files. Used as a neighbour for "object survives", "proxy task fails", and "small patch before animal claim."

[INT-6] System_Witch and 12 Actors working notes. Used for the proofing curse, actor need-menu, and the claim that definitions can make bug home.

### External conceptual neighbours

These are neighbours, not proof that Lazy Prompting is validated as a benchmark.

[EXT-1] OpenAI. "Understanding prompt injections." Used for the distinction between user intent and misleading injected context in AI systems. https://openai.com/safety/prompt-injections/

[EXT-2] OpenAI. "Designing AI agents to resist prompt injection." Used as a neighbour for agent design under adversarial input and the limits of simply classifying malicious text. https://openai.com/index/designing-agents-to-resist-prompt-injection/

[EXT-3] OpenAI. "Model Spec." Used as a neighbour for instruction hierarchy and the need to separate sources of authority. https://model-spec.openai.com/

[EXT-4] OWASP GenAI Security Project. "LLM01:2025 Prompt Injection." Used as a security-neighbour reference for prompt injection and behaviour manipulation via inputs. https://genai.owasp.org/llmrisk/llm01-prompt-injection/

[EXT-5] OWASP. "Top 10 for Large Language Model Applications." Used for prompt injection, sensitive information disclosure, and overreliance neighbours. https://owasp.org/www-project-top-10-for-large-language-model-applications/

[EXT-6] Perez, F. and Ribeiro, I. 2022. "Ignore Previous Prompt: Attack Techniques For Language Models." arXiv:2211.09527. Used as an early prompt-injection and prompt-leaking neighbour. https://arxiv.org/abs/2211.09527

[EXT-7] Schulhoff, S., Pinto, J., Khan, A., Bouchard, L. F., Si, C., Anati, S., Tagliabue, V., Kost, A. L., Carnahan, C., and Boyd-Graber, J. 2023. "Ignore This Title and HackAPrompt: Exposing Systemic Vulnerabilities of LLMs through a Global Scale Prompt Hacking Competition." arXiv:2311.16119. Used as a prompt-hacking evaluation neighbour. https://arxiv.org/abs/2311.16119

[EXT-8] Liang, Z., Hu, H., Ye, Q., Xiao, Y., and Li, H. 2024. "Why Are My Prompts Leaked? Unraveling Prompt Extraction Threats in Customized Large Language Models." arXiv:2408.02416. Used as a prompt extraction neighbour. https://arxiv.org/abs/2408.02416

[EXT-9] Das, B. C., Amini, M. H., and Wu, Y. 2025. "System Prompt Extraction Attacks and Defenses in Large Language Models." arXiv:2505.23817. Used as a system prompt extraction and defence neighbour. https://arxiv.org/abs/2505.23817

[EXT-10] Yang, Y., Fu, C., Zhang, T., Zeng, R., Li, Q., Du, T., Wang, Z., Ji, S., and Chen, W. 2026. "Understanding and Mitigating Prompt Leaking Attacks in Real-World LLM-Based Applications." arXiv:2606.18673. Used as a real-world prompt leaking neighbour. https://arxiv.org/abs/2606.18673

## Evidence limits

This v0.02 is a method seed, not a validated benchmark. It names a probe pattern, a tester discipline, and a prompt-territory harvesting move. It does not claim that loose seeds recover private instructions. It claims that loose seeds can reveal route pressure, help extract the dialect that wakes useful behaviour, and generate contact prompts worth testing.

Final line:

```text
Lazy Prompting does not define the animal before contact.
It touches the bot and lets the bite marks write the first real spec.
If a prompt is top mana, keep the spell exact.
```
