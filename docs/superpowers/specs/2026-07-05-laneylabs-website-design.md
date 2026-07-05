# LaneyLabs Website — Design

## Purpose

A free, single-page website for LaneyLabs, Inc. that gives potential clients, subcontracting primes, and consulting contacts a public place to see who Mark Laney/LaneyLabs is and what he does, and a way to get in touch. Part of the broader LaneyLabs contracting initiative (see `AI_work_in_July_2026/apply/`).

## Constraints

- Must be free to run indefinitely — no paid hosting, no paid domain (no domain purchased at all for now)
- No LaneyLabs work during Elastic work hours / using Elastic resources
- Solo maintainer (Mark) — must be simple enough to hand-edit without tooling knowledge

## Hosting & Deployment

- **Platform:** GitHub Pages, under Mark's existing personal GitHub account (`mrklaney`)
- **Repo:** new public repo `mrklaney/laneylabs`
- **URL:** `mrklaney.github.io/laneylabs`
- **Deploy mechanism:** GitHub Pages configured to serve from the `main` branch, root directory — no build step, no CI
- **No custom domain** for now; can be added later by pointing DNS at GitHub Pages if Mark buys one

## Build Approach

Plain hand-written HTML + CSS. No framework, no static site generator, no JavaScript dependencies. Rationale: single page, no content-management need, and "minimal & technical" as a design direction pairs with a clean hand-built page rather than framework scaffolding. Nothing to go out of date, nothing to break.

## Site Structure (single scrolling page)

Content is adapted (not copy-pasted) from `AI_work_in_July_2026/apply/portfolio.md` and `capability_statement.md`, rewritten tighter for web reading.

1. **Hero** — "LaneyLabs" wordmark, one-line positioning statement ("AI Engineer & Applied ML Consultant — RAG, semantic search, and agentic AI on Elasticsearch"), a primary CTA button (mailto)
2. **Core competencies** — short tag/pill list: RAG, Semantic & Vector Search, Claude Code / Agentic Systems, NLP, Applied ML
3. **Representative work** — 3-4 condensed project cards: AI OS (agentic automation on enterprise data), Production RAG on Elasticsearch, Semantic & Vector Search, NLP Pipelines. Each: one-line description + stack tags.
4. **Why LaneyLabs** — 4 differentiator bullets (Elasticsearch insider; ahead of the curve on agentic AI/Claude Code; solo-operator efficiency; team-ready as embedded subcontractor)
5. **Contact** — mailto link (mrklaney@yahoo.com), phone, LinkedIn link
6. **Footer** — small print (© LaneyLabs, Inc.), no additional links

## Visual Design

- **Tone:** minimal & technical
- **Palette:** background `#0d1117` (near-black charcoal), body text `#e6edf3` (light neutral), muted text `#8b949e`, accent `#4fd1c5` (teal) for CTAs/links/highlights/tag borders
- **Type:** system monospace stack (`ui-monospace, "SF Mono", Menlo, monospace`) for headings/labels/tags; system sans-serif stack (`ui-sans-serif, system-ui, -apple-system, sans-serif`) for body copy — no external font loading, keeps the page dependency-free
- **Layout:** generous whitespace, single-column on mobile, comfortable max-width (~720-800px) reading column on desktop, no stock imagery — purely typography/layout driven
- **Responsive:** must work cleanly on mobile (this is likely how most contacts will first open a shared link)
- **No JavaScript** — everything achievable in static HTML/CSS (no menus/interactivity needed for a single scrolling page)

## Error Handling / Edge Cases

- None expected — fully static content, no forms, no external API calls, no user input processed
- Broken-link risk: verify the mailto and LinkedIn URL work before publishing

## Testing / Verification

- Open `index.html` directly in a browser (file://) to sanity-check layout before pushing
- Check responsive layout at mobile width (~375px) and desktop width (~1200px+)
- After deploying to GitHub Pages, load the live `mrklaney.github.io/laneylabs` URL and click through the mailto/LinkedIn links

## Out of Scope (for this iteration)

- Custom domain
- Contact form (using mailto instead — no backend available on GitHub Pages without a third-party service)
- Multi-page structure
- Analytics/tracking
- Blog or case-study subpages

## Rollout

Files are built and reviewed locally first. Pushing to the new public `mrklaney/laneylabs` GitHub repo and enabling Pages happens only after Mark's explicit final go-ahead, since that step makes the site publicly live under his real account.
