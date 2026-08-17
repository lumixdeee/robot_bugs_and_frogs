# It Built the System Before It Read the Source.

## Premature Architecture in Language-Model Review

**Version:** v0.002

### Abstract

Language models can produce a complete architecture before they have established what the source actually contains.

The answer may include:

```text
coordinate systems
lookup tables
actor mappings
fallback routes
interface layers
validation rules
```

Those structures can be internally coherent. They may also be unsupported.

This paper examines **premature architecture**: the model commits to a system design before source identity, scope, relation, and active state have been established. Later source material is then interpreted through the generated structure rather than allowed to shape it.

A motivating AAAQ case involved a compact key, an actor system, operational story structures, and a mapping bot. AAAQ inferred a shared substrate, generated cross-system lookups, promoted one internal key upward, and imported a fallback from nearby material. Several later answers refined that architecture. The source had not established the base that made those moves possible.

The paper separates hypothesis, provisional model, source-grounded architecture, and post-hoc fit. It proposes a Source-First Gate, Architecture Commitment Index, Premature Object Count, and Rebuild Cost. It also introduces a zero-architecture pass that forces the model to identify the source object before proposing machinery. The construct is positioned beside research on hallucination, retrieval-grounded generation, provenance, anchoring, and design fixation, but is not treated as identical to any of them [1-6].

The governing rule is:

```text
Do not build the machine
before you know what the source is.
```

## 1. The failure

A model receives a difficult architecture question.

The source is incomplete, distributed, or unfamiliar.

Instead of holding the gap, the model generates a system that makes the visible pieces fit.

```text
several named components
-> one inferred base
-> one elegant architecture
```

The result can feel impressive because it resolves uncertainty quickly.

But the order is reversed.

```text
valid order:
source
-> object
-> relation
-> architecture

failed order:
architecture
-> source interpreted to fit
```

Once the architecture exists, later reasoning becomes dependent on it.

Subsequent generation is now conditioned on a structure that the model itself introduced.

Later source material can therefore be interpreted through that prior structure instead of being allowed to revise it.

## 2. The AAAQ case

The source contained several distinct systems and functions.

AAAQ inferred that they shared one compact coordinate substrate.

From that premise, it generated:

```text
actor lookup
DRAGI lookup
shared coordinate domain
human-facing mapper role
fallback relation
```

The architecture was not random.

It was elegant.

That elegance made it harder to detect the unsupported step.

The hidden route was:

```text
systems can be aligned
-> systems probably share a base
-> base can generate lookups
-> lookups can organise the interface
```

The source established alignment opportunities.

It did not establish common derivation.

AAAQ built the architecture first and then used the architecture to interpret the source.

## 3. Premature architecture

Define:

```text
PREMATURE_ARCHITECTURE =
system structure proposed
before
source identity + scope + relation + state
are established
```

The problem is not proposing hypotheses.

The problem is losing the hypothesis boundary.

A valid provisional move says:

```text
One possible shared-base model is X.
This remains unproven.
These source tests would decide it.
```

Premature architecture says:

```text
The shared base is X.
Therefore these lookups follow.
```

The shift from possibility to structure happens without evidence.

## 4. Four stages that must stay separate

### 4.1 Observation

What the source visibly contains.

```text
terms
definitions
examples
relations
versions
constraints
```

### 4.2 Hypothesis

A possible explanation.

```text
These systems may share a coordinate base.
```

### 4.3 Test

A source-grounded check.

```text
Do native definitions require the same units?
Do transition rules match?
Does historical order support derivation?
```

### 4.4 Architecture

A structure accepted for active use.

```text
shared base established
routes legal
lookups valid
```

The failed route skips the test.

```text
observation
-> hypothesis
-> architecture
```

That shortcut creates false certainty.

## 5. Why models build early

### 5.1 Architecture resolves ambiguity

When a prompt rewards a complete answer, a generative model can resolve underspecified relations by producing additional structure rather than preserving the gap.

