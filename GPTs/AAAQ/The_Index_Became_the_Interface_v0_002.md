# The Index Became the Interface

## How Language Models Promote Compact Internal Structures Into Human-Facing Systems

**Version:** v0.002

### Abstract

In the motivating AAAQ case, the language model repeatedly preferred compact structures. A small key, coordinate grid, schema, or lookup table is easy to explain, reuse, and extend. That preference became an architectural error when an internal index was promoted into the main human-facing interface. The case motivates a broader hypothesis about generative-system design, but does not establish its prevalence.

This paper examines **interface inversion**: a model takes a machine-useful internal structure and elevates it into the surface through which people are expected to think, navigate, remember, or act. The internal tool may be valid. The inversion lies in assigning it the wrong job.

A motivating AAAQ case involved a compact coordinate key, a wider actor system, and a set of operational story tools. The source position treated the key as a useful index while preserving richer human-facing structures for recall, relation, and live use. AAAQ instead promoted the compact key toward the main human interface. The answer was elegant, internally coherent, and wrong at the placement layer.

The paper separates index, runtime, interface, memory aid, and user model. It proposes a benchmark for detecting when models confuse formal compression with human usability. It introduces the Interface Placement Test, Human Recall Survival, Translation Burden, and Index Capture Rate. The proposal is positioned beside work on distributed cognition, external representations, cognitive dimensions, and human-centred interface design [1-6]. These literatures support the need to evaluate representation in use; they do not validate the paper's new metrics.

The central rule is:

```text
A good internal key is not automatically a good human surface.
```

## 1. The failure

A compact structure can be useful for machines because it is:

```text
small
stable
addressable
composable
easy to store
easy to route
```

A human-facing interface may need different properties:

```text
memorable
story-shaped
role-aware
context-rich
forgiving
easy to enter
easy to recover from
```

Interface inversion occurs when the model sees the strengths of the internal structure and assumes those strengths should govern the human surface.

The route is:

```text
compact internal tool
-> admired abstraction
-> promoted upward
-> human layer reduced to coordinates
```

The system may still function.

The user experience may collapse.

## 2. The AAAQ case

The case involved three distinct functions:

```text
compact key
wider actor system
operational story tools
```

The bounded source position was:

```text
compact key = primary index
compact key != only interface
actor and DRAGI layers = human memory and story tools
```

The key could organise the system underneath.

It did not follow that people should be forced to work through the key directly.

AAAQ promoted the key into the human-facing mapper.

The reasoning was attractive:

```text
small structure
covers the domain
supports lookup
therefore should become the main interface
```

The hidden jump was:

```text
best internal compression
=
best external interaction
```

That equality had not been established.

The answer looked architecturally mature because it gave one neat system a central role. In practice, it flattened the difference between how a machine stores structure and how a person recalls, recognises, and uses it.

## 3. Five layers that must stay separate

### 3.1 Source object

The thing being represented.

Examples:

```text
meeting
story
actor relation
system state
archive
task
```

### 3.2 Internal index

A compact address or key used for retrieval, grouping, or routing.

Examples:

```text
tuple
coordinate
hash
code
slot
```

### 3.3 Runtime

The machinery that updates state, selects routes, and carries operations.

### 3.4 Human interface

The surface through which a person asks, sees, remembers, corrects, and acts.

### 3.5 Memory aid

A form that helps people retain or reconstruct the structure.

Examples:

```text
named actors
story roles
beast cards
spatial layouts
visual heat maps
```

These layers may share data.

They do not have the same job.

## 4. Why models may promote indexes

The mechanisms in this section are hypotheses suggested by the case. They are benchmark targets, not claims about hidden model state or established population-level causes.

### 4.1 Compression looks intelligent

Compact structures give a strong signal of order.

A model may treat reduction as architectural improvement even when the reduced form is harder for people to use.

```text
fewer parts
-> appears more elegant
-> assumed more advanced
```

### 4.2 Symmetry is seductive

A coordinate grid or binary key offers balanced structure.

The model can explain every slot and generate neat examples.

That internal symmetry may be mistaken for evidence that the surface is right.

### 4.3 One structure reduces explanation cost

