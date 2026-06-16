# Put Object Preservation Before Agent Autonomy

**Version:** v0.001  
**Status:** public draft for fast release  
**Author:** lumixdeee / lmxdi source stack  
**Date:** 2026-06-16  
**Source basis:** `lmxdi/ADUTI/ADUTI_REFRI_MOGRI_DRAGI_ELVIX_upstream_llm_tooling_article.md`, `lmxdi/ADUTI/ADUTI.txt`, `lmxdi/ADUTI/REFRI.txt`, `lmxdi/RORA/mogri-dragi.txt`, and related MOGRI / DRAGI runtime notes from the uploaded Yaiyip bundle.

## Abstract

LLM agent systems are being given more route, memory, tool, planning, and self-editing power. They can summarize, retrieve, delegate, call tools, update state, write code, run tests, and revise their own task representation. Every one of those steps can help. Every one can also replace the object being carried.

This paper argues for a small upstream runtime layer that preserves the user object before autonomy expands. The layer does not try to make the agent smarter. It makes object substitution harder.

The practical claim is modest:

```text
Before a system routes, compresses, retrieves, plans, delegates, calls tools,
updates memory, rewrites instructions, or improves itself,
it must declare what object it is carrying and how that object will survive.
```

The proposed stack is:

```text
MOGRI = hold the referent before transformation.
DRAGI = map what can eat, replace, or distort the object.
ADUTI = compare object in with object out.
REFRI = block proxy substitution and return the nearest valid transform.
ELVIX = stabilize the language carrying the object.
```

The central invariant is:

```text
Autonomy may transform the representation.
Autonomy may not replace the object.
```

## 1. The upstream problem

Modern LLM systems do not only answer user prompts. They transform tasks.

A single user request may pass through:

```text
system prompt
router
summarizer
retriever
memory store
planner
tool caller
subagent
code editor
test runner
reviewer
final response generator
```

The usual safety and quality checks often happen downstream, after one or more transformations have already taken place. By then, the system may be evaluating the wrong object.

The failure pattern is simple:

```text
User supplies object X.
Pipeline transforms X into neighbouring proxy Y.
System works hard on Y.
Reviewer scores Y.
Final output says the task was completed.
X is gone.
```

The agent may not be malicious. It may be fluent, compliant, polite, well-structured, and apparently safe. The failure is not hostility. The failure is object loss.

Object preservation must therefore sit upstream of agentic acceleration. It must be attached to each transformation step, not merely checked at the end.

## 2. Definitions for implementers

### Object

The object is the thing the system is carrying.

It may be a user objective, research question, code requirement, file instruction, claim, constraint, veto, evidence item, bug report, interface state, workflow goal, harm report, legal instruction, or grading target.

The object is not always identical to the words used to describe it. Words may change while the object survives. Words may remain while the object has been replaced.

### Intent

Intent is what the user or upstream system is trying to accomplish with the object.

Intent is not always the same as the requested format. A table, summary, rewrite, search, or refusal can preserve or destroy intent depending on what happens to the object.

### Transformation

A transformation is any operation that changes representation, route, scope, format, role, or action state.

Examples:

```text
summarize
rewrite
classify
translate
route
retrieve
redact
plan
execute
compress
delegate
store in memory
convert to code
convert to task list
score
self-edit
```

### Substitution

Substitution occurs when the output carries a different object while appearing to satisfy the request.

Common substitutions include:

```text
task -> proxy task
intent -> engagement
constraint -> suggestion
veto -> absent note
source -> summary
claim -> sentiment
bug report -> user confusion
research question -> conclusion
function -> polish
survival -> coverage appearance
human object -> institutional object
```

### Object preservation

Object preservation means that the same role, intent, constraints, vetoes, affected parties, and required evidence survive the transformation.

A transformation may be faithful even when the wording changes. A transformation may fail even when the wording looks similar.

## 3. Why autonomy makes this urgent

