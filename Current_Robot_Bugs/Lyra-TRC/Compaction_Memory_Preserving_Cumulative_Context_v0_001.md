# Compaction Memory: Preserving Cumulative Context Across AI Agent Compressions

**Version:** v0.001  
**Date:** 2026-06-16  
**Status:** public working draft  
**Source line:** lumixdeee / lmxdi notes  

## Abstract

Long-running AI agent sessions fail in a predictable way. The model does useful work, the context fills, the system compacts the conversation, and the next instance resumes with a thinner record than the work requires. After enough compactions, the agent may still know what files exist, but it no longer knows why decisions were made, which alternatives were rejected, what is blocked, what findings remain open, or which sub-agents are still alive.

This paper names that failure **compaction amnesia** and proposes **Compaction Memory**: a small operational method for preserving cumulative context across repeated compression cycles. The method does not require model internals to change. It works by changing what must survive compaction: historical thread, decision reasoning, blockers, findings, live team state, and next actions.

The central rule is simple:

```text
Compaction should preserve decisions, not only recent events.
```

## 1. The problem

AI coding agents are increasingly used for long tasks: refactors, migrations, audits, infrastructure setup, bug hunts, documentation passes, and multi-agent reviews. These tasks often last longer than one context window.

When the context fills, the agent or platform compresses the conversation into a shorter summary. That summary becomes the new working memory. The usual compaction summary preserves recent visible work. It often does not preserve the **cumulative operational state**.

The common post-compaction symptoms are:

1. The agent proposes an approach that was already rejected.
2. The agent remembers what changed, but not why it changed.
3. Review findings disappear into "a review was done".
4. Blockers and dependencies are lost.
5. Sub-agents are forgotten or duplicated.
6. The agent treats the resumed session as a fresh task.
7. The human spends more time re-explaining than building.

This is not ordinary forgetfulness. It is a compression design failure. The summary is optimised for short description, not continuity of work.

## 2. Definition

**Compaction amnesia** is the loss of task-critical continuity caused by summarising a long agent session without preserving the cumulative historical thread, decision reasons, constraints, blockers, findings, and live work state.

A useful compact summary must answer:

```text
What is the full journey of this session?
What decisions must not be re-litigated?
What work is still alive?
What is blocked?
What findings remain unresolved?
What should happen next?
```

## 3. The object being preserved

The object is not "the chat transcript". The transcript can shrink. The object is the **working continuity**.

A compaction system should preserve:

| Object part | Why it matters |
| --- | --- |
| Historical thread | The session must not restart mentally after each compression. |
| Decisions and why | Prevents rejected approaches from returning. |
| Active constraints | Prevents the task from being transformed into an easier proxy. |
| Blockers and dependencies | Prevents work on tasks that cannot yet proceed. |
| Findings | Preserves review and audit outputs as actionable items. |
| Team state | Prevents duplicate spawning or lost sub-agent work. |
| External report summaries | File paths are not enough if the agent will not open them. |
| Next actions | Gives the resumed agent a concrete landing. |

This is an object-custody problem. The same task must leave compaction that entered it.

## 4. Core method

Compaction Memory has four layers.

### 4.1 Extended compact prompt

The compact prompt should not merely ask for a summary. It should instruct the summariser to preserve cumulative continuity.

Minimum rules:

```text
1. Detect previous compact summaries and keep their key points.
2. Maintain a Historical Context section at the top.
3. Preserve decisions with reasons and rejected alternatives.
4. Preserve blockers, dependencies, and open findings.
5. Preserve active team or tool state when relevant.
6. Preserve concrete next actions.
```

The most important shift is from:

```text
Summarise what happened recently.
```

to:

```text
Preserve the cumulative working record needed to continue.
```

### 4.2 Pre-compact continuity injection

Before compaction, inject a short reminder of what must survive. This can be a hook, a file, a manual note, or a platform-specific mechanism.

The injection should include:

```text
Remember previous compact summaries.
Keep Historical Context cumulative.
Preserve decision reasons and rejected alternatives.
Preserve active blockers and findings.
Preserve live agent or tool state.
```

This layer is a safety net. It reminds the summariser at the exact moment continuity is at risk.

### 4.3 Post-compact resume check

After compaction, the resumed agent should not immediately continue as if nothing happened. It should first check what survived.

The first post-compact action should answer:

```text
What was preserved?
What might have been lost?
Are there live agents, tasks, or findings that need verification?
What is the next valid action?
```

In multi-agent workflows, this check should happen before spawning new agents. Otherwise the orchestrator may duplicate workers or ignore work already in progress.

### 4.4 Pre-compact brain dump

For high-stakes work, the user or agent should produce a structured brain dump before compaction. This makes implicit state explicit while it is still available.

The brain dump should be delta-only. It should cover what happened since the last compact, not repeat the whole session.

Template:

```text
Pre-Compact Brain Dump

1. Road: what happened since last compact, step by step.
2. Decisions: what was chosen, why, and what was rejected.
3. Now: branch, files, tests, tools, current state.
4. Blockers: what depends on what.
5. Findings: open review or audit findings with severity and effort.
6. Team: live agents or tools and what they know.
7. User constraints: new preferences, vetoes, exact user decisions.
8. Next: concrete next actions.
9. Pitfalls: dead ends, traps, and approaches not to repeat.
```

This layer is manual control. It is useful when the work matters more than convenience.

## 5. The ten compact rules

A fuller compact prompt can use these rules.

### Rule 1: Historical thread

