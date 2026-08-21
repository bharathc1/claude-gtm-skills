# Calibration

Why the rubric has the shape it has, what it replaces, and a worked score to anchor against.

## What this replaces

Two hand-built rubrics scored the same Collate 2.0 launch blog in August 2026, four days apart, and disagreed on both dimensions and scale:

| File | Shape |
| :-- | :-- |
| `gtmos/260805-collate20-icp-resonance-benchmark.md` | Ten weighted dimensions summing to 100. Scored 81, re-scored 87 after five edits. Plus a persona resonance table and a six-axis competitor benchmark |
| `gtmos/260805-collate-20-launch-blog-narrative-review.md` | Ten *different* dimensions, current-vs-target columns (Problem urgency 4→9, Differentiation 4→9, Proof 3→8, Launch readiness 2→10) |

Both are useful history. Neither is executable twice with the same result, which is the whole argument for one rubric living in a skill.

### What carried over, and what changed

| Legacy dimension | Now | Why |
| :-- | :-- | :-- |
| ICP problem relevance 15% | **D1, 15%** | Unchanged. Correctly the heaviest |
| Hook and urgency 10% | **D2, 10%** | Re-anchored on ICP §5 triggers, so "urgency" has to name one |
| Executive business value 10% · Governance-leader resonance 10% · Platform/builder credibility 10% | **D4 Room register, 10%** | Three persona-titled dimensions collapsed into one. They were scoring the same text three times from three job titles, and the ICP records **zero CDOs across our discovery-call sample** — a rubric that awards 30% of its weight to how three named titles feel is measuring a buying group the field does not encounter |
| — | **D3 Message-setting fit, 10%** | New. The ICP's own model is initiative state A/B/C. Neither legacy rubric scored it at all |
| Differentiated positioning 15% | **D5, 15%** | Same weight, now also carrying the free-to-paid question |
| Evidence and trust 10% | **D6, 10%** | Narrowed to *presentation* of evidence, because `/defend-check` owns truth |
| Feature-to-outcome translation 5% | **D7, 10%** | Doubled. It was the dimension the legacy review kept citing in its prose findings while weighting it near-invisibly |
| — | **D8 Substance, 10%** | New, and the most important addition. See below |
| Narrative cohesion 10% | **D9, 5%** | Halved in weight, sharply harsher in anchors, and re-anchored on fit-to-purpose rather than distance from 2,000 words |
| Availability/next action 5% | **D10, 5%** | Unchanged |

**The persona resonance table was dropped deliberately.** It is still worth producing as commentary when a piece has a genuinely mixed audience, but it is not part of the score. Scoring by title contradicts the ICP's explicit instruction to route on initiative state, and it invites the exact failure the ICP warns about: writing to a CDO who is not in the room.

**The competitor benchmark table was dropped from the score** for a different reason: it needs current competitor posts read at review time, and a stale comparison scored as if fresh is worse than no comparison. Run it as a separate exercise when the question is "how does this stack up," not as five points of a resonance gate.

### On D9's weight

Length lost weight and gained teeth. At 10% with soft anchors, a bloated draft leaked a point and a half and passed. At 5% with a hard anchor — roughly 2x its target scores 2 — a bloated draft trips the **6.0 floor** and cannot pass at any composite. The floor does the work the weight used to do, and does it more decisively. See the worked example.

### Why D8 Substance exists

It was added after a Codex review of the first draft of this rubric, which produced the specific failure it exists to catch. Asked to game the rubric, Codex wrote a short email that recited the approved vocabulary — the four-columns scenario, "AI for Data," Context/Ontology/Memory, a sourced-looking benchmark, an OSS-graduation line, a stage-matched CTA — and scored it **9.9/10**. The email was a compressed recital of the scoring vocabulary with no thesis and a possibly fabricated number.

Nine dimensions were satisfiable by naming the right things at the right reader. Nothing asked whether the reader learned anything. **A recital passes every individual check**, which is why D8 is scored last, after the compliance reading is done.

The 10% came from D3, which dropped from 15%, and from folding objection pre-emption into D5. Objection handling is topic-dependent — a tightly scoped technical post has no natural place for a pricing answer — and a 5% standalone dimension was too small to move a composite anyway. Substance is not topic-dependent. Every piece either has some or does not.

## Worked score: Collate 2.0 launch blog v13

`/Users/bharath/Documents/test/frenemy/collate-2.0-launch-blog-v13.md`, scored 2026-08-11. Asset: blog. Setting scored against: **C**. Length target: **2,800 words**, the figure the legacy benchmark set for this launch, not the 1,800–2,500 standard-post default.

**Verdict: FIX — 8.6/10 (floor breach: D9 Cohesion 4.0)**

