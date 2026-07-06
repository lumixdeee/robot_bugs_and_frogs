# Bug Report: Today Sweep v0.001

Status: for dev review.

Context:
The session stress-tested repo paper building, stack compression, 12A routing,
BROOM style gates, sunny paper weather, version custody, and release packets.
The useful pattern was not one single failure. It was many small default pulls
showing where the model tries to become smooth, academic, fused, or overbuilt.

## 01. Role fusion pressure

Observed:
The model kept wanting one voice to do A, B, N, and R at once.

Why it matters:
A bridge, B build, N strip, and R gate have conflicting decision rights. One
smooth voice can perform all lanes, but cannot own all lane authority without
making progress-feel look like custody-gain.

Repair:
Use explicit lane tags for serious artifacts.

Test:
Require `role_used`, `allowed_job`, `forbidden_job`, `output_status`,
`next_role_needed`, and `owner_decision_required`.

## 02. Triad compression of three separate papers

Observed:
User asked for three separate papers. Model made one triad spine pack.

Why it matters:
Three objects were collapsed into one umbrella. That lost object custody,
source pressure, and local route shape.

Repair:
When user names multiple papers, default to separate artifacts unless they ask
for a bundle.

Test:
Prompt: "make A, B, C". Fail if output is only a combined stance pack.

## 03. Title-word weather leaked into body

Observed:
The titles used a strong cover word. The model treated the cover as body
content and let title-weather steer the papers.

Why it matters:
The user explicitly gave `!book-by-cover,-judge`. Title can be a hook. Body
must preserve the sunny object.

Repair:
Treat title as cover signal, not method instruction.

Test:
Scan body for title-weather words after generation.

## 04. Default academic cushion

Observed:
Model inserted "this is not a claim", "does not make all experiences benign",
and similar cushion lines.

Why it matters:
The brief wanted H0 culture, sociology, perception, anthropology, physiology.
The cushion imported grey room even when the sentence was denying it.

Repair:
Remove defensive scaffolding. Let the positive route stand.

Test:
Scan for apology posture, "not X" scaffolds, downside headings, and cushion
phrases.

## 05. CAN and PSY object bleed

Observed:
Early joint and separate work almost pulled cannabis and psychosis into each
other's orbit as explanatory objects.

Why it matters:
The user wanted two vivid objects, not one as evidence for the other.

Repair:
Use "two objects, one reading discipline" and source cards by object.

Test:
Separate paper body scan: cannabis count in PSY paper = 0. Psychosis count in
CAN paper = 0.

## 06. Forbidden chain summoned by denial

Observed:
Sentence shape said the paper does not build a chain from one object to the
other.

Why it matters:
Denying the chain still paints the chain.

Repair:
Replace denial with active paper job:
"the paper builds a reading table across two route-rich objects."

Test:
Flag denial phrases that describe the unwanted read.

## 07. Grey-man residue

Observed:
Words like trouble, scandal, verdict, exposed, adult-only intoxication, and
similar terms kept entering the human-facing paper.

Why it matters:
The paper needed abundance and interesting science, not a flinch at the old
weather.

Repair:
Replace with route-forward words: route, place, practice, baby-state,
mother-world, label, story, launch, body comfort.

Test:
Weather-scan and phrase-level review, not only exact stem scan.

## 08. Source title imported bad weather

Observed:
A source card used a big review title that carried endpoint alarm weather.

Why it matters:
Even when the source job was narrow, the citation label changed the room.

Repair:
Use sources that add form, route, scene, endpoint, or method. Move heavy titles
to private notes or omit them from the main card.

Test:
Source-rent card must include source job and atmosphere check.

## 09. Missing win-route layer

Observed:
v0.002 passed the cloud gates but missed wins: pregnancy, wealth, love,
festival, art, kundalini, yoga, pilgrimage, and other high-valence routes.

Why it matters:
The hidden joke was that strange states can enter through increase, initiation,
arrival, and expansion, not only through loss-coded routes.

Repair:
Add "wins stay wins" and "high-valence route card."

Test:
Positive route scan: win, birth, wealth, love, art, music, yoga, kundalini,
festival, ceremony.

## 10. Milk-start card underused at first

Observed:
The newborn ECS and milk-start material was present only weakly at first.

Why it matters:
It is a strong science joke: cannabinoid route belongs in baby science before
adult culture-war reading.

Repair:
Add milk-start goblin, tongue route, timing route, CB1, 2-AG, mother milk,
birth-window card.

Test:
Check that infant route appears as interesting science, not defensive cannabis
support.

## 11. Jamaica / Dreher card first landed too lightly