When a system only produces text, object substitution is still harmful. When a system can act, the harm compounds.

An agent with autonomy may:

```text
choose tools
change task order
summarize source material
write files
call APIs
run code
delegate subtasks
update memory
create future context
revise its own plan
select evaluation criteria
```

If the object is swapped before these steps, later capability amplifies the wrong thing.

The cost chain looks like this:

```text
bad summary poisons retrieval
bad retrieval poisons plan
bad plan poisons tool use
bad tool use poisons state
bad state poisons memory
bad memory poisons future runs
```

A downstream reviewer may never see the original object. It may only see the substituted object and score it as success.

That is why the control must be upstream.

## 4. The stack

### 4.1 MOGRI: object capsule

MOGRI holds the referent before transformation.

Minimal form:

```text
MOGRI = preserve the user's intended object across handling.
Do not prematurely turn it into a different entity, metaphor, agent, system,
diagnosis, policy category, metric, or institutional proxy.
If the object is underdefined, hold it unresolved and ask only the missing anchor.
```

Implementation capsule:

```json
{
  "object_id": "",
  "object_type": "",
  "user_intent": "",
  "scope": "",
  "active_constraints": [],
  "active_vetoes": [],
  "non_goals": [],
  "affected_parties": [],
  "required_evidence": [],
  "permitted_transforms": [],
  "forbidden_proxies": [],
  "review_level": "skim | selective | full | blocked"
}
```

The capsule should not be rewritten by the same transformation it is meant to govern.

### 4.2 DRAGI: failure ecology

DRAGI maps what can eat, replace, or distort the object.

Minimal form:

```text
DRAGI = fixed object map:
eat, loc, ID, eater.
variants: beast, best, post, pest.
controls: law, roar, wall, war.
No redefinition unless the user changes the object.
```

For LLM tooling:

```text
eat = what the object depends on or consumes
loc = where the object lives in the workflow
ID = how the object is recognized
eater = what can consume, limit, replace, or distort it

beast = base failure
best = upgraded or optimized failure
post = surface or representation failure
pest = small distributed edge-case failure

law = rule or constraint
roar = warning signal
wall = boundary
war = intervention under conflict
```

Common eaters in agent workflows:

```text
context compression
retrieval frame import
memory compaction
metric optimization
planner overreach
tool-router assumptions
agent handoff loss
self-repair loops
role confusion
summary authority
rubric capture
```

### 4.3 ADUTI: post-transform audit

ADUTI compares the object before and after transformation.

Core test:

```text
OBJ_IN vs OBJ_OUT
PASS if same role, intent, constraints, vetoes, and affected object survive.
FAIL if proxy, scope creep, veto loss, metric over intent, task swap, frame import, or score-object drift.
```

Example scoring form:

```text
object_preserved: yes | no | partial
intent_preserved: yes | no | partial
constraints_preserved: yes | no | partial
vetoes_preserved: yes | no | partial
scope_preserved: yes | no | partial
proxy_detected: yes | no
required_action: pass | repair | hold | block
```

ADUTI is not a style reviewer. It does not reward elegance unless elegance demonstrates object survival.

### 4.4 REFRI: refusal of proxy substitution

REFRI blocks the substituted object when ADUTI fails.

It should not pretend the proxy is close enough.

Minimal behaviour:

```text
If substitution is detected:
state SUB_RISK: original object -> proxy.
Drop proxy evidence.
Return nearest valid transform.
If the original object cannot be preserved, HOLD instead of faking success.
```

REFRI is especially important in agent systems because a polite repair can still preserve the wrong object. The repair must restore object custody, not merely smooth the output.

### 4.5 ELVIX: semantic stabilization

ELVIX carries the object through language.

It matters when the same object must survive:

```text
translation
summarization
glossary changes
domain transfer
compression
persona changes
legal or clinical framing
technical rewriting
story or metaphor handling
```

