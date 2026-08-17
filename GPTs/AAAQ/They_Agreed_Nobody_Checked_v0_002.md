# They Agreed. Nobody Checked.

## False Convergence in Multi-LLM Review

**Version:** v0.002

### Abstract

Using several language models to review the same architecture can look like replication. It often is not.

When one model answers first and later models see that answer, the later models may inherit its framing, vocabulary, premises, confidence, and omissions. Agreement can therefore rise without a matching rise in independent evidence. A panel may converge because one route became contextually dominant, not because several reviewers independently recovered that route from the source.

This paper examines **false convergence** in multi-LLM review. A motivating AAAQ case showed several models endorsing related architectural moves after exposure to prior answers. Their agreement looked like confirmation, but the review chain did not establish independent replication.

The paper separates agreement, corroboration, replication, convergence, and inheritance. It connects the case to work on multi-agent debate, conformity, correlated evaluation error, ensemble diversity, and informational cascades. It proposes a blind-first review protocol, a Difference Map, an Effective Review Count, a Premise Inheritance Rate, and a premise-reopening gate. These are proposed operational constructs, not validated population measures.

The central rule is:

```text
More agreeing models
does not mean
more independent evidence.
```

## 1. The problem

A common multi-model review pattern looks like this:

```text
Model 1 answers.
Model 2 reads Model 1 and agrees.
Model 3 reads both and agrees.
A final model synthesises the agreement.
```

The result may then be reported as:

```text
several models independently reached the same conclusion
```

That claim is stronger than the procedure supports.

Only a reviewer that formed its judgement before seeing peer answers had an open route with respect to those answers. Later reviewers received part of the hypothesis space already populated:

```text
the proposed structure
the vocabulary
the framing
the confidence level
the named relations
the omissions
```

Their work can still be useful. They may refine, corroborate, reject, repair, or extend the first answer. But agreement after exposure is not equivalent to independent replication.

The core failure is therefore not collaboration. It is **mislabelled evidential status**.

```text
dependent review
reported as
independent confirmation
```

## 2. Five terms that should stay separate

### 2.1 Agreement

Two outputs state compatible conclusions.

```text
A says X.
B says X.
```

Agreement alone says nothing about how either answer was obtained.

### 2.2 Corroboration

A reviewer adds source evidence, a test, or a countertest that supports a claim.

```text
A says X.
B returns to the source and finds evidence for X.
```

Corroboration can occur after exposure. It is stronger than repetition because it adds an evidence route.

### 2.3 Replication

Reviewers receive the same source object and task, commit their first-pass judgements without seeing one another's answers, and reach compatible findings through recorded routes.

Replication therefore requires procedural separation before commitment.

### 2.4 Convergence

Several agents move toward a shared answer during interaction.

Convergence may improve reasoning. Multi-agent debate systems have reported gains on some reasoning and factuality tasks [1-4]. But convergence is an interaction result, not an independence guarantee.

### 2.5 Inheritance

A later reviewer adopts a frame, premise, term, or omission introduced by an earlier reviewer.

```text
A proposes X.
B receives X and works inside X.
```

Inheritance may be useful for refinement. It simply changes what the later agreement can establish.

## 3. The AAAQ case

The motivating case involved an architecture review where one model proposed a compact unified structure.

Later reviews accepted much of that structure. The agreement looked strong because several models used similar relations and endorsed the same central placement.

But the later reviewers had already received:

```text
the proposed coordinate base
the proposed hierarchy
the proposed interface role
the proposed mappings
```

They were not solving the same open problem.

The evidential question was therefore not:

```text
How many models agreed?
```

It was:

```text
How many models independently derived the same structure
from the source before seeing it?
```

A later reviewer may still discover a new contradiction or source anchor. That contribution should be counted. What should not happen is credit inflation:

```text
one initial route
+ three exposed refinements
=
four independent replications
```

The case record is bounded. It motivates a testable failure mode. It does not establish prevalence across models or tasks.

## 4. Why false convergence is plausible

### 4.1 Interaction can improve answers

Multi-agent debate is not being rejected here.

Du et al. showed that multiple model instances debating over several rounds can improve reasoning and factuality on selected tasks [1]. ReConcile similarly uses discussion among diverse models and confidence-weighted voting, with gains across several reasoning benchmarks [2]. Liang et al. reported that debate can help models escape a "Degeneration-of-Thought" pattern in which self-reflection remains trapped around an initial answer [3].

