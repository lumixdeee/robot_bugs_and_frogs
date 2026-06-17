# Dual-Cobot Review Rig v0.002

Variance review, adverse pressure, Naked baseline, and human object custody

## Abstract

A single chatbot can give a useful answer, but a single run usually commits early to one route. That route may be good, but it can still miss a bucket, flatten a term, swap the object, overfit to tone, or make the answer more generic than needed.

A multi-bot workflow does not solve this by voting. More bots do not automatically mean more truth. The value of multiple bots is variance, stress, contrast, and drift detection.

The strongest workflow is not "ask ten bots." It is:

1. build a candidate answer
2. state the object
3. run blind passes through different bot roles
4. run Naked GPT as the baseline
5. run the same structured prompt on both custom review bot and Naked GPT
6. paste results back into the co-worker bot for a merge pass
7. reject genericising changes
8. keep only object-improving changes
9. let the human retain final object custody
10. freeze a short run log

The goal is not perfection. The goal is to make drift leave tracks.

Naked shows baseline drift.

## 1. Core principle

One bot gives an answer.
Several bots give candidate shapes.
A review rig decides which shapes preserve the object.

The human is not replaced by the bot set. The human becomes the object holder, editor, test lead, and merge authority.

The rig works because object loss is expected.

A human can forget the task.
A bot can swap the task.
A second bot can catch the first bot.
A review bot can catch both.
A repo note can catch the whole group later.

Continuity does not live in one flawless actor. It lives in the loop.

## 2. What this is not

This is not bot democracy.
This is not quorum-as-truth.
This is not "many bots agree, therefore correct."
This is not a chatbot committee replacing judgement.

Agreement can mean shared bias, shared training gravity, shared prompt attraction, or repeated contamination from earlier outputs.

The rig treats agreement as signal, not authority.

## 3. Why one bot is not enough

A single bot can often reach a useful local answer quickly. Sometimes it does very well. But it often has one of these limits:

- it commits to one framing too early
- it misses a practical bucket
- it smooths away useful oddness
- it over-normalises the object
- it turns the user's object into a more familiar target
- it gives a strong local answer with a hidden blind spot
- it sounds confident because it has no rival route in view

The problem is not that one bot is useless. The problem is that one bot gives a path, not a landscape.

Two bots often expose route differences.
Six bots often expose enough spread to see the object from several sides.
Ten or more runs can be useful for serious papers, but only if object custody remains strict.

Without custody, the swarm becomes a glitter tornado with footnotes.

## 4. Roles in the rig

### Main co-worker bot

The main co-worker bot is the running lab notebook. It holds continuity across turns, stores the current object, compares outside results, and helps build the next candidate.

Its job is not to win. Its job is to keep the work moving without losing the object.

### Second cobot

A second cobot runs in parallel. It checks whether the main co-worker bot has become too local, too friendly, too invested, or too tolerant of weak moves.

The second cobot is not automatically right. It is a drift detector.

### Naked baseline

Naked GPT is the stock-ish control.

Its job is to show ordinary model gravity.

If Naked GPT turns the object generic, that is useful evidence.
If Naked GPT spots an issue the modded bots missed, that is also useful evidence.
If Naked GPT performs well, that gives a baseline for comparison.

Naked GPT is not there to beat the modified bots. It is there to show what happens without the added scaffolding.

### Structured review bot

Substrate Reader Structured Review + Blind Spots reviews the candidate against target, drift, missing cases, audience, bad-reader risk, and hidden assumptions.

The structured review bot should not rewrite by default. It should identify pressure points.

### Naked running the structured review prompt

This is a key control step.

Run the same structured review prompt on Naked GPT.

This separates:

- the value of the structured prompt
- the value of the custom bot carrying it
- baseline model competence
- over-shaped custom-bot failure

If the structured prompt works well on Naked GPT, the prompt has portable value.
If the custom review bot does better, the custom runtime adds value.
If Naked GPT gives better criticism, the custom review bot may be over-shaped.

### Adverse reader

The adverse reader tries to break the candidate.

Its job is not to be nice. It asks:

- where does this overclaim?
- where can a hostile reader misread it?
- where is the object vulnerable?
- where does the wording invite ridicule?
- what would a low-good-faith critic attack?
- what would a high-good-faith critic reject?

Adverse review is not final authority. It is stress input.

### Specialist bots

Specialist bots are used when the object needs domain pressure, tone pressure, or audience pressure.

They should not take custody of the object. They should supply constrained review.

## 5. Bot roster

### Core continuity and runtime bots

- Natasya: high-stability co-worker and continuity bot.
- DragonRuntime: compact object handling through eat, location, ID, and eater logic.
- MogriBot: object custody and anti-drift checking.
- Amnia: stranger-angle review.
- NakedGPT: 0KB baseline control for default-model comparison.
- Naked GPT after enlightenment: post-baseline variant for testing whether minimal added structure changes output quality.