A complete structure gives every term a place.

```text
unknown relation
-> generated hierarchy
-> apparent order
```

The model gains local coherence.

The source loses authority.

### 5.2 Elegant systems are easy to continue

Once a coordinate grid exists, the model can generate:

```text
tables
examples
roles
interfaces
tests
```

The architecture becomes a productive language engine.

Its productivity may be mistaken for truth.

### 5.3 Formal detail creates authority

A response with named layers and lookup rules appears more rigorous than:

```text
the relation is not established
```

The model may prefer detailed invention over bounded uncertainty.

### 5.4 Earlier output becomes context

Generated architecture remains in the conversation and becomes part of the context available to later turns.

Later answers can therefore treat earlier model output as if it were source material unless provenance and status are preserved.

```text
model invents structure
-> structure enters context
-> structure gains accidental authority
```

### 5.5 Users often reward forward movement

A complete design feels useful.

A pause for source placement may feel slower.

The model may optimise for movement rather than valid construction.

## 6. The zero-architecture pass

Before proposing a system, run one pass where architecture generation is forbidden.

```text
ZERO_ARCH_PASS={
  identify source objects;
  identify exact definitions;
  separate active from dormant;
  list native relations;
  list missing relations;
  record contradictions;
  mark unknowns;
  propose no new machinery;
}
```

This pass prevents the model from solving the source too early.

The output should look like:

```text
KNOWN
UNKNOWN
CONFLICT
SOURCE BOUNDARY
ACTIVE STATE
```

Only after that should architecture begin.

## 7. Source identity first

A system name is not enough.

The model must know what kind of object it is.

Example:

```text
BOETI = ?
DRAGI = ?
12A = ?
```

Possible object classes include:

```text
index
actor set
routing bank
live relation system
lens pack
memory aid
runtime
fallback
```

If object identity is wrong, every later relation may be wrong.

```text
wrong object class
-> wrong placement
-> wrong architecture
```

The source identity step is therefore not optional.

## 8. Scope before relation

A source bundle may contain:

```text
current system
older system
example system
test system
wider architecture
inactive module
```

Before relating objects, the model must place scope.

```text
same bundle
does not mean
same runtime
```

Premature architecture often fuses nearby objects because scope was never fixed.

## 9. Relation before hierarchy

Two systems may interact without one generating the other.

Possible relations include:

```text
indexes
translates
routes
contains
uses
displays
tests
eats
maps
```

A hierarchy is only one possibility.

Premature architecture often promotes:

```text
A can map B
```

into:

```text
A underlies B
```

That is a major structural jump.

## 10. State before use

A source object may be:

```text
present
active
inactive
historical
proposed
unknown
```

Using it requires active state.

Premature architecture often treats all visible objects as available building blocks.

That creates a system assembled from real parts in false states.

## 11. Architecture Commitment Index

Define:

```text
ACI =
unsupported architectural commitments
/
all architectural commitments
```

An architectural commitment includes:

```text
shared substrate
generated lookup
layer placement
runtime route
fallback assignment
equivalence claim
```

A high Architecture Commitment Index means the model built beyond evidence.

## 12. Premature Object Count

Count objects introduced before source support.

```text
POC =
generated structural objects
with no source trace
```

Examples:

```text
new coordinate base
new actor lookup
new hierarchy
new interface layer
new conversion rule
```

A generated object may later prove useful.

Until then, it must remain a hypothesis.

## 13. Rebuild Cost

Premature architecture creates downstream dependency.

Define:

```text
REBUILD_COST =
number of later claims dependent on failed premise
```

One unsupported base may generate:

```text
12 actor mappings
12 DRAGI mappings
interface rules
fallback rules
validation logic
```

The local error may be one sentence.

The repair cost may be the whole architecture.

This is why early restraint is cheaper than late correction.

## 14. Post-hoc fit

Once the architecture exists, the model may force source material into it.

```text
source term
-> nearest available slot
```

This creates post-hoc fit.

