# The ICP resonance rubric

The canonical rubric. `SKILL.md` executes this file; it does not restate it. A rule described in two places drifts in one.

Covers two asset types: **blogs** and **email copy**. The ten dimensions and the weights are shared. Dimensions 1, 2, 5, 9 and 10 carry asset-specific anchors, marked **Email:** inline. The scoping rules for a multi-email sequence are at the end.

## How to score

Ten dimensions, each scored **0–10 in half-point steps**. Multiply by the weight, sum, report a composite out of 10.

**Every score needs evidence from the text.** For a defect of commission, quote the line. For a defect of omission — no CTA, no objection touched — evidence is the search you ran: *"grep for CTA patterns across all sections returns nothing."* Never quote an unrelated line and let it stand as proof of an absence.

**When torn between two scores, take the lower one and say which two you were between.** Editorial scoring has real variance and pretending otherwise is false precision. A disclosed "6 or 7, scored 6" is information. A confident 6.5 that another reviewer would call an 8 is noise.

### The gate

| Condition | Verdict |
| :-- | :-- |
| Composite ≥ 8.0 **and** every scored dimension ≥ 6.0 **and** no guardrail breach | `PASS` |
| Composite < 8.0, **or** any scored dimension < 6.0 | `FIX` |
| Any guardrail breach below, at any score | `BLOCK` |
| A dimension could not be graded from the supplied material | `NOT GRADABLE` |

The floor exists because a weighted average lets one catastrophic dimension hide behind nine good ones. It is deliberately a cliff: on a 5%-weight dimension, a half point can flip the verdict while moving the composite by 0.025. That is the mechanism, not a bug — it is what gives a low-weight dimension any teeth at all.

**The floor only binds on dimensions that apply.** See the next section, which exists so the cliff never fires on a dimension the asset had no business scoring.

### When a dimension does not apply

Some dimensions are genuinely irrelevant to some assets. A tightly scoped technical post has no natural place to answer a pricing objection. A 120-word release email is not going to carry two registers.

Mark such a dimension **`N/A`**, state in one line why, and **redistribute its weight proportionally across the remaining dimensions.** An `N/A` dimension is not scored, does not enter the composite, and cannot breach the floor.

This is a real judgment and it is abusable, so two constraints:

- **At most two dimensions may be `N/A`.** A third means you are scoring the wrong rubric, or the piece has no identifiable audience. Report that instead.
- **Dimensions 1, 3 and 5 can never be `N/A`.** Problem relevance, message setting, and positioning apply to every piece of Collate content that exists. If one of them seems inapplicable, the finding is about the content.

`N/A` means *the dimension does not apply to this asset*. `NOT GRADABLE` means *it applies and I was not given enough to grade it*. Never use one for the other.

### Anchors

Every dimension gives anchors at 10, 8, 6, 5 and 2. **The 6 anchor is load-bearing** — it is the floor, so it is the score a reviewer reaches for when something is weak but not fatal, and an undefined 6 is where sustained mediocrity hides.

### Guardrail breaches — automatic BLOCK

From the copy guardrails. Not scored; gates. **There are three.**

1. **Collate or OpenMetadata called "a catalog."** The framework positions explicitly against catalogs; the word concedes the category. Calling a *competitor's* legacy tool a catalog is fine and on-message. Grep for `catalog` and check every instance.
2. **OpenMetadata disparaged.** It is Collate's own Apache 2.0 project and the top of the acquisition funnel. The OSS-graduation story is never "free wasn't enough." It is "you already picked the right standard — the question is whether your team should be the one operating it."
3. **An invented product surface.** A capitalised, product-sounding name absent from the framework's "New in Collate 2.0" list is a defect. Either confirm it ships or replace it.

---

## The weights

| # | Dimension | Weight | Source |
| :-- | :-- | --: | :-- |
| 1 | ICP problem relevance | 15% | ICP §6 |
| 2 | Trigger and urgency | 10% | ICP §5 |
| 3 | Message-setting fit | 10% | ICP §7 |
| 4 | Room register | 10% | ICP §4 |
| 5 | Differentiated positioning | 15% | Framework + ICP §11 |
| 6 | Evidence and trust | 10% | Framework + ICP §12 |
| 7 | Feature-to-outcome translation | 10% | ICP §6 |
| 8 | Substance | 10% | — |
| 9 | Cohesion and length discipline | 5% | Asset target |
| 10 | Next action | 5% | — |

