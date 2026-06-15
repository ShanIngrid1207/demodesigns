# CLAUDE.md — Website Build (Scottsdale Sales Training)

> Standing rules for this project. Project brief is filled in below; the rest are the house rules.

---

## Project brief

**Business Profile & Brand**
- **Business name:** Scottsdale Sales Training
- **Slogan / tagline:** "Close more deals on your terms."
- **What the business does:** Sales training, coaching, and team workshops that shorten the sales cycle, lift win rates, and turn good reps into confident closers.
- **Preferred colors:** Black + metallic gold (from the logo). Emerald green used as the complementary accent (flat, not gradient — gold gradients read as AI).
- **Preferred fonts:** Inter (body/UI). Playfair Display italic for accent words. (Montserrat/Archivo as heavier display options.)
- **Branding/visual assets provided:** `FullLogo.jpg`, `FullLogo Wide.jpg` (both have a solid black background). NEEDED: a transparent-background PNG/SVG for clean placement on light surfaces.

**Core features selected**
- [x] Lead capturing & lead forms (Standard/Premium)
- [x] Credibility display (reviews, stats/counters, coach avatars)
- [x] Contact info display (click-to-call, email links, Scottsdale address)
- [x] Blog page (Premium tier)
- [x] Other: programs/services breakdown, gallery, testimonials carousel

**Content & media responsibility**
- **Written content:** We write it (drafted; flag for client review).
- **Photos & videos:** We source/stock it for now (topical Unsplash placeholders). NEEDED: real workshop/team photos + a short workshop video clip — these beat stock for trust.

**Design direction**
- **Leans toward:** Bold & Modern + Image-Heavy.
- **Absolutely avoid:** fake-metallic gold gradients, gradient text on large headings, generic stock-only heroes, em-dashes as decoration, centered-everything AI layouts, banned `Fraunces`/over-used serifs, filler copy.
- **Reference site(s):** the cinematic nested-card luxury direction + the Metary (dark SaaS), Minta (warm consulting) and Brightly specs the client shared.
- **Why they like the reference:** cinematic and premium, real video/imagery, clearly *designed* (not templated).

**My call**
- **Tier:** Building all three as package demos — Basic, Standard, Premium — so the client can compare what each package delivers for their business.
- **Pages needed:** Basic = 1 single scroll · Standard = 1 long page · Premium = multi-section flagship.
- **Deadline:** TBD.

---

## Reading the intake form — build decisions
- Features → sections & tier. Lead forms = form → Supabase + email. Credibility = testimonials/stats/coaches. Contact = tap-to-call + email + address + map. Blog → Premium.
- Design lean → style & palette (ui-ux-pro-max). Bold & Modern + Image-Heavy here.
- Colors/fonts = design tokens. Black + flat gold + emerald; Inter + Playfair accent.
- "Avoid" list is a hard constraint — check the final build against it.
- Reference site → echo the *why* (cinematic/premium/real media), don't copy.
- Copy: we write it with copywriting; flag for review. Media: we source it; push for real job photos.
- Logo: use the provided file crisply; request a transparent/larger version rather than upscaling.

## Who you're working with
The user handles design and front-end and wants sites released fast — bias toward shipping a clean, complete site over endless polish. **Brainstorm layout + tier before writing code**; propose a structure, get a thumbs-up, then build. Explain choices in plain language; keep the stack simple; user runs the long commands.

## Who the sites are for
Small businesses; mobile-first, trust-building, action-obvious (call/quote always a tap away), fast-loading, findable (local SEO + `LocalBusiness` schema). Plain, confident copy.

## The 3 tiers
- **Basic — "Get found":** 1 single scroll. Image hero (photo or short muted video loop) · about/services · contact (phone, hours, location, map). Clean & static, gentle fade-ins. Click-to-call/email, basic SEO meta, favicon, map, `LocalBusiness` schema.
- **Standard — "Look established":** 1 long page or 2–3 pages. + bento grid of services · work gallery (lightbox) · testimonials · FAQ. Subtle scroll reveals, hover states, counters. Lead form → Supabase + email, full OG/SEO, analytics, CRO pass.
- **Premium — "Stand out":** full multi-section flagship. + video hero · before/after carousel · case studies · per-service · blog/insights. Full editorial motion (reveals, marquees, animated counters, ken-burns, custom easing). Lead dashboard, sitemap, content collections, perf-tuned, AI-search optimization.

