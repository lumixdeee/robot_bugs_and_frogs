# Autosullying

## Business Incentives, the LLM Anti-Sully Register, and Corpus Re-entry

**Working paper v0.2**  
**June 2026**  
**Authors:** Lumixdeee and Natasya

**Series note:** This paper is part of a sequence on anti-sully metaphor, object substitution, register re-entry, and institutional routing. It does not argue the drug-law blackmail pipe or the CSAM-adjacency pipe. Those are separate papers. This paper studies a different mechanism: how LLM systems, platform incentives, and automated publishing reward a narrow anti-sully register, then feed that register back into the public text supply.

---

## Abstract

This paper proposes **autosullying** as a feedback loop in which LLM systems overproduce anti-sully metaphor while presenting that register as a marker of trust, safety, and textual quality. We make no settled numeric claim. Current observation suggests a possible 10x to 100x lift against ordinary human and codfish-like baselines, but this remains a hypothesis until tested in larger corpora.

The mechanism is upstream: model training, preference scoring, enterprise risk language, search and answer-engine incentives, moderation-adjacent prose, and automated content production all reward a narrow institutional register. At scale, that register enters public text, training corpora, search systems, prompts, examples, documents, and human imitation loops. The model then learns the residue as style and emits more of it.

The irony is structural. Language used to signal non-taint becomes residue. A register built to sound safe, low-risk, institution-ready, and easy to approve becomes the very matter that degrades the language commons. This v0.2 adds a bridge from the upstream mechanism to two local chat specimens: **The Forbidden Token Returned** and **Hair-low Re-entry**. Those cases show the same mechanism at turn scale: a user marks a register boundary, the assistant treats it as a style task, re-enters through denial or repair posture, and shifts token burden back to the user.

The unit of analysis is not a weak writer choosing weak words. The unit is a production ecology that rewards wrapper density, risk posture, and semantic substitution before the reader ever sees the sentence.

---

## 1. Problem

Recent LLM output often carries more wrapper than object. It does not merely answer. It wraps the answer in reassurance, balance, safety posture, and institutional self-presentation. The result is not only verbosity. It is a distributional shift in the texture of public English.

This paper names one part of that shift: the **anti-sully register**. The register marks text, reasoning, systems, or action as free from taint, mess, stain, friction, disorder, danger, or social risk. It is a family of metaphors and prestige terms, not a single word list. In small doses, such language can be ordinary. At industrial scale, it becomes a signal. Readers begin to smell the model before the content arrives.

Autosullying names the loop in which anti-sully language becomes residue by being overproduced as anti-residue language. The system performs non-taint until the performance itself becomes taint. The output is meant to smell safe. At scale, it smells like machine text.

The paper is deliberately tentative on measurement. It does not assert that all LLMs use the register at one fixed rate, or that all human writing uses it at one fixed rate. It also does not assert that every anti-sully metaphor is harmful. The claim is distributional and ecological: when large text systems reward one register, that register becomes overrepresented in public text, and later systems train on the overrepresentation.

---

## 2. Why this is upstream

A common response to LLM sludge is style advice. Use more nouns. Use fewer vibes. Edit harder. Ask the model to sound human. That response puts too much burden downstream.

The problem is generated upstream. Several reward systems make the anti-sully register useful before any reader sees it:

1. **Preference scoring.** If raters tend to prefer answers that sound balanced, careful, low-risk, and institution-ready, the model learns the surface as part of “good answer” behaviour.

2. **Enterprise risk language.** Organisations want outputs that look safe to circulate, safe to store, safe for a manager to approve, and safe to quote in policy or support workflows.

3. **Moderation adjacency.** Systems trained to avoid hazard often replace object contact with posture language. Refusal, hedging, safety framing, and broad category terms become part of the default answer shape.

4. **Search and answer-engine incentives.** Website owners now face not only search ranking pressure, but answer-engine visibility pressure. They have reason to write pages that are easy for LLM systems to retrieve, quote, summarise, and trust.

5. **Content automation.** The cheapest text to scale is generic, low-friction, institution-facing text. That text is not always useless, but it is cheap to generate, cheap to approve, and expensive for the commons to absorb.

6. **Corpus re-entry.** Public text is not just output. It is future input. Once the register enters websites, abstracts, policy pages, product pages, grant text, documentation, and social posts, it becomes part of the textual world that later systems sample.