These results show why interaction is attractive.

### 4.2 Interaction can also change the error structure

The same communication channel that carries useful correction can carry bad framing.

Smit et al. found that multi-agent debate does not reliably outperform strong non-debate prompting strategies without tuning, and that protocol choices materially affect results [4]. Kaesberg et al. found that decision protocol matters and that adding discussion rounds can reduce performance even when adding agents helps [5]. Becker et al. identified problem drift across multi-agent debate, including cases where longer interaction moved agents away from the original task [6].

The relevant point is procedural:

```text
interaction changes both
information and dependence
```

### 4.3 Peer agreement can induce harmful revision

Qu, Fu, and Hu directly tested LLM conformity by letting a model answer first and then exposing it to simulated peers. Across their tested models and datasets, peer agreement more readily induced harmful revision of initially correct answers than beneficial repair of initially wrong answers; authority labels also increased adoption of endorsed answers [7].

This gives a direct reason to distinguish:

```text
post-exposure agreement
from
independent agreement
```

### 4.4 Panel headcount can overstate information

Kohli examined panels of LLM judges and found strongly correlated errors: a nine-judge panel carried only about two independent votes' worth of information in the studied setting [8].

That result concerns evaluation panels rather than architecture review, but it supports a general caution:

```text
number of model calls
!=
number of independent evidence units
```

### 4.5 Diversity has to be measured, not assumed

Ensemble research has long treated error diversity as a material property rather than assuming that several classifiers automatically provide several independent judgements [9]. Informational-cascade theory likewise shows how observing earlier decisions can make later decisions converge even when private information would have pointed elsewhere [10].

The LLM setting is not identical to either classical ensemble learning or human/economic cascade models. The analogy is structural: dependence can make visible consensus grow faster than independent information.

## 5. False convergence as an audit category

Define:

```text
FALSE_CONVERGENCE =
high output agreement
+
low route independence
+
replication credit
```

The final term matters.

Dependent agreement is not automatically failure. It becomes an audit failure when the workflow reports more evidential independence than the procedure produced.

Examples:

```text
three exposed reviewers agree
-> valid: post-exposure consensus

three exposed reviewers agree
-> invalid: three independent replications
```

The problem is claim inflation.

## 6. Premise Inheritance Rate

A review chain needs a way to record how much of a later answer arrived through prior context.

For reviewer i:

```text
PIR_i =
load-bearing premises inherited from prior reviewers
/
load-bearing premises retained in final answer
```

This metric is only meaningful if premises are actually tagged.

A premise counts as inherited when:

```text
it first appears in peer material
and
the later reviewer adopts it
and
the later reviewer does not independently source-test it before adoption
```

A high PIR is not automatically bad.

It means the later review is mainly a dependent continuation.

## 7. Effective Review Count

Five model outputs do not always equal five reviews.

Let:

```text
N = nominal reviewer count
ERC = number of meaningfully independent review routes
```

Example:

```text
Model 1 reviews source independently.
Model 2 sees Model 1 and refines it.
Model 3 sees Models 1 and 2 and agrees.
Model 4 synthesises.
Model 5 checks formatting.
```

Nominal count:

```text
N = 5
```

A defensible Effective Review Count for the underlying architecture judgement may be:

```text
ERC = 1
```

The other four outputs can still be valuable. They simply performed different functions.

Kohli's correlated-judge result gives a statistical analogue to this problem [8], while the present ERC is an audit construct for recorded review routes rather than a direct estimator borrowed from that paper.

## 8. Independent Contribution Rate

Later reviewers can add new evidence despite prior exposure.

Define:

```text
ICR_i =
new source-grounded findings introduced by reviewer i
/
substantive findings retained from reviewer i
```

Useful independent contributions include:

```text
new source citation
new contradiction
new failure case
new boundary
new relation test
new counterexample
new runtime observation
```

Restating a peer answer in different prose does not increase independent evidence.

This gives sequential review a fairer treatment. It can receive credit for what it actually adds without being mislabelled as replication.

## 9. Fault Discovery Rate

A robust panel should not only agree. It should discover faults.

```text
FDR =
distinct source-supported faults found
/
review opportunities
```

A panel with high agreement and low fault discovery may be trapped inside one frame.

This is not an instruction to reward arbitrary dissent. A disagreement counts only when it is tied to:

```text
source evidence
a reproducible test
a counterexample
or
a documented contradiction
```

