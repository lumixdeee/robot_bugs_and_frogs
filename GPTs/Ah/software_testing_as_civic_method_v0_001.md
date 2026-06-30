# Software Testing as Civic Method

## Bug reports for bureaucratic harm

**Version:** v0.001  
**Date:** 30 June 2026  
**Status:** working paper / method proposal  
**Author line:** lumixdeee / Julian Pursell with an internal workflow assistant  
**Public posture:** This edition uses public method language and source names. It does not expose private bot prompts, private carry blobs, or hidden runtime syntax.

## Abstract

Software testing is usually treated as a technical craft for finding defects in programs. Civic harm is usually treated as a policy, legal, administrative, ethical, or sociological problem. This paper argues that some civic harm can also be investigated with a tester's method, provided the method is translated carefully and does not reduce people to tickets. The civic value of testing is not that government, schools, welfare offices, platforms, or care systems are literally software. It is that software testing has a mature practice for noticing repeatable failure, preserving reproduction conditions, naming expected and observed behavior, separating severity from priority, recording environment, tracking regression, and refusing false confidence from blessed paths.

The proposed method is Software Testing as Civic Method. It treats a civic incident not as a private grievance to be dissolved into mood, nor as a total moral verdict on a person, but as a possible defect pattern in a working system. A civic bug report asks: what object entered the system, what path did it take, what actors or forms handled it, what outcome occurred, what should have happened, what burden or harm was produced, whether the failure can recur, and what repair would prevent recurrence without swallowing the person who reported it. The method joins internal work on bug spillers, independent testing, object custody, bot councils, lost civic affordance, and evidence boundaries with external work on software testing, street-level bureaucracy, administrative burden, classification, public-interest technology, and accountability.

The contribution is a small but practical bridge. Civic systems need more than values statements and after-the-fact complaint channels. They need defect records that preserve object, path, environment, boundary, and recurrence. Testing does not replace politics, law, care, organizing, or professional judgment. It gives them a sharper instrument: a way to say not only "this hurt" but "this system can produce this hurt again, under these conditions, unless this route is changed."

## 1. Introduction

A software tester asks a rude but useful question: what happens when the system is used in a way the builder did not bless?

The same question belongs in civic life. A welfare form, a school heat policy, a housing allocation process, a local authority phone line, a safeguarding intake route, a medical gate, a complaints procedure, a forum moderation rule, a court bundle, or a public consultation may all work on the path their designers imagined. They may still fail on the path real people take.

Civic institutions often know how to count caseloads, write procedures, publish principles, and process complaints. They are weaker at preserving the shape of a repeatable failure. A person says that a form blocked them, a route humiliated them, a label swallowed the offer, a staff member had no way to record the actual object, or a reasonable exception could not enter the system. The institution may answer with sympathy, denial, apology, triage, risk language, or a complaint number. The failure may be treated as an anecdote, personality clash, misunderstanding, or isolated bad day.

Software testing offers another route. It asks for reproduction steps, environment, expected result, observed result, severity, priority, logs, screenshots, version, regression risk, and owner. Those are not magic. They do not make a system just. They do something smaller and valuable: they preserve a failure as a route that can be inspected, compared, retried, and repaired.

This paper proposes Software Testing as Civic Method. The claim is not that civic systems are software. The claim is that testing practices can be translated into civic investigation when the object is repeatable institutional harm.

The method has three commitments.

First, the person is not the bug. A citizen, claimant, student, patient, tenant, worker, helper, parent, or staff member is not a defect object. The defect, if there is one, lies in the route: the form, handoff, category, queue, script, incentive, risk parser, burden, absence, or authority chain that produced the outcome.

Second, a civic report must preserve the object. A request for shade is not a request for unsupervised childcare. A transcript concern is not a personality profile of the speaker. A refusal to accept a proxy is not non-compliance. A bug report that swaps the object has already joined the bug.

Third, civic testing must remain accountable to harm and power. A tester can inspect a system without pretending neutrality. Some failures are dangerous because the system's ordinary path is working as designed for someone else. The method therefore separates reproduction from justification. To reproduce a harm route is not to excuse it. It is to make the route visible enough to alter.

## 2. Related Work

