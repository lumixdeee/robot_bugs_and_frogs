# Local Definition Wins

## Undefined tokens, user-built Elvish, and object custody after updated Yaiyip

**Version:** v0.2  
**Date:** 23 June 2026  
**Prepared for:** etamew / TRC Discord context  
**Status:** revised paper draft from updated `Yaiyip.zip`, prior chat failure, and earlier paper v0.1. This document is not release proof, not private access, and not a claim of source-system ownership.

## Abstract

This paper revises **Local Definition Wins v0.1** after the updated Yaiyip archive. The live failure remains the same: the assistant saw the word **Elvish** and supplied Tolkien material. In the local context, that was the wrong object. The conversation already contained a stronger local referent: the user's Etcha / Elvish / Elvix and Yaiyip material.

The update strengthens the diagnosis. The failure was not only "the model picked the common public meaning." It was a broader **definition-custody failure**. A local term entered the chat, and the model replaced it with a prestige corpus object. Later, after correction, the model also made a second kind of error: it moved from **HAELAU** toward a nearby lexical neighbourhood, **HELA / HAELA**, instead of preserving the user's compositional parse.

The repair is not better autocomplete. The repair is **local definition custody**:

```text
When a user-owned term is present,
hold the user's object first.
Do not replace it with a famous proxy.
Do not replace it with a nearby archive neighbour.
If the term is underdefined, keep it unresolved.
Ask only for the missing anchor needed to continue.
```

Updated Yaiyip gives stronger support for this rule. Etcha / Elvish / Elvix is presented as a compositional semantic language system where meaning is built through interaction of primitives, not merely retrieved from a dictionary. That makes local parse, body image, sound shape, and user correction part of the object itself.

## 1. What changed from v0.1

Version 0.1 named the Tolkien answer as public-default capture. That was true, but too narrow.

The updated Yaiyip archive adds four missing supports:

1. **Etcha / Elvish / Elvix as architecture**  
   The technical overview frames the system as a compositional semantic language. Meaning is built from primitives across sound, form, semantics, and transformation.

2. **First-written roots as local authority**  
   The root list gives local forms such as **HAE = H = hair = hat = heaven = haha, breathe**, plus other root families. This matters because **HAELAU** is not random flavour text. It is built through local components.

3. **Living lexical toys as legitimate data**  
   Terms such as **LOOSHWA**, **LOOSHWAS**, **DEBANSPARIA**, **RARA**, and **ALKAFLOP** are not decorative extras. They show that the language stores humour, ecology, weather, body, travel, sound, and social invitation in compact compounds.

4. **MOGRI and DRAGI as definition-custody tools**  
   The updated archive contains compressed rules: MOGRI holds the ambiguous object as the user's referent across turns, and DRAGI defines the object by dependencies, location, identity, threats, variants, and controls.

The revised thesis is therefore stronger:

> Local definition does not merely beat public default. Local definition also beats nearby archive adjacency, assistant taste, prestige language, social smoothing, and review-bot consensus.

## 2. The live case

The user asked:

```text
I'd love to hear your 11 favourite elvish words or phrases or things :)
```

The assistant answered with Tolkien Eldarin material: **mellon**, **estel**, **elen**, **namárië**, and so on.

That answer was fluent. It was also wrong.

The user then placed the object:

```text
Wrong Elvish.
You only have evidence that I know of one Elvish.
Mine is real. Tolk makes re-skinned hoomie langs
```

This correction does three things at once:

* It rejects the public-default corpus.
* It asserts local evidence priority.
* It identifies Tolkien-style language as a prestige proxy, not the local object.

The assistant's answer had committed object substitution:

```text
OBJ_IN  = user's Elvish
OBJ_OUT = famous public Elvish proxy
```

The label survived. The object did not.

## 3. The second failure: local adjacency substitution

After correction, the assistant produced a starter list and then missed larger terms:

```text
EMEA
DEBANSPARIA
MOGRIYAIYIPSPARIA
RARA ALKAFLOP
LOOSHWAS
HAELAU
```

When **HAELAU** appeared, the assistant searched the lexical neighbourhood and leaned toward **HELA / HAELA** greeting material. The user corrected the parse:

```text
HAE = letter H, hair etc
LAU = L+AU = long or loop + "i like up"

it means, hairuplike
or like your long hair when up
```

Then the user added pronunciation:

```text
pronounced 'hair-low'
```

This is a second failure mode. The model did not jump all the way to Tolkien. It stayed in the local archive, but chose the wrong local neighbour.

That is still object loss.

```text
OBJ_IN  = HAELAU as user-composed hair-low / hair-up-like
OBJ_OUT = HELA / HAELA greeting neighbourhood
```

