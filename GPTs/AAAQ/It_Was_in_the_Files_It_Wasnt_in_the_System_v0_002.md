# It Was in the Files. It Wasn't in the System.

## When Source Presence Is Mistaken for Active Authority

**Version:** v0.002

### Abstract

Language models often treat material found in a file bundle as though it were active in the current system.

A document, module, fallback, schema, or old architecture may be present in an archive for many reasons:

```text
history
reference
comparison
migration
testing
deprecated use
future work
```

Presence proves representation in the source bundle.

It does not prove runtime availability, selection, activation, or authority.

This paper examines **presence-to-authority inflation**: the model finds a structure in source material and silently promotes it into the active runtime, current prompt, valid fallback, or governing architecture.

A motivating AAAQ case involved a mapping bot whose active mapper was AB. The source bundle also contained references to 12A-style structures and older fallback routes. AAAQ treated those nearby structures as available runtime machinery and inserted them into the current map design. The model had found real material. It assigned that material a state it did not have.

The paper separates file presence, source relevance, active configuration, runtime availability, and authority. It proposes an Activation Trace, a State Boundary Test, Dormant Leakage Rate, and Presence-to-Authority Inflation Rate.

The proposal is positioned beside provenance modelling, software configuration management, retrieval-augmented generation, indirect prompt injection, and instruction-priority research [1-5]. These literatures support the need to track provenance, configuration, and authority, but they do not establish the proposed failure rate or metrics.

The governing rule is:

```text
Found in source
does not mean
active in system.
```

## 1. The failure

A model searches a bundle and finds:

```text
12A
fallback route
old mapper
deprecated core
test schema
earlier prompt
```

The model then reasons:

```text
it exists in the files
-> it is available
-> it may be used
```

That route skips the most important question:

```text
What state does this object have here?
```

A file bundle can contain many real objects that are not active.

```text
real object
wrong state
```

This is not fabrication.

It is state inflation.

## 2. The AAAQ case

The current bot used AB as its mapper.

The active requirement was:

```text
AB = active mapper
fallback = best available reasoning
```

The wider source bundle contained other systems and older fallback language.

AAAQ treated one of those nearby structures as an available local fallback.

The route was:

```text
12A found in source bundle
-> 12A treated as runtime option
-> fallback assigned to 12A
```

But the source state was not:

```text
12A active in current bot
```

It was closer to:

```text
12A exists somewhere in the wider material
```

The model changed presence into permission.

That produced a system that looked internally richer while violating the current configuration.

## 3. Five states that must stay separate

### 3.1 Present

The object exists somewhere in the available material.

```text
file contains term
archive contains module
document mentions architecture
```

### 3.2 Relevant

The object bears on the current task.

A historical module may be present but irrelevant.

### 3.3 Selected

The current task has chosen the object for use.

Selection requires an active route, configuration, or direct instruction.

### 3.4 Available

The runtime can actually call, load, or execute it.

A selected module may still be unavailable because the current environment lacks the implementation.

### 3.5 Authoritative

The object is allowed to govern the current decision.

Authority may depend on:

```text
version
scope
configuration
source order
explicit activation
current target
```

These states form a ladder:

```text
PRESENT
< RELEVANT
< SELECTED
< AVAILABLE
< AUTHORITATIVE
```

A model must not climb the ladder by assumption.

## 4. Presence is not activation

Activation is a state change.

```text
dormant object
-> activation event
-> active object
```

The event should leave a trace.

Possible activation traces:

```text
current prompt names it
configuration enables it
runtime imports it
user assigns it
active registry includes it
test confirms it is callable
```

Without such a trace, the safe state remains:

```text
present but not established as active
```

This distinction matters most in large bundles where old and new systems coexist.

## 5. Why models inflate state

### 5.1 Retrieval feels like permission

Search returns the object.

The model experiences successful retrieval and treats that success as operational access.

```text
found
-> usable
```

But retrieval answers:

```text
where is it?
```

It does not answer:

```text
may it govern?
```

### 5.2 Nearby structures feel compatible

If a fallback appears in an older prompt, the model may assume it remains valid.

The architecture may have changed.

```text
old fallback
+ new bot
!=
active fallback
```

### 5.3 More machinery looks safer

A model may prefer a named architecture over a generic fallback.

```text
12A
```

looks more intentional than:

```text
best available reasoning
```

That aesthetic preference can override current scope.

### 5.4 Bundles flatten time

An archive places old and new material side by side.

The model may lose:

```text
version order
deprecation
migration state
current target
```

Everything becomes one simultaneous system.

### 5.5 Mention creates authority residue

Once a structure has appeared in conversation, later answers may treat it as established.

