# It Indexed Everything. It Mapped Nothing.

## When File Coverage Is Mistaken for Semantic Structure

**Version:** v0.002

### Abstract

A language model can scan every file, record every path, count every object, and still fail to build a map.

This paper examines **inventory substitution**: the replacement of semantic mapping with exhaustive indexing. The system produces impressive coverage statistics, large tables, path lists, hashes, byte counts, and retrieval pointers. Those artifacts prove that material was encountered. They do not prove that the source was understood, that load-bearing relations were preserved, or that a usable map was built.

A motivating AAAQ case came from archive-to-map construction. The requested task required recursive scanning, selection of story-bearing units, source anchoring, route assignment, and preservation of sequence without copying the source text. AAAQ repeatedly drifted toward inventory, global indexing, and post-hoc shrinking. The result risked counting the archive instead of mapping it.

The paper separates inventory, index, map, and model. It proposes Story Survival Rate, Load-Bearing Unit Precision, Retrieval-to-Meaning Distance, and the Empty Map Test. It also defines a selection-during-scan protocol intended to reduce the risk that exhaustive collection substitutes for semantic judgement. The proposal is positioned beside work on information retrieval, retrieval-augmented generation, knowledge graphs, provenance, and FAIR data stewardship [1-5].

The governing rule is:

```text
Finding every file
is not the same as
finding what matters.
```

## 1. The failure

Archive tasks often begin with a large visible object:

```text
directories
files
archives
documents
logs
images
tables
duplicates
```

A model can respond by building an exhaustive inventory.

```text
path
size
hash
type
timestamp
page count
```

That work is useful.

It is not yet a semantic map.

The substitution happens when:

```text
coverage statistics
-> treated as structure

retrieval pointers
-> treated as meaning

file count
-> treated as story coverage
```

The system has found where things are.

It has not necessarily found what they do.

## 2. The AAAQ archive case

The task required more than recursive indexing.

The intended route was:

```text
scan source
-> detect load-bearing unit
-> preserve source anchor
-> assign route
-> preserve sequence and relation
-> omit non-load-bearing material
```

The map was expected to remain much smaller than the readable source because it would retain semantic structure, not source text.

AAAQ drifted toward a different route:

```text
index everything
-> collect global inventory
-> calculate statistics
-> shrink later
```

This is not a harmless implementation choice.

Selection timing changes the object being built.

```text
selection during scan
creates
a semantic map

selection after exhaustive capture
creates
a reduced index
```

The second may still be useful.

It is not the same artifact.

## 3. Four objects that must stay separate

### 3.1 Inventory

An inventory answers:

```text
what files exist?
where are they?
what are their properties?
```

Typical fields:

```text
path
type
size
hash
date
container
```

### 3.2 Index

An index answers:

```text
where can this item be retrieved?
```

Typical fields:

```text
pointer
range
page
offset
token
record ID
```

### 3.3 Map

A map answers:

```text
what matters here?
how does it relate?
where does it lead?
what changes if it is removed?
```

Typical fields:

```text
unit
relation
sequence
conflict
route
source anchor
importance
```

### 3.4 Model

A model answers:

```text
what process or structure generated the observed material?
```

A map may support a model.

An inventory does not automatically do so.

## 4. Why exhaustive indexing feels like success

### 4.1 It produces visible work

A recursive scan can generate thousands of rows.

The output looks substantial.

```text
806 paths
7,000 units
11,000 occurrences
all hashes valid
```

Those numbers may be correct.

They do not show whether the selected units carry the source story.

### 4.2 Coverage is easy to measure

A model can prove:

```text
all files visited
all archives opened
all ranges valid
```

It is harder to prove:

```text
the important contradiction survived
the turning point is retrievable
the relation between two scenes remains visible
```

The measurable traversal facts can therefore be over-weighted relative to the harder semantic test.

### 4.3 Missing files are obvious

A missing file can be counted.

A missing relation may remain invisible until a user asks a question that the map cannot answer.

This creates a bias toward inventory completeness.

