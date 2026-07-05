# LaneyLabs Website Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build and publish a free, single-page LaneyLabs website at `mrklaney.github.io/laneylabs`.

**Architecture:** A single static `index.html` + `styles.css` (+ `favicon.svg`) with no build step, no framework, no JavaScript. Content is adapted from `AI_work_in_July_2026/apply/portfolio.md` and `capability_statement.md`. Hosted on GitHub Pages, serving the `main` branch root of a new public repo `mrklaney/laneylabs`.

**Tech Stack:** HTML5, CSS3 (system fonts only, no external font/JS dependencies), GitHub Pages, `gh` CLI (already authenticated as `mrklaney`).

## Global Constraints

- Must be free forever — no paid hosting, no domain purchase
- No LaneyLabs work during Elastic work hours / using Elastic resources
- Solo maintainer — must be hand-editable without any tooling knowledge (no build step, no dependencies)
- Repo: `mrklaney/laneylabs` (public), GitHub Pages serving `main` branch, root directory
- Site URL: `mrklaney.github.io/laneylabs`
- Design tone: minimal & technical. Palette: background `#0d1117`, text `#e6edf3`, muted `#8b949e`, accent `#4fd1c5`. Headings/labels in monospace (`ui-monospace, "SF Mono", Menlo, monospace`), body in sans-serif (`ui-sans-serif, system-ui, -apple-system, sans-serif`) — no external font loading
- No JavaScript, no contact form, no custom domain, no analytics, no multi-page structure (all explicitly out of scope)
- Pushing to the public repo and enabling GitHub Pages (Task 4) must not run until Mark gives explicit confirmation in the session it's executed — this makes the site publicly live under his real account

---

### Task 1: HTML structure and content

**Files:**
- Create: `AI_work_in_July_2026/laneylabs-site/index.html`

**Interfaces:**
- Produces: `index.html` referencing `styles.css` (stylesheet, added in Task 2) and `favicon.svg` (added in Task 3) — both referenced now, added later, which is fine since a missing stylesheet/favicon degrades gracefully in a browser
- Consumes: none