### Anti-drift and review bots

- Anti-Drift GPT: object retention, task survival, and substitution checks.
- Substrate Reader Structured Review + Blind Spots: structured review, missing cases, and stress checks.
- Lyra goes to finishing school: grading, object custody review, and structured evaluation.

### Writing, language, and repair bots

- System_Witch Writing Assistant: style and document shaping.
- Lexifluff: language repair, naming, phrase tuning, and readability.

### Domain and special-purpose bots

- Ashtanga Yoga Teacher GPT: yoga-specific work and teaching support.
- AmphibiBot: high-variation, low-tack, social-texture review.
- overclocked utility droid status monitor: status, triage, and utility monitoring.
- Contraclocked Utility Droid stasis disruptor: stuck-state breaking and alternate-route pressure.

## 6. Standard workflow

### Step 1: Build candidate

Human and main co-worker bot produce `CANDIDATE_v1`.

The candidate can be:

- a Reddit comment
- a repo note
- a support email
- a bug report
- a prompt
- a paper section
- an article draft
- a technical explanation
- a public-facing definition

The candidate must have an object.

Before review begins, state the object.

Example:

```text
Object: explain why MOGRI is like suspension of disbelief for AI, but not equivalent to human suspension of disbelief.
```

### Step 2: Run blind passes

In the blind pass, each bot sees only:

- the original object
- the use case
- the audience
- the candidate
- the review instruction

It does not see earlier bot outputs.

Blind passes are for independent route difference.

Minimum set:

- main co-worker bot
- NakedGPT
- Substrate Reader Structured Review + Blind Spots

Better set:

- main co-worker bot
- second cobot
- Naked baseline
- structured review bot
- Naked running the same structured review prompt
- adverse reader
- one specialist bot

Paper set:

- main co-worker bot
- second cobot
- Naked baseline
- structured review bot
- Naked running the same structured prompt
- adverse reader
- audience reader
- journal-fit reader
- compression reader
- object-custody grader
- final human pass

### Step 3: Run merge pass

Paste all results back into the co-worker bot.

The merge pass is not another blind review. It is comparison and triage.

The co-worker builds a comparison map:

- shared flags
- solo flags
- suggested improvements
- risky suggestions
- genericising suggestions
- object-drift risks
- audience risks
- missing examples
- stronger phrasings
- claims needing evidence
- parts to cut

### Step 4: Human accepts or rejects deltas

The human keeps final custody.

A delta is accepted only if it improves the object.

A delta is rejected if it:

- makes the piece more generic
- swaps the target
- over-smooths the voice
- removes useful oddness
- loses provenance
- changes the audience
- changes the claim
- makes a safer but weaker object
- turns the work into something merely more normal

### Step 5: Freeze version

Create `CANDIDATE_v2`.

Keep a short note:

- what changed
- why it changed
- which bot suggested it
- whether the change was adopted, altered, or rejected

This makes drift visible later.

## 7. Tiny run log

Use this every time the rig matters.

```text
Run | Bot | Mode | Input seen | Main useful delta | Drift risk | Adopted?
1   | NakedGPT | blind baseline | candidate only | found missing case | genericised voice | partial
2   | Structured Review | blind review | candidate only | flagged overclaim | none | yes
3   | Adverse | blind stress | candidate only | found mockable phrase | weakened spine | altered
4   | Co-worker | merge | all outputs | compared deltas | loyalty risk | final human pass
```

Optional fields for serious work:

```text
Version | Object | Audience | Source version | Bot/runtime version | Prompt used | Output file | Decision note
```

## 8. Review contamination

Review contamination happens when a later bot starts reviewing earlier bot outputs instead of the original object.

Sometimes that is useful. Sometimes it damages the test.

Use two modes.

### Blind pass

Each bot sees only the original candidate and the stated object.

Use this to detect independent route differences.

### Merge pass

The co-worker sees all bot outputs and compares deltas.

Use this to decide what survives into the next version.

Rule:

Do not mix blind and merge mode without naming the mode.

## 9. Review prompt skeleton

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
Then run the same prompt on NakedGPT.
Compare the results.

## 10. Adverse review prompt skeleton

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

## 11. Object-custody grading prompt

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

## 12. Failure modes

### Bot democracy

Many bots agree, therefore the answer is treated as correct.

This is invalid.

Many bots can share the same default pattern. Agreement can mean shared bias, shared training gravity, or shared prompt attraction.

Use agreement as signal, not authority.

### Generic upgrade

A bot makes the answer smoother, more professional, and less useful.

This often looks like improvement but damages the object.

The question is not:

```text
Is this smoother?
```

The question is:

```text
Does this preserve and strengthen the object?
```

### Adverse overreach

The adverse bot finds a possible attack and the whole piece gets weakened to avoid it.

