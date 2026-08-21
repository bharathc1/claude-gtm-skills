---
name: collate-landing-page
description: "Write, rewrite, or audit Collate landing page copy — web landing pages, launch pages, campaign pages, event/session registration pages. Reads the messaging framework and ICP standard as sources of truth, enforces the copy guardrails, runs a Codex + Grok critique pass, and delivers to a measured word ceiling. Use whenever the asset is a page someone lands on. Not for emails, decks, blogs, or one-pagers."
---

# Collate landing page copy

A landing page has one job: make a specific reader do a specific thing. This skill exists because Collate copy fails in predictable ways — it drifts from approved positioning, it hangs real statistics on the wrong product, it invents product names, and it gets written for an executive who is not in the room. Each step below closes one of those failure modes.

**Encode the pointer, not the content.** The messaging framework is regenerated with `/refresh-messaging` and the ICP doc is versioned. Never write copy from what you remember of them. Read the files, every time.

---

## Step 1 — Read the sources before drafting a single line

Non-negotiable. All three, every run.

| Source | Path | What you take from it |
| :-- | :-- | :-- |
| Messaging framework | `~/Documents/Claude/Claude Projects/Messaging source of truth/messaging-framework.md` | Category claim, positioning statements, the three primitives, approved sound bites, product capability descriptions, terminology rules |
| ICP standard | `~/Documents/Claude/Claude Projects/ICP/` — list the folder, take the **newest** `YYMMDD-*standard*.md` | Who is actually reading this, which of the three message settings applies, what they're in pain about |
| Copy guardrails | The user's memory dir, `collate-copy-guardrails.md` | The two hard rules below |

Check the framework's header date and its manual-edit notes first. Manual redlines can postdate the source decks and will be reverted by the next refresh — if a redline is load-bearing for your draft, say so.

**Where the framework and the ICP disagree, flag it — never silently pick.** The known live conflict: the framework names CDO/VP as primary economic buyer; the ICP records **zero CDOs across our discovery-call sample**. That tension has a defensible resolution (see Step 3), but the user decides, not you.

---

## Step 2 — The guardrails

Two hard rules. Both came from the user correcting a draft. Neither is negotiable.

1. **Never disparage OpenMetadata.** It is Collate's own Apache 2.0 project and the top of the acquisition funnel. The OSS-graduation story is never "free wasn't enough." It is "you already picked the right standard — the question is whether your team should be the one operating it." Flatter the reader's OSS choice, including when selling against it.
2. **Never call Collate or OpenMetadata "a catalog."** The framework positions explicitly *against* catalogs ("AI native by design rather than AI bolted onto a catalog"); using the word concedes the category. Calling a *competitor's* legacy tool a catalog is fine and on-message.

Plus the framework's own terminology rules, which change — read them, don't recall them. As of the last check they included:

- **No product sub-brands.** AskCollate and Collate AI are retired. Attribute capabilities to Collate or to the named agent (Documentation, Data Quality, Tier, Ontology). **A capitalised product-sounding surface name that does not appear in the framework's "New in Collate 2.0" list is a defect** — either confirm it ships or replace it.
- **Lead with the three primitives** — Context (Connect), Ontology (Reason), Memory (Remember). Never with "shared semantic context" or "semantic intelligence"; both are banned as buyer-unclear. "Semantic search" remains fine as a feature name.
- Primary category claim: **"AI for Data"** (Collate) built on the **"open context layer"** (OpenMetadata). That label belongs to OpenMetadata, not Collate — getting this backwards is a common and confident error.

**Before delivering, grep your draft for `catalog`** and confirm every instance points at a competitor.

---

## Step 3 — Aim it at the person actually reading

Pull the current numbers from the ICP doc; the shape below is stable but the figures are not.

**Who is in the room:** a data architect, data engineer, or governance/DQ lead — one or two levels below whoever holds budget. The economic buyer is frequently absent and represented by your champion. Practitioner-facing material is what the room needs.

**Which of the three message settings applies** — route on *initiative state*, never on job title:

| What the page's audience is doing | Setting | What the copy leads with |
| :-- | :-- | :-- |
| No AI in the conversation | **A — Governance Foundation** | Catalog-replacement, lineage, DQ, glossary, compliance |
| AI named as a future reason to fix the data | **B — AI-Ready Governance** | The foundation you won't throw away when the mandate lands |
| Agents live now or being built | **C — AI-Context-Native** | Context layer, ontology, MCP, agent grounding |