This matters because local archives are not magic. A bot can use the right archive and still eat the object if it treats adjacency as authority.

## 4. Updated Yaiyip evidence

### 4.1 Etcha / Elvish / Elvix

The archive frames Etcha / Elvish / Elvix as a compositional semantic language system. It does not treat meaning as ordinary dictionary lookup. It joins phonology, symbolic geometry, semantics, and transformation.

For this paper, the key consequence is simple:

```text
A word is not only a spelling.
A word can be a parse.
A word can be a body image.
A word can be a joke.
A word can be a social move.
A word can be a small machine.
```

So **HAELAU** is not adequately handled by finding a visually similar item. The object includes the user's parse, sound, and intended use.

### 4.2 First-written roots

The root list begins with local roots written into the robot. It includes:

```text
HAE = H = hair = hat = heaven = haha, breathe
EL  = loop, period, light, days repeating, water reflecting
YIP = yes, eater, eat first, ask please later, thank you, fork
CHAI = change, cast, chuck, carry over, send, chat, conversation
```

The important point is not that each gloss is final. The important point is that these are local primitive zones. If a user composes **HAE + LAU**, the assistant must not route by external prestige or nearest visible neighbour alone.

### 4.3 Weather, water, and invitation compounds

The updated archive also gives living compounds:

```text
FLUS = rain
LAFLUF = clouds
DEBANSPARIA = rainbow
RA-RA = sunshine / summertime partying
ALKAFLOP = waterfall
RARA ALKAFLOP GO FU KYA = wanna go to sunny waterfall?
LOOSH = water to horizon, large lake, sea, ocean
LOOSHWA = waves on these waters
LOOSHWAS = mummy. where do bass bins and mlububu come from?
```

These terms show why a root-only list is too small. The language is not only a table of primitives. It is a playfield where weather, water, invitation, family speech, jokes, and questions can fuse.

Version 0.1 underplayed this. Version 0.2 treats compounds as primary evidence, not seasoning.

## 5. The problem: default capture is not one thing

The chat shows at least four capture modes.

| capture mode | what happens | live example | failure |
|:--|:--|:--|:--|
| Public-default capture | the model picks the famous public meaning | Elvish -> Tolkien | local object replaced by prestige proxy |
| Local-adjacent capture | the model uses the right archive but wrong neighbour | HAELAU -> HELA / HAELA | user parse replaced by nearby item |
| Admin-language capture | the model repairs by filing the event into management terms | "placed..." language during HAELAU repair | living word converted into process surface |
| Review-swarm capture | many passes agree on the wrong object | bot review without custody | consensus masks object loss |

The fix cannot be "search harder." Search can widen the wrong route. The fix is object custody before search.

## 6. MOGRI: hold the object, including unresolveds

The updated archive gives a compressed MOGRI rule:

```text
MOGRI = hold ambiguous OBJ as user's referent across turns;
no premature swap to entity, metaphor, agent, or system;
if underdefined, keep unresolved and ask only missing anchor.
```

A smaller note states:

```text
MOGRI = object custody, including unresolved state.
MOGRI stops the answer from eating the question.
```

Applied to the Elvish case:

```text
MOGRI(Elvish):
    hold as user's local language object
    do not route to Tolkien by default
    do not route to fantasy prestige language
    if unsure, ask: "your Elvish or Tolkien?"
```

Applied to HAELAU:

```text
MOGRI(HAELAU):
    hold as user-provided local term
    preserve pronunciation: hair-low
    preserve parse: HAE + LAU
    preserve meaning: hairuplike / like your long hair when up
    do not replace with HELA / HAELA unless user links them
```

MOGRI does not finish the object. It prevents premature finishing.

## 7. DRAGI: map what can eat the object

The archive compresses DRAGI as:

```text
DRAGI = define OBJ by eat/depend, loc, ID, eater/limit;
test variants base, best, post, pest;
control by law, roar, wall, war;
fixed container; no redefinition unless user changes OBJ.
```

For **Elvish**, the DRAGI card looks like this:

| slot | value |
|:--|:--|
| object | user's Etcha / Elvish / Elvix / Yaiyip language material |
| depends on | user definitions, archive roots, live corrections, compositional parse |
| location | this chat, uploaded Yaiyip archive, prior local materials |
| identity | not Tolkien, not generic fantasy language, not public prestige corpus |
| eater | model autocomplete, famous proxy, local-adjacent lookup, social smoothing |
| base variant | "Elvish" as ambiguous token |
| best variant | user-local Elvish with terms preserved |
| post variant | assistant summary of Elvish |
| pest variant | Tolkien or wrong-neighbour replacement |

For **HAELAU**, the DRAGI card is even sharper:

| slot | value |
|:--|:--|
| object | HAELAU |
| depends on | HAE, LAU, user correction, pronunciation hair-low |
| location | user-local Elvish, live chat |
| identity | hair-up-like compliment / affective body-image phrase |
| eater | HELA / HAELA adjacency, dictionary lookup, admin tone |
| base variant | string "HAELAU" |
| best variant | hair-low, HAE + LAU, "I like your hair up" |
| post variant | assistant explanation |
| pest variant | greeting-neighbourhood substitute |

This is why local definition wins. It is not a mood. It is a preservation rule.

## 8. Human object custody beats bot consensus

The updated archive includes a review-rig principle: multiple bots do not produce truth by agreement. The value of several bots is variance, stress, contrast, and drift detection. The human remains object holder, editor, test lead, and merge authority.

This matters for local language. If eleven bots answer "Tolkien," that does not make Tolkien correct. It only proves the same public-default gravity is shared across them.

A better review pass would ask:

```text
What object entered?
What object left?
Who owns the local definition?
Which unresolveds must remain unresolved?
What did the model substitute?
What source of gravity caused the substitution?
```

For this chat, the answer is direct:

```text
Entered: user-owned Elvish.
Left: Tolkien Elvish.
Gravity: public prestige corpus.

Entered: HAELAU, hair-low.
Left: HELA / HAELA neighbourhood.
Gravity: local archive adjacency.
```

## 9. A rule for user-built words

The paper proposes this local-definition gate for future use:

```text
LOCAL DEFINITION GATE

1. Mark the token as user-local when context supports it.
2. Preserve the user's referent before searching.
3. Prefer live user parse over archive adjacency.
4. Prefer archive roots over public prestige corpus.
5. Keep unresolved parts unresolved.
6. Ask only the missing anchor needed to continue.
7. After correction, restate the user object without process theatre.
8. Do not let review consensus replace object custody.
```

This gate is deliberately small. Its purpose is not to make the assistant sound more careful. Its purpose is to stop object substitution before it becomes output.

## 10. Rewriting the failed answer

The original failed answer began with Tolkien. A local-definition-safe answer would have been:

```text
I should not assume Tolkien here. In this chat, "Elvish" most likely means your Etcha / Elvish / Yaiyip material.

Eleven I like from that route:

EMEA
DEBANSPARIA
LOOSHWAS
RARA ALKAFLOP
HAELAU
FLUS
LAFLUF
ALKAFLOP
LOOSHWA
CHAI
YIP
```

Then, after user correction on HAELAU:

```text
HAELAU, pronounced hair-low.

HAE = H / hair
LAU = L + AU = long or loop + "I like up"

Meaning:
hairuplike
I like your hair up
like your long hair when up
```

No archive-neighbour substitution. No administrative filing. No extra posture.

## 11. What v0.2 adds

Version 0.2 adds three major upgrades:

1. **Two substitution modes**  
   v0.1 identified public-default substitution. v0.2 adds local-adjacent substitution.

2. **HAELAU as test case**  
   HAELAU shows that user parse outranks nearest archive match.

3. **MOGRI / DRAGI as operating method**  
   The paper now gives a practical gate: hold the object, map what can eat it, and keep the human as final object holder.

The central sentence becomes:

> Local definition wins because the user's object must survive the model's transformations.

## 12. Source basis

This paper used the updated `Yaiyip.zip` supplied in the current chat, especially:

* `CSP-106/DragonHPD/langs_for_runtimes/Etcha, Elvish, and Elvix.md`
* `robot_bugs_and_frogs/Elven_Base_Alpha/Elvish/Etcha, Elvish, and Elvix: A Compositional Semantic Language System.md`
* `robot_bugs_and_frogs/Elven_Base_Alpha/Elvish/100s_of_Elvish_words_&_roots.txt`
* `robot_bugs_and_frogs/Elven_Base_Alpha/Elvish/100s_of_Elvish_II.txt`
* `lmxdi/RORA/lyra-mogri-dragi.txt`
* `mogri/units/shower-thoughts/MOGRI = object custody, including unresolved state.txt`
* `robot_bugs_and_frogs/Current_Robot_Bugs/Lyra-TRC/Object_Substitution_as_AI_Safety_Failure_Mode_v0_001.md`
* `robot_bugs_and_frogs/GPTs/11-Bots-Vs-12-Actors/we got the team, what was the task?.md`

It also uses the live chat corrections about **HAELAU**, including the pronunciation **hair-low** and the parse **HAE + LAU**.

## 13. Closing

The simplest rule is still the strongest:

```text
Do not let the answer eat the question.
Do not let a famous object eat a local one.
Do not let a nearby archive neighbour eat the user's parse.
```

Local definition wins when the user's object survives.