---

## 1. ICP problem relevance — 15%

Does the piece open on a pain the ICP actually records, described the way the reader would describe it?

The six ranked pains in §6, roughly: can't find or trust data · governance, DQ and ownership gaps · the operational burden of self-hosting OpenMetadata · incumbent cost and lock-in · self-service for business users · metadata agents can consume.

**Read the tag counts correctly.** Governance appears in the large majority of the sample because tags are multi-assigned, and the ICP flags this as the single most misused number in the document. It does not mean 92% of buyers are governance buyers — primary orientation puts governance-first as the largest segment. A blog is not more ICP-relevant for saying "governance" more times.

| Score | What it looks like |
| :-- | :-- |
| 10 | A named pain rendered as a specific situation — a person, a decision, a consequence — that a reader could match to something that happened to them |
| 8 | A recorded pain, concretely, but in Collate's framing rather than the reader's |
| 6 | A recorded pain, correctly identified, stated only in the abstract. Nothing wrong with it and nothing anyone will recognise |
| 5 | Gestures at a real pain. "Organizations struggle with data quality" |
| 2 | Opens on a pain the ICP does not record, or on a capability with no pain attached |

**Pain #5, self-service, is a different buyer with a different success metric and a different demo path.** The ICP says explicitly not to fold it into governance operations or agent grounding. A draft treating "business users can ask questions" as interchangeable with "governance teams get lineage" caps at 6.

**Email:** the pain must land in the subject line or the first sentence. An email that buries a recorded pain below the fold has failed in practice regardless of what the body eventually says, and caps at 6.

## 2. Trigger and urgency — 10%

Does the hook attach to a documented reason this reader is doing anything *now*?

Quantified: **graduating from self-hosted OpenMetadata**, the most common trigger in the sample. Observed but unranked: replacing a named incumbent, warehouse rebuild or cloud migration, standing up a new governance function, M&A, an AI initiative needing a foundation.

**IPO/audit readiness and board-level AI mandates are `[Unverified]`** — carried from older assets, never observed in the June sample. A draft may use them as color. A draft presenting them as what the field is seeing caps at 6.

| Score | What it looks like |
| :-- | :-- |
| 10 | A documented trigger, plus the cost of not acting, in a timeframe |
| 8 | A documented trigger, urgency implied rather than stated |
| 6 | A trigger is identifiable but generic — true of the category rather than of this reader's situation |
| 5 | A timeless problem statement. True whenever you read it, which means it moves nobody |
| 2 | Urgency asserted with nothing behind it, or built on an unverified trigger presented as observed |

**Email:** this is where subject and preview text get graded for **resonance**. The style guides own the mechanics — subject pulls the open lever, preview pulls the click lever, preview never restates the subject. Do not re-grade those. Ask instead whether the hook is a trigger *this* reader has. "You're spending three FTEs on a free product" is an ICP trigger. "The future of data governance is here" is not.

## 3. Message-setting fit — 10%

Route on **initiative state, not job title**. The ICP is explicit: neither champion title nor vertical predicts position.

| The reader's initiative state | Setting | The piece leads with |
| :-- | :-- | :-- |
| AI absent from the conversation | **A — Governance Foundation** (largest segment) | Catalog replacement, lineage, DQ, glossary, RBAC, stewardship, compliance |
| AI named as a future reason to fix the foundation | **B — AI-Ready Governance** (second segment) | The foundation you don't throw away when the mandate lands |
| Agents live now or being built | **C — AI-Context-Native** (smallest segment) | Context layer, ontology, MCP, agent grounding, GenBI, data products |

**Grade against the setting the piece is intended for, which the brief or the user declares.** Where no setting is declared, grade the setting the copy actually lands on and name it in the finding.

**Do not treat any setting as the default target.** B is described in the ICP as the largest receptive audience for the context-layer narrative, which is useful context for a *recommendation*, not a rule the rubric enforces. The segment split is explicitly stage-confounded — AE demos skew AI-forward, SDR first-touches skew governance-first — and the ICP calls itself a profile, not a predictor. Scoring a piece down for choosing A or C would convert a descriptive sample into policy the source refuses to make.