Setting B is the **largest receptive audience for the context-layer narrative** — they voice the intent before they are AI-native. Most launch and campaign pages should be written to land on B while staying legible to A and C.

### The register rule — this is the judgment that matters most

Executive-stakes framing (capital allocation, headcount, risk) is **legitimate and valuable** on a landing page even though no CDO is in the room. It is precisely the ammunition a technical champion cannot build alone and needs in order to sell upward. Do not sand it out in the name of "matching the ICP."

**But it must not be the only register.** If every sentence is written for the absent buyer, the person who actually chose to read the page never sees themselves. Give the practitioner at least one concrete beat — a failure they had this quarter, in their vocabulary.

---

## Step 4 — Claim hygiene

Where most real defects live. Check each of these explicitly.

**Every statistic carries its baseline and its provenance.** A bare "10.8% → 76.5%" invites "measured by whom, against what," and if the reader discovers the answer is "us" later rather than from you, the number stops being an asset and becomes a credibility problem. Name the baseline model and own the benchmark: *"Collate's own benchmark moved text-to-SQL from 10.8% (Sonnet 4.5, ungrounded) to 76.5% on Spider 2.0-Snow."* Never phrase it so it reads as though Collate owns the public benchmark itself.

**No weasel attribution.** "Experts agree," "studies show," "industry reports suggest," "widely regarded as." Name the source or cut the claim — and never invent one. This is the same defect as an unprovenanced statistic, one level down in the prose: both ask the reader to trust an authority you have not named.

**Hang each claim on the capability that actually earns it.** The framework separates claims that sound adjacent. Its clearest live example: **AI Analytics is governed dashboards from ontology and metrics, *not* text-to-SQL on raw schemas** — so the text-to-SQL benchmark validates the *grounding layer*, and attaching it to AI Analytics re-creates the exact positioning the framework is trying to escape.

**Describe capabilities in the framework's own words.** When you paraphrase, you invent. Pull the description from the "New in Collate 2.0" section rather than reconstructing it.

**Prefer failure modes that are silent and plausible over ones that are obviously broken.** "The agent invents a column" is both less accurate and less frightening than "four columns could mean *active customer*, nobody wrote down which, so it picks one." The second is scarier precisely because nothing in the output looks wrong. Reach for the failure the reader would not catch.

**Watch absolutes.** "Every," "the whole estate," "every human and agent action" are easily falsifiable coverage claims. Keep them only where the framework makes them.

---

## Step 5 — Word ceiling and shape

**Rewriting supplied copy:** the original's word count is a **hard ceiling**, and the original's formatting is a **template**.

- Measure the original with `wc -w`. **Never estimate** — a past miss guessed "~130 words" for a 114-word abstract and delivered 190.
- Same house prefix verbatim (e.g. `| Data30`). Same number of paragraphs. Same punctuation register. Do not add headers, bullets, or paragraph breaks the original did not have.
- Measure your draft with `wc -w` too, and **state the count alongside the delivered copy**.
- When the ceiling forces cuts, say what was dropped, and flag any cut that creates a content risk as the content owner's decision.

**Net-new page:** there is no source ceiling, so establish one before drafting — ask for the word budget or the page module it fills. "As long as it needs to be" produces copy nobody can place.

### Craft patterns that have worked

- **Open on something concrete with attitude, not an abstract negation.** *"AI multiplies decisions. It has no opinion on whether they're any good."* beats *"Multiplying a broken decision is not an improvement"* — indifference is a sharper threat than a flat abstraction, and the wordplay pivot on multiplier/multiplying reads as mechanical.
- **Bridge from claim to example by making the reader enact it, not by labelling it.** *"Ask an agent for active customers…"* beats *"As an example…"*. Labelling announces that a demonstration is coming and drains it; enacting implicates the reader.
- **Let one short sentence stand alone as the hammer — but only one per page.** *"So it picks."* Two words carry the paragraph. Both stop-slop guides would cut this line as dramatic fragmentation, so it is a deliberate carve-out with rules: one per page, landing a concrete point the prose already built, never in the opening, never as the final line. A second one is slop. See `~/.claude/skills/no-ai-slop/COLLATE-OVERLAY.md`.
- **Put the sharpest strategic claim in the title**, where it recruits, rather than burying it in paragraph four.

---

## Step 5.5 — The anti-slop pass

Runs before the critique, so Codex and Grok review clean copy instead of spending their findings on AI tells you already know how to fix.

Two systems, one precedence rule. **Collate's gtmos style guides bind; the vendored `no-ai-slop` skill covers what they miss.** Read, in order:

| Read | Path |
| :-- | :-- |
| Structures | `~/Documents/Claude/Claude Projects/gtmos/03-knowledge/style-guides/stop-slop-structures.md` |
| Phrases | same directory, `stop-slop-phrases.md` |
| Precedence + carve-outs | `~/.claude/skills/no-ai-slop/COLLATE-OVERLAY.md` |

Read the guides; do not work from memory of them. The overlay is the single place where precedence, the divergences, and the carve-outs are settled — do not re-derive them here.

Then gate it:

```bash
python3 "$HOME/Documents/Claude/Claude Projects/gtmos/04-skills/scripts/lint-prose.py" --strict FILE
```

**A passing lint does not mean the copy is clean, and a failing one does not always mean it is dirty.** The linter checks em dashes plus a phrase blocklist, so every structural rule needs the manual read. It also cannot see inside double quotes, and `--strict` promotes single-word warnings to failures with no proper-noun handling, so a real name like Paramount Global fails a clean draft. Overrule false positives and say in the delivery notes that you did. Treat the linter as the floor, not the finish line.

Two failure modes to watch:

- **Over-editing.** The gtmos rules are entirely subtractive, so chasing a clean lint run flattens copy. Make the minimum effective edit, protect every concrete number and name, and if the tone got more corporate, say so.
- **Pattern swapping.** Replacing a binary contrast with a colon reveal is not a fix.

---

## Step 6 — The critique pass

**Runs by default. Skip only if the user says so, or for a single-line tweak** (a word swap or one-sentence edit — like polishing a hook — is inline work; do not spend ten minutes on it).

Write a **self-contained** prompt file to the scratchpad, then:

```bash
~/.claude/scripts/frenemy-review.sh /path/to/prompt.md /path/to/outdir
```

Foreground, Bash-tool `timeout` at 600000ms. Background it for large reviews.

### Give the reviewers the full source excerpts — this is the step people get wrong

Codex and Grok start blank. **Any framework language you do not paste, they will flag as invented.** In the session this skill is built from, Codex confidently flagged a verbatim framework description of AI Analytics as an unsupported product claim, purely because it had only been shown an excerpt. Paste the complete relevant framework sections, the ICP facts that set the audience, both guardrails, and the word ceiling.

The same applies to the style rules. Paste `~/.claude/skills/no-ai-slop/eval.md` and the conflict table from `COLLATE-OVERLAY.md`; unpasted, the reviewers will either miss slop or flag a deliberate carve-out (the one hammer sentence) as a defect.

Ask for: wrong assumptions, claims that read as unverifiable to a skeptical technical reader, missed edge cases, anything that cannot actually work, whether the tone got more corporate in the edit, and any surviving pattern from the pasted eval checklist. Tell them to be specific, quote exact phrases, and skip praise.

### Reconcile — you own the verdict

Check every critique against the actual source docs before accepting it. **They are frequently wrong and confidently so.** Do not fold to a critique you disagree with; do not adopt one without verifying it.

Report to the user: what was raised, what you accepted, and what you rejected **with the reason in one line each**. If one reviewer fails (Grok hitting its free-tier limit is common), **say so plainly** — a single-reviewer pass is not a two-reviewer pass and the user should know which they got.

---

## Step 7 — Deliver

**Keep the copy clean and the commentary separate.** The copy block is what gets pasted onto a page — no inline notes, no rationale, no bracketed alternatives inside it. Analysis goes above or below it, clearly divided.

Deliver:

1. The copy, in its final shape, with the **measured** word count stated.
2. A short assessment: what was misaligned and what you changed, one line each.
3. **Open items the user must resolve** — an unconfirmed product name, a rhetorical specific that plants a number the docs don't support, a framework/ICP conflict. Name them; do not bury them.

### Exporting to Google Docs

If asked to export: `mcp__claude_ai_Google_Drive__create_file`, `contentMimeType: text/markdown`. Put the clean copy at the top and everything else under a "Notes — not for publication" divider.

**The Drive tools can create and read but not update.** A revision means a *new* file, and you cannot delete the stale one. So: **export once, when the copy has settled.** If the user is still iterating line by line, say the doc is N lines behind and offer to re-export rather than spawning a file per revision. If you do supersede a doc, hand over both links and tell them to trash the old one.

---

## Reference

`references/worked-example.md` — the Data30 session page this skill was derived from: original copy, the four alignment defects found, every revision with its reasoning, and how the Codex critique was reconciled. Read it when you want to see the method applied end to end.
