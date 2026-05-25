# SVRN Lessons (HTML archive)

Static HTML archive of SVRN course lessons. Linked from the SVRN Operator Platform curriculum pages.

## Canonical surfaces
- **Repo:** `Brodiekern1/svrn-lessons`
- **Live URL:** https://svrn-lessons.vercel.app
- **Canonical branch:** `main`
- **Consumed by:** `svrn-command-center` lesson viewer

## What lives here
- Rendered one-pager HTML for each lesson, produced by the `/svrn-lesson-to-onepager` skill from Notion source pages in "The Sovereign Operator (V3)".
- **`brand-onepager.html` — the source file for the canonical SVRN brand one-pager.** It deploys to https://svrn-lessons.vercel.app/brand-onepager — that live URL is what every other repo, skill, and agent should read.

## Reading the brand one-pager

**ALWAYS use the live URL via WebFetch:**

```
WebFetch  https://svrn-lessons.vercel.app/brand-onepager
```

Don't read `brand-onepager.html` locally as a design reference — if a change was pushed from another machine and you haven't pulled, your local file is stale. The live URL is cached `no-store, must-revalidate` so it's always current within seconds of any push. Only read the local file when *editing* the brand (then commit + push, and the live URL updates).

## Non-obvious rules
- **Notion is the source of truth for lesson copy, not this repo.** If lesson copy is edited, re-render from Notion via the skill — don't edit HTML by hand.
- **Brand changes start here.** When updating any SVRN visual standard (colors, typography, components), edit `brand-onepager.html` FIRST. Then cascade to consumers (`svrn-design-system` npm tokens, `svrn-admin`, `svrn-command-center`). Never the reverse.
- Cache headers on `brand-onepager.html` are `no-store, must-revalidate` so updates render instantly without browser cache games.
- Lessons are long-form lecture prose, not bullet summaries (~1500–3000 words, Brodie's voice, Loom-ready).
- Every lesson opens with a Centered Monolith hero; first paragraph auto-promotes as the lede.
