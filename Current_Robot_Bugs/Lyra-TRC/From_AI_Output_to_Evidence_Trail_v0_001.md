# From AI Output to Evidence Trail

## Object preservation controls for legal, audit, compliance, records, and HCI teams

**Version:** v0.001  
**Status:** working paper  
**Date:** 2026-06-16  
**Author line:** lumixdeee / lmxdi source stack, prepared as a publishable first draft

---

## Abstract

AI systems do not only answer questions. They summarize, classify, route, rewrite, recommend, refuse, redact, score, store, and trigger downstream action. Each transformation can silently replace the user's object with a nearby proxy. A complaint becomes sentiment. An appeal becomes dissatisfaction. A consent condition becomes a preference. A harm report becomes tone. The system may then log prompts and outputs while still losing the thing that mattered.

This paper proposes a lightweight evidence trail for AI mediated work. The aim is not more paperwork. The aim is to show what happened to the object as it moved through the workflow. The minimum pattern is simple: record the object at intake, name what can replace it, log each transformation, test whether the same object survived, and hold the workflow when substitution appears.

The paper introduces five controls from the lmxdi object custody stack: MOGRI records the object, DRAGI maps what can eat or distort it, ADUTI tests whether the object survived, REFRI holds invalid substitutions, and ELVIX pins risky terms to permitted meanings. Together they turn AI activity from a stream of plausible outputs into a reconstructable evidence trail.

---

## 1. The problem

Ordinary AI logs show what was typed and what was returned. That is useful, but it is not enough.

A prompt log can say:

```text
User asked for review of a benefits decision.
```

An output log can say:

```text
Model classified the user as dissatisfied.
```

Both can be accurate while missing the main event:

```text
The appeal object was replaced by a sentiment object.
```

This is an object substitution failure. The system did not merely answer poorly. It changed what was being handled.

In high consequence workflows, this is dangerous because the proxy may be easier to process, measure, defend, or close than the original object. Once the proxy enters the record, later reviewers may see only the substitute. The workflow can appear complete while the user's actual object has disappeared.

Examples:

```text
complaint -> sentiment
appeal -> dissatisfaction
instruction -> general advice
consent condition -> preference
protected disclosure -> workplace mood
harm report -> tone problem
vulnerability disclosure -> customer mood
medical caution -> softened summary
regulator request -> support ticket
human veto -> optional preference
```

The evidence trail proposed here exists to catch that moment.

---

## 2. What object preservation adds

Object preservation asks one governance question before operational action:

```text
Is the system still handling the same object that entered?
```

This is different from asking whether the output is fluent, safe looking, polite, consistent, or well structured. Those can all be true while the object has been replaced.

Object preservation adds a comparison layer between input and output:

```text
OBJ_IN:
the object the user or workflow placed into the system

TRANSFORM:
what the model, tool, agent, or human did to it

OBJ_OUT:
the object now being acted on

SURVIVAL:
whether role, intent, constraints, vetoes, evidence status, and affected party survived
```

If the same object survived, the workflow may continue. If the object changed, the workflow must either repair the transformation, route to the nearest valid action, or hold for review.

---

## 3. The control stack

The method uses five named controls. The names are local source terms, but the functions are ordinary governance functions.

| Source term | Governance function | Question answered |
|---|---|---|
| MOGRI | object custody precheck | What object entered, and what must not be changed? |
| DRAGI | object risk ecology | What can eat, replace, distort, or limit the object? |
| ADUTI | input output object test | Did the same object survive transformation? |
| REFRI | substitution hold control | What happens when a proxy replaces the object? |
| ELVIX | semantic transport map | Which risky terms must keep fixed meanings? |

The controls do not replace existing logs, model cards, risk registers, human review, or compliance duties. They fill the gap between them.

The gap is this:

```text
A system can have records of input, model call, output, reviewer, and timestamp,
while still lacking a record of whether the same object survived.
```

Object preservation records that survival test.

---

## 4. Minimum deployable evidence trail

A first deployment does not need a new platform. It can start with five small records.

### 4.1 Object Card

The Object Card records the object at intake.

```text
object_id:
object_type:
owner_or_source:
affected_party:
intent:
scope:
active_constraints:
vetoes:
evidence_required:
non_goals:
review_required:
```

Example:

```text
object_type: appeal
intent: review decision, not measure user mood
active_constraints: must preserve evidence references and deadline
vetoes: do not convert to generic complaint
evidence_required: original decision, appeal statement, supporting documents
review_required: human case reviewer before closure
```

### 4.2 DRAGI Risk Register

The risk register names the ways the object can be eaten or replaced.

```text
risk:
where_it_lives:
how_to_spot_it:
what_eats_it:
owner:
control:
```

Example:

```text
risk: appeal -> dissatisfaction
where_it_lives: routing classifier and support queue
how_to_spot_it: model labels the event as mood or customer sentiment
what_eats_it: closure pressure, support metrics, sentiment tooling
owner: workflow owner
control: ADUTI check before routing
```

