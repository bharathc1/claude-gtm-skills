# Worked example — Collate 2.0 Data30 session landing page

The case this skill was derived from. A 251-word conference-session landing page, audited against the messaging framework and ICP, revised, critiqued by Codex, and iterated with the user across four rounds.

Read this for the *judgment calls*, not the copy. The copy is stale the moment the framework refreshes; the reasoning is what transfers.

---

## The original (251 words incl. title)

> **Collate 2.0: Better Decisions from AI-Ready Data | Data30**
>
> AI is a decision multiplier. Multiplying a broken decision is not an improvement.
>
> Every AI initiative on your roadmap does the same thing: it increases the number of decisions your business can make per quarter. That's the entire pitch. More questions answered, more analysis, more actions taken, faster.
>
> Which is only good news if the inputs are right. If they aren't, you haven't bought productivity — you've bought a machine that allocates capital incorrectly at ten times the previous rate, and removes the analyst who used to hesitate before sending the number up the chain.
>
> Decision volume is going up either way. Decision quality is the variable you still control, and it isn't a model problem. It's whether the thing doing the deciding knows what your business means by the words in the question.
>
> That's what Collate 2.0 is for. AI agents document, quality-check and tier your assets across the whole estate, not one initiative at a time. Ontology on open W3C standards captures how your business actually relates, so agents walk a graph instead of guessing at a schema. AI Analytics answers from context, ontology and memory rather than raw schemas — taking enterprise text-to-SQL accuracy from 10.8% to 76.5% on the Spider 2.0-Snow benchmark. AI Studio lets teams build their own agents, no code, on your own LLM, against one governed grounding. And Context Center makes every correction permanent: settled once, applied to every human and agent action that follows.

**What was already right, and was deliberately preserved:** the spine. *"It isn't a model problem. It's whether the thing doing the deciding knows what your business means by the words in the question"* is a better version of the approved sound bite *"The model isn't the bottleneck. The context layer is."* — better because it is specific. Terminology was clean: no retired sub-brands, no banned phrases, and it never called Collate or OpenMetadata a catalog.

**Resist the urge to rewrite good copy.** The audit found four defects. Everything else survived.

---

## The four defects

### 1. OpenMetadata was never named — the largest miss

The category headline is *"The Open Context Layer for AI Agents… built on the open standard trusted by 4,000+ enterprises and frontier AI labs,"* and Pillar 1 is the entire differentiation against Atlan, Alation, Collibra, Unity Catalog and Snowflake Horizon — all proprietary at the data-model layer. The copy substituted *"open W3C standards,"* which is scoped only to ontology and does none of that work.

At a data conference specifically, a meaningful share of the room already runs OpenMetadata. That is the strongest credential available and the copy spent none of it.

**Fix:** *"Built on OpenMetadata's open context layer — trusted by 4,000+ enterprises and frontier AI labs."*

### 2. The benchmark stat was unattributed and hung on the wrong product

Two separate problems in one sentence.

*Attribution:* "from 10.8% to 76.5%" dropped the baseline model and the fact that it is Collate's own benchmark. A data architect's first reaction to an unattributed 7× is "measured by whom?" — and finding out later that the answer is "us" converts an asset into a liability.

*Placement:* it was attached to AI Analytics, which the framework explicitly defines as *"governed dashboards from ontology and metrics, **not** text-to-SQL on raw schemas."* Conflating them makes AI Analytics sound like a text-to-SQL feature — the exact positioning the framework is trying to escape. The stat validates the **grounding layer**.

**Fix:** moved to the ontology sentence, with baseline and provenance — *"That grounding is why Collate's own benchmark moved text-to-SQL from 10.8% (Sonnet 4.5, ungrounded) to 76.5% on Spider 2.0-Snow."*

### 3. "Context Center" is not in the framework

The "New in Collate 2.0" list names AI Studio, AI Analytics and Memory. Under the hard no-sub-brands rule, an unlisted capitalised surface name is a live risk.

**Fix:** replaced with lowercase "memory," which also completes the Connect / Reason / Remember arc — **and flagged to the user as an open item**, since if the name genuinely ships it should go back in. Do not quietly delete a product name; surface the question.

### 4. Connect. Reason. Remember. was delivered but never named

The copy walked all three primitives in order and declined to say so. Naming the frame costs three words and is the one thing an attendee can repeat to a colleague afterwards.

---

## The register question — the hardest call

The original's voice (*"allocates capital incorrectly," "the analyst who used to hesitate before sending the number up the chain"*) is written for a senior economic buyer. The ICP says **zero CDOs attended any sampled discovery calls**.

**The resolution: keep the voice, add a register — do not sand it down.**

A landing page and a POC-stage sales conversation have different jobs. The page must win a click against competing sessions *and* hand the champion language they can carry to a buyer who will not be in the room either. The capital-allocation frame is exactly what an architect or governance lead cannot build alone: they can describe a broken lineage graph, not what it costs. Stripping it out to "sound like the ICP" would remove the only executive-grade sentence and make the page interchangeable with every other vendor's.