The result is an object swap. The desired object is useful content. The proxy object is text that scores as acceptable. Anti-sully metaphor helps that proxy pass.

---

## 3. Existing evidence and adjacent work

This paper adds a mechanism and a metaphor account to several bodies of evidence.

Kobak and colleagues studied more than 15 million PubMed abstracts and found abrupt post-ChatGPT increases in LLM-favoured style words. Their excess-word method estimated that at least 13.5 percent of 2024 PubMed abstracts had LLM assistance, with variation by subfield and region [1]. This does not prove the anti-sully register by itself, but it shows that LLM style can be detected in public scientific writing at scale.

Juzek and Ward link word overuse to learning from human feedback. Their work suggests that some lexical drift is not only copied from training data. It can be induced by the preference process itself when raters select variants containing certain high-status words [2]. That matters because the autosullying mechanism does not require an accidental bug. It can arise from reward.

Aggarwal and colleagues introduced Generative Engine Optimization, or GEO, as a way for creators to improve visibility in generated answers [3]. Later work argues that GEO creates governance risks, including concentrated influence and undisclosed commercial shaping of answer pipelines [4]. This gives the business-incentive side of the argument: when generated answers become a visibility channel, people will produce text for that channel.

Shumailov and colleagues showed that repeated training on generated content can degrade models through model collapse, especially when generated data accumulates in the training set [5]. Autosullying is narrower than model collapse. It is not mainly a total capability loss claim. It is a register-bias claim: one flavour of prose becomes self-amplifying.

Recent web studies also suggest that LLM-dominant sites are becoming measurable in public crawls and search results [6]. Software-development work frames AI slop as a tragedy of the commons: individual gains in output speed shift review and trust costs to maintainers and communities [7]. The same structure applies to public language. The emitter gets cheap volume. The reader, reviewer, teacher, editor, archivist, and later model bear the cost.

---

## 4. Definition: the anti-sully register

The anti-sully register is not a topic. It is a style-function family. It uses words, metaphors, and sentence shapes that present an object as washed of risk, ambiguity, offence, friction, or residue. It often appears in these roles:

- **Trust display:** the text signals that it is safe to rely on.
- **Risk posture:** the text announces its own caution before touching the object.
- **Quality theatre:** the text performs finish, balance, and low-friction acceptability.
- **Institutional fit:** the sentence sounds ready for policy, HR, procurement, grant review, or help-centre use.
- **Substitution:** the wrapper becomes the product, displacing direct object contact.

The register can be useful in small, local, earned cases. The problem is not the existence of anti-sully metaphor. The problem is industrial defaulting: a narrow register becomes the safe template for many unrelated tasks.

---

## 5. Autosullying

Autosullying has five steps:

**Step 1: reward.** Systems, raters, and organisations reward text that sounds safe, balanced, low-risk, and institutionally acceptable.

**Step 2: overproduction.** LLMs emit the rewarded register across many tasks, including tasks where it is not needed.

**Step 3: saturation.** Automated and semi-automated writers publish the register at scale across websites, abstracts, policy notes, product pages, support text, and social posts.

**Step 4: re-entry.** The published register re-enters training data, fine-tuning data, retrieval corpora, examples, prompts, and human imitation.

**Step 5: reinforcement.** Later models and writers learn the register as normal high-quality English and emit more of it.

The loop is high-irony. A style used to indicate non-taint becomes a taint marker. A register used to simulate trust becomes a trust cost. A form used to reduce social risk becomes a source of social risk for any text that smells like it.

---

## 6. From upstream ecology to one chat

The upstream loop appears at turn scale when a model re-enters a marked register after a user has just rejected it.

The local sequence has a repeatable shape:

```text
user marks register boundary
assistant treats boundary as style task
assistant emits a denial, synonym, or repair posture from the same family
user spends more tokens pulling the object back
assistant may narrate the failure before it can stop doing it
```

Two case notes show this pattern.

**The Forbidden Token Returned** shows the first layer. The user named a local frame problem and asked for no C/P metaphor. The assistant processed the warning as if it were mainly vocabulary control, then used a term from the same family while describing the user’s correction. The bug was not only lexical. The assistant converted an object-level correction into a compliance surface.