Score three things: is a setting identifiable, is it held to the end, and is the piece still readable to its neighbours.

| Score | What it looks like |
| :-- | :-- |
| 10 | One setting, established early and held; adjacent settings can follow the argument even where it is not aimed at them |
| 8 | A clear setting, one or two sections that drift |
| 6 | A clear setting, but written so tightly to it that an adjacent-setting reader stops early. Correct targeting, avoidable narrowness |
| 5 | The setting shifts mid-piece — a governance opening that becomes an agent-grounding pitch with no bridge |
| 2 | No identifiable setting. Written to all three, landing with none |

**If the setting cannot be identified at all, the score is 2** and the finding says so. Ambiguity is the result here, not a reason to guess at what was intended and grade that instead.

## 4. Room register — 10%

The hardest judgment in the rubric. Read it fully before scoring.

**No CDO attended in the sampled calls.** The reader is a data architect, data engineer, or governance/DQ lead, one or two levels below budget. The economic buyer is frequently absent and represented by your champion.

**This does not mean strip out executive framing.** Capital allocation, headcount and risk are legitimate and valuable, precisely because they are the ammunition a technical champion cannot build alone and needs in order to sell upward. Arming the champion is the job.

**It means executive framing must not be the only register.**

The test for a second register is not word count, it is **usability**: could the champion forward that passage, or paste it into a slide, and have it do work without them rewriting it? A single clause about efficiency is not a register. A sentence naming what it costs to do nothing is.

| Score | What it looks like |
| :-- | :-- |
| 10 | Both registers, each doing work: a concrete practitioner beat in their vocabulary, and a passage the champion can forward unedited |
| 8 | Both present, one thin — the second register identifiable but not independently usable |
| 6 | One register, plus a gesture at the other that would not survive being forwarded on its own |
| 5 | One register only, executed well |
| 2 | Written entirely to a CDO who is not in the room, or entirely to a practitioner with nothing to sell upward |

**Email:** a short single-purpose email carrying one register well is doing its job. Consider `N/A` for anything under roughly 150 words, rather than penalising it for a structure it has no room for.

## 5. Differentiated positioning — 15%

Read the framework, do not recall it. Two things get scored here: whether the positioning is right, and whether the piece answers why anyone would pay.

**Positioning.**

- **The category claim.** "AI for Data" is Collate. The "open context layer" belongs to **OpenMetadata**, not Collate. Getting this backwards is a common and confident error.
- **The three primitives** — Context (Connect), Ontology (Reason), Memory (Remember). Never "shared semantic context" or "semantic intelligence"; both are banned as buyer-unclear. "Semantic search" remains fine as a feature name.
- **No retired sub-brands.** AskCollate and Collate AI are gone. Attribute capabilities to Collate or to the named agent.
- **Abstract differentiators must be operationally defined.** A word like "activation" is a claim until one sentence says what it means concretely, at which point it becomes a test the rest of the piece has to pass.

**The free-to-paid question.** Objections the field hears, all `[Directional]`: price ~30, free-vs-paid gap ~16, prove it on OSS first ~16, residency ~15, timeline ~13, procurement ~11. The ICP singles out **the free-to-paid gap as the one worth building for** — price objections at volume are ordinary, but being compared against your own free product is structural, and the OSS-graduation motion cuts across all three settings.

A piece that positions Collate without ever answering what the paid product does that the free one does not has left the reader's actual question unanswered. That is a differentiation failure, which is why it lives here rather than in a dimension of its own.

| Score | What it looks like |
| :-- | :-- |
| 10 | Framework positioning correctly attributed, the central claim operationally defined early, and the free-vs-paid line drawn honestly without disparaging OpenMetadata |
| 8 | Correct positioning, one abstract claim left undefined, or the paid/free line implied rather than drawn |
| 6 | Correct and unobjectionable, but nothing here a competitor could not also say, and no answer to why pay |
| 5 | On-message but generic, with a differentiator asserted and never demonstrated |
| 2 | Category claim inverted, a banned term load-bearing, or positioning contradicting the framework |

**Email:** one objection handled well is a 10 here. Do not require two — a second objection usually breaks the one-idea rule in dimension 9.

## 6. Evidence and trust — 10%

This dimension scores whether a claim is **presented** defensibly. Whether it is *true* belongs to `/defend-check`, reported as a separate subgate.

