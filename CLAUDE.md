# NGO Website — Project Handoff

## What this is
Static website for an NGO (dog training charity template) styled after k9ti.org / spiritdogtraining.com.
Plain HTML/CSS — no framework, no build step.

## Where everything lives
- **Live site (Vercel):** https://ngo-website-gamma-livid.vercel.app
- **GitHub repo:** https://github.com/dhruvsunoly1234-cpu/ngo-website (account: dhruvsunoly1234-cpu)
- **Vercel project:** team `samsharma3295-2728s-projects`, project `ngo-website` (Hobby plan)
- **Deploys:** auto — any push to `main` redeploys to Vercel in ~30s. No build command; framework preset "Other".

## Files
- `index.html` — homepage: hero, stats, 6 training programs, about, testimonials, LEAD FORM (#get-help), FAQ, footer
- `donate.html` — Donate tab. IMPORTANT: NO payment links by owner's decision — every donation button/amount card redirects to the lead form (index.html#get-help)
- `thanks.html` — post-form-submit thank-you page
- `blog/index.html` — blog listing page (`/blog`), card grid of all posts
- `blog/<slug>.html` — individual posts (`/blog/<slug>` thanks to cleanUrls). Currently 3:
  puppy-first-week-at-home, reactive-dog-on-lead, rescue-dog-first-30-days
- `styles.css` — all styling (orange accent #e8722a, Poppins/Nunito fonts)
- `hero-dog.svg`, `about-dog.svg` — placeholder art, meant to be replaced with real photos
- `vercel.json` — cleanUrls
- `TALLY-FORM-SPEC.md` — exact fields/settings to rebuild the lead form in Tally

## Business facts (owner-provided)
- Address: Empire House, Mulcture Hall Rd, Halifax HX1 1SP, UK
- Name "Halifax Dog Training Trust" is a PLACEHOLDER — real NGO name pending
- Phone/email: not provided yet — do not invent

## PENDING WORK (in priority order)
1. **Lead form is WIRED but not live**: Tally embed, form ID `dWe58A` (owner chose Tally on
   2026-08-30 — free plan gives unlimited submissions + a dashboard, which email-only tools don't).
   Embed verified working locally; NOT yet pushed to Vercel.
   OUTSTANDING: (a) Program dropdown options in Tally don't match the site — see
   "Known mismatch" in `TALLY-FORM-SPEC.md`, includes "Protection Training" which contradicts
   the site's force-free positioning; (b) confirm Tally Settings: self email notifications ON,
   redirect on completion → /thanks.
   Owner ruled out GHL for this site ("whatever is free just not GHL"), and Formspree was
   rejected because its free tier only archives submissions for 30 days.
2. Real NGO name, phone, email, charity number — swap in when the owner provides them.
3. Owner wants this site for a Google Ads account (possibly Ad Grants — which would additionally
   need a UK registered charity + custom domain; the free .vercel.app URL is fine for regular paid Ads).
4. Custom domain: add in Vercel → Project → Settings → Domains when purchased.
5. Vercel 2FA setup was skipped during onboarding — recommend enabling.

## Adding a new blog post
Copy any file in `blog/`, change the `<title>`, meta description, canonical, date/read-time in
`.post-meta`, `<h1>`, and body. Then add a matching `<article class="post-card">` to BOTH
`blog/index.html` and the "From the Blog" section in `index.html` (homepage shows the newest 3).
No build step — it's live on push.

## Rules learned from the owner
- Do NOT use LocalSites Pro / other website builders — hand-coded + Vercel only.
- No Stripe/PayPal/donation payment links anywhere — all CTAs funnel to the lead form.
- Every action on the site should lead to the lead form (leads are the goal).
