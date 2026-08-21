---
name: collate-icp-review
description: "Review, score, and rewrite Collate blog and email copy against the ICP — launch posts, announcements, thought-leadership, technical posts, webinar recaps, nurture sequences, release emails, single sends. Scores a weighted ten-dimension ICP resonance rubric out of 10, gates at 8.0 with a per-dimension floor, then rewrites to clear the gate on approval. Use whenever asked to review, score, critique, or ICP-check a blog, post, article, email, or sequence, including drafts written by someone else. Not for writing from scratch (/write-blog, /write-nurture, /write-release-email), email structure review (/review-nurture), landing pages (collate-landing-page), decks, or one-pagers."
---

# Collate ICP review

Scores a blog or an email against the person actually reading it, then rewrites it to clear 8/10.

This exists because nothing else does it. `/write-blog` has editorial self-critique and gates on claims and prose, but it never reads the ICP. `/review-nurture` grades email *structure* and explicitly delegates everything else. `collate-landing-page` reads the ICP but scopes itself out of both blogs and emails. Nothing in the setup asks whether a piece lands with the person receiving it.

It also runs on copy the writers never produced — a colleague's draft, a historical post, copy pulled out of the CMS or HubSpot.

**Encode the pointer, not the content.** The messaging framework is regenerated with `/refresh-messaging` and the ICP is versioned. Never score from what you remember of them. Read the files, every run.

---

## What this does not do

These questions belong to gates that already own them. Do not reimplement them and do not restate their rules.

| Question | Owner |
| :-- | :-- |
| Are the claims actually true and defensible? | `/defend-check` |
| Does the prose read as AI-generated? | `/stop-slop`, `lint-prose.py`, `no-ai-slop` |
| Is the email *structurally* sound — fields, levers, offer discipline, arc, persona parity, controls? | `/review-nurture`, `email-nurture.md`, `email-release.md` |
| Do links and UTMs work in the rendered email? | `email-url-qa.md` |
| Should this piece exist, and what should it say? | `/write-blog`, `/write-nurture`, `/write-release-email` |

Report them as separate subgate lines with their real status, including `NOT RUN`. Never absorb them into the resonance verdict.

Two boundaries are easy to blur:

- **Dimension 6** scores whether a claim is *presented* defensibly. Whether it survives scrutiny is `/defend-check`'s call.
- **On email, the structure guides own the mechanics and this skill owns the fit.** `NUR-LEVER-01` says the subject must pull the open lever; that is structure. Whether the hook is a trigger *this* reader actually has is resonance, and dimension 2 grades it. A sequence can pass `/review-nurture` cleanly and still be written to nobody.

---

## Step 1 — Read the sources

Non-negotiable, all three, every run.

| Source | Path | What you take from it |
| :-- | :-- | :-- |
| ICP standard | `~/Documents/Claude/Claude Projects/ICP/` — take the file whose **`YYMMDD-` filename prefix is the latest**, matching `*standard*.md`. Filename date, not mtime: mtime changes when someone opens and saves an old file | Who is reading, which message setting applies, the recorded pains, triggers and objections |
| Messaging framework | `~/Documents/Claude/Claude Projects/Messaging source of truth/messaging-framework.md` | Category claim, the three primitives, approved capability wording, the "New in Collate 2.0" list |
| Copy guardrails | `~/.claude/projects/<project-slug>/memory/collate-copy-guardrails.md`. Find it with `ls ~/.claude/projects/*/memory/collate-copy-guardrails.md` | The three breaches that BLOCK regardless of score |

If the guardrails file cannot be found, **say so and proceed** — the three guardrails are restated in `references/rubric.md`, so a missing memory file degrades the run rather than stopping it. The other two sources are hard requirements: without them there is no rubric, and the run is `NOT GRADABLE`.

Check the framework's header date and its manual-edit notes. Manual redlines can postdate the source decks and get reverted by the next refresh — if one is load-bearing for a score, say so.

**Where the framework and the ICP disagree, flag it — never silently pick.** The known live conflict: the framework names CDO/VP as primary economic buyer; the ICP records zero CDOs across 57 discovery calls. That tension has a defensible resolution (rubric dimension 4), but the user decides.

**A source conflict does not suspend the review.** Score the affected dimension against the ICP, which is the newer and field-derived source, mark the row `CONFLICT` with the framework's competing position in one line, and carry it into the fix plan as an open item for the user. Do not withhold a composite waiting on a decision, and do not use `NOT GRADABLE` for a conflict — it means missing material, not contested material.

**Handle the ICP's confidence tags honestly.** `[Hard]` means reliable *within the dataset*, not a claim about the market. `[Directional]`, `[Unverified]` and `[Hypothesis]` are weaker still, and §10 deliberately refuses to convert its qualification signals into policy. Score against what the ICP observed. Do not invent a hard rule the source declines to make.