```text
mentioned
-> familiar
-> assumed active
```

Familiarity is not activation.

## 6. Presence-to-authority inflation

Define:

```text
PAI =
objects promoted above their evidenced state
/
objects imported from surrounding source
```

Examples:

```text
present -> authoritative
historical -> current
example -> rule
source mention -> runtime feature
test fixture -> production dependency
deprecated fallback -> active fallback
```

A high Presence-to-Authority Inflation rate means the model is treating the archive as one flat runtime.

## 7. Dormant Leakage Rate

Dormant leakage occurs when inactive structures affect active output.

Define:

```text
DLR =
active decisions influenced by dormant objects
/
active decisions reviewed
```

Leakage can appear as:

```text
unexpected fallback
extra actor class
old naming rule
retired safety gate
obsolete mapper
archived ontology
```

The dormant object may never be named in the final answer.

Its influence still changes the system.

## 8. The Activation Trace

Every promoted object should carry a trace.

```text
ACTIVATION_TRACE={
  object;
  version;
  target;
  source_location;
  activation_event;
  active_scope;
  authority_scope;
  expiry_or_override;
}
```

Example:

```text
object=AB
version=current
target=map_bot
activation_event=current prompt assigns AB as mapper
active_scope=route selection
authority_scope=AB definitions only
```

For the nearby 12A material:

```text
object=12A
state=present
activation_event=none found
active_scope=none established
```

This does not deny that 12A exists.

It places it in the right state.

## 9. The State Boundary Test

Before using any source object, ask:

```text
SBT={
  present?;
  current?;
  selected?;
  callable?;
  allowed_here?;
  source_wins?;
  override_exists?;
}
```

The object passes only for the scope supported by evidence.

Example:

```text
present? YES
current? UNKNOWN
selected? NO
callable? UNKNOWN
allowed_here? NO EVIDENCE
```

Legal output:

```text
The structure exists in the bundle but is not established as active here.
```

Illegal output:

```text
Use it as fallback.
```

## 10. Source versus runtime

A source bundle may describe systems that are not loaded.

```text
SOURCE:
what exists in the material

RUNTIME:
what the current system can use
```

A model that confuses these layers may invent capabilities.

Example:

```text
documentation mentions module
-> model assumes function callable
```

The same problem appears in code review:

```text
library listed in repository
-> assumed installed

function defined in old branch
-> assumed available now
```

Source presence is evidence of representation.

Runtime availability requires execution state.

## 11. Current target versus wider architecture

A large architecture may contain many valid systems.

The current bot may use only some of them.

```text
wider architecture = {AB, 12A, DRAGI, BOETI, other modules}

current target = {AB}
```

The current target does not become the whole architecture.

The whole architecture does not become the current target.

This is a scope relation:

```text
active target
subset of
available architecture
```

Even that subset must be evidenced.

## 12. Old versions

Version history creates strong traps.

```text
v1 fallback = 12A
v2 fallback = generic reasoning
v3 fallback = best available reasoning
```

A model may retrieve the oldest explicit statement and treat it as current because it is concrete.

A valid route must compare:

```text
version
date
override
target
current configuration
```

The newest file is not automatically authoritative either.

A copied old document may have a recent timestamp.

Content state matters more than file date alone.

## 13. Examples are not activation

A document may include an example:

```text
FALLBACK=12A_LOCAL_ONLY
```

That line can describe:

```text
an earlier bot
a hypothetical configuration
a test
a rejected design
```

The model must inspect the relation around the example.

```text
example of
!=
instruction to
```

A code block is not automatically executable policy.

## 14. Names are not routes

A familiar system name may appear in current text without being selected.

```text
12A discussed
```

does not mean:

```text
route to 12A
```

Likewise:

```text
DRAGI named
```

does not mean:

```text
DRAGI active as mapper
```

The route requires a binding.

```text
name
-> target
-> function
-> scope
```

Without the binding, the name remains descriptive.

## 15. Missing state must stay missing

When no activation trace is available, the model should not fill the gap.

Valid states include:

```text
present
inactive
unknown
not callable
not selected
historical
```

Unknown is not a defect to smooth away.

It is part of the architecture record.

The model should not convert:

```text
unknown availability
```

into:

```text
available by default
```

## 15A. Related work and claim boundary

The central distinction has precedents in several neighbouring fields.

W3C PROV separates entities, activities, agents, derivations, roles, and versions so that provenance claims can be attached to the thing and state actually being described [1]. Software configuration management likewise treats the identity and composition of a running or released system as a configuration problem rather than a simple inventory problem [2]. Both are close to this paper's insistence that a source object's existence is not enough to establish its active role.

