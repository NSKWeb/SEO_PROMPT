# SEO_PROMPT

A reusable **SEO / search-visibility prompt** and an **OpenHands skill** you can drop into
any web-facing GitHub repository. It turns "make my site rank on Google" into a concrete,
repeatable workflow: discover the stack, audit against a checklist, implement the fixes,
and open a PR.

## What's inside

| Path | Purpose |
|---|---|
| `SEO_PROMPT.md` | Copy-paste prompt (full version + one-liner) for any AI agent — OpenHands, Copilot, Cursor, etc. |
| `.agents/skills/seo-audit/SKILL.md` | OpenHands skill that auto-loads on SEO requests so the agent runs the same audit in any repo. |

## What it covers

1. **Project discovery** — stack, rendering mode (SSG/SSR/CSR), routes, build commands, base URL, existing SEO assets. No guessing.
2. **Technical foundation** — status codes, crawlability, `robots.txt`, `sitemap.xml`, HTTPS, mobile-first, Core Web Vitals, canonicals, clean URLs, `hreflang`.
3. **On-page SEO** — titles, meta descriptions, headings, Open Graph / Twitter cards, JSON-LD structured data, image alt text, internal links.
4. **Content & E-E-A-T** — about/contact, author identity, dates, sources, topical depth.
5. **Off-page / authority** — backlink strategy, penalty risks, brand consistency.
6. **Accounts & measurement** — Google Search Console, GA4, Bing Webmaster Tools, Google Business Profile.
7. **Deliverables** — audit table with `file:line` evidence, direct implementation, verification, one focused PR.

## How to use it

### Option A — as a prompt
Copy the block between the `PROMPT (copy from here)` / `PROMPT (copy to here)` markers in
[`SEO_PROMPT.md`](SEO_PROMPT.md) and paste it into your agent inside the target repo.

### Option B — as an OpenHands skill
Copy the skill folder into your repo:

```bash
cp -r .agents/skills/seo-audit <target-repo>/.agents/skills/
```

Then tell the agent:

> Run the seo-audit skill on this repo.

## Placeholders

| Placeholder | Meaning | Example |
|---|---|---|
| `<BASE_URL>` | Canonical production domain | `https://example.com` |
| `<STACK>` | Framework, if you want to force it | `Next.js 14 App Router` |
| `<GOAL>` | Primary business goal | `rank for "invoice software"` |
| `<LOCALE>` | Language/region targeting | `en-US`, `en-US + es-ES` |

## Notes & safeguards

- It flags **SPA/CSR-only apps** as an SEO risk and recommends SSR/SSG/prerendering, because
  Google may not reliably see client-rendered content.
- It never invents metrics, rankings, or backlinks.
- It asks before deploying, changing the production domain, or adding data-leaking analytics.

## License

MIT — use it, fork it, adapt it to your stack.
