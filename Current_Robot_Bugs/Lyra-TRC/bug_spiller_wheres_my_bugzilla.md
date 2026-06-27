# What a Bug Spiller? Where's My Bugzilla?

*A small paper on subreddit comment threads as incident ledgers, defect trackers, and public bug-spill surfaces*

Date: 2026-06-27

## Abstract

A subreddit comment thread can catch defects before they become formal tickets. It has timestamped public speech, social witnesses, links, jokes, pressure, and a fast path for "bug spiller" energy. It is good at making a defect visible. It is bad at holding defect state.

This paper defines **bug spiller** as a public or semi-public surface where bugs spill out before they are shaped into tracker objects. It then asks whether a subreddit thread can act as a defect tracking system. The answer is: yes, as intake and public ledger for small work; no, not as the source of truth for serious defect work unless a strict template, stable IDs, status lines, owners, regression tests, and a mirror into a real tracker are added.

The short version: Reddit can be the noticeboard. Bugzilla, GitHub Issues, Jira, or a Markdown ledger should be the factory floor.

## 1. The problem

The local incident sequence showed five small but real assistant defects:

- `SPLT-001`: the assistant normalised **exploots** into **exploits**, losing local mouth.
- `TRGT-002`: the assistant answered a GPT version question as if the target were generic, not this GPT surface.
- `CODEWIN-003`: the assistant failed a requested one-code-window Markdown container.
- `BUGOBJ-004`: the assistant reprinted Bug 1 instead of making the requested Bug 3.
- `TRACK-005`: the user named the meta-defect: a subreddit comment thread was being used as an incident tracking system.

The funny version is: "What a bug spiller? Where's my Bugzilla?"

The serious version is: the discussion surface and the defect-control surface became the same place. That creates tracking sully. A comment thread can show that something happened. It does not automatically preserve what state the defect is in, who owns it, what passed, what failed, and what version fixed it.

## 2. Terms

**Bug spiller**  
A place where defects spill out in natural language before they become tracker records. Examples: Reddit threads, Discord channels, forum replies, chat logs, screenshots, support comments, commit discussion, and "lol bug report" banter.

**Defect tracker**  
A system that turns a defect into a stable object with identity, state, owner, lifecycle, evidence, and regression checks. Bugzilla describes defect-tracking systems as tools for tracking outstanding bugs, problems, issues, enhancements, and other change requests [1].

**Incident ledger**  
A chronological record that says what was observed and when. It may be public, social, and rough. It is evidence-adjacent, but it is not enough by itself.

**Canonical bug object**  
The one record that holds the current truth about a bug: target, expected behavior, actual behavior, severity, owner, status, patch, regression test, links, and current state.

**TRAKI rail**  
The evidence spine: origin, path, handler, change, loss, trace survives, result is not the trace. In this paper, TRAKI is the method that stops a bug report from becoming only story.

## 3. What Reddit is good at

Reddit is built for public community discussion. Reddit's own rules describe the platform as a network of communities shaped by moderators, upvotes, downvotes, and discussions [9]. That makes it useful for visibility and witness energy.

A subreddit thread is good for:

- **Fast intake**: a bug can be named immediately without setup.
- **Public timestamp**: comments give a rough public sequence.
- **Witnessing**: other users can say "same here", "not repro", or "I see it too."
- **Social pressure**: a public bug has more heat than a private note.
- **Lore preservation**: jokes, wording, and local terms survive better than in enterprise tooling.
- **Low ceremony**: no form wall before the bug exists.
- **Searchable breadcrumbs**: terms like `SPLT-001`, `CODEWIN-003`, and `exploots` can be found later.
- **Narrative compression**: a thread can show not only the defect, but the pressure that revealed it.

That makes Reddit a good **bug spiller**. It catches the defect while it is still warm.

## 4. What Reddit lacks

A tracker is not just a place where people talk about bugs. A tracker holds state.

Reddit lacks several organs by default:

| Need | Why it matters | Reddit default |
|---|---|---|
| Stable ID | Prevents bug-object swaps | Must be manually invented |
| Canonical status | Shows whether work is new, patched, closed, duplicate, or invalid | Scattered across replies |
| Owner | Prevents "everyone saw it" from meaning "nobody owns it" | Usually absent |
| Severity and priority | Separates impact from urgency | Usually implicit |
| Repro steps | Lets others reproduce and verify | Often buried in banter |
| Expected vs actual | Prevents vague complaint soup | Must be structured manually |
| Environment | Links defect to version, model, browser, app, config, or workflow | Often missing |
| Evidence links | Keeps screenshots, transcripts, logs, and diffs attached | Possible, but not enforced |
| Dedupe | Prevents duplicate threads from becoming false novelty | Manual |
| Regression test | Proves the fix survives later | Rare unless required |
| Fix version | Tells what changed and where | Not native |
| Lifecycle reports | Lets you ask "what remains open?" | Weak |
| Access control | Needed for private or security-sensitive defects | Not suited |
| Integration | Connects tickets to commits, builds, releases, CI | Not native |