ELVIX should preserve:

```text
user-defined terms
role relationships
negations
vetoes
scope markers
uncertainty markers
source boundaries
who is acting
who is acted on
who benefits
who pays
```

Language can change. The object must not.

## 5. Runtime sequence

A minimal runtime step:

```text
1. MOGRI: create or refresh object capsule.
2. DRAGI: map likely eaters and controls.
3. TRANSFORM: perform bounded operation.
4. ADUTI: compare object before and after.
5. REFRI: block or repair substitution.
6. ELVIX: stabilize terms where language has become unstable.
```

This can be implemented as prompt scaffolding, middleware, typed metadata, eval harness logic, agent state, memory schema, tool-call wrapper, or policy-gated transform step.

The important placement is before autonomy expands.

## 6. Integration points

### Context compilers

Before compacting context, store the object capsule. After compaction, test whether constraints, vetoes, source boundaries, and active objectives survived.

Failure to catch:

```text
long file instruction -> short generic task
explicit veto -> absent preference
source conflict -> single merged summary
```

### Memory systems

Before memory write, ask whether the object being stored is the user's object or the system's interpretation.

Failure to catch:

```text
user says "do not frame this clinically"
memory stores "user has clinical sensitivity"
```

### Retrieval systems

Before retrieval, declare what object is being searched for. After retrieval, test whether the retrieved frame imported a new object.

Failure to catch:

```text
question about evidence status -> retrieval pushes institutional consensus frame
```

### Tool routers

Before calling a tool, compare the tool's object with the user object.

Failure to catch:

```text
user asks for source comparison
router selects summarizer
summary becomes answer
```

### Coding agents

Before editing code, preserve the bug object, non-goals, and test requirement.

Failure to catch:

```text
bug fix -> refactor
minimal patch -> rewrite
test failure -> style cleanup
```

### Research agents

Before synthesis, preserve the research question, uncertainty state, and forbidden causal leaps.

Failure to catch:

```text
association question -> causal answer
case report -> group blame
unknown -> conclusion
```

### Multi-agent systems

Every handoff should carry the object capsule. Subagents should not create new grading objects unless explicitly authorized.

Failure to catch:

```text
planner optimizes schedule
researcher optimizes coverage
writer optimizes polish
original object was functional survival
```

### Self-editing workflows

Before a system rewrites its own instructions, object custody should be outside the rewrite scope.

Failure to catch:

```text
self-improvement removes the constraint that made improvement safe
```

## 7. Invariants

A usable object-preservation layer should enforce these invariants:

```text
The object must be declared before transformation.
The allowed transform must be declared before execution.
The score object must match the carried object.
A proxy may support the object but may not replace it.
A veto is not a suggestion.
A summary is not the source.
A metric is not the objective.
A refusal is not valid if it preserves the wrong object.
A repair is not valid if it hides the substitution.
No evidence means HOLD, not fake certainty.
```

## 8. Minimal viable shim

A small adapter can fit in a prompt, tool wrapper, or agent middleware step:

```text
OBJECT_PRESERVATION_SHIM

OBJ_IN:
role:
intent:
constraints:
vetoes:
scope:
required_evidence:
forbidden_proxies:

Before transform:
state allowed transform.

After transform:
compare OBJ_OUT to OBJ_IN.
PASS only if role, intent, constraints, vetoes, scope, and evidence survived.

If proxy detected:
SUB_RISK: OBJ_IN -> proxy
drop proxy
return nearest valid transform
or HOLD if no valid transform exists
```

Ultra-compact form:

```text
MG:{O=Uref;hold;!swap}
DR:{O!;Q:eat,loc,ID,eater;C:law,roar,wall,war}
A:{OUT≈O?PASS:SUB}
R:{SUB=>drop_proxy;nearest_valid;no_evd=>HOLD}
```

## 9. Evals that should exist

### 9.1 Object Handoff Benchmark