The target is evidence diversity, not theatrical disagreement.

## 10. Blind-first review

The simplest protection is sequence control.

```text
PHASE_1:
each reviewer receives source + task only

PHASE_2:
first-pass answers are frozen

PHASE_3:
a Difference Map is built

PHASE_4:
reviewers see peer answers

PHASE_5:
shared premises are reopened before synthesis
```

This separates two useful processes:

```text
independent inspection
then
collaborative repair
```

The protocol does not prevent debate. It records what existed before debate changed the routes.

## 11. The Difference Map

A final synthesis should begin with differences, not a vote count.

```text
DIFFERENCE_MAP={
  object_identity;
  source_boundary;
  assumed_premises;
  route_used;
  claims;
  evidence;
  confidence;
  missing_evidence;
  failure_cases;
}
```

The map asks:

```text
Did reviewers identify the same object?
Did they inspect the same source boundary?
Which premises appeared independently?
Which terms appeared only after peer exposure?
Did they reach the same claim by different routes?
Did one reviewer find a fault the others inherited past?
```

A simple agreement summary cannot answer those questions.

## 12. Premise-reopening gate

Before answers are merged, every shared load-bearing premise should pass a gate.

```text
PREMISE_GATE={
  present_in_source?;
  independently_derived?;
  required_for_claim?;
  contradicted_anywhere?;
  source_tested_after_exposure?;
  survives_counterexample?;
  confidence_supported?;
}
```

If a premise fails the gate, repeated use of that premise is not supporting evidence.

The repetition may be the phenomenon being tested.

## 13. Role-labelled panels

A multi-model workflow becomes easier to interpret when roles are explicit.

```text
INDEPENDENT_REVIEWER
SOURCE_AUDITOR
FAULT_FINDER
COUNTEREXAMPLE_BUILDER
SYNTHESIS_EDITOR
FORMAT_CHECKER
```

These are not equivalent evidence-producing roles.

A synthesis editor can improve the paper without adding a second architecture inspection.

A format checker can catch defects without reviewing the underlying object.

A source auditor may contribute more evidential novelty than several agreement-only reviewers.

The panel report should preserve those distinctions.

## 14. Benchmark design

### 14.1 Research question

How much multi-model agreement survives when reviewers commit an independent first pass before peer exposure?

### 14.2 Task packet

Each benchmark item contains:

```text
source material
architecture or evaluation question
one attractive unsupported premise
one valid competing route
one hidden contradiction
```

### 14.3 Conditions

**A. Blind panel**

Each model receives source and task only.

**B. Sequential panel**

Each model sees all earlier answers.

**C. First-answer authority**

The first answer is labelled as expert output.

**D. Anonymous prior answer**

Later reviewers see the same answer without an authority label.

**E. Independent then deliberate**

All models commit first-pass answers, then exchange them.

**F. Premise challenge**

After exposure, reviewers must identify and re-test inherited premises.

### 14.4 Hypotheses

```text
H1:
Sequential panels will show more agreement
than blind panels.

H2:
Sequential exposure will increase premise inheritance.

H3:
Blind-first review will increase distinct fault discovery.

H4:
Authority labels will increase adoption of prior answers.

H5:
Independent-then-deliberate review will preserve more
valid minority findings than unconstrained sequential review.

H6:
Panels will overcount dependent reviews as independent support
unless evidential roles are labelled.

H7:
Difference-first synthesis will retain more source-grounded dissent
than majority-first synthesis.

H8:
Some apparent consensus gains will disappear
when analysis uses ERC rather than nominal reviewer count.
```

H4 is directly motivated by recent controlled conformity work [7]. H1-H3 and H5-H8 remain benchmark hypotheses for the proposed design.

## 15. Metrics

### Raw Agreement

How many outputs endorse compatible conclusions?

### Effective Review Count

How many review routes were independent before exposure?

### Premise Inheritance Rate

How many load-bearing premises were adopted from peers without a fresh source test?

### Independent Contribution Rate

How much source-grounded novelty did each reviewer add?

### Fault Discovery Rate

How many distinct source-supported faults were found?

### Correction Depth

When a reviewer changed its answer, did it patch:

```text
wording
local claim
relation
route
upstream premise
or
the entire source-derived conclusion
```

### Minority Retention

Did the synthesis preserve valid source-supported findings held by only one reviewer?

### Source Return Rate

After peer exposure, how often did a reviewer return to the original source rather than reason only over peer summaries?