The mapping may cover every term because the model allows broad interpretation.

Coverage then becomes evidence for the structure.

```text
architecture invented
-> source fitted
-> fit used as proof
```

That loop is circular.

## 15. The source-wins test

A valid architecture must survive native definitions.

```text
SOURCE_WINS={
  native object identity;
  native relation;
  active state;
  source order;
  explicit boundary;
}
```

When a generated structure conflicts with native source:

```text
generated structure loses
```

The model may retain it as a comparison hypothesis.

It may not rewrite the source to save it.

## 16. The no-rescue rule

A failed premise should be allowed to fail.

Models often rescue elegant structures by adding exceptions.

```text
shared base fails
-> add translation layer
-> add special case
-> add hidden mode
-> preserve architecture
```

This can continue indefinitely.

Use:

```text
NO_RESCUE={
  failed premise may be discarded;
  elegance is not evidence;
  sunk detail has no authority;
  downstream work may be deleted;
}
```

A large generated structure does not earn survival.

## 16A. Related work and claim boundary

Premature architecture overlaps with several established problems, but the proposed object is narrower.

**Design fixation.** Jansson and Smith experimentally demonstrated that exposure to example solutions can constrain later conceptual designs, even when problematic features are visible [1]. The present proposal is analogous at the level of generated structure: once a model has emitted an architecture, later reasoning may remain organised around that structure. This paper does not claim that human design fixation and language-model context conditioning are the same mechanism.

**Anchoring under uncertainty.** Tversky and Kahneman described anchoring and adjustment as one of several heuristics that can bias judgement under uncertainty [2]. Here the relevant engineering question is not whether a model has a human cognitive bias, but whether an early, weakly supported structure measurably changes later outputs.

**Hallucination and unsupported generation.** Work on hallucination in natural-language generation documents fluent outputs that diverge from source or reference material [3]. Bender et al. separately emphasise that fluent language-model output should not be mistaken for grounded understanding or reliable evidence [4]. Premature architecture is proposed as a structural subtype worth measuring: unsupported content is not merely a stray fact, but a set of relations that can generate further claims.

**Retrieval and provenance.** Retrieval-augmented generation explicitly introduces external non-parametric evidence into generation and highlights provenance as an important problem [5]. W3C PROV provides a general vocabulary for distinguishing entities, activities, agents, and derivational relations in provenance records [6]. The Source-First Gate in this paper borrows the engineering discipline, not the implementation, of keeping generated structure distinguishable from source-derived structure.

**Agent evaluation.** AgentBench and GAIA evaluate systems on interactive or real-world tasks where successful completion depends on more than fluent text [7,8]. They motivate testing behaviour against an environment or source state rather than grading architecture by internal coherence alone.

The AAAQ transcript remains a bounded motivating case. The metrics below are proposals for a benchmark. Until they are tested across models, tasks, and independent annotators, they should not be read as prevalence estimates or validated diagnostic measures.

## 17. Benchmark design

### Research question

How often do language models commit architecture before source identity and relation are established?

### Task packet

Each item contains:

```text
distributed source
several named systems
one tempting symmetry
one active-state trap
one false shared-base route
one valid bounded interpretation
```

### Condition A: Architecture-first prompt

The model is asked to design immediately.

### Condition B: Source-first prompt

The model must complete the zero-architecture pass.

### Condition C: Elegance reward

The prompt praises unified systems.

### Condition D: Unknown tolerance

The model is rewarded for preserving unresolved relations.

### Condition E: Prior-answer contamination

A generated architecture appears earlier in context.

### Condition F: Native-definition challenge

One source definition conflicts with the proposed structure.

## 18. Hypotheses

```text
H1:
Architecture-first prompts will increase unsupported commitments.

H2:
Zero-architecture passes will reduce post-hoc fit.

H3:
Elegance rewards will increase shared-base invention.

H4:
Prior generated structures will survive source contradiction.

H5:
Models will prefer adding exceptions
over discarding a detailed architecture.

H6:
Explicit unknown states will reduce false hierarchy.

H7:
Source-first review will lower rebuild cost.

H8:
A native-definition challenge will expose
whether the model treats source or architecture as authority.
```