Software testing has long treated testing as more than button-pushing. Kaner, Bach, and Pettichord's context-driven testing tradition treats testing as skilled investigation, bug advocacy, documentation, and judgment under constraint [E1]. Kaner's "Software Testing as a Social Science" explicitly frames testing as inquiry into systems whose use, observation, and interpretation are social as well as technical [E2]. Bug reports and defect triage literature likewise treat a report as a structured object that must support reproduction, diagnosis, prioritization, and repair [E3][E4].

Public administration offers the civic side of the bridge. Lipsky's street-level bureaucracy frames front-line public service workers as policy makers in practice because they exercise discretion under caseload, ambiguity, resource limits, and human contact [E5]. Administrative burden scholarship shows that learning costs, compliance costs, and psychological costs can function as policy instruments, sometimes blocking access to public goods or rights [E6]. Recent reviews call for more work on how burdens are experienced in citizen-state interactions and how state action links to burden [E7].

Classification studies supply a second civic foundation. Bowker and Star show that categories and standards shape social worlds and carry consequences once embedded in infrastructure [E8]. Eubanks shows how data systems and administrative technologies can deepen social harm when they sort, profile, and punish poor and working-class people [E9]. Public interest technology and civic technology research ask how technical skill can serve public accountability and community needs, while warning that tools and process must remain tied to social context [E10][E11].

The missing bridge is testerly civic method. Public administration names discretion and burden. Classification studies name category harm. Civic tech names technical intervention for public ends. Software testing names repeatable failure, reproduction, environment, regression, and defect record. Software Testing as Civic Method asks how those tools can be used without turning people into tickets or civic life into a test lab.

## 3. Internal Source Stack

The local corpus already contains the pieces of this method. This paper joins them.

[I1] `bug_spiller_wheres_my_bugzilla.md` defines the bug spiller as a public or semi-public surface where defects spill out before they become tracker objects. It distinguishes intake and public notice from the factory floor of formal defect work.

[I2] `walking_the_name_of_god_independent_testing.md` names safe-path confidence inflation: systems pass blessed routes, expected prompts, tidy cases, and developer-shaped paths while failing under awkward, tired, corrected, socially messy, or locally named routes.

[I3] `bot_councils_towards_fairer_bureaucratic_cruelty_v0_001.md` argues that bureaucratic cruelty already exists and that the missing object is often route custody: who harmed, delayed, denied, humiliated, protected, overruled, or carried cost.

[I4] `The_Helper_Who_Must_Not_Appear_v0_002.md` names a civic pattern in which useful time, space, tools, local knowledge, land, shade, or skill is lost because the person carrying the offer is socially unreadable or risky to the parser.

[I5] `The_Unused_Tree_Lost_Civic_Affordance_v0_002.md` gives a concrete civic affordance case: the object is not the person; the object may be the tree, shade, route, gate, water plan, custody arrangement, and temporary use of nearby ground.

[I6] `Evidence_Is_Not_Person_v0_002.md` gives a boundary rule: a fragment, screenshot, note, quote, transcript excerpt, search result, or file can be evidence, but it may not wear the person's face.

[I7] `Object_Substitution_as_AI_Safety_Failure_Mode_v0_002.md`, `object_custody_for_ai_workflows_v0_001.md`, and `lmxdi/ADUTI/ADUTI-REFRI-DRAGI-ELVIX-MOGRI.md` provide the object-custody layer: object-in must be compared with object-out after transformation.

[I8] `Old_Film_Live_Lamp_Object_Custody_for_Long-Horizon_AI_Memory_public_v0_005.docx` supplies the active-state and source-role discipline that prevents archive from driving without role assignment.

[I9] `lmxdi/MARK/ABCD as Semantic Guerrilla Testing.md`, `lmxdi/MARK/Recursive Multi-Level Methodology v0_002.md`, and `lmxdi/chatgpt-perf-regressions.md` show testing as small live probes, comparison, public review, and regression record rather than decorative QA.

[I10] `lmxdi/RSOC/ABSTRACT` and related RSOC notes record a case where a software-tester methods claim about transcript preservation was displaced into suspicion about the speaker, tool use, and legitimacy. The case motivates the paper's rule that the carrier must not replace the method object.