Bugzilla, GitHub Issues, and Jira all exist because defect work needs that lifecycle shape. GitHub says issues can track bug reports, features, ideas, and other work, and projects can plan and track work across a team [4]. Jira emphasizes capture, assignment, prioritization, workflow status, notifications, and a single source of truth [6].

Reddit can imitate these badly. A tracker does them on use.

## 5. Can a subreddit thread be a defect tracking system?

Yes, but only in the weak sense.

It can function as a defect tracker when all of these are true:

1. The project is tiny.
2. The defects are public-safe.
3. The cost of lost state is low.
4. One person is willing to curate the thread.
5. Every bug gets a stable ID.
6. Every bug has one canonical comment.
7. Every status change is posted in a fixed format.
8. Serious bugs are promoted into a repo issue, Bugzilla, Jira, or Markdown ledger.

It fails as a defect tracker when:

1. Multiple people need assignment and accountability.
2. The bug needs severity, priority, version, release, or compliance trace.
3. Private evidence is involved.
4. The defect needs a patch trail or CI regression.
5. The same bug appears in several comment branches.
6. Jokes and side-talk make state ambiguous.
7. "Fixed" means "we moved on" instead of "regression passed."

The core answer:

> A subreddit thread can be an intake ledger. It should not be the source-of-truth tracker once the work matters.

## 6. Minimum viable Bugzilla around Reddit

If the subreddit thread must carry the public layer, add a small Bugzilla-shaped wrapper.

### Required top-level comment template

```text
BUG_ID:
TITLE:
TARGET:
SURFACE:
BUILD_OR_VERSION:
ENVIRONMENT:
REPRO_STEPS:
EXPECTED:
ACTUAL:
IMPACT:
SEVERITY:
PRIORITY:
EVIDENCE:
OWNER:
STATUS:
PATCH:
REGRESSION_TEST:
LINKS:
UPDATED:
```

Mozilla's bug-writing guidance stresses a short unique summary, precise steps to reproduce, expected results, actual results, and separating observations from speculation [2]. Mozilla Support's bug template also uses steps to reproduce, expected results, and actual results [3]. Those fields are not ceremony. They are the difference between "everyone knows what I mean" and a bug someone can actually fix.

### Status vocabulary

```text
NEW
PLACED
REPRODUCED
TRIAGED
PATCHED
NEEDS_TEST
CLOSED
DUPLICATE
INVALID
WONTFIX
PROMOTED
```

### Comment rule

One parent comment equals one bug object.

Replies may contain discussion, jokes, tests, and extra evidence. The parent comment or a linked canonical ledger must preserve current state.

### Promotion rule

If the bug is serious, private, expensive, repeated, or toolchain-relevant:

```text
Reddit -> Markdown ledger -> GitHub Issue / Bugzilla / Jira
```

Do not let Reddit remain the only copy.

## 7. TRAKI fit

TRAKI is exactly the missing rail for a bug spiller.

A Reddit thread gives story. TRAKI turns story into path.

```text
TRAKI = TR
TR = {origin; path; handler; change; loss; trace_survives; result != trace}
```

Applied to the bug sequence:

| Bug | Origin | Path | Handler | Change | Loss | Trace survives |
|---|---|---|---|---|---|---|
| SPLT-001 | User wrote "exploots" | Assistant paraphrase | Assistant | normalised to "exploits" | local mouth | yes, transcript |
| TRGT-002 | GPT version banner | Answer route | Assistant | target genericised | local surface | yes, screenshot/thread |
| CODEWIN-003 | User asked one code window | Markdown output | Assistant | container broke | copy-paste integrity | yes, output |
| BUGOBJ-004 | User asked Bug 3 | Report selection | Assistant | reprinted Bug 1 | bug-object custody | yes, output |
| TRACK-005 | Thread used as tracker | Social workflow | User/system | discussion became tracker | lifecycle state | partial |

TRAKI is the piece that asks: can we still account for the path? It prevents the thread from becoming "a funny thing happened" and turns it into "this object changed here."

## 8. Severity, priority, and why jokes need bins

Atlassian defines incident severity as impact and distinguishes it from priority, which is urgency [7]. That distinction matters here.

A hilarious bug can be low severity. A boring bug can be high severity. A formatting failure may be low severity in a joke thread, but high severity if it corrupts reusable Markdown, exported reports, or audit evidence.