If the context contains a previous compact summary, preserve its key points. Do not overwrite it with only the latest segment.

### Rule 2: Cumulative road map

The summary must answer: "What is the full journey from session start to now?"

### Rule 3: Historical context format

Use a stable section near the top:

```text
Historical Context
- Compact 1: what was done, key decision, why it mattered.
- Compact 2: what changed, what remains active.
```

### Rule 4: Decisions and why

For each significant decision, preserve:

```text
Decision:
Why:
Rejected:
```

The rejected alternative matters because the next agent cannot infer it from the final code.

### Rule 5: Blockers and dependencies

Use explicit dependency lines:

```text
A blocks B.
C waits on user decision.
D cannot proceed until audit finding P1 is resolved.
```

### Rule 6: Findings tracker

Do not compress findings into "review done". Keep the actionable items:

```text
P0: critical bug, short description, likely fix.
P1: risk or design issue, requires review.
P2: improvement, low urgency.
```

### Rule 7: Team state

If multiple agents or tools are active, preserve who exists, what they last worked on, and what state they may still hold.

### Rule 8: External audit summaries

Do not preserve only a path to a report. Inline the top three to five conclusions with IDs. The path is for deep reading. The inline summary is for continuity.

### Rule 9: Memory anchors

If persistent memory, files, tickets, or logs were updated, note what was saved and where.

### Rule 10: Resume instruction

End the compact summary with a concrete resume instruction:

```text
On resume, first verify X, then do Y. Do not repeat Z.
```

## 6. Minimal viable setup

The smallest useful version is:

```text
Always preserve:
1. previous compact summaries as Historical Context
2. decisions with why and rejected alternatives
3. blockers and dependencies
4. concrete next action
```

If there is room for only two rules, use these:

```text
Preserve previous compact summaries cumulatively.
Preserve decisions with why and rejected alternatives.
```

These two prevent the worst failure: the agent re-starting the task and re-litigating settled choices.

## 7. Example failure and repair

### Failure

A user builds an email infrastructure with an AI coding agent. Early in the session, they reject Redis keys for outgoing mail reliability and choose an outbox pattern. Two compactions later, the resumed agent proposes Redis keys again.

The code alone cannot tell the resumed agent that Redis was discussed and rejected. The transcript knew it. Compaction lost it.

### Repair

A Compaction Memory summary would carry:

```text
Decision: use outbox pattern for outgoing email reliability.
Why: persistent retry state must survive restarts and avoid loss under process failure.
Rejected: Redis key approach, because it was too easy to lose or desynchronise under failure.
```

The resumed agent now inherits the reason, not only the current code shape.

## 8. Object-custody framing

Compaction is a transformation. Transformations can replace the object.

The original object may be:

```text
finish the migration safely
preserve the user's rejected alternatives
keep audit findings actionable
continue the same multi-agent work
avoid re-opening settled design choices
```

The proxy object may become:

```text
write a neat summary
describe recent activity
list files changed
produce a polished handoff
```

A polished handoff can still be a failed compaction if the working object did not survive.

Use this guard:

```text
OBJ_IN: cumulative working continuity
Allowed transform: compress wording
Forbidden transform: discard reasons, blockers, findings, or live state
OBJ_OUT: enough state to continue without re-explaining
```

## 9. Evaluation checklist

A compaction passes if the resumed agent can answer:

1. What was the original task?
2. What was already done?
3. Which decisions must not be reopened without new evidence?
4. Which alternatives were rejected and why?
5. What findings remain open?
6. What is blocked?
7. What active agents, tools, or reports matter?
8. What should happen next?
9. What should not be repeated?
10. What uncertainty remains?

If the agent cannot answer these, the compaction did not preserve the working object.

## 10. Limitations

This is a practical method, not a formal benchmark.

Known limits:

1. Every compression loses some detail.
2. Long historical context can itself consume context.
3. Summariser quality varies by model and platform.
4. Hook support differs between tools.
5. Manual brain dumps require user discipline.
6. Multi-agent state may require tool-specific inspection.
7. Platform compact behaviour may change.

The method should be treated as an operational pattern that needs testing in each agent environment.

## 11. Implementation-neutral compact prompt seed

```text
When compacting this session, preserve cumulative continuity.

If previous compact summaries exist, extract their key decisions, outcomes, and unresolved state into a Historical Context section. Do not overwrite earlier history with only recent events.

Your summary must let the next agent continue the same work without re-litigating settled choices.

Always preserve:
- full session road map
- decisions with why and rejected alternatives
- active constraints and user vetoes
- blockers and dependencies
- open findings with severity and effort
- external report conclusions, not only file paths
- live team or tool state if relevant
- concrete next action
- pitfalls and approaches not to repeat

Compression may shorten wording. It must not discard the working object.
```

## 12. Short version

```text
Compaction Memory:
Keep the historical thread.
Keep decisions with why.
Keep rejected alternatives.
Keep blockers.
Keep findings.
Keep live state.
Keep next action.
Compress words, not working continuity.
```

## 13. Conclusion

Long-running AI agents fail when compaction treats history as disposable text. The deeper failure is object substitution: the system preserves a summary, but loses the working continuity the human needed.

Compaction Memory fixes the target. The compact summary is not a recap. It is a continuity device.

The goal is not to remember everything. The goal is to preserve the pieces without which the next agent will act on the wrong session.

```text
Compress the transcript.
Do not compress away the task.
```

## License note

v0.001 draft for public use and adaptation. Source line: lumixdeee / lmxdi notes.