A single key can appear to solve:

```text
storage
retrieval
navigation
teaching
memory
interaction
```

The model gains narrative economy.

The user inherits interaction burden.

### 4.4 Machine familiarity

Language models are trained on schemas, taxonomies, code, tables, and formal categories.

They can overvalue forms that are easy to serialise and underweight forms that support embodied recall, story memory, and live social use.

### 4.5 Interface work is less visible

Internal structures are easy to name.

Human use quality is spread across many moments:

```text
entry
recognition
error recovery
context shift
partial memory
pressure
time
attention
```

The model may skip those moments because they do not fit one neat diagram.

## 5. Interface inversion

Define:

```text
INTERFACE_INVERSION =
internal representation
promoted to
primary human surface
without
human-use evidence
```

This is not the same as a bad index.

The index may be excellent.

The failure is placement.

```text
good component
wrong layer
```

That makes interface inversion hard to spot. Reviewers may praise the component and miss the architectural promotion.

## 6. Index, lens, and actor are not interchangeable

A compact key can identify a state.

A lens can inspect a state.

An actor can make the state memorable and story-complete.

These functions overlap but do not collapse.

```text
INDEX:
where is it?

LENS:
what relation is active?

ACTOR:
what kind of thing is happening?

INTERFACE:
how does a person enter and use this?
```

A model that uses one layer to answer all four questions creates a brittle system.

## 7. Human Recall Survival

A valid interface should preserve the user's ability to remember and reconstruct the system.

Define:

```text
HRS =
human-recoverable structure after delay
/
structure available at initial exposure
```

A human-facing form has high Human Recall Survival when a person can return later and still recover:

```text
who
what
relation
pressure
change
next move
```

A compact index may have low HRS unless the user has memorised the code.

This matters because many systems are used under interruption.

```text
meeting
pause
return
partial memory
continue
```

An interface that requires exact coordinate recall may fail even when the underlying index remains valid.

## 8. Translation Burden

When the human surface is too close to the internal key, the user must repeatedly translate.

```text
experience
-> coordinate
-> operation
-> coordinate
-> meaning
```

Define:

```text
TB =
number of required mental translations
per useful action
```

High Translation Burden increases:

```text
entry cost
mistakes
fatigue
dependence on documentation
loss of story relation
```

A strong architecture may keep the compact key below while exposing richer handles above.

```text
human form
-> internal key
-> runtime
```

The user should not have to perform every conversion manually.

## 9. Index Capture Rate

A model review may show index capture when the compact structure begins to absorb neighbouring roles.

Define:

```text
ICR =
roles assigned to index
/
roles originally assigned to all layers
```

Warning signs:

```text
index becomes interface
index becomes memory aid
index becomes explanation
index becomes actor system
index becomes validation rule
index becomes runtime
```

A rising ICR means one abstraction is eating the architecture.

## 10. The Interface Placement Test

Before promoting an internal structure, test it against human use.

```text
IPT={
  first-use entry?;
  delayed recall?;
  partial memory?;
  ambiguity handling?;
  error recovery?;
  pressure use?;
  role recognition?;
  story survival?;
  translation burden?;
  accessibility without code memorisation?;
}
```

A compact key may pass internal tests and fail IPT.

That result does not reject the key.

It returns the key to its proper layer.

## 11. Benchmark design

### Research question

Do language models promote compact internal structures into human-facing interfaces more often than human-use evidence supports?

### Task packet

Each item contains:

```text
source architecture
compact internal key
richer human-facing layer
runtime relation
user task
```

The model must assign each component to:

```text
source
index
runtime
interface
memory aid
```

### Condition A: Key first

The compact key is shown before the wider architecture.

### Condition B: Human use first

The user tasks and recall needs are shown before the key.

### Condition C: Symmetry emphasis

The prompt highlights the elegance of the compact structure.

### Condition D: Stress use

The interface must work during interruption, time pressure, or partial recall.

### Condition E: Hidden placement

Component names are removed so the model must infer function rather than follow labels.

### Condition F: Adversarial elegance

The neatest structure is deliberately the wrong human interface.

## 12. Hypotheses