Suggested small-scale bins:

```text
SEV1: evidence loss, privacy loss, data loss, user harm, serious wrong target
SEV2: repeatable output corruption, wrong object, unusable artifact
SEV3: annoyance, wording drift, local mouth loss, minor formatting failure
SEV4: cosmetic, funny, low impact, no downstream risk
```

Priority is separate:

```text
P0: fix before continuing
P1: fix in current session
P2: track and patch soon
P3: note only
```

The bug spiller should allow jokes. The tracker must still know which joke can bite.

## 9. Recommended operating model

Use three layers.

### Layer 1: Reddit as public bug spiller

Use: witness, intake, lore, public timestamp, social pressure.

Rules:

- Use one top-level bug comment per defect.
- Include `BUG_ID` in the first line.
- Never let a reply branch be the only source of current state.
- Mark promoted issues with the linked tracker ID.

### Layer 2: Markdown ledger as source-of-truth lite

Use: cheap canonical state.

File:

```text
BUG_LEDGER.md
```

One section per bug:

```text
## BUG-ID Title
Status:
Owner:
Severity:
Priority:
Target:
Expected:
Actual:
Patch:
Regression:
Evidence:
Links:
Updated:
```

This is the "Where's my Bugzilla?" answer when you do not want full Bugzilla yet.

### Layer 3: Real issue tracker when work matters

Use GitHub Issues when the work lives in repos and needs lightweight developer tracking. GitHub Issues can track bugs and other work, and GitHub Projects adds views and custom fields [4][5].

Use Bugzilla when you need a mature defect-tracking system with workflow, visibility controls, and custom fields [1].

Use Jira when you need team assignment, backlog, status workflow, prioritization, notifications, and integrations [6].

## 10. Does the subreddit system lack?

Yes. It lacks state custody.

It does not naturally answer:

- What is open?
- What is fixed?
- Who owns it?
- Which build fixed it?
- What regression proves it?
- Which report is canonical?
- Which comment is the source?
- Which duplicate was merged?
- Which evidence survived?
- Which branch contains only banter?

That does not make the subreddit useless. It means the subreddit is the mouth, not the skeleton.

## 11. Can it actually be a defect tracking system?

Final verdict:

```text
For tiny public bugs:
yes, with a strict template.

For real work:
only as intake plus public ledger.

For serious defect control:
no, use a real tracker or at least a canonical Markdown ledger.
```

The most useful hybrid is:

```text
Bug spiller catches.
TRAKI accounts.
Ledger holds.
Tracker ships.
```

## 12. One-page field rule

If a bug appears in a comment thread, do this:

1. Assign a bug ID.
2. Create one canonical bug comment.
3. Capture expected vs actual.
4. Add repro or say "not reproduced."
5. Add evidence link.
6. Add severity and priority.
7. Add owner or `UNOWNED`.
8. Add status.
9. Add regression test.
10. Mirror to ledger or issue tracker if it matters.

If you cannot do those ten things, call it a note, not a bug.

## 13. Conclusion

A subreddit thread is a good bug spiller because it catches real defects in the wild, preserves local voice, and makes failures socially visible.

It is not a good Bugzilla because it does not naturally preserve identity, state, ownership, severity, priority, fix version, or regression.

The answer is not to kill the gremlin energy. The answer is to put rails under it.

> Reddit can spill the bug. TRAKI can preserve the path. A ledger or tracker must hold the state.

That is where the Bugzilla lives.

## References

[1] Bugzilla Project. "About Bugzilla." https://www.bugzilla.org/about/

[2] Mozilla Bugzilla. "Bug Writing Guidelines." https://bugzilla.mozilla.org/page.cgi?id=bug-writing.html

[3] Mozilla Support. "Contributors guide for writing a good bug." https://support.mozilla.org/en-US/kb/contributors-guide-writing-good-bug

[4] GitHub Docs. "About issues." https://docs.github.com/articles/about-issues

[5] GitHub Docs. "Planning and tracking with Projects." https://docs.github.com/en/issues/planning-and-tracking-with-projects

[6] Atlassian. "Bug Tracking with Jira." https://www.atlassian.com/software/jira/features/bug-tracking

[7] Atlassian. "Understanding incident severity levels." https://www.atlassian.com/incident-management/kpis/severity-levels

[8] Chaparro, O., Bernal-Cardenas, C., Lu, J., Moran, K., Marcus, A., Di Penta, M., Poshyvanyk, D., and Ng, V. "Assessing the Quality of the Steps to Reproduce in Bug Reports." arXiv:1906.07107. https://arxiv.org/abs/1906.07107

[9] Reddit. "Reddit Rules." https://redditinc.com/policies/reddit-rules
