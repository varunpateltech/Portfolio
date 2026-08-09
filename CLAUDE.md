# CLAUDE.md

Guidance for working in this repository.

## What this is

A single-page personal portfolio site, live at **buildwithvarun.com**.

- `index.html` — the entire site: all HTML, CSS, and JS inline in one file. No framework, no build tools, no `package.json`, no bundler. Open it directly in a browser for local dev.
- `README.md` — human-facing overview.
- `Varun_Patel_Resume.pdf` — linked resume download. May be out of date relative to the site content; confirm with Varun before assuming it's current.
- `Images/` — photo assets used in the gallery/media sections.
- `Certifications/` — one subfolder per credential, each holding the real `certificate.pdf` for the `#certifications` section. Cards are text-led (no screenshot image, no "Completed" badge) by design — see `Certifications/README.md`.
- `assets/css/`, `assets/js/` — currently empty. Reserved for when the inline `<style>`/`<script>` blocks in `index.html` eventually get split into standalone files. That split hasn't happened yet — treat it as a deliberate future change, not something to do incidentally while touching something else.
- `docs/` — currently empty. Reserved for documentation beyond the top-level README (e.g. a content-editing guide, changelog, confirmed Netlify setup notes).

There is no CMS and no data files — all copy (bio, experience timeline, case studies, testimonials) is hardcoded directly inside `index.html`. When updating content, edit it there; there's nowhere else it lives.

Page sections in order: hero, `#about`, `#experience`, `#certifications`, `#case-studies`, `#media`, `#gallery`, `#skills`, `#testimonials`, `#blog`, `#contact`. Note `#testimonials` currently has no nav link (nav-scroll only) — a known gap, not a bug in the certifications work.

## Who this site is for

Varun Patel, Staff Product Manager at emnify (Germany). 14+ years across IoT, connectivity platforms, satellite, and enterprise SaaS, spanning Africa, Asia, and Europe.

The full, authoritative career timeline lives in `index.html` under `#about` and `#experience` — treat it as source of truth rather than re-deriving or summarizing it elsewhere, so edits don't drift out of sync. Current arc at a glance:

- **2025–now**: Staff Product Manager, emnify (Germany)
- **2023–2025**: Senior Product Manager, emnify — emnify Innovation Award 2024
- **2021–2023**: Product Manager, Core Networks, emnify
- **2019–2021**: Product Manager, LYNX Technik AG (Germany) — HDR Evie converter, NAB Product of the Year, IBC Best of Show
- **2016–2019**: IoT Product Manager, Willowmore Pvt. Ltd. (Singapore) — patented smart padlock (SG Patent No. 10201708266U), first enterprise sale
- **2011–2015**: Wireless Engineer, Huawei Technologies (Nairobi, Kenya) — 2G/3G/LTE rollouts across East and Southern Africa

If Varun says his role or timeline has changed, update `index.html` (and this file's summary) to match — don't silently keep stale info here just because it was true when this file was written.

## Domain & deployment

- Live domain: `buildwithvarun.com`.
- `README.md` states the site auto-deploys to Netlify on every push to `main`, with the custom domain configured there. There is **no in-repo Netlify config** (no `netlify.toml`, `_redirects`, `_headers`) — everything is managed through the Netlify dashboard.
- Varun has Netlify dashboard access. Treat deployment/DNS/build-hook specifics as **unverified from the repo** — confirm with him before stating them as fact or changing anything that depends on them.

## Third-party integrations

- **Google Analytics**: gtag.js hardcoded in `<head>`, tracking ID `G-97844V7NBN`.
- **Contact**: plain `mailto:mailvarunpatel@gmail.com` link in `#contact`. No form, no form backend (Netlify Forms, Formspree, etc.), no env vars anywhere in the project.

## Tone of voice

Match the voice already used in the site's own copy (see `#about` and `#experience` in `index.html`) when writing or editing any text for this project — bio copy, case studies, README, commit messages, anything reader-facing.

- First person, direct, achievement-led: "I own...", "I led...", "I co-invented..." — not third person, not generic marketing-brochure phrasing.
- Concrete over vague: name the technology, the patent number, the award, the country list, the deal size. Never settle for "significant results" or "great impact" without the specific behind it.
- No em dashes in generated text. Use a period, comma, or parentheses instead.
- No AI-slop phrasing: no "delve," "in today's fast-paced world," no stacked triple adjectives, no generic motivational closers ("the journey continues," etc.).
- Confident, not boastful. State facts and outcomes plainly; let the specifics carry the weight instead of inflating them with adjectives.

## Known open items

Not being worked on right now, just flagged so future sessions don't have to rediscover them:

- `Varun_Patel_Resume.pdf` may be out of date relative to the site's experience section.
- Contact is mailto-only; may move to a real form later.
- Netlify/DNS configuration lives outside this repo — confirm against the actual dashboard before treating any deployment claim here as current.
- `#certifications` is fully live: real PDFs are in place under `Certifications/<slug>/certificate.pdf` and "Verify Credential" links point at real Product School verification URLs. Cards deliberately don't show a "Completed" badge — attaching the certificate PDF already implies completion, so a separate status label would be redundant.
- Nav is missing a link to `#testimonials`; no favicon; no Open Graph/Twitter Card meta tags; no `robots.txt`/`sitemap.xml`. Flagged during a site audit, not yet addressed.