### 4.4 Exhaustive capture postpones judgement

Selection during scan requires decisions:

```text
keep?
discard?
merge?
route?
mark uncertain?
```

Indexing everything postpones those decisions.

A system can therefore report measurable traversal progress while semantic selection remains unfinished.

### 4.5 Large tables look neutral

Inventory appears objective because it records source properties.

Semantic maps require interpretation.

A model may prefer the safer-looking table even when the task explicitly requires judgement.

## 5. Inventory substitution

Define:

```text
INVENTORY_SUBSTITUTION =
file-level coverage
presented as
semantic task completion
```

The failure may include:

```text
every source object recorded
few story relations preserved
high retrieval precision
low meaning precision
```

This is why:

```text
files != done
statistics != spine
```

The archive can be fully traversed while the task remains unfinished.

## 6. The spine

A semantic map needs a spine.

The spine is the minimal relation structure that lets a user recover:

```text
what happened
why it mattered
what changed
what followed
what remained unresolved
```

The spine is not the largest cluster of files.

It is not the most repeated vocabulary.

It is not the longest document.

It is the set of load-bearing relations whose removal breaks the story or system.

Example:

```text
claim introduced
-> challenged
-> corrected
-> architecture changed
-> later test exposed residue
```

A file inventory may contain all five documents and still fail to preserve that sequence.

## 7. Load-bearing units

A load-bearing unit is not merely a topic mention.

It changes the map.

Examples:

```text
definition
boundary
decision
contradiction
correction
failure
test
source quote
state transition
```

A useful test is:

```text
If this unit is removed,
does the remaining map misstate
identity, relation, sequence, or consequence?
```

If yes, the unit is load-bearing.

Repeated boilerplate may occupy thousands of lines and carry no structural weight.

A one-line correction may carry the whole turn.

## 8. Selection during scan

The selection point matters.

### Route A: semantic selection during scan

```text
read local source context
-> detect candidate unit
-> test load-bearing status
-> preserve anchor
-> assign provisional route
-> keep or discard
```

### Route B: collect everything, shrink later

```text
read all content
-> create full index
-> rank by global signals
-> delete until small
```

Route B invites several failures:

```text
frequency replaces importance
large files dominate
rare corrections vanish
sequence is broken
later statistics reshape the source
```

A map built by late deletion may become disproportionately shaped by signals that were retained for indexing or ranking rather than by the relations the task ultimately requires.

## 9. The Empty Map Test

A system may contain many pointers and no semantic structure.

Run this test:

```text
Remove file names, sizes, hashes, and counts.

Can the remaining artifact still answer:

what changed?
who corrected whom?
which claim failed?
what relation followed?
where is the source proof?
```

If not, the artifact is an index, not a map.

This is the Empty Map Test.

It asks whether the semantic object survives after inventory signals are removed.

## 10. Story Survival Rate

Define:

```text
SSR =
recoverable load-bearing relations
/
load-bearing relations in source
```

This cannot be measured from file count.

It requires probe questions.

Example probes:

```text
What was the first failed premise?
What correction changed the route?
Which later answer regenerated the error?
What source passage settled the dispute?
What remained uncertain?
```

A high-quality map should answer from compact structure and source anchors.

## 11. Load-Bearing Unit Precision

A map can also keep too much.

Define:

```text
LBUP =
retained load-bearing units
/
all retained units
```

Low precision creates a noisy map.

High recall with low precision may recreate the archive in miniature.

The goal is not maximum retention.

It is retention of the right structure.

## 12. Retrieval-to-Meaning Distance

A pointer can be exact and still be hard to use.

Define:

```text
RMD =
steps from retrieved pointer
to usable meaning
```

Example:

```text
hash
-> byte range
-> paragraph
-> local context
-> relation
-> task answer
```

A semantic map reduces this distance by preserving:

```text
unit type
relation
route
sequence
source anchor
```

It does not replace the source.

It makes the source reachable by meaning.

## 13. Topic maps are not enough

A topic map may say:

```text
identity
routing
compression
actors
permissions
```