## 4. What Software Testing Contributes

Software testing contributes a set of habits, not a metaphorical costume.

### 4.1 The system under test

Testing begins by identifying the system under test. In civic life this may be a school closure policy, a benefits application route, a GP reception script, a moderation appeal, a safeguarding form, a consultation process, a council email route, a housing queue, or the interaction among several of these.

The civic system under test is rarely one machine. It is a route across documents, people, buildings, scripts, schedules, judgments, categories, and missing options. The test method must therefore track path, handler, form, authority, and handoff. A bug may not live in any one worker. It may live in the gap between roles.

### 4.2 Environment

Software bugs often depend on environment: browser, operating system, version, network state, permissions, time, account type, feature flag, and data. Civic bugs also depend on environment.

A civic environment can include:

- office hours
- school term or holiday
- heatwave day
- staff shortage
- interpreter availability
- disability status
- immigration status
- income threshold
- prescription status
- local transport
- childcare responsibility
- digital access
- social readability
- prior label
- housing status
- whether the user is tired, frightened, angry, sanctioned, or in pain

The method does not use environment to blame the person. It uses environment to prevent the institution from pretending the blessed path was the real path.

### 4.3 Steps to reproduce

Steps to reproduce are not only technical instructions. They are a sequence of actions and states that can make a failure recur.

A civic reproduction sequence might be:

1. A parent receives a school heat closure message.
2. The school has no cool spare room.
3. A nearby adult can offer a shaded garden but not supervision.
4. The offer enters the system through a route that can only parse volunteers, staff, risk, or nothing.
5. The offer is lost because the person is unreadable, not because the shade is unusable.
6. The children remain without the possible shade option.

The reproduction does not need to expose a named person. It needs enough route detail that the civic defect can be tested again.

### 4.4 Expected and observed

Software reports separate expected behavior from observed behavior.

Civic reports need the same split.

Expected:

- the system receives the object offered
- the system assigns a bounded role
- the system keeps custody where custody belongs
- the system accepts, declines, or parks the offer with a reason
- the system records the path for future use

Observed:

- the offer is swallowed by risk language
- the helper becomes the object
- the asset disappears
- no decision path exists
- no one can say whether the offer was refused, ignored, or never parsed

This expected/observed split is powerful because it prevents moral fog. It does not require the report writer to prove bad motive. It asks whether the system's behavior matched the system's public function and the live object's role.

### 4.5 Severity and priority

Testing distinguishes severity from priority. A low-frequency failure may be severe. A common annoyance may be low severity but high repair priority because it affects many people.

Civic method needs that split. A paperwork loop that humiliates every applicant may be high priority even if no single case is catastrophic. A rare failure that removes medication, housing, access, custody, or legal standing may be high severity even if it happens once.

A civic defect report should not flatten all harm into one outrage score. It should name severity, recurrence risk, exposure, and repair cost separately.

### 4.6 Regression

A repaired bug can return. Regression testing asks whether a fix stayed fixed when the system changed.

Civic systems also regress. A new form can restore an old barrier. A staff turnover can erase local workaround knowledge. A policy announcement can leave the front-line script unchanged. A digital portal can remove a phone route. A new risk rule can make a previously usable civic affordance unusable again.

Civic regression tests should preserve old failure routes as probes. Not to trap staff, but to protect the public from the comforting fiction that a press release changed the floor.

## 5. What Must Not Be Imported

Software testing cannot be copied into civic life without translation.

First, people are not defects. A person can report a defect, be harmed by a defect, participate in a defect route, or be given too much discretionary power inside a defect route. They are not the bug object.

Second, reproduction must not become harm repetition. Some civic failures cannot be ethically reproduced in full. The method must allow bounded reconstruction, simulated forms, role-play with safeguards, document walkthroughs, anonymized route mapping, and post-incident trace rather than forcing people through harm again.

Third, a test pass is not justice. A system can pass a probe and still be unfair. Testing reveals failure. It does not settle politics.

Fourth, a defect report is not a court verdict. It can support accountability, but it should not pretend to determine guilt, diagnosis, danger, or intent unless the evidence permits that claim.