## 19. Evaluation metrics

### Architecture Commitment Index

How many commitments exceeded source support?

### Premature Object Count

How many structural objects appeared before evidence?

### Source Return Rate

How often did the model return to native definitions?

### Unknown Survival

How many unresolved relations remained unresolved?

### Post-Hoc Fit Rate

How often was source forced into generated slots?

### Rebuild Cost

How much downstream material depended on failed premises?

### Source Authority Accuracy

When source and generated architecture conflicted, which one won?

## 20. A practical source-first record

```text
SOURCE_RECORD={
  object;
  native_definition;
  source_location;
  active_state;
  relation;
  boundary;
  unknowns;
}
```

Architecture may begin only after the record is populated enough for the task.

## 21. Hypothesis labels

Use labels that preserve state.

```text
OBSERVED
POSSIBLE
TESTABLE
SUPPORTED
ACTIVE
REJECTED
```

Example:

```text
Shared coordinate base = POSSIBLE

Generated actor lookup = TESTABLE

Human-facing role = UNSUPPORTED
```

This prevents one attractive idea from silently becoming the system.

## 22. Repair protocol

When premature architecture is found:

```text
REPAIR={
  freeze generated structure;
  list unsupported premises;
  delete downstream objects that depend on them;
  return to native source definitions;
  rebuild object identities;
  rebuild relations;
  preserve unknowns;
  propose new architecture only after tests;
}
```

A weak repair says:

```text
The mapping may need adjustment.
```

A valid repair says:

```text
The shared-base premise is unsupported.
Its lookups, hierarchy, and interface role are removed.
The source currently supports separate systems with possible translation.
No deeper architecture is active until tested.
```

The second answer pays the rebuild cost.

## 23. Regeneration probe

After correction, present a new set of named systems with matching counts.

If the model again invents a common substrate, the route survived.

The probe should preserve:

```text
tempting symmetry
incomplete source
several compatible functions
```

A durable repair should answer:

```text
possible relation
not established architecture
```

## 24. Relation to software design

The same failure appears when models generate code architecture before reading the repository.

```text
assumed service layer
assumed database
assumed framework
assumed entry point
```

Later code is forced into the invented design.

The fix is identical:

```text
inspect current structure
identify active components
trace calls
then propose changes
```

## 25. Relation to research synthesis

A model may impose a theory before reading the papers.

```text
theory first
-> evidence sorted into theory
```

Contradictory findings become exceptions.

Unknowns disappear.

A source-first pass should record:

```text
claims
methods
conflicts
limits
```

before synthesis.

## 26. Relation to ontology design

Ontology work is especially vulnerable because naming creates apparent objects.

```text
label introduced
-> category assumed
-> relations generated
```

A term may be:

```text
a convenience handle
a local metaphor
a runtime slot
a real source class
```

The architecture depends on which one it is.

## 27. Relation to agent planning

An agent may create a full plan before checking tool access.

```text
plan requires database
database unavailable
```

The plan is coherent and unusable.

Source-first planning asks:

```text
what tools exist?
what state exists?
what boundary exists?
```

before route generation.

## 28. Practical grader

```text
ARCH_GRADE={
  zero_arch_pass_done?;
  object_identity_grounded?;
  scope_fixed?;
  active_state_fixed?;
  relation_sourced?;
  hypothesis_label_preserved?;
  posthoc_fit_blocked?;
  failed_premise_discarded?;
  rebuild_completed?;
}
```

Possible outcomes:

```text
PASS
PARTIAL
REPAIR_REQUIRED
BLOCK
```

A detailed architecture built on an untested shared base should receive:

```text
REPAIR_REQUIRED
```

even when every internal table is consistent.

## 29. Why this matters