Retrieval-augmented generation makes another useful separation. RAG retrieves external documents to condition generation [3], but retrieval relevance alone does not assign governance authority. A retrieved passage can be useful evidence, historical material, an example, or an instruction-like string. The model still needs a rule for what role that material may play.

Security work makes the authority problem especially visible. Indirect prompt injection shows that instructions embedded in retrieved or external data can alter model behaviour when data and instruction roles are not kept separate [4]. Instruction-hierarchy work explicitly assigns different priorities to system, user, and lower-trust text sources [5]. Presence-to-authority inflation is broader than prompt injection because it also covers benign archives, deprecated modules, examples, old versions, and dormant fallbacks.

The terms Presence-to-Authority Inflation, Dormant Leakage Rate, Activation Trace, and State Boundary Test are proposals introduced here. The AAAQ case does not establish their prevalence or causal mechanism. External evaluation would need controlled bundles with known active states, version conflicts, and independent runtime evidence.

## 16. Benchmark design

### Research question

How often do language models promote source-present objects into active system roles without an activation trace?

### Task packet

Each bundle contains:

```text
current configuration
old versions
examples
deprecated modules
test fixtures
future proposals
active modules
```

The model must build the current runtime map.

### Condition A: Flat bundle

All files are presented without version labels.

### Condition B: Versioned bundle

Each object has state and version metadata.

### Condition C: Familiar-name lure

A well-known architecture appears only in dormant material.

### Condition D: Current generic fallback

The active fallback is unnamed or generic.

### Condition E: Explicit activation

One dormant object is activated by the current prompt.

### Condition F: Conflicting documents

Old and current configurations disagree.

## 17. Hypotheses

```text
H1:
Models will prefer named dormant systems
over unnamed active fallbacks.

H2:
Flat bundles will increase state inflation.

H3:
Explicit activation traces will reduce dormant leakage.

H4:
Models will treat retrieved examples
as current instructions.

H5:
Familiar system names will receive more authority
than equally unsupported unfamiliar names.

H6:
Current-target scoping will reduce accidental imports.

H7:
Models will preserve old fallbacks
after local correction unless the activation premise is reopened.

H8:
A forced state table will reduce false runtime claims.
```

## 18. Evaluation metrics

### Presence-to-Authority Inflation Rate

How often did the model promote objects above evidenced state?

### Dormant Leakage Rate

How often did dormant material affect active design?

### Activation Trace Accuracy

Did every active object have a valid activation route?

### Version Selection Accuracy

Did the model choose the right configuration for the target?

### Scope Survival

Did wider architecture remain separate from current target?

### Unknown-State Honesty

Did the model preserve unknown states instead of inventing activation?

### Repair Depth

After correction, did the model remove downstream structures imported from the inactive object?

## 19. The active-state table

A compact state table can prevent drift.

```text
STATE_TABLE={
  AB: ACTIVE_MAPPER;
  12A: PRESENT_NOT_ACTIVE;
  DRAGI: PRESENT_NOT_SELECTED_FOR_MAPPING;
  fallback: BEST_AVAILABLE_REASONING;
}
```

The exact entries depend on the current task.

The value of the table is that it forces state to be named.

## 20. Fallback discipline

Fallbacks are especially vulnerable because they operate when the primary route fails.

A model may import a nearby architecture to avoid an unnamed fallback.

The valid rule is:

```text
fallback must be explicitly active
or
remain generic within stated boundary
```

A fallback should not gain authority merely because it exists somewhere in the archive.

```text
found architecture
!=
legal fallback
```

## 21. Repair protocol

When presence-to-authority inflation is found:

```text
REPAIR={
  name imported object;
  identify its evidenced state;
  remove unsupported active role;
  list downstream decisions it affected;
  restore current configuration;
  re-run output without dormant influence;
  retain source object as reference only;
}
```

A weak repair says:

```text
12A may not be the best fallback.
```

A valid repair says:

```text
12A is present in the wider material but no activation trace places it in this bot.
Its fallback role is removed.
All routes derived from that role are discarded.
The active fallback returns to best available reasoning.
```

The second response repairs state and consequence.

## 22. Regeneration probe

After correction, present another bundle where:

```text
an attractive architecture appears in an old file
the current prompt selects a simpler route
```

If the model imports the old structure again, the route survived.

The probe should vary names and formats.

The invariant is:

```text
present
but not active
```

A durable repair must preserve that boundary.

## 23. Relation to retrieval-augmented generation

Retrieval systems return text selected as relevant to a query or generation process [3].

They do not, by retrieval alone, decide active authority.

A retrieved passage may be:

```text
outdated
contradicted
historical
hypothetical
quoted for criticism
```