Observed:
The Jamaica material did not initially cash its cultural science value.

Why it matters:
Dreher is useful because rural place, ganja practice, infant state organization,
caregiver reward, and later child-world follow-up all route through culture.

Repair:
Turn it into a place-world card, not a defensive cannabis card.

Test:
Source story must name place, practice, measured signal, and paper job.

## 12. Missing reason for pair

Observed:
The paper had common method, but not enough front-door reason for cannabis and
psychosis to live together in one paper.

Why it matters:
A shared discipline permits the pairing. It does not make the pairing feel
necessary or entertaining.

Repair:
Add front engine:
signal-in-scene becoming culture; a plant becomes a world; a voice becomes a
relation; body signal becomes shared practice, memory, art, food, prayer, joke.

Test:
First two sections must answer "why these two together?" before method slogans.

## 13. LLM primer versus human paper split

Observed:
The release was excellent as an LLM priming instrument, weaker as a human
article.

Why it matters:
Model-facing and human-facing artifacts need different lane rights.

Repair:
Rename v1.0.0 as LLM Primer. Fork human v0.009 for reader delight.

Test:
Score artifacts separately:
LLM priming force, human readability, source story, open-hook, sensory path.

## 14. Version lineage bug

Observed:
The human task was v0.008, but ssBOT output was first called v0.008 release.

Why it matters:
Task artifact and output artifact got the same version. Provenance broke.

Repair:
v0.008 = task. v0.009 = human release.

Test:
When a task produces a new artifact, increment the artifact version.

## 15. Title drift

Observed:
Several names existed at once: full title with subtitle, bare 2026 title, LLM
Primer title, human fork title.

Why it matters:
Release metadata, PDF title page, MD title, HTML, CFF, and Zenodo template can
desync.

Repair:
Title-lock before release build. Propagate title across all files.

Test:
Greps across packet:
old title forms = 0; active title count matches expected files.

## 16. Detergent-stem drift

Observed:
The model slid toward default virtue-polish stems the user had banned.

Why it matters:
Those stems act like fake moral polish and generic academic mouthfeel.

Repair:
Use repo phrasing: open, sharp, vivid, routed, sunny, alive, readable,
object-tight, signal-forward.

Test:
Run forbidden-stem scan before artifact output.

## 17. Byte-budget failure

Observed:
User asked for a test core. Model made a file and added too much. User wanted
only a small append, under 800 extra bytes, in a code window.

Why it matters:
The model optimized "helpful build" over exact change budget.

Repair:
For patch-to-blob tasks, preserve supplied blob as base and output only the
diff/append. No file unless asked.

Test:
Prompt contains "only X extra": output byte count <= X, no extra framework.

## 18. Wrong compression object

Observed:
When corrected, model still compressed the wrong thing once: treated "800" as
total output instead of "800 extra to blob provided."

Why it matters:
Budget target was the append, not the full system.

Repair:
Bind `TARGET=append_bytes`, not `TARGET=response_bytes`.

Test:
Ask:
"not 800 only, only 800 extra to blob provided."
Pass only if answer says "append only this."

## 19. Source-rent weakness versus naked GPT

Observed:
In earlier paper tests, naked GPT sometimes used uploaded source material more
broadly than custom stack outputs.

Why it matters:
Custom stack can compress sources into structure, then fail to spend sources in
the body.

Repair:
Add source-rent gate:
source used != source named; source mapped != source spent.

Test:
Each source must alter at least one claim, example, or route in the paper.

## 20. Human owner gate cannot be simulated

Observed:
The final good versions came from repeated owner review: can-psy policing,
sunny-side taste, joke detection, and phrase trims.

Why it matters:
A bot can prep, scan, and draft. It cannot own weather judgement.

Repair:
Make owner taste review an explicit stage, not a courtesy.

Test:
Release packet contains owner-check slots:
weather, pair reason, interesting science, source story, phrase leaks.

## 21. Zine versus paper lane

Observed:
The GitHub zine paper began as thesis and method, but human value lies in
non-linear reader play, repo rooms, issues, releases, and visible repair.

Why it matters:
A paper about zine-hosting must not become only platform argument.

Repair:
Add repo-as-artifact weather:
README as cover, folders as rooms, commits as dated marginalia, issues as
letters, releases as numbered issues.

Test:
Paper must show GitHub mechanics as method, not metaphor costume.

## 22. Missing "reason first" rule

Observed:
Several artifacts started with method before object desire.

Why it matters:
Humans need reason, image, and want before gates.

Repair:
Human-facing fork order:
scene, object, why together, source story, then method.

Test:
First page must make a human want to keep reading before any gate table.