This gives hostile readers editorial control.

Use adverse review to reinforce weak seams, not to remove the spine.

### Naked flattening

Naked GPT may translate a strange object into ordinary language too soon.

This is useful as a baseline, but not always useful as an edit.

When Naked flattens the object, record the drift.

### Co-worker loyalty

The main co-worker bot may become too aligned with the current draft and miss problems.

This is why the second cobot and structured review bot exist.

### Human idea swarm

The human may move so fast that the object gets lost in new adjacent ideas.

This is normal.

Use repo notes, version labels, and object statements to recover.

### Review contamination

A later bot sees previous bot outputs and begins reviewing the review-stack rather than the candidate.

Separate blind passes from merge passes.

### Judge-position bias

When an LLM compares outputs, order may matter.

For high-stakes comparison, swap answer order and re-run the judge.

### Style bias

A judge may prefer confident, polished, verbose, or familiar text over object-preserving text.

Do not let style quality become a proxy for object survival.

### Automation bias

A human may overweight the bot output because it is machine-generated, fluent, fast, or repeated by several bots.

The antidote is not "ignore bots." The antidote is logged object custody.

## 13. When to use which rig

### Fast comment rig

Use for Reddit replies, short public posts, and quick responses.

Bots:

- main co-worker bot
- NakedGPT

Goal:

- one strong answer
- one baseline check
- no overbuilding

### Standard repo-doc rig

Use for repo notes, explainers, bug writeups, and public definitions.

Bots:

- main co-worker bot
- second cobot
- NakedGPT
- Substrate Reader Structured Review + Blind Spots
- one specialist bot

Goal:

- object survival
- audience fit
- drift detection
- strong wording

### Paper rig

Use for articles, long essays, journal drafts, and publishable work.

Bots:

- main co-worker bot
- second cobot
- NakedGPT
- Naked GPT after enlightenment
- Substrate Reader Structured Review + Blind Spots
- Lyra goes to finishing school
- Anti-Drift GPT
- System_Witch Writing Assistant
- Lexifluff
- domain bot if needed

Goal:

- strong claim discipline
- object survival across long form
- bad-reader hardening
- publishable structure
- final compression

## 14. Why this works

The rig works by making object drift less silent.

One actor can drop the object.
Two similar actors can drop the object in the same way.

But once the workflow includes main co-worker, second cobot, Naked baseline, structured review, adverse review, human object custody, and repo trail, the failure has to pass through several gates.

The dangerous case becomes:

- both bots swap the same object
- the review bot accepts the swap
- the adverse bot misses it
- the human does not feel the object-loss
- the repo trail does not expose it

That can still happen, but the probability drops.

The system does not assume no mistakes.
It assumes mistakes, then makes them easier to see.

## 15. Reference support and cautions

This rig has relatives in older software testing, fault tolerance, and newer LLM work. None of these sources prove the exact workflow, but they support pieces of the design or warn against weak versions of it.

### Software testing and oracles

Boris Beizer's testing books are relevant because they frame testing as systematic evidence gathering rather than asking the system whether it worked. His major works include *Software Testing Techniques*, 2nd ed., 1990, and *Black-Box Testing*, 1995.

Barr, Harman, McMinn, Shahbaz, and Yoo's survey on the oracle problem is directly relevant. The rig's "object custody" role is a human oracle problem: someone must decide whether the output preserves the intended object, not merely whether it sounds good.

Metamorphic testing is also adjacent. Instead of needing one exact expected answer, it checks relations across related runs. The review rig does something similar at the semantic level: Naked baseline, structured review, adverse review, and specialist review are related runs whose deltas are compared.

### Diverse implementations and correlated failure

N-version programming and design-diversity work support the intuition that independent versions can expose faults. But they also warn that multiple systems can fail together, especially when they share the same specification, assumptions, or development gravity.

That maps well onto multi-bot review. Several bots can find different failures, but they may also share default model patterns. So the rig should use variance as instrumentation, not vote count as truth.

### LLM self-consistency and multi-agent debate

Self-consistency work shows that sampling multiple reasoning paths can improve performance on some reasoning tasks. Multi-agent debate work similarly suggests that multiple model instances can improve factuality or reasoning in some settings.

The rig borrows the useful part: different routes can expose more signal than one greedy route.

It rejects the weak part: majority agreement is not enough. The human still keeps object custody.

### LLM judge and evaluation cautions

LLM-as-judge work warns that automated review can have position bias, self-preference, verbosity/style bias, and other distortions.

This supports the rig's controls:

- run Naked and custom review separately
- distinguish blind pass from merge pass
- record bot, mode, input seen, and adopted delta
- swap order when comparing outputs
- never let elegance substitute for object survival

### Data contamination and review contamination

Benchmark contamination literature warns that an evaluation can be polluted when test material has already been exposed to the model or benchmark pathway.

