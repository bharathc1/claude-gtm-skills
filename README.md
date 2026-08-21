# claude-gtm-skills

Claude Code skills for B2B product marketing work: reviewing content against an ICP, writing landing-page copy, and running a positioning-strategist persona. Built for and used on Collate's own GTM work; generalized here so the workflow ports to any B2B SaaS product.

**What's inside:**

- **`collate-icp-review/`** — scores blog/email copy against a weighted, ten-dimension ICP-resonance rubric and rewrites to clear the gate. Point it at your own ICP doc and messaging framework instead of Collate's.
- **`collate-landing-page/`** — writes and audits landing-page copy against a messaging framework and ICP, with a worked before/after example of turning an executive-only page into one that lands with a wider buying committee.
- **`product-marketing-specialist/`** — a senior PMM/messaging-strategist persona: diagnose the strategic problem before writing copy, build a message hierarchy, adapt to the asset.
- **`collate-content-eval/`** — a publication gate for external copy: eight scored dimensions (recognizable problem first, plain language, connected argument, provable claims, human-edited voice, and more), each with hard-gate questions and a required score vector. Won't mark anything `READY` short of 10/10 across the board.

**Using this on your own product:** each skill references "your messaging framework" and "your ICP doc" — swap those pointers for your own internal docs. The internal Collate-specific data (deal counts, buyer-segment splits, discovery-call samples) has been generalized out; the review methodology is what's left.