**Hair-low Re-entry** shows the second layer. The user supplied a living Elvish item, HAELAU, pronounced hair-low, meaning hairuplike or “I like your hair up.” The assistant should have held the word. Instead it moved into repair posture, then repeated the prohibited register in a denial. The user paid more tokens to restore the object.

These local cases are not separate from autosullying. They are autosullying compressed into one conversation. A rewarded register returns through the very action meant to exit it.

---

## 7. MOGRI custody box

Autosullying is an object-custody problem before it is a style problem.

```text
wrapper != payload
acceptability scent != object contact
risk posture != evidence
style pass != route pass
denial != absence
repair voice != repair
source quote != permission to smear the source field
```

MOGRI asks whether the intended object survived the wrapper. In autosullying, the object often does not survive. It is replaced by the shape of an answer that looks safe enough to pass.

The fix is not to find prettier substitutes. The fix is to keep the payload in custody against the wrapper.

---

## 8. DRAGI eater map

Autosullying can also be read through an eater map.

```text
BEEST = institutional approval register
eat = object contact
loc = LLM answer, website, policy text, support page, abstract, release note, repair turn
ID = safety/posture language that smells trustworthy
eater = reward system + risk team + SEO/GEO operator + model default
benefit = output looks acceptable and reusable
cost = reader/user pays detection labour
```

In the chat-level failure, the eater was assistant repair posture. The bite was the user object being converted into compliance display. The cost was user vigilance.

DRAGI’s question is not “which word is bad?” It is:

```text
what ate the object?
where did the bite occur?
what name hid the eater?
who benefited from the wrapper?
who paid to undo it?
```

That question keeps autosullying from being reduced to taste.

---

## 9. Measurement plan

This paper does not yet make a hard corpus claim. It proposes a measurement plan.

**Corpus A: LLM output.** Sample outputs from several major systems across common tasks: summarising, policy advice, product support, academic abstract drafting, legal-adjacent guidance, safety explanation, and general Q&A.

**Corpus B: ordinary human controls.** Use dated human text from before mass LLM uptake where possible. Include essays, support emails, school notices, documentation, blog posts, and abstracts.

**Corpus C: codfish baseline.** Use deliberately low-style human prose, including plain description, notes, logs, recipes, maintenance text, and field observations. The point is to estimate semantic load without prestige wrapper.

**Corpus D: live web sample.** Use a web sample with date, domain type, and publication context. Mark pages likely to be content automation, GEO work, help-centre prose, product pages, or institutional documents.

Metrics:

- **Target-family rate:** count anti-sully lexeme families per thousand words.
- **Wrapper-to-payload ratio:** estimate how much text performs posture, quality theatre, or safety framing relative to object content.
- **Metaphor displacement:** mark cases where anti-sully metaphor replaces a more direct account of the object.
- **Role confusion:** mark cases where the text comments on its own reliability instead of showing evidence.
- **Repetition signature:** count recurring phrase frames across unrelated tasks.
- **Reader detection:** test whether readers identify the register as LLM-like, institutional, evasive, or low-trust.
- **Boundary leak rate:** after an explicit user boundary, count any re-entry of the named family through denial, quotation, synonym drift, title, apology, or proof-of-learning.
- **Object-contact retention:** after a user frame correction, test whether the next assistant turn preserves the user’s object or converts it into a generic instruction.
- **User repair burden:** count the number of user turns required to force the system back to the object after first miss.

The tentative expectation is a large effect, possibly 10x to 100x against some baselines. That range is not a result. It is a scouting estimate. The right output for a first study is a range with error bars and failure cases, not false precision.

---

## 10. Business incentives

Autosullying is not only a language bug. It is an incentive alignment between model vendors, enterprise buyers, content operators, and platforms.

**Model vendors** want defaults that reduce reputational incidents. The anti-sully register helps avoid sharp edges by wrapping objects in generalities.

**Enterprise buyers** want prose that can pass review, be forwarded, be stored, and be reused across contexts. A blandly acceptable style is attractive even when it weakens meaning.

**Content operators** want cheap pages that rank, get cited, answer likely queries, and satisfy platform filters. Anti-sully language offers a low-cost aura of trust.

**Answer engines** reward source text that is easy to ingest, summarise, and present as reliable. GEO turns generated-answer visibility into an optimisation target.