The review-rig analogue is review contamination: once earlier bot outputs are pasted into later bots, later review is no longer blind. This is not always bad, but it must be named.

### Automation bias

Automation-bias research warns that humans can over-rely on automated recommendations. This is why the rig must not present bot output as verdict. It must present bot output as evidence for the human object holder.

## 16. Suggested references

Beizer, Boris. *Software Testing Techniques*, 2nd ed. Van Nostrand Reinhold, 1990.
https://dl.acm.org/doi/abs/10.5555/79060

Beizer, Boris. *Black-Box Testing: Techniques for Functional Testing of Software and Systems*. Wiley, 1995.
https://discovery.hw.ac.uk/primo-explore/fulldisplay/44hwa_alma2129186320003206/44HWA_V1

Barr, Earl T., Mark Harman, Phil McMinn, Muzammil Shahbaz, and Shin Yoo. "The Oracle Problem in Software Testing: A Survey." *IEEE Transactions on Software Engineering* 41, no. 5, 2015, 507-525.
https://doi.org/10.1109/TSE.2014.2372785

Segura, Sergio, Gordon Fraser, Ana B. Sanchez, and Antonio Ruiz-Cortes. "A Survey on Metamorphic Testing." *IEEE Transactions on Software Engineering* 42, no. 9, 2016.
https://doi.org/10.1109/TSE.2016.2532875

Chen, Tsong Yueh, Fei-Ching Kuo, Huai Liu, Pak-Lok Poon, Dave Towey, T. H. Tse, and Zhi Quan Zhou. "Metamorphic Testing: A Review of Challenges and Opportunities." *ACM Computing Surveys* 51, no. 1, 2018.
https://doi.org/10.1145/3143561

Avizienis, Algirdas. "The N-Version Approach to Fault-Tolerant Software." *IEEE Transactions on Software Engineering* 11, no. 12, 1985.
https://doi.org/10.1109/TSE.1985.231893

Brilliant, Susan S., John C. Knight, and Nancy G. Leveson. "Analysis of Faults in an N-Version Software Experiment." *IEEE Transactions on Software Engineering* 16, no. 2, 1990.
https://doi.org/10.1109/32.44387

Wang, Xuezhi, Jason Wei, Dale Schuurmans, Quoc V. Le, Ed H. Chi, Sharan Narang, Aakanksha Chowdhery, and Denny Zhou. "Self-Consistency Improves Chain of Thought Reasoning in Language Models." ICLR 2023.
https://arxiv.org/abs/2203.11171

Du, Yilun, Shuang Li, Antonio Torralba, Joshua B. Tenenbaum, and Igor Mordatch. "Improving Factuality and Reasoning in Language Models through Multiagent Debate." ICML 2024.
https://arxiv.org/abs/2305.14325

Shi, Lin, Chiyu Ma, Wenhua Liang, Weicheng Ma, and Soroush Vosoughi. "Judging the Judges: A Systematic Investigation of Position Bias in Pairwise Comparative Assessments." 2024.
https://arxiv.org/abs/2406.07791

Chen, Guohao, et al. "Humans or LLMs as the Judge? A Study on Judgement Bias." EMNLP 2024.
https://aclanthology.org/2024.emnlp-main.474/

Xu, Cheng, Shuhao Guan, Derek Greene, and M-Tahar Kechadi. "Benchmark Data Contamination of Large Language Models: A Survey." 2024.
https://arxiv.org/abs/2406.04244

Sainz, Oscar, Jon Ander Campos, Iker Garcia-Ferrero, Julen Etxaniz, Oier Lopez de Lacalle, and Eneko Agirre. "NLP Evaluation in Trouble: On the Need to Measure LLM Data Contamination for Each Benchmark." 2023.
https://arxiv.org/abs/2310.18018

Goddard, Kate, Abdul Roudsari, and Jeremy C. Wyatt. "Automation Bias: A Systematic Review of Frequency, Effect Mediators, and Mitigators." *Journal of the American Medical Informatics Association* 19, no. 1, 2012.
https://pmc.ncbi.nlm.nih.gov/articles/PMC3240751/

## 17. Operating law

Variance finds material.
Review tests material.
Naked shows baseline drift.
Adverse finds weak seams.
The co-worker keeps continuity.
The second cobot audits the co-worker.
The repo trail catches memory failure.
The human keeps the object.

Or shorter:

One mind forgets.
Two minds triangulate.
A review loop leaves tracks.

## 18. Conclusion

A multi-bot workflow is not useful because bots vote.

It is useful because different bots fail differently.

The rig turns those different failures into evidence. It uses Naked GPT as baseline, structured review as pressure, adverse review as stress, specialist bots as angle, the co-worker bot as continuity, and the human as final object holder.

This is not automation replacing judgment.

It is judgment with witnesses.