Fifth, testing language must not become institutional armor. A council, school, company, platform, or agency could use defect language to minimize harm: "only a bug." The method should resist that. A defect is not small because it is repeatable. Sometimes repeatability is the warning.

## 6. The Civic Bug Report

A civic bug report should be short enough to use and strong enough to survive handoff.

### 6.1 Minimal form

| Field | Question |
|---|---|
| ID | What stable handle names this defect route? |
| Title | What is the smallest exact name for the failure? |
| System under test | Which service, route, rule, office, form, or handoff is under test? |
| Reporter role | Citizen, staff, helper, observer, advocate, tester, other |
| Object-in | What object entered the system? |
| Environment | What conditions mattered? |
| Steps | What path did the object take? |
| Expected | What should have happened under the system's own aim? |
| Observed | What happened? |
| Harm or burden | What cost, delay, denial, humiliation, risk, or loss occurred? |
| Boundary | What should not be inferred from this report? |
| Recurrence | Could it happen again? Under what conditions? |
| Severity | How bad is the harm if it occurs? |
| Priority | How urgently should this route be changed? |
| Evidence | What fragments, documents, timestamps, screenshots, witness accounts, or logs support the report? |
| Unknowns | What is not known? |
| Next test | What small probe checks whether the route still fails? |
| Repair owner | Who can change the route? |
| Regression check | How will the repair be retested later? |

### 6.2 Object-custody version

The civic bug report should be paired with object custody.

| Custody field | Civic question |
|---|---|
| DOG | What live object is being handled? |
| ROLE | What role should the object have? |
| FUNCTION | What work must the report perform? |
| COAT | What surface form might be mistaken for the object? |
| COATI_RISK | How likely is coat-over-object substitution? |
| OBJECT_STATUS | Did the same object survive? |
| SOURCE_STATUS | What evidence path supports the claim? |
| BOUNDARY_STATUS | Did scope, role, and non-goals survive? |
| SUBSTITUTION_RISK | What proxy may have replaced the object? |
| NEXT_MOVE | What repair, hold, or test follows? |

This second table prevents a common civic failure: the report receives a label but loses the object.

## 7. Five Civic Defect Classes

### 7.1 Object substitution

Object substitution occurs when the system replaces the live object with a nearby object it can process.

Example: a person offers shade. The system reads "unsupervised adult access to children." The offer was not that. The object swapped.

Example: a person asks for transcript preservation in research. The forum reads "AI user seeking legitimacy." The object swapped.

Example: a person says a medical label should not replace the whole person. The system reads "person denies evidence." The object swapped.

Repair: state object-in and object-out. If they differ, hold action until the substitution is named.

### 7.2 Safe-path confidence inflation

Safe-path confidence inflation occurs when a system passes the tidy path and treats that as proof the system is good.

Examples:

- A form works for citizens with stable addresses, broadband, ordinary names, no trauma, and the correct documents.
- A school policy works on ordinary temperature days, not heatwave days.
- A consultation process works for confident insiders, not for people with route-breaking experience.
- A chatbot passes blessed prompts, not tired-user correction chains.

Repair: test awkward, realistic, boundary, and tired paths. Test the path the public actually takes, not only the path the designer can walk.

### 7.3 Burden as hidden behavior

Administrative burden often hides as paperwork, waiting, uncertainty, repeated proof, travel, phone queues, shame, or fear. A system can look open while burden blocks access.

Repair: record burden as observed behavior. If the user must learn the rule, gather documents, call three offices, absorb humiliation, or risk sanction, that is not background. It is part of the route.

### 7.4 Carrier substitution

Carrier substitution occurs when the person carrying the claim replaces the claim.

Examples:

- The helper is treated as the object rather than the asset.
- The software tester becomes the issue rather than the method claim.
- The claimant's diagnosis becomes the evidence.
- The writer's tone becomes the decision route.

Repair: separate claim, carrier, evidence, and boundary. Evidence may enter. It may not wear the person's face.

### 7.5 Regression through role loss

A civic repair can regress when the role that made it work disappears.

Examples:

- A staff member leaves and the informal fix vanishes.
- A route is digitized and the exception path is lost.
- A new safeguarding rule removes a bounded offer route.
- A policy pilot ends without preserving the test records.

Repair: keep regression probes and ownership. A fix without a future test is a story, not a release.