| # | Dimension | Wt | Score | Wtd | Evidence |
| :-- | :-- | --: | --: | --: | :-- |
| 1 | ICP problem relevance | 15% | 9.0 | 1.35 | The three-decisions table (which revenue, which plan, which territory map) is ICP pain #6 exactly — *"agents try to figure out your schema themselves."* Silent, plausible failure. Costs a point because the protagonist is a finance analyst, a buyer §6 says to keep separate, so the architect reading translates one hop |
| 2 | Trigger and urgency | 10% | 8.5 | 0.85 | "An AI initiative needing a data foundation" is a documented trigger, and the consequence is timed: *"One answer costs two quarters and the plan built on top of them."* Not a 10 because the underlying why-now is partly "we shipped" |
| 3 | Message-setting fit | 10% | 7.5 | 0.75 | Clear setting C, held to the end. But it assumes agents are live — *"A platform engineer builds an agent that watches continuously"* — and Part 1 plus the self-hosted table are the only places an A reader stays with it. Scored on legibility to neighbours, not on choosing C, which is a legitimate choice for a platform launch |
| 4 | Room register | 10% | 9.0 | 0.90 | Both registers, each usable. Practitioner: `get_persona_context`, semantic chunking, MCP identity propagation. Champion ammunition: the stay-self-hosted / evaluate-Collate table is forwardable unedited. Short of 10 because the forwardable passage is about hosting, not business value |
| 5 | Differentiated positioning | 15% | 9.0 | 1.35 | Category claim correctly attributed: *"Collate 2.0, the agentic orchestration platform that activates OpenMetadata, the Open Context Layer for AI Agents."* Three primitives with Connect/Reason/Remember. Free-to-paid drawn honestly and without disparagement: *"The graph stays portable either way, which means the decision above stays reversible."* Loses a point because "activates" is demonstrated across six parts and never defined in one sentence |
| 6 | Evidence and trust | 10% | 9.0 | 0.90 | Best-in-class separation: *"The evidence, in three separate categories."* Benchmark carries baseline, model, subset and methodology link. Explicitly says the customer results *"validate the open foundation. They do not measure outcomes from Collate 2.0."* Scenario flagged as illustration with the figures owned |
| 7 | Feature-to-outcome translation | 10% | 9.5 | 0.95 | Every capability lands inside the running scenario. Policy Agent → a scoped Snowflake grant. Memory → the APAC renewal-timing rule, with the four record components kept separate |
| 8 | Substance | 10% | 9.0 | 0.90 | Carries an argument that is not in any public material: that reach was never the limitation, and the three failures are questions of authority, effective dates, and how a policy document relates to a table. The stay/evaluate table is a genuine decision aid. Short of 10 because the insight is concentrated in the first third |
| 9 | Cohesion and length | 5% | **4.0** | 0.20 | **FLOOR BREACH.** 5,253 words total, 4,534 publishable, 3,972 excluding the capability table. Against a 2,800 target that is ~1.6x. It does apply the prescribed fix — exhaustive coverage lives in the table — and still runs long |
| 10 | Next action | 5% | 9.0 | 0.45 | One primary (webinar series), Release Preview enrollment correctly placed as an inline link in the section that earns it. Two secondary CTAs split the residual |
| | **Composite** | **100%** | | **8.6** | |

### Guardrails

| Guardrail | Status |
| :-- | :-- |
| "catalog" usage | **PASS** — zero occurrences |
| OpenMetadata treatment | **PASS** — actively flattered throughout |
| Product names in framework | **NOT FULLY RUN** — not checked against the framework's "New in Collate 2.0" list in this pass |

### Why this example is the calibration anchor

It is the case that proves the floor. **Composite 8.6 clears the 8.0 gate; D9 at 4.0 fails the floor; verdict is FIX.** A rubric without the floor would have passed a 4,500-word launch blog on the strength of nine good dimensions.

It also lands where it should against the legacy rubric, which scored an earlier version of the same launch 81/100 before edits and 87/100 after cutting to 2,695 words. v13 sits at 8.6 — between the two — and the gap from 8.7 is almost entirely length. The two rubrics agree on the piece and disagree on what to do about it, which is the intended difference.

**When re-calibrating after a rubric change, re-score this file.** A result outside roughly 8.0–9.0, or a D9 above 5.0, means the change loosened something.

### The second calibration case, which does not exist yet

The v13 score anchors the **high** end. Nothing anchors the low end, and a rubric calibrated only on good content drifts generous.

The gap worth closing: score a piece that should fail, ideally the recital email from the D8 note above, and record it here. Until that exists, treat scores in the 5–7 band as less reliable than scores near 8.5, because no worked example has ever landed there.

### Note on the legacy comparison

`gtmos/260805-announcing-collate-20-rewrite.md` and its 81/87 pair remain available as a second calibration point. Score it only against the same asset type and remember the legacy number is out of 100 on different dimensions — it is a sanity check on ordering, not a target to reproduce.