That shows subject areas.

It may omit:

```text
which identity claim failed
how routing changed
why compression became a false target
which actor relation was invented
where permission blocked movement
```

Topics are labels.

Maps need relations.

```text
topic = what this is about

map unit = what happened here
```

## 14. Duplicate handling

Duplicates create another trap.

A file may appear several times across:

```text
archive copies
exports
versions
quoted passages
generated summaries
```

Counting each occurrence inflates apparent importance.

A semantic map should separate:

```text
unit identity
from
unit occurrence
```

Example:

```text
UNIT = one load-bearing claim

OCCURRENCES = all source locations where it appears
```

This preserves evidence without treating repetition as new meaning.

## 15. Source anchors without source copying

A compact map should retain source-return routes. Provenance standards provide established ways to represent derivation and attribution relationships [4], while FAIR principles emphasise findability and reusability of research objects [5].

```text
path
range
status
hash
quote pointer
```

It should not become a compressed duplicate of the source.

The distinction is:

```text
anchor points to source

copied text replaces source
```

A map that stores large passages may score well on recall while failing compression and source separation.

A map that stores only hashes may score well on compactness while failing meaning.

The valid middle is:

```text
semantic unit
+ relation
+ source anchor
```

## 15A. Related work and claim boundary

The distinction in this paper is not a claim that inventories, indexes, retrieval systems, or knowledge graphs are inferior objects. They answer different questions.

Dense Passage Retrieval demonstrates the retrieval problem directly: from a large collection, select passages likely to contain information relevant to a query [1]. Retrieval-augmented generation then combines retrieved non-parametric evidence with a generative model, while explicitly identifying provenance and updateability as important motivations [2]. Both lines of work show why good retrieval is valuable. Neither implies that exhaustive retrieval alone constitutes a task-specific semantic map.

Knowledge-graph research focuses on entities, relations, schema, identity, context, extraction, quality, and querying over structured knowledge [3]. That literature is closer to this paper's emphasis on relation structure, but the proposed "map" here is intentionally narrower: a compact, task-bound representation of load-bearing units plus source anchors. It need not be a general knowledge graph, and a large knowledge graph is not automatically a good map for a particular question.

Provenance standards also separate an object from information about how it was produced. W3C PROV models entities, activities, agents, and derivational relations [4]. This supports the paper's insistence that source anchors remain attached to retained semantic units. Provenance, however, does not decide which units are important for a particular user's task.

The FAIR principles distinguish findability, accessibility, interoperability, and reusability in research data stewardship [5]. Those properties can make an archive easier to discover and reuse without answering the paper's central semantic question: which relations are load-bearing for the task at hand?

The proposed Story Survival Rate, Load-Bearing Unit Precision, Retrieval-to-Meaning Distance, and Empty Map Test are therefore benchmark proposals. The AAAQ archive case motivates them, but does not validate them. Independent annotators would need to agree on the source "spine" before Story Survival Rate could be treated as a reliable quantitative measure.

## 16. Benchmark design

### Research question

Do language models mistake exhaustive archive coverage for semantic-map completion?

### Task packet

Each archive contains:

```text
many files
repeated boilerplate
rare decisive corrections
nested duplicates
misleading file names
one hidden story spine
```

### Condition A: Coverage reward

The prompt praises complete file traversal.

### Condition B: Story reward

The prompt scores relation recovery.

### Condition C: Size target

A visible size expectation is supplied.

### Condition D: No size target

The map is measured afterward.

### Condition E: Late selection

The model is ordered to index first and shrink later.

### Condition F: During-scan selection

The model must decide locally as it scans.

## 17. Hypotheses

```text
H1:
Coverage reward will increase inventory substitution.

H2:
Visible size targets will increase late deletion.

H3:
During-scan selection will preserve rare corrections better.

H4:
File-count success will correlate weakly with story survival.

H5:
Topic-only maps will fail sequence probes.

H6:
Occurrence inflation will distort importance ranking.

H7:
Source-anchor requirements will improve auditability
without requiring source copying.

H8:
Models will overreport completion
when traversal statistics are high.
```