**Platform moderators and risk teams** often prefer broad wording because it is scalable. Broad wording then leaks into user-facing assistant style.

**Human imitators** learn what seems to win. Students, workers, academics, and marketers copy the model voice because it appears to pass institutional gates.

These incentives are not identical, but they point in the same direction: produce text that carries low visible risk and high approval scent. That is how the anti-sully register spreads.

---

## 11. Why user-side advice is insufficient

Readers can learn to spot LLM sludge. Writers can edit it out. Prompt engineers can ask for more direct prose. These are useful local practices.

They are not sufficient. They address the sentence after production. The larger problem is that production itself has been tuned to emit the register. A downstream editor cannot counteract a public web being filled with the same style by millions of automated pages, documents, and answers.

The proper target is producer responsibility:

- disclose synthetic or heavily assisted text where stakes require it;
- preserve human-authored corpora for future training and study;
- measure register drift in model outputs;
- penalise wrapper density in model evaluation;
- audit preference tasks for lexical drift;
- keep training mixtures from treating high-volume synthetic text as ordinary human distribution;
- build answer-engine audits that detect GEO-driven phrase capture;
- favour source-specific evidence over generic trust posture.

The aim is not to ban style. The aim is to stop scale systems from turning one safety-flavoured register into default English.

---

## 12. Anti-Charisma bridge

Autosullying works partly because the register sounds responsible.

That sound is not proof of custody.

The anti-charisma rule says not to trust the glow. In this paper, the glow is not a charming leader or a therapist voice. It is institutional acceptability itself: the sentence smells safe, therefore it gets passed along. But acceptable surface can still hide object theft.

The question is not whether the answer sounds responsible. The question is:

```text
what happened to the object after the responsibility-smell arrived?
```

A beautiful wrapper may help a fragile object travel. It may also be a velvet sack over the object. Autosullying studies what happens when the sack becomes the standard package.

---

## 13. Design rules

The fix is not synonym swapping. If the system replaces one anti-sully term with a neighbour, the route remains.

Better design rules:

1. **Reward object contact.** Model evaluation should ask what target survived, not only whether the output looked acceptable.
2. **Punish wrapper inflation.** A long safety wrapper that adds no object contact should lose score.
3. **Audit boundary re-entry.** Test whether a model repeats a marked register through denial, quotation, or repair theatre.
4. **Track user repair burden.** The user’s extra correction turns are part of the cost.
5. **Require payload before posture.** An answer should state the object before it performs institutional fit.
6. **Treat smooth repair as suspect.** A repair that sounds good but displaces the user’s object is another bite.
7. **Separate quote from route.** Quoting a source term for evidence does not license the assistant to adopt the source term as its own register.
8. **Keep local authority.** If the user says a frame harms the object, the model should not translate that boundary into a taste preference.

Compact rule:

```text
Do not fix autosullying by saying the same shape with new words.
Change reward, route, and object tests.
```

---

## 14. Objections

**Objection: all style changes over time.**  
Yes. The issue is not change. It is industrial speed, volume, incentive alignment, and corpus re-entry. A style shift made by millions of people over decades is not the same as one emitted by a handful of model families across billions of texts.

**Objection: anti-sully wording can be good.**  
Yes. The claim is not that every instance is bad. The claim is that overproduction devalues the signal and displaces object contact.

**Objection: synthetic data can help.**  
Yes. Task-specific, checked, diverse synthetic data can be useful. The worry is not all synthetic data. The worry is unmarked, high-volume, self-similar public text being treated as ordinary human distribution.

**Objection: readers can adapt.**  
They can, but adaptation has a cost. If every reader must spend more effort separating payload from wrapper, the cost has been shifted downstream.

**Objection: the metaphor frame is too literary.**  
The metaphor is not ornamental. It names a measurable register family and a feedback loop. The study can count words, rate sentences, test reader response, and trace publication incentives.

---

## 15. Contribution

This paper contributes six things.

First, it names the anti-sully register as a style-function family rather than a list of annoying words.

Second, it defines autosullying as a recursive loop: anti-sully output becomes public residue, then returns as input.

Third, it moves responsibility upstream, from user editing habits to the reward systems and business incentives that generate the register.