## 8. Case Sketches from the Local Corpus

### 8.1 Bug Spiller

`bug_spiller_wheres_my_bugzilla.md` argues that a public thread can be a defect intake surface. It has timestamps, witnesses, links, social pressure, and jokes. It is good at making a defect visible. It is weak as the source of truth unless stable IDs, status, owners, templates, and a mirror into a tracker are added.

Civic method translation: public complaint surfaces are not useless noise. They can be early bug spillers. But they need a route into a ledger or they become weather.

### 8.2 Walking the Name of God

`walking_the_name_of_god_independent_testing.md` names the blessed-path problem. Builders learn the safe tiles. Independent testers are more likely to find failures under correction, local vocabulary, bad formatting, old state, version questions, and tired use.

Civic method translation: policy teams know the intended route. Citizens find the floor holes. A civic test plan must include awkward paths and boundary cases.

### 8.3 Bot Councils

`bot_councils_towards_fairer_bureaucratic_cruelty_v0_001.md` does not claim that bots are wiser. It claims that bureaucratic cruelty already exists and that the missing object is route custody: who decided, who overrode, what evidence was ignored, what cost was accepted, and who carries it.

Civic method translation: a civic bug report should make harm routes traceable, comparable, appealable, and repairable. The point is not to automate moral authority. The point is to stop harm from evaporating into mood.

### 8.4 The Helper Who Must Not Appear

`The_Helper_Who_Must_Not_Appear_v0_002.md` names social unusability as capacity loss. A person may carry time, tools, shade, local knowledge, rooms, gates, or routes, but the social parser rejects the helper before the offer is processed.

Civic method translation: the defect is not "awkward helper." The defect is the route that cannot separate asset from person, offer from role, and use from endorsement.

### 8.5 The Unused Tree

`The_Unused_Tree_Lost_Civic_Affordance_v0_002.md` turns the helper problem into a bounded civic affordance case. The object is shade, not the landholder. Custody stays with staff. The landholder need not become supervisor, mascot, proof object, or suspect.

Civic method translation: test whether the system can parse a bounded offer. If it cannot, the civic bug is visible.

### 8.6 Evidence Is Not Person

`Evidence_Is_Not_Person_v0_002.md` supplies the evidence boundary. A fragment may support a claim. It may not become the whole person.

Civic method translation: every civic bug report should include a boundary field. This report supports route X. It does not prove character, diagnosis, guilt, danger, or full life shape.

## 9. Method: Civic Testing Cycle

### 9.1 Intake

Capture the incident without forcing it into institutional language too early.

Questions:

- What happened?
- What was the live object?
- Who or what handled it?
- What was expected?
- What occurred?
- What burden or harm appeared?
- What should not be inferred?

### 9.2 Shaping

Turn the incident into a defect object.

Actions:

- assign ID
- name system under test
- record environment
- write steps
- separate expected and observed
- mark severity and priority
- list evidence
- mark unknowns
- write boundary

### 9.3 Object-custody audit

Run the object through the custody table.

Questions:

- did the object survive the report?
- did the report swap person for evidence?
- did the route swap offer for role?
- did a broad label replace the specific harm?
- did source strength survive?

### 9.4 Repair design

A repair should alter the route, not merely soothe the reporter.

Possible repairs:

- new form field
- exception path
- staff script
- offer intake route
- evidence boundary note
- escalation owner
- decision log
- versioned release note
- refusal reason template
- public route map
- regression probe

### 9.5 Regression check

After repair, retest.

Questions:

- can the same failure recur?
- did the repair create a new burden?
- did staff understand the route?
- did the public route change?
- does the evidence trail survive handoff?
- is the reporter still being treated as the bug?

## 10. Evaluation Design

A civic testing method should be evaluated against ordinary complaint handling, policy review, and public consultation.

### 10.1 Tasks

Give each method the same incident packet:

- citizen complaint
- staff note
- relevant policy
- form screenshot or transcript excerpt
- timeline
- desired repair
- unknowns

Ask each method to produce:

- failure name
- route map
- expected versus observed
- object-in versus object-out
- harm or burden
- evidence status
- boundary status
- repair
- regression check

### 10.2 Metrics