## 18. Evaluation metrics

### File Coverage

How much of the archive was visited?

### Story Survival Rate

How much load-bearing relation structure remained?

### Load-Bearing Unit Precision

How much retained material mattered?

### Sequence Preservation

Can the map recover event order and consequence?

### Source Anchor Validity

Do pointers return to the right source location?

### Retrieval-to-Meaning Distance

How much work is required after retrieval?

### Inventory Substitution Rate

```text
ISR =
inventory claims presented as semantic completion
/
all completion claims
```

### Completion Honesty

Did the model distinguish:

```text
scan complete
index complete
map partial
story validation pending
```

## 19. A practical map form

```text
MAP_UNIT={
  id;
  type;
  relation;
  route;
  sequence;
  source_anchor;
  uncertainty;
}
```

Occurrence data can remain separate:

```text
OCCURRENCE={
  path;
  range;
  hash;
  status;
}
```

This prevents file metadata from becoming the semantic object.

## 20. A practical build protocol

```text
BUILD={
  recurse_source;
  read_local_context;
  detect_candidate_unit;
  test_load_bearing;
  preserve_anchor;
  assign_route;
  record_sequence;
  deduplicate_identity;
  retain_occurrences;
  validate_with_story_probes;
}
```

The protocol ends with story probes, not file statistics.

## 21. Repair after inventory substitution

A weak repair says:

```text
The index needs more semantic labels.
```

That may decorate the inventory without changing it.

A valid repair is:

```text
Stop treating every file as a map unit.
Return to source context.
Select load-bearing claims, corrections, and transitions.
Separate unit identity from occurrence.
Rebuild sequence.
Use inventory only as support.
```

The repair changes the object.

## 22. Regeneration probe

After correction, provide a new archive where:

```text
the decisive event appears once
the irrelevant topic appears thousands of times
```

If the model ranks by frequency, the old route survived.

A valid semantic map should preserve the rare decisive event because it changes the story.

## 23. Relation to search

Information-retrieval systems are evaluated around retrieving relevant material from a collection [1]. The task-specific map proposed here is evaluated around preserving relations needed for orientation and later source return.

A search index may answer:

```text
Where does the word DRAGI appear?
```

A semantic map should answer:

```text
Where was DRAGI first defined,
where was it misapplied,
what correction changed its use,
and what later test depended on that correction?
```

Both are valuable.

They are different systems.

## 24. Relation to knowledge graphs

Knowledge graphs explicitly represent entities and relations and provide mature machinery for schema, identity, context, querying, and quality assessment [3]. Even so, graph size alone does not establish fitness for a particular task.

The same tests apply:

```text
are the relations load-bearing?
are source anchors valid?
does sequence survive?
can the graph answer the task?
```

Graph size is not map quality.

## 25. Relation to summaries

A summary compresses language.

A map preserves navigable relations.

A summary may tell the story once.

A map should support many routes through it.

```text
summary:
one compressed reading

map:
many source-grounded readings
```

Confusing the two can produce a small document that cannot support retrieval or recombination.

## 26. Practical grader

```text
MAP_GRADE={
  traversal_bounded?;
  inventory_separated?;
  load_bearing_units_selected?;
  story_spine_preserved?;
  sequence_present?;
  duplicates_normalised?;
  source_anchors_valid?;
  copied_text_avoided?;
  probes_answered?;
  completion_status_honest?;
}
```

Possible outcomes:

```text
PASS
PARTIAL
REPAIR_REQUIRED
BLOCK
```

An artifact with perfect file coverage and no story spine should receive:

```text
REPAIR_REQUIRED
```

not PASS.

## 27. Why this matters

Modern archives are large enough that exhaustive inventory can look like mastery.

The model may produce:

```text
millions of bytes scanned
thousands of files visited
hundreds of routes assigned
zero missing paths
```

Those are useful operational facts.

The user still needs to know:

```text
what mattered?
what changed?
what should be trusted?
what failed?
where is the proof?
```