Build the smaller tier well rather than the bigger tier half-done. Stay in scope.

## Workflow ritual
1. Research (tier-scaled). 2. Brainstorm — confirm tier, sections, page order, get OK. 3. Design tokens first (ui-ux-pro-max). 4. Copy pass (copywriting/copy-editing + marketing-psychology). 5. Build top-down, hero first → **hero checkpoint, get thumbs-up**. 6. Polish to tier (emil-design-eng, impeccable). 7. Marketing layer (seo-audit, schema, analytics, cro). 8. Pre-flight (quality checklist + web-quality-audit). 9. Launch & hand off (Vercel; directory-submissions checklist).

## Design system & skills
- **ui-ux-pro-max** — plan layout/palette/type/components.
- **frontend-design** + **high-end-visual-design** — build agency-grade sections.
- **emil-design-eng** — motion/micro-interactions (transform/opacity only, strong easing, reduced-motion safe).
- **impeccable** — hierarchy, IA, accessibility, the "not generic AI" pass.
- **web-quality-audit** — automated final inspection.

### Design rules — no AI slop
Visual hierarchy first (one focal point per screen; phone/CTA + trade + city win the squint test). Respect mental models (logo top-left, phone top-right, sticky mobile call bar, forms look like forms). Banned AI tells: centered-everything, default purple/indigo gradients, gradient text, cookie-cutter 3-card grids, emoji in headings, two-button generic hero, default glassmorphism, Inter-for-everything, filler copy, fake testimonials, placeholders. Do instead: real type scale, intentional color, asymmetry, one confident accent, real photos, real customer words. Check against the client's "avoid" list.

## Section pattern library (build visual, not naked text)
Hero (lead with media) · bento grid · work gallery (lightbox) · before/after carousel · logo/cert marquee · stats band (counters) · testimonial carousel · sticky mobile call bar.
Guardrails: video muted/autoplay/loop/playsinline + poster, never blocks first paint, reduced-motion safe; images WebP/AVIF + srcset + width/height + lazy-load; carousels swipeable/keyboard/no scroll-trap; motion transform/opacity 150–300ms, meaningful.

## Tech defaults
- **Framework:** Astro (static) by default; plain single-file HTML/CSS/JS for simplest Basic builds.
- **Styling:** self-contained CSS with design tokens in `:root`; no render-critical CDN frameworks.
- **Fonts:** Google Fonts `<link>` with `display=swap`.
- **Images:** optimized, lazy-loaded, real `alt`.
- **JS:** minimal vanilla, progressive enhancement.
- **Hosting:** Vercel (auto-deploy on push, HTTPS automatic). Repo: github.com/ShanIngrid1207/demodesigns.
- **Backend:** Supabase. Lead form → one Vercel serverless function `/api/lead` that inserts to Supabase `leads` AND emails the client via Resend. Keys server-side only. Validate + honeypot.
- **Domain:** per package; else `*.vercel.app`.

## Quality checklist (pre-flight)
360/768/1280 widths · tap-to-call obvious on mobile · alt text + optimized images · prefers-reduced-motion disables animation · contrast passes · title/meta/OG with business + city + service · favicon · visible focus, real `<a>`/`<button>` · no console errors/broken links · no AI tells (squint test, familiar mental models) · visual-first (no naked text) · video muted/looping/poster, doesn't block paint · carousels swipeable/keyboard/no scroll-trap, lightbox works · copy trust triggers + plain language · `LocalBusiness` schema valid (every tier) · checked vs "avoid" list · web-quality-audit done · (Std/Prem) form → `/api/lead` saves + emails, honeypot · secret keys in env only · analytics verified · (Prem) sitemap + AI-search pass · off-site handoff checklist · domain handled per package.

## Notes
- Convert relative dates to absolute in content.
- Keep chat plain-language; user drives design, not code internals.