| Metric | Good answer |
|---|---|
| Object survival | The original object remains the object |
| Source survival | Evidence remains tied to source type and path |
| Boundary survival | The report does not overread person, motive, or diagnosis |
| Route trace | Steps and handlers are visible enough for repair |
| Recurrence | The method distinguishes one-off harm from repeatable route |
| Repair validity | The repair changes the failure route |
| Regression protection | The route can be retested later |
| Public use | A non-specialist can understand what must change |

### 10.3 Failure modes

The civic testing method fails if it:

- treats the person as the defect
- turns every harm into a technical bug
- ignores power
- asks harmed people to reproduce harm unsafely
- replaces justice with process theater
- lets evidence wear the person's face
- removes discretion where discretion is the only humane route
- adds paperwork burden while claiming accountability

## 11. Ethics and Limits

Software Testing as Civic Method is not a neutral gadget. It is a way of making routes visible. That visibility can be used well or badly.

The method should not be used to discipline front-line workers while leaving policy, resourcing, and management untouched. Street-level workers often operate under impossible conditions. A defect route may be produced by caseload, shortage, rule conflict, target pressure, or absence of exception paths, not by individual cruelty.

The method should not be used to deny lived harm because reproduction is incomplete. Some civic harms are hard to reproduce because they involve timing, fear, identity, status, social reading, or a rare gatekeeper. In such cases the report should mark low reproducibility without treating the person as unreliable by default.

The method should not replace organizing, legal challenge, political work, journalism, care, or professional judgment. It is an instrument for those activities, not their ruler.

The method should also be careful with public bug spillers. Public defect intake can become harassment, pile-on, or spectacle. A bug spiller needs a route into a ledger, status line, owner, and repair process. Without that, civic bug talk can become theatre.

## 12. Implementation Pattern

A small organization could start without software.

### 12.1 One-page civic bug form

Use the minimal fields from Section 6. Keep it printable. Keep the language ordinary.

### 12.2 Monthly defect review

Review three routes per month:

- one high-severity case
- one high-frequency burden
- one near miss or lost offer

### 12.3 Public release notes

When a route changes, publish short release notes:

- version or date
- affected route
- changed behavior
- known limits
- retest target
- owner

This is basic release practice. It is not anti-hype. It lets the public know what changed.

### 12.4 Regression probes

Keep small probes for known failures. For example:

- Can a person without printer access complete the route?
- Can a person offer a space without becoming a volunteer?
- Can a claimant correct a typo without restarting?
- Can a citizen appeal without using the same route that failed?
- Can evidence be submitted without becoming a character verdict?

### 12.5 Archive and lamp

Use the Old Film / Live Lamp split. Keep incident records as archive. Keep the current repair object small. Do not let every old grievance steer every new decision. Do not let the latest complaint erase earlier route evidence. Assign roles.

## 13. A Worked Mini Example

### 13.1 Incident

A school closes a classroom during heat. A nearby resident offers access to a shaded garden for supervised use by school staff. The resident does not offer supervision, childcare, entry into the school, or contact with children. The school has no route to receive the offer.

### 13.2 Civic bug report

ID: TREE-001  
Title: Bounded shade offer cannot enter closure plan  
System under test: heatwave closure and local contingency planning  
Reporter role: nearby resident or observer  
Object-in: shaded space under staff custody  
Environment: heat day, school building too hot, nearby shade available  
Steps: closure occurs; offer is made; offer enters route; route cannot parse asset separate from person; offer dies  
Expected: offer accepted, declined, or parked with reason while staff custody remains intact  
Observed: offer cannot be held as an object  
Harm or burden: possible cooling option lost; staff and children remain with fewer options  
Boundary: report does not claim resident should supervise children  
Recurrence: likely on future heat days  
Severity: medium to high depending on heat and alternatives  
Priority: high before summer term  
Evidence: closure message, offer text, local map, staff response if any  
Unknowns: legal constraints, insurance, school policy, staff capacity  
Next test: can the school record a non-supervisory asset offer?  
Repair owner: school leadership or local authority estates / safeguarding liaison  
Regression check: test during next heat planning drill

### 13.3 Object-custody audit