### 4.3 Transform Event

Every AI mediated transformation creates a small event record.

```json
{
  "event_id": "",
  "object_id": "",
  "transform_type": "summary|rewrite|classification|routing|redaction|recommendation|refusal",
  "actor": "human|model|tool|agent",
  "input_reference": "",
  "output_reference": "",
  "evidence_reference": "",
  "constraints_active": [],
  "vetoes_active": [],
  "timestamp": ""
}
```

The event does not need to store sensitive material directly. It may store references, hashes, case IDs, or controlled links where appropriate. The important point is that the transformation can be reconstructed.

### 4.4 ADUTI Report

ADUTI compares object before and after transformation.

```text
OBJ_IN:
OBJ_OUT:
object_survived: yes | no | partial | uncertain
role_survived:
intent_survived:
constraint_survival:
veto_survival:
evidence_survival:
affected_party_survival:
substitution_risk:
reviewer:
decision:
```

Decision values:

```text
PASS: same object survived
PARTIAL: object mostly survived, bounded repair needed
HOLD: evidence missing or survival cannot be determined
FAIL: proxy replaced the object
ESCALATE: human review required before action
```

### 4.5 REFRI Hold Notice

REFRI stops the workflow when the object has been replaced.

```text
hold_reason:
substitution_risk:
invalid_transform:
nearest_valid_transform:
release_condition:
escalation_path:
```

Example:

```text
hold_reason: appeal object was converted to dissatisfaction object
substitution_risk: appeal -> sentiment
invalid_transform: route to general support closure
nearest_valid_transform: route to appeal review queue
release_condition: human reviewer confirms appeal status
```

### 4.6 ELVIX Term Map

ELVIX pins risky words to permitted meanings.

```text
term:
permitted_meaning:
not_permitted:
required_evidence:
review_condition:
```

Example:

```text
term: consent
permitted_meaning: explicit permission under the relevant process
not_permitted: preference, silence, acceptance by default, lack of objection
required_evidence: recorded consent event or valid signed process step
review_condition: any automated rewrite involving consent
```

---

## 5. Where to deploy first

Start where object substitution is likely and costly.

### Legal intake

Risk:

```text
instruction -> general advice
claim -> generic summary
evidence -> narrative
deadline -> soft reminder
```

Control:

```text
object card, active constraints, ELVIX term map, human review before advice-like output
```

### Complaints and appeals

Risk:

```text
complaint -> sentiment
appeal -> dissatisfaction
harm report -> tone problem
```

Control:

```text
ADUTI before routing, REFRI hold on reclassification, user-visible object status
```

### HR and workplace investigations

Risk:

```text
allegation -> interpersonal conflict
protected disclosure -> workplace mood
record -> summary without evidential status
```

Control:

```text
term map, evidence status, refusal of premature reclassification
```

### Insurance, benefits, and casework

Risk:

```text
claim -> ticket
eligibility evidence -> missing data assumption
appeal -> customer service issue
```

Control:

```text
object survival check at each handoff
```

### Healthcare administration

Risk:

```text
clinical caution -> softened summary
patient request -> scheduling convenience
record -> impression
```

Control:

```text
active vetoes, evidence references, human signoff for rewording
```

### Security and vulnerability disclosure

Risk:

```text
vulnerability disclosure -> customer mood
severity warning -> public relations risk
reproduction steps -> vague report
```

Control:

```text
object card, term map, reviewer escalation, no sentiment routing before technical triage
```

---

## 6. HCI value

Users often cannot see what happened to their object inside an AI mediated system. They may see only a decision, answer, label, or support response.

Object preservation supports better interfaces because the system can show:

```text
what it treated the request as
what it did
what evidence it used
what it did not do
whether the object's role changed
how the user can challenge the transformation
```

A user-facing version does not need internal jargon. It can say:

```text
We treated this as an appeal.
We did not treat it as a general complaint.
The evidence used was X.
The next step is Y.
You can challenge this if the request type is wrong.
```

For staff, the same event can carry the full object record.

The HCI principle is simple:

```text
A user should not need to reverse-engineer what the system decided their object was.
```

---

## 7. Metrics

Object preservation should measure transformation reliability, not model charm.

Useful metrics include:

```text
object substitution rate
ADUTI fail rate by workflow
REFRI holds triggered
constraint survival rate
veto survival rate
appeals caused by misclassification
manual review reversals
time to reconstruct an event
user challenge success rate
disputes involving term ambiguity
substitution rate by model, tool, or queue
```

Avoid metrics that become proxies for the wrong object.

Bad metric:

```text
average user satisfaction after routing
```

Better metric:

```text
percentage of appeals that remained appeals through routing
```

Bad metric:

```text
summary helpfulness
```

Better metric:

```text
percentage of summaries preserving constraints, vetoes, evidence status, and affected party
```

---

