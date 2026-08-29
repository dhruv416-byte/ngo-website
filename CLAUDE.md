# NGO Website — Project Handoff

## What this is
Static website for an NGO (dog training charity template) styled after k9ti.org / spiritdogtraining.com.
Plain HTML/CSS — no framework, no build step.

## Where everything lives
- **Live site (Vercel):** https://ngo-website-murex.vercel.app  ← CURRENT, deployed 2026-08-30
- **GitHub repo:** https://github.com/dhruv416-byte/ngo-website (account: dhruv416-byte) ← CURRENT
- **Vercel project:** team `dhruv-s-projects11` ("dhruv's projects", Hobby), project `ngo-website`

### Why the repo/host moved (2026-08-30)
The original repo `dhruvsunoly1234-cpu/ngo-website` and its Vercel project (team
`samsharma3295-2728s-projects`, URL `ngo-website-gamma-livid.vercel.app`) are on accounts this
machine is NOT signed into — both the terminal git credential and the Chrome session are
`dhruv416-byte`, which has no write access there. With ads waiting, the owner chose to redeploy
on the accounts we do control. **The old repo and old URL are frozen at the pre-blog version
(commit 886d045) and are no longer maintained.** If access to the original account is ever
restored, `git push origin main` from this repo will bring it up to date (remote `origin` is
still configured alongside `deploy`).
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
1. **Lead form is LIVE**: Tally embed, form ID `dWe58A` (owner chose Tally on 2026-08-30 —
   free plan gives unlimited submissions + a dashboard, which email-only tools don't).
   The form collects FOUR fields only: name, phone, email, dog's name & breed. On 2026-08-30 the
   owner deleted the Program dropdown and the "What's going on?" message field, so all site copy
   was rewritten to promise a CALL BACK rather than asking visitors to describe their problem.
   **If either field is ever added back, that copy must be revisited** (homepage lead section,
   FAQ answer 4, footer "Request a call back", all 3 blog post CTAs, blog listing CTA, donate.html).
   STILL UNCONFIRMED by the owner: Tally Settings → self email notifications ON, and
   redirect on completion → /thanks. Without notifications, leads sit unseen in Tally.
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