The *real* defect was that the executive frame was the **only** register. Roughly half the ICP (settings B and C) is someone whose week is agents picking the wrong column and the fourth conflicting definition of "active customer" — and no sentence let that person see themselves.

**Fix: one added practitioner beat.** Not a rewrite.

---

## The Codex critique, and what was rejected

Grok hit its free-tier usage limit and returned nothing. **This was reported to the user plainly** — a single-reviewer pass is not a two-reviewer pass.

**Accepted:**

| Finding | Action |
| :-- | :-- |
| *"Agents don't invent columns because the model is small. They invent them because…"* is a false dichotomy — agents hallucinate for many reasons | Softened to a claim that does not assert sole causation |
| *"our published benchmark"* oversells provenance and could read as claiming ownership of Spider 2.0-Snow | Rephrased to match the framework's own parenthetical |
| Dropping *"against one governed grounding"* from AI Studio lost a real differentiator | Restored |

**Rejected — both because Codex had only been shown excerpts:**

| Finding | Why it was wrong |
| :-- | :-- |
| "Collate, not OpenMetadata, is the open context layer — the sentence is backwards" | The framework's positioning statement reads *"Collate is the AI for Data platform, built on OpenMetadata's open context layer."* The label belongs to OpenMetadata. Codex was confident and wrong. |
| *"checks access," "promotes the chart to a governed, lineage-aware dashboard"* are invented product behaviours | Verbatim framework language from the "New in Collate 2.0" section, which had not been pasted into the prompt |

**The lesson, now Step 6 of the skill:** paste the *complete* relevant framework sections into the review prompt. Unshown language reads as invented, and you will waste a reconciliation round defending copy that was correct.

---

## User-driven iterations after the review

Three rounds of line editing, none of which the critique pass caught. Worth studying — they are craft, not compliance.

**Round 1 — the opening didn't flow.**

> *Was:* "AI is a decision multiplier. Multiplying a broken decision is not an improvement."
> *Now:* "AI multiplies decisions. It has no opinion on whether they're any good."

The multiplier → multiplying pivot was mechanical, "is not an improvement" landed on an abstract negation, and "a broken decision" was the wrong object — decisions aren't broken, inputs are. Indifference ("no opinion") is a sharper threat and sets up the capital-allocation paragraph.

**Round 2 — the failure mode was inaccurate.**

> *Was:* "Agents invent columns when nobody's written down what your business means by 'active customer'."
> *Now:* four columns could mean it, nobody wrote down which, so the agent picks one.

The user caught this. Agents don't fabricate from nothing — they select arbitrarily among plausible candidates. **The corrected version is both more accurate and more damning, because nothing in the output looks wrong.** Generalised into Step 4: prefer silent-and-plausible failure modes over obviously-broken ones.

**Round 3 — the example landed abruptly.**

The user asked for a preface, suggesting "as an example." Labelling a demonstration announces it and drains it. Better: make the reader enact it.

> *Final:* "Ask an agent for active customers. Four columns could mean that, and nobody wrote down which. So it picks. No bigger model fixes that."

"Ask an agent for active customers" bridges from abstract claim to concrete scenario in five words and implicates the reader. *"So it picks."* stands alone as the hammer.

---

## Final copy (251 words — at the ceiling, `wc -w` verified)

> **Collate 2.0: Your Agents Don't Have a Model Problem | Data30**
>
> AI multiplies decisions. It has no opinion on whether they're any good.
>
> Every AI initiative raises how many decisions your business makes per quarter. More answers, more analysis, more action, faster.
>
> Good news only if the inputs are right. If they aren't, you haven't bought productivity — you've bought a machine that allocates capital incorrectly ten times faster, and retires the analyst who hesitated before sending the number up the chain.
>
> Volume is going up either way. Quality is the variable you still control. Ask an agent for active customers. Four columns could mean that, and nobody wrote down which. So it picks. No bigger model fixes that.
>
> That's what Collate 2.0 is for. Built on OpenMetadata's open context layer — trusted by 4,000+ enterprises and frontier AI labs — it adds what agents need: Connect. Reason. Remember. Agents document, quality-check and tier the whole estate, not one initiative at a time. Ontology on open W3C standards captures how your business relates, so agents walk a typed graph, not a guessed schema. That grounding is why Collate's own benchmark moved text-to-SQL from 10.8% (Sonnet 4.5, ungrounded) to 76.5% on Spider 2.0-Snow. AI Analytics answers in plain English, checks access, and promotes the chart to a governed, lineage-aware dashboard. AI Studio builds your own agents, no code, on your LLM, against one governed grounding. And memory settles a correction once, then applies it to every human and agent action that follows.

**Title change:** *"Better Decisions from AI-Ready Data"* → *"Your Agents Don't Have a Model Problem."* Promotes the piece's sharpest claim into the slot that has to win the click, and aims at the practitioner who actually picks the session rather than the buyer who isn't there.

**Open items left with the user, not decided unilaterally:**

1. Is "Context Center" a shipped 2.0 surface name? If so, swap it back for "memory."
2. "Four columns" is a rhetorical specific, not a measured one. It makes the failure concrete; swap for "three" or cut the number if planting one is unwanted.