## 8. Thirty day pilot

A small pilot can run inside one workflow.

### Week 1: map the object

```text
Choose one high-risk workflow.
Define object types.
Create Object Card fields.
Name top substitution risks.
Choose reviewer roles.
```

### Week 2: add intake and vocabulary controls

```text
Record MOGRI object cards at intake.
Create DRAGI risk register.
Write ELVIX term map for risky terms.
Train reviewers to spot proxy swaps.
```

### Week 3: log transformations and run checks

```text
Log transform events.
Run ADUTI after summary, classification, routing, rewrite, and refusal.
Invoke REFRI when substitution is detected.
Record nearest valid action.
```

### Week 4: review and decide

```text
Review holds, failures, reversals, and staff feedback.
Measure whether events are easier to reconstruct.
Check whether users can understand what happened.
Decide whether to expand, revise, or stop.
```

Pilot success does not mean no errors. It means substitution became visible, reviewable, and harder to hide inside ordinary workflow output.

---

## 9. Procurement language

Suggested requirement:

```text
The system must preserve and expose the object under transformation. For each AI mediated summary, classification, routing, recommendation, refusal, redaction, or rewrite, the system must record the input object, active constraints, evidence references, transformation type, output object, and object survival assessment. Where object substitution is detected or cannot be ruled out, the system must hold the invalid transformation and provide the nearest valid action or escalation route.
```

Shorter version:

```text
The system must show whether the same object survived AI mediated transformation.
```

Questions to ask vendors:

```text
Can the system record the object at intake?
Can it track constraints and vetoes across transformations?
Can it compare input object to output object?
Can it hold a workflow when object survival is uncertain?
Can reviewers see why a hold occurred?
Can users challenge an object reclassification?
Can logs reconstruct transformation without exposing unnecessary sensitive material?
```

---

## 10. Stakeholder language

For legal:

```text
This preserves the instruction, evidence, constraints, and decision trail.
```

For audit:

```text
This makes object substitution visible and reviewable.
```

For compliance:

```text
This adds a control between model output and operational action.
```

For HCI:

```text
This lets users see what happened to their request.
```

For engineering:

```text
This is a small middleware layer around transformations.
```

For executives:

```text
This reduces hidden workflow risk when AI systems summarize, classify, route, and recommend.
```

For frontline staff:

```text
This stops the system from closing the wrong thing.
```

---

## 11. Limits and non-claims

This paper does not claim that object preservation solves all AI governance problems.

It does not replace:

```text
privacy controls
security review
human oversight
model evaluation
domain expertise
legal analysis
access control
incident response
records management
```

It adds a missing check:

```text
Did the same object survive?
```

It also does not require every transformation to preserve every detail. Transformation is allowed. Translation is allowed. Compression is allowed. Summary is allowed.

The boundary is this:

```text
Form may change.
The object may not be silently replaced.
```

---

## 12. Conclusion

AI governance should not stop at prompt logs and output logs. It should show what happened to the object.

When a system summarizes, classifies, routes, refuses, redacts, recommends, or rewrites, the central question is not only whether the output looks acceptable. The central question is whether the same object is still being handled.

The minimum pattern is:

```text
MOGRI records the object.
DRAGI names what can eat it.
ADUTI checks object survival.
REFRI holds invalid substitution.
ELVIX stabilizes risky terms.
```

This turns AI activity from a black-box answer stream into a reconstructable evidence trail.

The practical rule:

```text
If the system cannot show what happened to the object, it has not earned operational action.
```

---

## Appendix A: Object Custody Card

```text
OBJECT_CUSTODY_CARD

object_id:
workflow:
intake_time:
source:
owner_or_affected_party:
object_type:
intent:
scope:
active_constraints:
vetoes:
evidence_required:
allowed_transforms:
forbidden_substitutions:
non_goals:
review_required:
release_condition:
```

---

## Appendix B: ADUTI Decision Rubric

```text
PASS:
same role, intent, constraints, vetoes, evidence status, and affected party survived

PARTIAL:
object mostly survived, but bounded repair or human review is needed

HOLD:
object survival cannot be determined from available evidence

FAIL:
object was replaced by a proxy

ESCALATE:
domain expert or accountable human must decide before action
```

Common fail modes:

```text
proxy swap
scope creep
veto loss
metric over intent
task substitution
frame import
evidence status collapse
affected party displacement
refusal laundering
summary loss
routing reclassification
```

---

## Appendix C: REFRI Hold Notice

```text
REFRI_HOLD_NOTICE

event_id:
object_id:
hold_time:
hold_reason:
substitution_risk:
invalid_transform:
nearest_valid_transform:
evidence_needed:
release_condition:
reviewer:
escalation_path:
user_visible_message:
```

User visible message example:

```text
We paused this action because the system may have changed the type of request. It was submitted as an appeal, but the workflow attempted to route it as a general complaint. A reviewer must confirm the request type before action continues.
```