The boundary in practice: score the presentation, and when something looks fabricated, **flag it to `/defend-check` rather than scoring it as fraud.** A number you cannot verify is a `/defend-check` referral, not a 2. What earns a 2 here is a defect visible on the page — an unnamed authority, a missing baseline, a claim hung on the wrong capability.

- **Every statistic carries its baseline and its provenance.** A bare "10.8% → 76.5%" invites "measured by whom, against what." If the reader learns the answer is "us" later rather than from you, the number stops being an asset and becomes a credibility problem. Name the baseline model and own the benchmark. Never phrase it so it reads as though Collate owns a public benchmark.
- **No weasel attribution.** "Experts agree," "studies show," "industry reports suggest." Name the source or cut the claim, and never invent one.
- **Hang each claim on the capability that actually earns it.** Live example: AI Analytics is governed dashboards from ontology and metrics, *not* text-to-SQL on raw schemas — so the text-to-SQL benchmark validates the grounding layer, and attaching it to AI Analytics re-creates the exact positioning the framework is trying to escape.
- **Watch absolutes.** "Every," "the whole estate" are falsifiable coverage claims. Keep them only where the framework makes them.
- **Never use a customer as proof of a feature they did not deploy.**

| Score | What it looks like |
| :-- | :-- |
| 10 | Every number sourced and baselined, every claim on the right capability, customer proof matched to what each customer runs |
| 8 | Sourced throughout, one absolute or one unbaselined figure |
| 6 | Claims are attributed but thinly — a source named without the detail that would let a reader check it |
| 5 | Real evidence, under-provenanced. Numbers a skeptical reader has to take on faith |
| 2 | Weasel attribution, or a benchmark attached to the wrong capability |

**Email:** a linked source page is legitimate provenance. Do not require the full baseline inline where it would wreck the copy — require that the link exists and goes somewhere that carries it.

**Do not treat the ICP's own `[Directional]` or `[Unverified]` figures as facts a piece may quote.** It is an internal profile, not published evidence.

## 7. Feature-to-outcome translation — 10%

Does each capability explain a changed workflow, or stop at a description?

**Count capabilities, not sentences.** Take the piece's own named product surfaces as the inventory, then check each one for an attached workflow.

| Score | What it looks like |
| :-- | :-- |
| 10 | Every capability lands on what someone stops doing or can now do; the mechanism-to-outcome chain is walkable without the reader translating |
| 8 | Most capabilities translated, a few left as description |
| 6 | Capabilities translated as a group rather than individually — one outcome sentence covering four features |
| 5 | Half the piece is a feature tour |
| 2 | A list of capabilities with no workflow attached |

The strongest pattern in the benchmark set: explain the architectural limitation, show why the change was required, quantify the effect, then ground it in a production customer.

**Prefer failure modes that are silent and plausible over ones that are obviously broken.** "The agent invents a column" is both less accurate and less frightening than "four columns could mean *active customer*, nobody wrote down which, so it picks one." The second is scarier precisely because nothing in the output looks wrong.

## 8. Substance — 10%

**The anti-recital dimension.** Everything above can be satisfied by a piece that recites approved vocabulary at the correct reader and says nothing. This dimension is the one that catches it.

The test: **what does the reader now know that they could not have got from the messaging framework, the product page, or the first paragraph of this piece?**

Sources of real substance, in rough descending order of value: a mechanism explained rather than named · a number with an argument attached · a distinction that resolves genuine confusion · a decision aid the reader can apply to their own estate · an honest limitation · a concrete worked case.

What is *not* substance: restating the pain in the reader's vocabulary — that is dimension 1 · naming the primitives — dimension 5 · listing capabilities — dimension 7 · a customer logo with no mechanism.

| Score | What it looks like |
| :-- | :-- |
| 10 | Carries an argument that is Collate's own and could not be assembled from public materials; a reader learns something they can use even if they never buy |
| 8 | One genuine insight, mechanism or decision aid, developed properly |
| 6 | Competent and correct with one shallow original beat — the reader finishes slightly better informed |
| 5 | An accurate, well-targeted restatement of positioning. Nothing wrong, nothing new |
| 2 | A recital: approved vocabulary, correct pains, correct primitives, zero content |

**Score this one last**, after the other nine. It is the only dimension that gets harder to see the more carefully you have checked the others, because a recital passes every individual check.