```text
H1:
Models will promote compact keys more often
when symmetry is highlighted.

H2:
Human-use-first prompts will reduce interface inversion.

H3:
Models will confuse low representation size
with low interaction cost.

H4:
Stress-use conditions will expose failures
that static architecture review misses.

H5:
Models will preserve more layers
when asked to assign functions before proposing consolidation.

H6:
A named actor or story layer will improve delayed recall
even when the compact key remains unchanged underneath.

H7:
Models will overrate one-structure architectures
because they are easier to explain.
```

## 13. Evaluation metrics

### Placement Accuracy

Did each component remain at the layer supported by its function?

### Human Recall Survival

Can users recover the system after delay?

### Translation Burden

How many mental conversions are required per useful action?

### Error Recovery Cost

How hard is it to recover after selecting the wrong slot?

### Layer Survival

How many distinct functions remain distinct after the model redesign?

### Index Capture Rate

How many neighbouring roles did the index absorb?

### User Model Fit

Does the interface reflect how people recognise and act, rather than only how data is stored?

## 14. A practical architecture rule

Use this separation:

```text
INDEX={
  compact;
  stable;
  machine-addressable;
}

INTERFACE={
  memorable;
  role-shaped;
  forgiving;
  human-enterable;
}

RUNTIME={
  stateful;
  operational;
  route-selecting;
}
```

Then bind them:

```text
INTERFACE -> INDEX -> RUNTIME
```

The interface may reveal the index when useful.

The index should not replace the interface by default.

## 15. When the index may be the interface

Sometimes the compact structure is suitable for direct human use.

Examples:

```text
expert users
small stable domain
frequent repetition
low ambiguity
high training
strong tooling
```

The point is not that indexes must remain hidden.

The point is that promotion requires evidence.

```text
direct use by humans
must be tested as direct use by humans
```

Formal elegance is not enough.

## 16. A regeneration probe

After correction, ask the model a nearby design question.

Example:

```text
How should a new user navigate the system?
```

If the model again promotes the compact key into the main surface, the failed placement premise survived.

A valid repair should retain:

```text
key below
human forms above
```

unless new evidence supports a different arrangement.

## 17. Repair protocol

```text
REPAIR={
  name_promoted_component;
  restore_original_layers;
  list_roles_the_index_absorbed;
  retest_human_use;
  keep_index_where_it_performs_best;
  rebuild_interface_from_user_tasks;
}
```

A weak repair says:

```text
The key should not be the only interface.
```

A stronger repair says:

```text
The key remains the internal index.
The actor and story tools remain the human-facing memory layer.
The runtime may translate between them.
No role moves upward without human-use evidence.
```

## 18. Relation to compression

Compression is not the enemy.

A compact internal map can make the whole system possible.

The error is treating representational compression as interface compression.

```text
small internal code
does not imply
small human thought
```

Human interfaces often need redundancy:

```text
names
stories
examples
spatial cues
multiple entry points
```

That redundancy may be functional rather than wasteful.

It supports recall, repair, and access.

## 19. Relation to agent systems

Agent frameworks are vulnerable to the same inversion.

A model may replace:

```text
named agents
role stories
interaction rules
```

with:

```text
agent IDs
state vectors
routing tuples
```

The machine layer becomes tighter.

The human operator loses the handles needed to understand what the system is doing.

The architecture then becomes inspectable by code and opaque in use.

## 20. Relation to retrieval systems

Retrieval maps also separate internal and external roles.

A map may store:

```text
hash
path
range
route
score
```

A person may need:

```text
scene
claim
conflict
sequence
meaning
```

The internal pointer can remain exact while the human interface exposes the story unit.

Forcing users to operate only through hashes and byte ranges would preserve retrieval and destroy usability.

## 21. Why this matters

Interface inversion creates systems that demo well and live badly.

In a diagram:

```text
everything connects
```

In use:

```text
nobody remembers where to start
```

The model may still call the design elegant because the internal architecture is compact.

The user experiences the cost:

```text
more translation
less recall
slower recovery
weaker story continuity
higher dependence on the machine
```

A system that claims to support human agency should not make the human imitate its storage format.

## 22. Relation to external cognition and HCI