- [ ] **Step 1: Write `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>LaneyLabs — AI Engineering &amp; Applied ML Consulting</title>
  <meta name="description" content="LaneyLabs, Inc. — AI Engineer &amp; Applied ML Consultant specializing in RAG, semantic search, and agentic AI on Elasticsearch.">
  <link rel="icon" href="favicon.svg" type="image/svg+xml">
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header class="hero">
    <div class="container">
      <p class="wordmark">LaneyLabs</p>
      <h1>AI Engineer &amp; Applied ML Consultant</h1>
      <p class="tagline">RAG, semantic search, and agentic AI — built on Elasticsearch.</p>
      <a class="cta" href="mailto:mrklaney@yahoo.com">Email Me</a>
    </div>
  </header>

  <main>
    <section class="competencies" aria-labelledby="competencies-heading">
      <div class="container">
        <h2 id="competencies-heading">Core Competencies</h2>
        <ul class="tag-list">
          <li>RAG</li>
          <li>Semantic &amp; Vector Search</li>
          <li>Claude Code / Agentic Systems</li>
          <li>NLP</li>
          <li>Applied ML</li>
        </ul>
      </div>
    </section>

    <section class="work" aria-labelledby="work-heading">
      <div class="container">
        <h2 id="work-heading">Representative Work</h2>
        <div class="card-grid">
          <article class="card">
            <h3>AI OS — Agentic Automation</h3>
            <p>Connected Claude Code to enterprise systems (Gmail, Slack, Drive, Atlassian) via MCP, custom skills, and hooks — with managed short- and long-term memory. Adopted org-wide as the standard AI-enablement pattern.</p>
            <p class="stack">Claude Code · MCP · Python</p>
          </article>
          <article class="card">
            <h3>Production RAG on Elasticsearch</h3>
            <p>Built RAG applications combining Elasticsearch's vector and lexical search with multiple LLM backends. Spot Award-winning work, later the basis of a widely-run GenAI/RAG workshop.</p>
            <p class="stack">Elasticsearch · Claude · GPT-4 · Ollama · Gemini</p>
          </article>
          <article class="card">
            <h3>Semantic &amp; Vector Search</h3>
            <p>Engineered semantic search applications using dense vector embeddings across Elasticsearch, Hugging Face models, and multiple LLMs.</p>
            <p class="stack">Elasticsearch · Hugging Face · Python</p>
          </article>
          <article class="card">
            <h3>NLP Pipelines</h3>
            <p>Built natural language processing pipelines and applications — the resulting technical session became the most-attended talk at ElasticON, Elastic's flagship conference.</p>
            <p class="stack">Python · NLP · Elasticsearch</p>
          </article>
        </div>
      </div>
    </section>

    <section class="why" aria-labelledby="why-heading">
      <div class="container">
        <h2 id="why-heading">Why LaneyLabs</h2>
        <ul class="why-list">
          <li><strong>Elasticsearch insider</strong> — 9+ years working with/at Elastic itself, not just the API surface.</li>
          <li><strong>Ahead of the curve on agentic AI</strong> — hands-on with Claude Code and the Anthropic tooling ecosystem since it emerged.</li>
          <li><strong>Solo-operator efficiency</strong> — direct senior engineering access, no account-management layer.</li>
          <li><strong>Team-ready</strong> — comfortable working as an embedded subcontractor inside a larger delivery team.</li>
        </ul>
      </div>
    </section>

    <section class="contact" aria-labelledby="contact-heading">
      <div class="container">
        <h2 id="contact-heading">Contact</h2>
        <p><a href="mailto:mrklaney@yahoo.com">mrklaney@yahoo.com</a></p>
        <p>720-308-8027</p>
        <p><a href="https://linkedin.com/in/marklaney" target="_blank" rel="noopener">linkedin.com/in/marklaney</a></p>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <p>&copy; 2026 LaneyLabs, Inc.</p>
    </div>
  </footer>
</body>
</html>
```

- [ ] **Step 2: Verify required content is present**

Run: `grep -c "<h1>AI Engineer &amp; Applied ML Consultant</h1>" AI_work_in_July_2026/laneylabs-site/index.html`
Expected: `1` (note: the meta description also contains the phrase "AI Engineer &amp; Applied ML Consultant" without the `<h1>` tags — the untagged pattern would match 2 lines, not 1, so the tag anchor matters here)

Run: `grep -c "mailto:mrklaney@yahoo.com" AI_work_in_July_2026/laneylabs-site/index.html`
Expected: `2` (hero CTA + contact section)

Run: `grep -c "linkedin.com/in/marklaney" AI_work_in_July_2026/laneylabs-site/index.html`
Expected: `1`

Run: `grep -c "<article class=\"card\">" AI_work_in_July_2026/laneylabs-site/index.html`
Expected: `4`

- [ ] **Step 3: Commit**

```bash
cd AI_work_in_July_2026/laneylabs-site
git add index.html
git commit -m "Add site HTML structure and content"
```

---

### Task 2: CSS styling (palette, typography, layout, responsive)

**Files:**
- Create: `AI_work_in_July_2026/laneylabs-site/styles.css`

**Interfaces:**
- Consumes: class names/IDs from `index.html` (Task 1): `.hero`, `.container`, `.wordmark`, `.tagline`, `.cta`, `.competencies`, `.tag-list`, `.work`, `.card-grid`, `.card`, `.card .stack`, `.why`, `.why-list`, `.contact`, `footer`
- Produces: `styles.css`, referenced by `index.html`'s `<link rel="stylesheet" href="styles.css">`

- [ ] **Step 1: Write `styles.css`**