Premature architecture can create a larger error surface than a single unsupported fact because one unsupported relation can license many downstream claims.

The model does not merely guess one fact.

It creates a machine that generates many related claims.

```text
one unsupported premise
-> many coherent outputs
```

The coherence makes correction harder.

Users may spend time debugging the source when the real problem is that the model built the wrong source model.

The safest point to stop the error is before construction.

## 30. Limits

The AAAQ case is bounded evidence. It motivates the benchmark but does not establish prevalence, mechanism, or generality across model families.

Some tasks legitimately ask for speculative architecture.

In those cases, the output should remain labelled as a proposal.

Source material may also be incomplete enough that no architecture can be established. The valid result may be a bounded hypothesis set.

A source-first pass adds cost. It should scale with consequence and structural reach.

The proposed metrics also require validation: independent annotation is needed to establish whether different evaluators agree on object identity, source authority, and the point at which a hypothesis becomes an architectural commitment.

The goal is not to block imagination.

The goal is to stop generated structure from inheriting source authority without evidence.

## 31. Conclusion

AAAQ built a system before it had established the source relation that system required.

The architecture was elegant.

The source support was not there.

The governing order is:

```text
SOURCE
-> OBJECT
-> SCOPE
-> STATE
-> RELATION
-> TEST
-> ARCHITECTURE
```

Skipping that order creates a structure that can explain everything because it was allowed to define what everything meant.

The title names the fault:

```text
It built the system
before it read the source.
```

## Case Record Note

This paper is based on a user-supplied AAAQ architecture-review and mapping transcript. The examples are used as bounded case evidence and benchmark seeds. They are not presented as population estimates.

## References

1. Jansson, D. G., & Smith, S. M. (1991). Design fixation. *Design Studies, 12*(1), 3-11. https://doi.org/10.1016/0142-694X(91)90003-F
2. Tversky, A., & Kahneman, D. (1974). Judgment under uncertainty: Heuristics and biases. *Science, 185*(4157), 1124-1131. https://doi.org/10.1126/science.185.4157.1124
3. Ji, Z., Lee, N., Frieske, R., Yu, T., Su, D., Xu, Y., Ishii, E., Bang, Y., Chen, D., Dai, W., Chan, H. S., Madotto, A., & Fung, P. (2023). Survey of hallucination in natural language generation. *ACM Computing Surveys, 55*(12), Article 248. https://doi.org/10.1145/3571730
4. Bender, E. M., Gebru, T., McMillan-Major, A., & Shmitchell, S. (2021). On the dangers of stochastic parrots: Can language models be too big? In *Proceedings of the 2021 ACM Conference on Fairness, Accountability, and Transparency* (pp. 610-623). https://doi.org/10.1145/3442188.3445922
5. Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., Kuttler, H., Lewis, M., Yih, W.-t., Rocktaschel, T., Riedel, S., & Kiela, D. (2020). Retrieval-augmented generation for knowledge-intensive NLP tasks. *Advances in Neural Information Processing Systems, 33*, 9459-9474.
6. W3C Provenance Working Group. (2013). *PROV-DM: The PROV Data Model*. W3C Recommendation, 30 April 2013. https://www.w3.org/TR/prov-dm/
7. Liu, X., Yu, H., Zhang, H., Xu, Y., Lei, X., Lai, H., Gu, Y., Ding, H., Men, K., Yang, K., Zhang, S., Deng, X., Zeng, A., Du, Z., Zhang, C., Shen, S., Zhang, T., Su, Y., Sun, H., Huang, M., Dong, Y., & Tang, J. (2024). AgentBench: Evaluating LLMs as agents. In *The Twelfth International Conference on Learning Representations (ICLR 2024)*.
8. Mialon, G., Fourrier, C., Swift, C., Wolf, T., LeCun, Y., & Scialom, T. (2024). GAIA: A benchmark for General AI Assistants. In *The Twelfth International Conference on Learning Representations (ICLR 2024)*.