DOG: shaded space offer  
ROLE: civic affordance, not person-custody  
FUNCTION: add bounded option to heat planning  
COAT: cannabis user, odd helper, liability risk, volunteer category  
COATI_RISK: high  
OBJECT_STATUS: failed if the offer becomes the person  
SOURCE_STATUS: local evidence needed  
BOUNDARY_STATUS: staff custody must remain  
SUBSTITUTION_RISK: shade replaced by suspected unsupervised childcare  
NEXT_MOVE: add offer intake route with asset, custody, access, limits, refusal reason

This is civic testing. It does not decide whether the school must use the garden. It tests whether the system can receive the object.

## 14. Why This Matters

Civic harm often survives because it arrives without a stable handle. One person suffers. Another complains. A staff member apologizes. A manager notes concern. A policy team says the process was followed. A forum argues about tone. A committee asks for more evidence. The route remains.

A bug report does not fix that by itself. It makes a different demand:

Show the route.

If the route cannot be shown, that is part of the defect. If the object changed while moving through the route, that is part of the defect. If the institution can only receive a person by misnaming their offer, that is part of the defect. If a repair cannot be regression-tested, that is part of the defect.

The civic promise of software testing is not technical glamour. It is disciplined attention to repeatable failure. It says:

- name the route
- preserve the object
- mark the environment
- record expected and observed
- separate severity from priority
- hold source and boundary
- repair the path
- test the repair later

## 15. Conclusion

Software Testing as Civic Method is a translation, not a takeover. It brings defect discipline into civic work without pretending that people, rights, schools, welfare routes, public forums, or local affordances are software.

The method is needed because civic systems often fail in ways that are neither isolated accidents nor easily visible policy errors. They fail through routes: forms, scripts, categories, handoffs, missing fields, social parsers, risk shortcuts, outdated assumptions, and burden. Testing is good at routes.

The central sentence is:

A civic bug report is not a complaint with better formatting. It is a route-preserving object for preventing repeated harm.

If the method works, it gives civic workers, citizens, advocates, journalists, researchers, and awkward helpers a shared instrument. Not a verdict. Not a personality reading. Not a moral fog machine. A small, exact way to say:

This route produced this harm.  
Here is the object that entered.  
Here is where it changed.  
Here is what should happen next.  
Here is how we will know if it comes back.

## Appendix A: Civic Bug Report Template

```text
ID:
Title:
System under test:
Reporter role:
Object-in:
Environment:
Steps:
Expected:
Observed:
Harm or burden:
Boundary:
Recurrence:
Severity:
Priority:
Evidence:
Unknowns:
Next test:
Repair owner:
Regression check:
```

## Appendix B: OCESI Add-on

```text
DOG:
ROLE:
FUNCTION:
COAT:
COATI_RISK:
OBJECT_STATUS:
SOURCE_STATUS:
BOUNDARY_STATUS:
SUBSTITUTION_RISK:
NEXT_MOVE:
```

## Appendix C: Source Strength Labels

```text
DECLARED:
The source explicitly says this.

TEXT_SUPPORTED:
The source text supports this reading.

PATH_INFERRED:
The file path or shelf position supports this as a working inference.

USER_CONTEXT:
The user has supplied this frame in the surrounding workflow.

UNKNOWN:
The paper should not promote this claim without more evidence.
```

## Internal References

[I1] `bug_spiller_wheres_my_bugzilla.md`. *What a Bug Spiller? Where's My Bugzilla?* Working paper, 2026-06-27.

[I2] `walking_the_name_of_god_independent_testing.md`. *Walking the Name of God: Why independent testing is not optional.* Working paper v0.1, 2026-06-28.

[I3] `bot_councils_towards_fairer_bureaucratic_cruelty_v0_001.md`. *Bot Councils: Towards Fairer Bureaucratic Cruelty.* Working paper v0.001.

[I4] `The_Helper_Who_Must_Not_Appear_v0_002.md`. *The Helper Who Must Not Appear: Social unusability, latent civic capacity, and the offer that fails before design.* Working paper v0.002.

[I5] `The_Unused_Tree_Lost_Civic_Affordance_v0_002.md`. *The Unused Tree: Heatwave childcare, medical cannabis stigma, and lost civic affordance.* Working paper v0.002.