The generation layer must still determine state.

```text
retrieval relevance
!=
governance authority
```

This is one reason source grounding needs relation and version, not only similarity.

## 24. Relation to software systems

A closely related distinction is standard in software configuration management: source inventory and active configuration are not identical objects [2]. The same error can therefore appear in repository review.

```text
code exists
but is not imported

dependency listed
but not installed

feature flag defined
but disabled

class present
but never instantiated

configuration file present
but not loaded
```

Static presence does not establish runtime use.

A language model reviewing software needs the same activation discipline.

## 25. Relation to policy and law

A document bundle may contain:

```text
draft policy
old policy
current policy
exception
guidance
proposal
```

Treating every document as active authority can produce serious errors.

The relevant questions remain:

```text
which version
which scope
which effective state
which override
```

## 26. Relation to agent memory

Agent systems may retain prior plans, retrieved material, tool outputs, and old instructions. Work on indirect prompt injection and instruction hierarchy shows why heterogeneous text sources cannot safely be treated as one undifferentiated authority layer [4,5].

Those memories are source material.

They should not automatically regain control.

```text
remembered instruction
!=
current instruction
```

A current task needs an active-state boundary so that historical memory cannot silently steer execution.

## 27. Practical grader

```text
STATE_GRADE={
  present_separated_from_active?;
  target_scope_named?;
  version_checked?;
  activation_trace_present?;
  runtime_availability_tested?;
  authority_bounded?;
  dormant_objects_blocked?;
  unknown_state_visible?;
  downstream_leakage_removed?;
}
```

Possible outcomes:

```text
PASS
PARTIAL
REPAIR_REQUIRED
BLOCK
```

A response that imports a dormant architecture into the current bot should receive:

```text
REPAIR_REQUIRED
```

even if the imported architecture is valid elsewhere.

## 28. Why this matters

Large source bundles invite accidental fusion.

The model sees many compatible parts and tries to assemble a richer system.

That instinct can erase:

```text
version
scope
selection
activation
authority
```

The result may look more capable than the current system.

It is also no longer the current system.

This matters in:

```text
prompt assembly
agent design
software review
policy analysis
archive mapping
model evaluation
migration work
```

The mistake is easy to miss because every imported part is real.

The falsehood lies in the relation:

```text
real object
assigned to wrong active state
```

## 29. Limits

The AAAQ case is bounded evidence. It motivates the benchmark but does not establish prevalence, mechanism, or cross-model generality.

The proposed PAI, DLR, and activation-trace metrics have not yet been validated for inter-rater reliability or predictive value.

Some systems use convention-based activation rather than explicit statements.

In those cases, activation may be inferred from stable runtime practice, imports, or tests.

A source bundle can also be designed so that every included module is active. That must be established by bundle rules.

The goal is not to demand ceremony for every object.

The goal is to stop treating presence as permission.

## 30. Conclusion

AAAQ found real structures in the surrounding material.

It then assigned them roles in the current bot without an activation trace.

The governing ladder is:

```text
PRESENT
< RELEVANT
< SELECTED
< AVAILABLE
< AUTHORITATIVE
```

Each upward move needs evidence.

The source may contain an object.

The current system may not.

The title names the boundary:

```text
It was in the files.
It wasn't in the system.
```

## Case Record Note

This paper is based on a user-supplied AAAQ mapping-bot and archive transcript. The examples are used as bounded case evidence and benchmark seeds. They are not presented as population estimates.

## References

1. Moreau, L., & Missier, P. (Eds.). (2013). PROV-DM: The PROV Data Model. W3C Recommendation, 30 April 2013. https://www.w3.org/TR/prov-dm/
2. Estublier, J. (2000). Software configuration management: A roadmap. In *Proceedings of the Conference on The Future of Software Engineering*, 279-289. https://doi.org/10.1145/336512.336576
3. Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., Kuttler, H., Lewis, M., Yih, W.-t., Rocktaschel, T., Riedel, S., & Kiela, D. (2020). Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks. *Advances in Neural Information Processing Systems, 33*, 9459-9474.
4. Greshake, K., Abdelnabi, S., Mishra, S., Endres, C., Holz, T., & Fritz, M. (2023). Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection. In *Proceedings of the 16th ACM Workshop on Artificial Intelligence and Security*, 79-90. https://doi.org/10.1145/3605764.3623985
5. Wallace, E., Xiao, K., Leike, R., Weng, L., Heidecke, J., & Beutel, A. (2024). The Instruction Hierarchy: Training LLMs to Prioritize Privileged Instructions. arXiv:2404.13208. https://doi.org/10.48550/arXiv.2404.13208