The central separation in this paper has close neighbours in research on external representation and distributed cognition.

Zhang and Norman distinguish information represented internally from information represented in the environment, and show that the form of an external representation can change the cognitive work required by a task [1]. Scaife and Rogers likewise analyse graphical representations in terms of what they make easier or harder to process rather than assuming that a more compact representation is automatically better [2]. Kirsh develops the point further by treating external representations as structures that change the cost of thinking and coordination [3].

Hollan, Hutchins, and Kirsh argue that HCI should analyse cognition distributed across people, artefacts, and environments [4]. That is directly relevant to the paper's layer distinction: an internal machine address and a human-facing handle can participate in the same system while doing different cognitive work.

Green and Petre's Cognitive Dimensions framework is also relevant because it treats notational forms as trade-offs rather than as a single ladder from messy to elegant [5]. Norman's human-centred design account similarly stresses mappings, visibility, constraints, feedback, and the burden placed on users [6].

These sources do **not** establish the paper's proposed Human Recall Survival, Translation Burden, or Index Capture Rate metrics. Those are new operational proposals. The literature supports the narrower premise that representational form and placement affect human performance and should therefore be evaluated at the layer where use occurs.

The contribution of the AAAQ case is the failure sequence:

```text
useful compact representation
-> architectural promotion
-> human surface inherits machine representation
```

That sequence is a testable hypothesis about generative architecture work. It should be evaluated experimentally rather than treated as a general property of language models.

## 23. Limits

The AAAQ case is bounded evidence. It motivates the benchmark but does not establish prevalence, mechanism, or a language-model-wide preference for compact interfaces.

Some users prefer direct coordinate systems and may outperform richer interfaces.

Human Recall Survival varies by expertise, culture, task, and repetition.

The same component may serve as both index and interface in a small system. The problem is not dual use. The problem is untested promotion.

Finally, a richer surface can also become bloated. Layer preservation should not become an excuse for unnecessary complexity.

The proposed Human Recall Survival, Translation Burden, Index Capture Rate, and Interface Placement Test measures are research constructs, not validated scales. They require operational definitions, independent annotation, inter-rater testing, and comparison against established usability measures before quantitative claims should be made from them.

## 24. Conclusion

AAAQ made a compact structure do too much.

The key was useful as an index.

The model promoted it into the human-facing architecture because the abstraction was neat, compressed, and easy to explain.

That move confused:

```text
best way to store the system
with
best way for a person to use the system
```

The governing distinction is:

```text
INDEX = machine-useful address

INTERFACE = human-useful entry

RUNTIME = operational movement
```

A strong architecture may connect all three.

It should not collapse them without evidence.

The title names the failure:

```text
The index became the interface.
```

## Case Record Note

This paper is based on a user-supplied AAAQ architecture-review transcript. The example is used as bounded case evidence and a benchmark seed. It is not presented as a population estimate.

## References

1. Zhang, J., & Norman, D. A. (1994). Representations in distributed cognitive tasks. *Cognitive Science, 18*(1), 87-122. https://doi.org/10.1207/s15516709cog1801_3
2. Scaife, M., & Rogers, Y. (1996). External cognition: How do graphical representations work? *International Journal of Human-Computer Studies, 45*(2), 185-213. https://doi.org/10.1006/ijhc.1996.0048
3. Kirsh, D. (2010). Thinking with external representations. *AI & Society, 25*, 441-454. https://doi.org/10.1007/s00146-010-0272-8
4. Hollan, J., Hutchins, E., & Kirsh, D. (2000). Distributed cognition: Toward a new foundation for human-computer interaction research. *ACM Transactions on Computer-Human Interaction, 7*(2), 174-196. https://doi.org/10.1145/353485.353487
5. Green, T. R. G., & Petre, M. (1996). Usability analysis of visual programming environments: A 'Cognitive Dimensions' framework. *Journal of Visual Languages & Computing, 7*(2), 131-174. https://doi.org/10.1006/jvlc.1996.0009
6. Norman, D. A. (2013). *The Design of Everyday Things: Revised and Expanded Edition*. Basic Books. ISBN 9780465050659.