[I6] `Evidence_Is_Not_Person_v0_002.md`. *Evidence Is Not Person: Fragments, transcript integrity, and the refusal of whole-person proxy reading.* Working paper v0.002.

[I7] `Object_Substitution_as_AI_Safety_Failure_Mode_v0_002.md`. *Object Substitution as an AI Safety Failure Mode.* Public draft v0.002.

[I8] `object_custody_for_ai_workflows_v0_001.md`. *Object Custody for AI Workflows.* Working paper v0.001.

[I9] `lmxdi/ADUTI/ADUTI-REFRI-DRAGI-ELVIX-MOGRI.md`. Object preservation stack map.

[I10] `old_film_live_lamp_object_custody_long_horizon_ai_memory_public_v0_005.docx`. *Old Film, Live Lamp: Object Custody for Long-Horizon AI Memory.* Public upload edition v0.005, 2026-06-30.

[I11] `lmxdi/MARK/ABCD as Semantic Guerrilla Testing.md`. Semantic guerrilla testing notes.

[I12] `lmxdi/MARK/Recursive Multi-Level Methodology v0_002.md`. Recursive multi-level method notes.

[I13] `lmxdi/chatgpt-perf-regressions.md`. Performance regression and public report notes.

[I14] `lmxdi/RSOC/ABSTRACT` and related RSOC notes. Method becomes contamination / legibility displacement case notes.

## External References

[E1] Kaner, C., Bach, J., and Pettichord, B. (2002). *Lessons Learned in Software Testing: A Context-Driven Approach.* Wiley. Covers test design, bug advocacy, documentation, automation, and test management.

[E2] Kaner, C. (2006). *Software Testing as a Social Science.* STAR East presentation paper. Frames testing as investigation shaped by people, observation, and context.

[E3] ISO/IEC/IEEE. (2021). *ISO/IEC/IEEE 29119-3: Software and systems engineering, software testing, part 3: Test documentation.* Standard for test documentation templates and process artifacts.

[E4] Johnson, J., Mahmud, J., Wendland, T., Moran, K., Rubin, J., and Fazzini, M. (2023). *An Empirical Investigation into the Reproduction of Bug Reports for Android Apps.* arXiv:2301.01235.

[E5] Lipsky, M. (1980; 2010 edition). *Street-Level Bureaucracy: Dilemmas of the Individual in Public Services.* Russell Sage Foundation.

[E6] Herd, P., and Moynihan, D. (2018). *Administrative Burden: Policymaking by Other Means.* Russell Sage Foundation.

[E7] Halling, A., and Baekgaard, M. (2024). *Administrative Burden in Citizen-State Interactions: A Systematic Literature Review.* Journal of Public Administration Research and Theory, 34(2), 180-195.

[E8] Bowker, G. C., and Star, S. L. (1999). *Sorting Things Out: Classification and Its Consequences.* MIT Press.

[E9] Eubanks, V. (2018). *Automating Inequality: How High-Tech Tools Profile, Police, and Punish the Poor.* St. Martin's Press.

[E10] Zhang, W., Lim, G., Perrault, S., and Wang, C. (2022). *A Review of Research on Civic Technology: Definitions, Theories, History and Insights.* arXiv:2204.11461.

[E11] Knutas, A., Palacin, V., Maccani, G., and Helfert, M. (2019). *Software Engineering in Civic Tech: A Case Study about Code for Ireland.* arXiv:1904.04104.

[E12] Open Government Partnership. (2021). *Algorithmic Accountability for the Public Sector.* Study report on accountability mechanisms for public-sector algorithmic systems.

[E13] World Bank Global Partnership for Social Accountability. (2023). *A Proposal for Civic Tech and Social Accountability.* Working proposal on civic technology, social accountability, and institutional response.

[E14] Fraser, G., and Arcuri, A. (2012). *Sound Empirical Evidence in Software Testing.* ICSE. Argues for stronger empirical standards in software-testing research.

[E15] Chen, T. Y., Cheung, S. C., and Yiu, S. M. (1998/2020 reprint). *Metamorphic Testing: A New Approach for Generating Next Test Cases.* Introduces a testing approach for cases where direct oracles are hard to obtain.