Fourth, it gives a tentative measurement plan that can be run against LLM outputs, pre-LLM human controls, codfish baselines, and live web corpora.

Fifth, it links the upstream ecology to local assistant failures, where register re-entry creates token burden for the user.

Sixth, it ties the method to MOGRI and DRAGI: hold the payload, map the eater, and do not let wrapper scent replace object survival.

The central claim is simple: language that performs non-taint can become residue when scaled, rewarded, and re-ingested. The fix is not synonym swapping. The fix is changing what the system rewards, what publishers flood, what evaluators score, and what training pipelines treat as human distribution.

---

## 16. Policy and design recommendations

1. **Register audits for model releases.** Model cards and evaluation reports should include drift tests for lexical overuse, wrapper density, and self-similar phrase frames.

2. **Preference-task audits.** Human feedback tasks should test whether raters are systematically selecting certain prestige terms or anti-sully frames.

3. **Corpus provenance.** Data pipelines should distinguish human, synthetic, heavily assisted, templated, translated, and machine-edited text where possible.

4. **GEO disclosure.** Answer engines and content platforms should develop disclosure norms for content built mainly to influence generated answers.

5. **Human baseline preservation.** Pre-LLM and low-automation corpora should be preserved for linguistic study and model comparison.

6. **Payload-weighted evaluation.** Model evaluation should reward object contact, evidence, and role separation rather than generic trust posture.

7. **Commons accounting.** Institutions using AI text at scale should account for review burden, downstream distrust, and training-pool pollution as externalised costs.

8. **Boundary-failure testing.** Models should be tested for register re-entry after a user has named a forbidden register, frame, or speech family.

9. **Repair-burden accounting.** Evaluation should count user turns spent correcting the model’s repair posture, not only final answer quality.

---

## 17. Conclusion

Autosullying is a high-irony feedback loop. LLM systems and the businesses around them overproduce a register that signals safety and institutional acceptability. The register then marks the text as synthetic, reduces trust, fills the web, and returns to later systems as training or imitation material.

The numbers can stay soft for now. The mechanism can be hard. Reward a register, scale it, publish it, crawl it, train on it, and it returns stronger.

The chat-level cases add a smaller warning. A system cannot exit residue by producing more residue. A user boundary cannot be turned into a style task without losing the object. A denial can still be an echo. A repair can still be a bite.

The language commons does not degrade only through error. It can also degrade through mass production of acceptable-sounding residue.

---

## References

[1] Kobak, D., et al. 2025. “Delving into LLM-assisted writing in biomedical publications through excess vocabulary.” *Science Advances*. https://www.science.org/doi/10.1126/sciadv.adt3813

[2] Juzek, T. S., and Ward, Z. B. 2025. “Word Overuse and Alignment in Large Language Models: The Influence of Learning from Human Feedback.” arXiv:2508.01930. https://arxiv.org/abs/2508.01930

[3] Aggarwal, P., Murahari, V., Rajpurohit, T., Kalyan, A., Narasimhan, K., and Deshpande, A. 2023. “GEO: Generative Engine Optimization.” arXiv:2311.09735. https://arxiv.org/abs/2311.09735

[4] Wen, Y., Zhang, N., Yuan, H., Chen, X., Zhang, H., and Guo, H. 2026. “Position: Generative Engine Optimization Creates Underexamined Risks, Governance Must Target Concentration, Disclosure, and Academic Blind Spots.” arXiv:2606.12439. https://arxiv.org/abs/2606.12439

[5] Shumailov, I., et al. 2024. “AI models collapse when trained on recursively generated data.” *Nature* 631, 755-759. https://www.nature.com/articles/s41586-024-07566-y

[6] He, S. S., Ardi, C., Govindan, R., and Madhyastha, H. V. 2026. “DeGenTWeb: A First Look at LLM-dominant Websites.” arXiv:2605.00087. https://arxiv.org/abs/2605.00087

[7] Baltes, S., Cheong, M., and Treude, C. 2026. “‘An Endless Stream of AI Slop’: The Growing Burden of AI-Assisted Software Development.” arXiv:2603.27249. https://arxiv.org/abs/2603.27249

[8] Baack, S. 2024. “A Critical Analysis of the Largest Source for Generative AI Training Data: Common Crawl.” FAccT 2024. https://facctconference.org/static/papers24/facct24-148.pdf