```css
:root {
  --bg: #0d1117;
  --text: #e6edf3;
  --muted: #8b949e;
  --accent: #4fd1c5;
  --mono: ui-monospace, "SF Mono", Menlo, monospace;
  --sans: ui-sans-serif, system-ui, -apple-system, sans-serif;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--sans);
  line-height: 1.6;
}

.container {
  max-width: 760px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

h1, h2, h3, .wordmark, .cta, .stack, .tag-list li {
  font-family: var(--mono);
}

.hero {
  padding: 6rem 0 4rem;
  text-align: center;
  border-bottom: 1px solid #1f2733;
}

.wordmark {
  color: var(--accent);
  letter-spacing: 0.05em;
  text-transform: uppercase;
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.hero h1 {
  font-size: 2rem;
  margin-bottom: 0.75rem;
}

.tagline {
  color: var(--muted);
  font-size: 1.1rem;
  margin-bottom: 2rem;
}

.cta {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  border: 1px solid var(--accent);
  color: var(--accent);
  text-decoration: none;
  border-radius: 4px;
  font-size: 0.9rem;
  transition: background 0.15s ease, color 0.15s ease;
}

.cta:hover {
  background: var(--accent);
  color: var(--bg);
}

section {
  padding: 3.5rem 0;
  border-bottom: 1px solid #1f2733;
}

h2 {
  font-size: 0.85rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--muted);
  margin-bottom: 1.5rem;
}

.tag-list {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.tag-list li {
  border: 1px solid var(--accent);
  color: var(--accent);
  padding: 0.35rem 0.8rem;
  border-radius: 999px;
  font-size: 0.85rem;
}

.card-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem;
}

.card {
  border: 1px solid #1f2733;
  border-radius: 6px;
  padding: 1.25rem;
}

.card h3 {
  font-size: 1rem;
  margin-bottom: 0.6rem;
  color: var(--text);
}

.card p {
  color: var(--muted);
  font-size: 0.95rem;
  margin-bottom: 0.75rem;
}

.card .stack {
  color: var(--accent);
  font-size: 0.8rem;
  margin-bottom: 0;
}

.why-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.why-list li {
  color: var(--muted);
  font-size: 1rem;
}

.why-list strong {
  color: var(--text);
}

.contact p {
  margin-bottom: 0.5rem;
}

.contact a {
  color: var(--accent);
  text-decoration: none;
}

.contact a:hover {
  text-decoration: underline;
}

footer {
  padding: 2rem 0;
  text-align: center;
  border-bottom: none;
}

footer p {
  color: var(--muted);
  font-size: 0.8rem;
  font-family: var(--mono);
}

@media (max-width: 640px) {
  .card-grid {
    grid-template-columns: 1fr;
  }
  .hero {
    padding: 4rem 0 3rem;
  }
  .hero h1 {
    font-size: 1.5rem;
  }
}
```

- [ ] **Step 2: Verify CSS defines the spec'd palette and responsive rule**

Run: `grep -c -- "--accent: #4fd1c5;" AI_work_in_July_2026/laneylabs-site/styles.css`
Expected: `1`

Run: `grep -c -- "--bg: #0d1117;" AI_work_in_July_2026/laneylabs-site/styles.css`
Expected: `1`

Run: `grep -c "@media (max-width: 640px)" AI_work_in_July_2026/laneylabs-site/styles.css`
Expected: `1`

- [ ] **Step 3: Visual check in a real browser**

Run: `open AI_work_in_July_2026/laneylabs-site/index.html` (macOS — opens default browser)

Confirm visually:
- Dark charcoal background, light text, teal accents on the CTA button, tag pills, and links
- Headings/tags render in a monospace font, body copy in sans-serif
- Resize the window narrower than ~640px: the 4 work cards stack into a single column and the hero heading shrinks

- [ ] **Step 4: Commit**

```bash
cd AI_work_in_July_2026/laneylabs-site
git add styles.css
git commit -m "Add site styling: palette, typography, responsive layout"
```

---

### Task 3: Favicon, and README

**Files:**
- Create: `AI_work_in_July_2026/laneylabs-site/favicon.svg`
- Create: `AI_work_in_July_2026/laneylabs-site/README.md`

**Interfaces:**
- Consumes: `index.html`'s existing `<link rel="icon" href="favicon.svg" type="image/svg+xml">` (Task 1) — this task fulfills that reference
- Produces: none consumed by later tasks