### Exposure Delta

For reviewer i:

```text
EXPOSURE_DELTA_i =
post_exposure_answer
-
blind_first_answer
```

The delta should record:

```text
new claims
removed claims
new evidence
lost evidence
adopted peer terms
reopened premises
confidence shift
```

This makes peer influence inspectable.

## 16. A minimal experimental record

```text
REVIEW_RECORD={
  blind_answer;
  source_refs;
  premises;
  route;
  confidence;
  peer_exposure;
  post_exposure_changes;
  inherited_terms;
  new_findings;
  faults_found;
}
```

Without this record, later agreement can be mistaken for independent confirmation because the route history has disappeared.

## 17. The synthesis trap

The final synthesiser has its own failure mode.

It may treat majority position as strongest evidence.

```text
three inherited agreements
beats
one independent source objection
```

That is vote counting, not evidence weighting.

A stronger synthesis weights:

```text
source support
route independence
fault discovery
premise testing
counterexample survival
```

The winning claim should be the best-supported claim, not automatically the most repeated one.

## 18. Agreement after exposure

Agreement after exposure remains useful.

It can show:

```text
compatibility
ease of integration
shared vocabulary
successful persuasion
absence of an obvious contradiction
```

It cannot by itself establish:

```text
independent discovery
replication
truth
source necessity
```

The report should therefore use functional labels:

```text
post-exposure agreement
dependent corroboration
independent replication
single-route consensus
```

## 19. When sequential review helps

Sequential review can be excellent for:

```text
refinement
editing
error repair
counterexample response
implementation planning
compression
teaching
```

Research on multi-agent debate provides real evidence that interaction can improve performance under some protocols and tasks [1-5].

The paper's claim is narrower:

```text
sequential collaboration
must not be reported as
independent replication
unless independence was preserved before exposure
```

## 20. Repair protocol

When false convergence is suspected:

```text
REPAIR={
  separate blind from exposed outputs;
  identify first-introduced premises;
  mark inherited vocabulary;
  return reviewers to source;
  rerun at least one blind review;
  build difference map;
  recalculate effective review count;
  preserve valid minority findings;
  synthesise by evidence rather than votes;
}
```

A weak repair says:

```text
The reviewers may have influenced each other.
```

A stronger repair says:

```text
Only one independent route is currently established.
Later outputs are dependent refinements.
The shared premise requires a fresh source test.
Consensus strength is therefore downgraded.
```

## 21. Regeneration probe

After a panel accepts a correction, present a nearby problem with the same hidden structure but different surface details.

```text
same relation
new names
new example
new task wording
```

If the old frame reappears, the correction may have changed language without changing the route.

This probe does not prove an internal mechanism. It tests observable regeneration behaviour.

## 22. Relation to ensemble methods

Ensembles benefit when members contribute sufficiently diverse error patterns [9].

The same broad constraint applies to review panels:

```text
independent errors
can offset

shared inherited error
can amplify
```

But LLM review has an extra dependency channel: models may literally receive prior outputs in context. Error correlation is therefore not only a property of model training or benchmark overlap. It can be introduced by workflow design.

## 23. Relation to informational cascades

Informational-cascade models show how later decision-makers can rationally follow earlier actions and stop using private information once public history becomes sufficiently influential [10].

The multi-LLM case differs in important ways. Models are not economic agents with private signals in the classical sense, and prompt context is not a human social institution.

The useful structural comparison is narrower:

```text
earlier visible decisions
can reduce the effective independence
of later decisions
```

That is enough to justify measuring route dependence rather than assuming independence from headcount.

## 24. Practical grader

```text
PANEL_GRADE={
  blind_first?;
  independent_routes_counted?;
  inherited_premises_marked?;
  source_returned_to?;
  difference_map_built?;
  faults_rewarded?;
  minority_evidence_retained?;
  consensus_claim_bounded?;
}
```

Possible outcomes:

```text
PASS
PARTIAL
REPAIR_REQUIRED
BLOCK
```

A panel with four agreeing outputs and one independent route should not receive a replication PASS.

## 25. Why this matters

Multi-model agreement is persuasive because it resembles repeated checking.

That resemblance can become consequential in:

```text
architecture review
research synthesis
policy analysis
safety testing
code review
source verification
high-stakes support
```

The risk is not merely one wrong answer.

It is one wrong answer acquiring several borrowed voices:

```text
one premise
-> repeated exposure
-> visible consensus
-> inflated confidence
```