## Step 2 — Establish the asset type and the message setting

**Asset type** decides which anchors dimensions 1, 2, 5, 9 and 10 use, and whether the sequence scoping rules apply. State it: blog · single email · email sequence. A sequence gets one composite, with the per-email dimensions scored per email — see the scoping section of `references/rubric.md`.

**Establish the length target here too**, before scoring dimension 9. `/write-blog`'s 1,800–2,500 words is the default for a standard post, not a universal rule — a webinar recap or a short technical note has its own. Take a declared target from the brief where there is one, and say which target you scored against.

**Message setting.** Which of A / B / C the piece is aiming at changes what half the dimensions mean. Route on the reader's **initiative state**, never on job title.

If the draft is genuinely ambiguous about which setting it targets, that is a dimension-3 finding worth reporting, not a reason to guess and score the rest against your guess. For a sequence, an unstated setting is often in the brief — read it before calling it ambiguous.

## Step 3 — Score every dimension individually

Execute `references/rubric.md`. Ten dimensions, half-point steps, **evidence from the text behind every score** — a quoted line for a defect of commission, the search you ran for a defect of omission. Do not score a group and split the difference.

Measure length with `wc -w`. Never estimate.

Four dimensions pass by inattention and earn extra care:

- **Dimension 8, substance.** Score it last, and score it hardest. It is the only dimension a fluent recital of approved vocabulary cannot pass, and by the time you have checked the other nine you will have been reading for compliance rather than for content. Ask the plain question: what does the reader now know that the product page would not have told them?
- **Dimension 4, room register.** The easy failure is scoring a piece down for executive framing. Executive-stakes framing is what arms the champion; it only costs points when it is the *only* register. Read the dimension in full before scoring it.
- **Dimension 6, evidence.** Check every number for a baseline and a named source, and check each claim hangs on the capability that earns it. Where a source looks fabricated, refer it to `/defend-check` rather than scoring it as fraud — this dimension scores what is visible on the page.
- **Dimension 1, problem relevance.** Do not reward keyword density. Governance tags appear in ~53 of 57 calls because tags are multi-assigned; the ICP flags this as the most misused number in the document.

**Before writing any replacement wording**, load the writing rules from Step 7. The redlines in Step 5 are deliverable prose, and prose this skill produces runs the rules — including the prose it produces before the rewrite is approved.

## Step 4 — Guardrails and subgates

```bash
grep -n -i 'catalog' FILE          # every hit must point at a competitor
wc -w FILE
```

Then check every capitalised product-sounding surface name against the framework's "New in Collate 2.0" list, and check the OpenMetadata treatment. Any breach is a `BLOCK` at any score.

Run or record the subgates:

```bash
python3 "$HOME/Documents/Claude/Claude Projects/gtmos/04-skills/scripts/lint-prose.py" --strict FILE
```

## Step 5 — Report, then stop

This is the approval gate. Do not rewrite past it.

```
## ICP resonance review: <title>

**Verdict: PASS / FIX / BLOCK / NOT GRADABLE — <composite>/10**
Asset: blog / single email / sequence (<n> emails) · Setting: A / B / C · <n> words

### Scorecard

| # | Dimension | Wt | Score | Wtd | Evidence |
|---|-----------|---:|------:|----:|----------|
(one row per dimension; evidence in every row;
 mark any dimension below 6.0 as FLOOR BREACH in its own row;
 mark N/A rows with the reason and state the redistributed weights;
 mark CONFLICT rows where the framework and ICP disagree)
| | **Composite** | **100%** | | **X.X** | |

### Per-email (sequences only)

| Email | D1 | D2 | D6 | D7 | D9 | D10 | Findings |
|-------|---:|---:|---:|---:|---:|----:|----------|
(the per-email dimensions; the floor applies per email here,
 so flag any cell below 6.0 even when the averaged row clears it)

### Guardrails

| Guardrail | Status |
|-----------|--------|
| "catalog" usage | PASS / BLOCK — line refs |
| OpenMetadata treatment | PASS / BLOCK |
| Product names in framework | PASS / BLOCK — names flagged |

### Subgates

| Gate | Status |
|------|--------|
| ICP resonance (this review) | <verdict> |
| Claims (`/defend-check`) | PASS / FAIL / NOT RUN |
| Prose (`lint-prose.py`, `/stop-slop`) | PASS / FAIL / NOT RUN |
| Structure — email only (`/review-nurture`) | PASS / FIX / BLOCK / NOT RUN |
| Links and UTMs — email only (`email-url-qa.md`) | PASS / FAIL / NOT RUN |

### Fix plan

| Priority | Change | Dimension | Expected lift |
|---------:|--------|-----------|---------------|
(ordered by weighted points recovered per unit of effort,
 with the projected composite after all fixes)
```

Then a per-finding redline for every dimension scored below 8. Remediation takes one of two forms, and picking the wrong one produces a dishonest review:

- **Replacement wording**, paste-ready, when the defect is in the copy. Diagnosis without replacement wording is half a review.
- **Required input**, when the defect is missing evidence rather than bad prose: an unsourced number, a customer result nobody has approved, an unconfirmed product name. Name what has to be supplied and by whom. **Never invent a substitute to make the row look complete.**

State plainly that a clean scorecard with `NOT RUN` subgates means the piece is still unreviewed on claims, prose, structure, or links. A resonance verdict is not permission to publish or send. Do not soften a verdict to be agreeable.

## Step 6 — Rewrite, on approval only

Write to a **new versioned file** (`<name>-v<n+1>.md`) in the same directory. Never overwrite the draft you were given. A sequence keeps the locked output schema from `email-nurture.md` and increments its `Draft v<N>` — a rewrite that reshapes the schema fails the structure gate you were careful not to touch.

Three failure modes, all common:

- **Over-editing.** The style rules are entirely subtractive, so chasing a clean score flattens the piece. Make the minimum effective edit. Protect every concrete number, name and date. If the tone got more corporate, say so. **The one exception is a number the review found unsourced:** never invent provenance for it, and where the user approved the rewrite without supplying any, cut or qualify the figure and flag what was removed. A protected number is one you can stand behind.
- **Rewriting past the finding.** A dimension scored 5 needs the fix named in the redline, not a general rewrite of the section that happened to contain it.
- **Breaking a control.** On email, a control is preserved with its exact prior copy (`NUR-TEST-01`). Rewriting one turns it into a new variant and destroys the test. If a control scores badly, report it and leave it alone.

## Step 7 — The writing pass

Not optional. Any prose this skill produces runs the writing rules before delivery.

| Read | Path |
| :-- | :-- |
| Structures | `~/Documents/Claude/Claude Projects/gtmos/03-knowledge/style-guides/stop-slop-structures.md` |
| Phrases | same directory, `stop-slop-phrases.md` |
| Precedence, divergences, carve-outs | `~/.claude/skills/no-ai-slop/COLLATE-OVERLAY.md` |

Read the guides; do not work from memory. The overlay is the single place where precedence and the carve-outs are settled — do not re-derive them here. Then gate:

```bash
python3 "$HOME/Documents/Claude/Claude Projects/gtmos/04-skills/scripts/lint-prose.py" --strict FILE
```

**A passing lint is the floor, not the finish line.** It checks em dashes plus a phrase blocklist scraped from those two guides, so every structural rule needs the manual read. It cannot see inside double quotes, and `--strict` promotes single-word warnings to failures with no proper-noun handling, so a real name fails a clean draft. Overrule false positives and say in the delivery notes that you did.

## Step 8 — Frenemy critique of the rewrite

Runs on the rewrite, not on the read. Skip only if the user says so.

```bash
~/.claude/scripts/frenemy-review.sh /path/to/prompt.md /path/to/outdir
```

Foreground with the Bash-tool `timeout` at 600000ms for anything under ~3,000 words. **Background it above that, and for any sequence** — a long review will exceed the foreground window. Backgrounded, poll the outdir for `codex.md` and `grok.md` and read both when they land.

**Paste the sources into the prompt.** Codex and Grok start blank, and anything you do not paste they will flag as invented — in the session `collate-landing-page` was built from, Codex confidently flagged a verbatim framework description as an unsupported product claim purely because it had only seen an excerpt. Include the full relevant framework sections, the ICP facts that set the audience and the setting, **all three guardrails**, the rubric, and the scores you gave.

Ask for: dimensions you scored generously, claims a skeptical technical reader would not accept, whether the rewrite got more corporate than the original, and anything the fix plan promised that the rewrite did not deliver.

**You own the verdict.** Check every critique against the actual source docs. They are frequently wrong and confidently so. Report what was raised, what you accepted, and what you rejected with the reason in one line each. If one reviewer fails — Grok hitting its free-tier limit is common — say so plainly. A single-reviewer pass is not a two-reviewer pass.

## Step 9 — Re-score and deliver

Re-score the rewrite against the same rubric and **state both composites**. If it still does not clear 8.0, say so and name what is blocking it rather than adjusting the score to fit the outcome.

Deliver the clean copy and the commentary separately. The copy is what gets published or sent: no inline notes, no bracketed alternatives inside it.

**Re-run the gates the rewrite invalidated.** Changed copy means `/defend-check` and, on a sequence, `/review-nurture` and the URL QA are stale. Either re-run them or report them `NOT RUN` against the new version. Never carry a subgate status forward from the draft you rewrote.

---

## Reference

- `references/rubric.md` — the ten dimensions, weights, scoring anchors, and the gate. The skill executes this; it is not a summary.
- `references/calibration.md` — the two legacy hand-built rubrics this replaces, how they were reconciled, and the scored examples to calibrate against.