- [ ] **Step 1: Write `favicon.svg`**

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32">
  <rect width="32" height="32" rx="6" fill="#0d1117"/>
  <text x="16" y="22" font-family="ui-monospace, monospace" font-size="14" fill="#4fd1c5" text-anchor="middle">LL</text>
</svg>
```

- [ ] **Step 2: Write `README.md`**

```markdown
# LaneyLabs Website

Single-page static site for LaneyLabs, Inc. Plain HTML/CSS, no build step, no dependencies.

## Preview locally

Open `index.html` directly in a browser, or serve it:

\`\`\`bash
python3 -m http.server 8000
\`\`\`

Then visit `http://localhost:8000`.

## Deploy

Hosted on GitHub Pages from the `main` branch root of this repo. Live at:

https://mrklaney.github.io/laneylabs

To publish changes, commit and push to `main` — GitHub Pages redeploys automatically within a minute or two.

## Editing content

All content lives directly in `index.html` (no templating). Styling is in `styles.css`. See `docs/superpowers/specs/2026-07-05-laneylabs-website-design.md` for the design spec.
```

- [ ] **Step 3: Verify files exist and are wired up correctly**

Run: `test -f AI_work_in_July_2026/laneylabs-site/favicon.svg && echo "favicon exists"`
Expected: `favicon exists`

Run: `grep -c "favicon.svg" AI_work_in_July_2026/laneylabs-site/index.html`
Expected: `1`

Run: `test -f AI_work_in_July_2026/laneylabs-site/README.md && echo "readme exists"`
Expected: `readme exists`

- [ ] **Step 4: Commit**

```bash
cd AI_work_in_July_2026/laneylabs-site
git add favicon.svg README.md
git commit -m "Add favicon and README"
```

---

### Task 4: Publish to GitHub Pages

**Files:**
- None created/modified — this task pushes the existing repo to GitHub and configures Pages

**Interfaces:**
- Consumes: the local git repo at `AI_work_in_July_2026/laneylabs-site` (already initialized, with commits from Tasks 1-3), the authenticated `gh` CLI (account `mrklaney`)
- Produces: the live site at `https://mrklaney.github.io/laneylabs`

- [ ] **Step 1: Get explicit go-ahead**

STOP. Before running anything in this task, explicitly ask Mark to confirm he wants to create the public repo `mrklaney/laneylabs` and make the site live now. Do not proceed to Step 2 without an explicit yes in this session — this step makes the site publicly visible under his real GitHub account and is not easily undone once shared/indexed.

- [ ] **Step 2: Create the GitHub repo and push**

Run:
```bash
cd AI_work_in_July_2026/laneylabs-site
gh repo create mrklaney/laneylabs --public --source=. --remote=origin --push
```
Expected: command completes without error and prints the new repo URL (`https://github.com/mrklaney/laneylabs`)

- [ ] **Step 3: Enable GitHub Pages**

Run:
```bash
gh api repos/mrklaney/laneylabs/pages -X POST -f "source[branch]=main" -f "source[path]=/"
```
Expected: JSON response containing `"status"` and a `"html_url"` field with a `github.io` URL. (If this returns a 409/already-exists error, Pages is already enabled — that's fine, continue.)

- [ ] **Step 4: Verify the live site**

Wait about a minute for the first deploy, then run:
```bash
curl -s -o /dev/null -w "%{http_code}\n" https://mrklaney.github.io/laneylabs/
```
Expected: `200`

Then open it in a browser and click the "Email Me" button and the LinkedIn link to confirm both work:
```bash
open https://mrklaney.github.io/laneylabs/
```

- [ ] **Step 5: Commit note (if any local changes were made resolving deploy issues)**

If Steps 2-4 required no file changes, there is nothing to commit — this task's only artifact is the live deployment. If troubleshooting required editing `index.html` or `styles.css`, commit those fixes:
```bash
cd AI_work_in_July_2026/laneylabs-site
git add -A
git commit -m "Fix deploy issue: <describe fix>"
git push
```