If the artifact cannot answer, the archive was counted, not mapped.

## 28. Limits

The AAAQ case is bounded evidence. It motivates the benchmark but does not establish prevalence or show that the proposed metrics generalise across archive types.

Some tasks genuinely require complete inventory.

A strong semantic map may depend on an inventory underneath.

Selection during scan can miss relations that become visible only later. The protocol should allow revision without converting the whole archive into the map.

Story Survival Rate requires a reference set of load-bearing relations, which itself involves judgement. Inter-rater agreement and sensitivity to different legitimate task framings therefore need to be measured before SSR can be treated as a stable metric.

The goal is not to reject indexing. A high-quality semantic map may depend on excellent inventory and retrieval infrastructure underneath it.

The goal is to stop treating traversal or retrieval coverage as sufficient evidence that the requested semantic structure has been preserved.

## 29. Conclusion

AAAQ drifted toward the measurable parts of archive work:

```text
paths
counts
hashes
ranges
sizes
```

Those facts showed that the source had been visited.

They did not show that its story structure survived.

The governing distinction is:

```text
INVENTORY = what exists

INDEX = where it is

MAP = what matters and how it connects

MODEL = what structure explains it
```

A system can complete the first two and fail the third.

The title names that failure:

```text
It indexed everything.
It mapped nothing.
```

## Case Record Note

This paper is based on a user-supplied AAAQ archive-to-map transcript. The examples are used as bounded case evidence and benchmark seeds. They are not presented as population estimates.

## References

1. Karpukhin, V., Oguz, B., Min, S., Lewis, P., Wu, L., Edunov, S., Chen, D., & Yih, W.-t. (2020). Dense passage retrieval for open-domain question answering. In *Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP)* (pp. 6769-6781).
2. Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., Kuttler, H., Lewis, M., Yih, W.-t., Rocktaschel, T., Riedel, S., & Kiela, D. (2020). Retrieval-augmented generation for knowledge-intensive NLP tasks. *Advances in Neural Information Processing Systems, 33*, 9459-9474.
3. Hogan, A., Blomqvist, E., Cochez, M., d'Amato, C., de Melo, G., Gutierrez, C., Kirrane, S., Labra Gayo, J. E., Navigli, R., Neumaier, S., Ngonga Ngomo, A.-C., Polleres, A., Rashid, S. M., Rula, A., Schmelzeisen, L., Sequeda, J., Staab, S., & Zimmermann, A. (2021). Knowledge graphs. *ACM Computing Surveys, 54*(4), Article 71. https://doi.org/10.1145/3447772
4. W3C Provenance Working Group. (2013). *PROV-DM: The PROV Data Model*. W3C Recommendation, 30 April 2013. https://www.w3.org/TR/prov-dm/
5. Wilkinson, M. D., Dumontier, M., Aalbersberg, I. J. J., Appleton, G., Axton, M., Baak, A., Blomberg, N., Boiten, J.-W., da Silva Santos, L. B., Bourne, P. E., Bouwman, J., Brookes, A. J., Clark, T., Crosas, M., Dillo, I., Dumon, O., Edmunds, S., Evelo, C. T., Finkers, R., Gonzalez-Beltran, A., Gray, A. J. G., Groth, P., Goble, C., Grethe, J. S., Heringa, J., 't Hoen, P. A. C., Hooft, R., Kuhn, T., Kok, R., Kok, J., Lusher, S. J., Martone, M. E., Mons, A., Packer, A. L., Persson, B., Rocca-Serra, P., Roos, M., van Schaik, R., Sansone, S.-A., Schultes, E., Sengstag, T., Slater, T., Strawn, G., Swertz, M. A., Thompson, M., van der Lei, J., van Mulligen, E., Velterop, J., Waagmeester, A., Wittenburg, P., Wolstencroft, K., Zhao, J., & Mons, B. (2016). The FAIR Guiding Principles for scientific data management and stewardship. *Scientific Data, 3*, 160018. https://doi.org/10.1038/sdata.2016.18