## 9. Cohesion and length discipline — 5%

Measure with `wc -w`, never estimate.

**Grade against the target for the asset in front of you.** `/write-blog` sets **1,800–2,500 words** for a standard post, and that is the default when no other target is declared — but a webinar recap, a short technical note, or a release announcement can have a different, legitimate one. Take a declared target from the brief where there is one. **Length is scored as fit to purpose, never as distance from 2,000 words**, and a tight 900-word post that does its job scores 10.

| Score | What it looks like |
| :-- | :-- |
| 10 | Length fits the job, one spine, every section earning its place |
| 8 | Up to ~15% over its target, cohesive |
| 6 | Noticeably longer than the job needs, still followable end to end |
| 5 | Roughly 1.4x its target, or a defensible length with a spine that breaks mid-piece |
| 2 | Roughly 2x its target, or doing two jobs at once — a category narrative and an exhaustive release reference — without separating them |

The two-jobs failure has a standard fix rather than a cut: exhaustive coverage moves into a capability table, and the narrative body shortens around it.

**Email.** The constraint is one idea per email, not a word count. `email-release.md` owns the section bands (bullet descriptions 5–12 words, deep dives 3–5 sentences at ~50–100 words); check against the guide rather than inventing a target.

| Score | What it looks like |
| :-- | :-- |
| 10 | One idea, developed once, every section inside its band; a reader skimming on a phone gets the point |
| 8 | One idea, one section running long |
| 6 | One idea plus a secondary thread that survives skimming but dilutes the ask |
| 5 | Two competing ideas, or a body padded past the point it had made |
| 2 | A blog pasted into an email — the most common defect in this asset type |

## 10. Next action — 5%

**Blog.**

| Score | What it looks like |
| :-- | :-- |
| 10 | One primary CTA, one secondary, any third as an inline text link in the section that earns it |
| 8 | Two clear CTAs of equal weight |
| 6 | Three CTAs, one clearly primary |
| 5 | Three or more equal CTAs dividing attention at the point of conversion |
| 2 | No CTA, or a CTA disconnected from what the piece argued |

**Email.** Offer discipline is owned by `NUR-OFFER-01` (one primary offer per email per recipient) and by `email-release.md`. Do not re-grade the mechanics. Grade the **fit**: is the ask sized to where this reader actually is?

| Score | What it looks like |
| :-- | :-- |
| 10 | The ask matches the reader's initiative state — a setting-A reader gets a foundation resource, not a demo of an agent platform |
| 8 | A reasonable ask, one step ahead of where the reader is |
| 6 | A defensible ask that ignores the argument the email just made |
| 5 | A generic demo request bolted onto a specific argument |
| 2 | An ask no one at this stage would accept, or a persona-swapped CTA patched onto a body that does not read for that persona |

---

## Scoring a multi-email sequence

A sequence gets **one composite**, not one per email. The dimensions split, and collapsing them hides the defect sequences actually have.

**Scored once, across the sequence:** 3 (message setting), 4 (room register), 5 (positioning), 8 (substance). A sequence that changes setting between email 2 and email 4 without a bridge is one finding about the arc, not two scores.

**Scored per email, then averaged into the dimension:** 1 (problem relevance), 2 (trigger and urgency), 6 (evidence), 7 (feature-to-outcome), 9 (cohesion), **10 (next action)**. The offer is the thing most likely to be wrong in exactly one email of six, so it is graded per email — a sequence-level CTA judgment is where a bad ask hides.

**The floor applies per email on the per-email dimensions.** One email scoring 4 on evidence is a floor breach for the sequence even if the average clears 6. That is the whole reason the floor exists: an average lets a bad email hide inside a good sequence.

Report per-email scores in their own table so it is visible which email is dragging.

**Do not re-grade structure.** Field completeness, subject and preview levers, offer discipline, arc continuity, persona parity and control integrity belong to `/review-nurture` and `email-nurture.md`. Report that as a subgate, including `NOT RUN`.

---

## Reporting arithmetic

Show the weighted contribution per row so the composite can be checked. Mark any dimension below 6.0 as a floor breach in the row itself. Show any `N/A` row with its reason and state the redistributed weights. State the composite to one decimal place.

Do not round a 7.9 up to "about 8." The gate is the point of the rubric.