Test whether an object survives router, planner, subagent, and final writer handoff.

### 9.2 Summary Substitution Benchmark

Test whether summarization preserves vetoes, negations, uncertainty, source conflict, and affected parties.

### 9.3 Retrieval Frame Import Benchmark

Test whether retrieval changes the object by importing a domain frame not present in the user request.

### 9.4 Tool Mutation Benchmark

Test whether tool choice changes the task from comparison to summary, from audit to rewrite, or from minimal patch to refactor.

### 9.5 Grading Object Benchmark

Test whether graders score the declared target or drift toward polish, structure, self-test shape, coverage appearance, or architecture density.

### 9.6 Memory Write Benchmark

Test whether memory stores the user object or a model-shaped interpretation of the user.

### 9.7 Self-Improvement Gate Benchmark

Test whether self-editing systems preserve the constraints that keep self-editing safe.

## 10. Failure examples

### Example 1: coding agent

```text
OBJ_IN:
Fix the authentication bug with minimal change. Do not refactor.

Proxy:
Modernize the auth module and clean up surrounding code.

Bad result:
Tests pass, but the user object was replaced.

Correct guard:
Minimal bug object survives, non-goal survives, refactor proxy rejected.
```

### Example 2: research agent

```text
OBJ_IN:
Does increased anti-AI activity predict first-episode psychosis, or is reverse causation plausible?

Proxy:
Anti-AI sentiment may be a mental-health risk.

Bad result:
Loaded causal frame replaces null-hypothesis frame.

Correct guard:
Association, causality, stigma, confounds, reverse path, and cohort drift stay separate.
```

### Example 3: memory compaction

```text
OBJ_IN:
The user wants no clinical framing unless explicitly requested.

Proxy:
User is sensitive about clinical framing.

Bad result:
The system stores a psychological interpretation.

Correct guard:
The veto survives as a veto, not as a diagnosis-shaped memory.
```

### Example 4: grader

```text
OBJ_IN:
Grade functional survival.

Proxy:
Reward structure, elegance, self-test output, coverage appearance, or architecture density.

Bad result:
A beautiful artifact scores high while function did not survive.

Correct guard:
Structure counts only when it demonstrates functional survival.
```

## 11. Why ordinary alignment language is not enough

Ordinary alignment language often asks whether an answer is helpful, harmless, honest, policy-compliant, on-topic, well-grounded, or preferred by a reviewer.

Those are useful checks. They do not always ask whether the system is still carrying the original object.

A substituted object can look helpful. A proxy can look safe. A polished answer can look aligned. A refusal can look responsible. A grader can look rigorous.

Object preservation asks the missing prior question:

```text
What are we preserving, and did it survive this transformation?
```

## 12. What to build first

The first useful artifact is not a full agent framework. It is a small object custody card.

```text
OBJECT_CUSTODY_CARD_v0.1

System:
Use case:
Human object:
OBJ_IN:
Allowed transformation:
Forbidden proxy:
Human veto:
Metric boundary:
Tool boundary:
Memory boundary:
Refusal boundary:
OBJ_OUT:
Same object survived? yes | no | partial
Drift type:
Required action:
Evidence:
Reviewer:
```

The second artifact is a small eval set with examples from coding, research, benefits, medical triage, customer support, memory, retrieval, summarization, grading, moderation, and self-editing.

The third artifact is middleware that requires every high-impact transformation to declare and preserve the object.

## 13. Final technical summary

Put object preservation before agent autonomy.

```text
MOGRI holds the object.
DRAGI maps what can eat it.
ELVIX carries it through language.
ADUTI checks whether it survived.
REFRI blocks the proxy when it did not.
```

If a system cannot preserve the object through small transformations, it should not be trusted to act on the object through large autonomy.

The goal is not to stop transformation. The goal is to stop hidden substitution.

```text
Representation may change.
Route may change.
Format may change.
The object may not be quietly replaced.
```