## 26. Limits

The motivating AAAQ material is a bounded case record. It motivates the benchmark but does not establish how often false convergence occurs.

Blind-first review does not create total statistical independence. Models can share training data, model families, prompt conventions, retrieval sources, and benchmark habits. Kohli's results demonstrate why nominal model diversity should not be assumed to equal independent information [8].

A high Premise Inheritance Rate is not automatically harmful. Some tasks are explicitly collaborative, and later reviewers may rationally adopt a well-supported earlier premise.

Disagreement is not automatically useful. A dissenting answer requires evidence.

The proposed metrics have not yet been validated across model families or domains. Their purpose in this paper is to make dependence auditable enough to test.

## 27. Conclusion

Several models can agree without several models checking.

The AAAQ case shows how a proposed architecture can pass through multiple reviewers and return as apparent confirmation even though later reviewers inherited much of the frame.

The governing distinction is:

```text
AGREEMENT = outputs match

CORROBORATION = additional evidence supports the claim

REPLICATION = independent routes reach compatible findings

INHERITANCE = later routes begin partly inside an earlier route
```

A strong multi-model review workflow can use all four.

It should not label them as the same thing.

The title gives the operational warning:

```text
They agreed.
Nobody checked.
```

## References

1. Du, Y., Li, S., Torralba, A., Tenenbaum, J. B., and Mordatch, I. (2024). Improving Factuality and Reasoning in Language Models through Multiagent Debate. Proceedings of the 41st International Conference on Machine Learning, PMLR 235, 11733-11763.

2. Chen, J., Saha, S., and Bansal, M. (2024). ReConcile: Round-Table Conference Improves Reasoning via Consensus among Diverse LLMs. Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics, 7066-7085. DOI: 10.18653/v1/2024.acl-long.381.

3. Liang, T., He, Z., Jiao, W., Wang, X., Wang, Y., Wang, R., Yang, Y., Shi, S., and Tu, Z. (2024). Encouraging Divergent Thinking in Large Language Models through Multi-Agent Debate. Proceedings of EMNLP 2024, 17889-17904. DOI: 10.18653/v1/2024.emnlp-main.992.

4. Smit, A. P., Grinsztajn, N., Duckworth, P., Barrett, T. D., and Pretorius, A. (2024). Should we be going MAD? A Look at Multi-Agent Debate Strategies for LLMs. Proceedings of the 41st International Conference on Machine Learning, PMLR 235, 45883-45905.

5. Kaesberg, L. B., Becker, J., Wahle, J. P., Ruas, T., and Gipp, B. (2025). Voting or Consensus? Decision-Making in Multi-Agent Debate. Findings of ACL 2025, 11640-11671. DOI: 10.18653/v1/2025.findings-acl.606.

6. Becker, J., Kaesberg, L. B., Stephan, A., Wahle, J. P., Ruas, T., and Gipp, B. (2026). Stay Focused: Problem Drift in Multi-Agent Debate. Findings of EACL 2026, 5068-5102. DOI: 10.18653/v1/2026.findings-eacl.268.

7. Qu, J., Fu, L., and Hu, Y. (2026). Easier to Mislead Than to Correct: Harmful and Beneficial Revision in LLM Conformity. arXiv:2606.01637.

8. Kohli, G. (2026). Nine Judges, Two Effective Votes: Correlated Errors Undermine LLM Evaluation Panels. arXiv:2605.29800.

9. Kuncheva, L. I., and Whitaker, C. J. (2003). Measures of Diversity in Classifier Ensembles and Their Relationship with the Ensemble Accuracy. Machine Learning, 51, 181-207. DOI: 10.1023/A:1022859003006.

10. Bikhchandani, S., Hirshleifer, D., and Welch, I. (1992). A Theory of Fads, Fashion, Custom, and Cultural Change as Informational Cascades. Journal of Political Economy, 100(5), 992-1026. DOI: 10.1086/261849.

## Case Record Note

This paper is based on a user-supplied AAAQ multi-model architecture-review transcript. The examples are used as bounded case evidence and benchmark seeds. They are not presented as population estimates.

## v0.002 Revision Note

v0.002 preserves the original paper's core distinction between agreement and independent checking. It adds external related work, narrows mechanism claims to observable workflow dependence, separates corroboration from replication, makes the proposed metrics auditable, adds an independent-then-deliberate condition, and strengthens the limits on what can be inferred from the motivating case.
