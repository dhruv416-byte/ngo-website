# Tally Form Spec — "Request Training Help"

Build this form at **https://tally.so** in the owner's own account, then paste the form ID into
`index.html` (search for `REPLACE_WITH_TALLY_FORM_ID`).

Free plan covers everything below: unlimited submissions, dashboard, email notifications,
redirect on completion, Google Sheets sync. Only branding removal is paid.

---

## Form title
`Request Training Help`

Turn **Hide title** on in the embed (already set via `hideTitle=1` in the embed URL), so the
page's own heading is the one visitors see.

## Fields — in this order

| # | Label | Tally block type | Required |
|---|---|---|---|
| 1 | Your name | Short answer | Yes |
| 2 | Phone | Phone number | Yes |
| 3 | Email | Email | Yes |
| 4 | Dog's name & breed | Short answer | No |
| 5 | Program | Dropdown | Yes |
| 6 | What's going on? | Long answer | Yes |

### Placeholders (optional, matches the old form)
- Your name → `Jane Smith`
- Phone → `07xxx xxxxxx`
- Email → `you@example.com`
- Dog's name & breed → `Rex — Labrador`
- What's going on? → `Tell us a little about your dog and what you'd like help with…`

### Field 5 — "Program" dropdown options (exact, in order)
```
Puppy Training
Obedience Training
Behaviour & Reactivity Help
Rescue Dog Rehabilitation
Service & Therapy Dog Training
Dog Owner Workshop
I want to donate / support the trust
Not sure — need advice
```

### Submit button text
`Send My Request`

---

## Settings to switch on (Tally → form → Settings)

1. **Self email notifications** → ON, to the inbox that should receive leads.
   Without this you only see leads when you log in to Tally.
2. **Redirect on completion** → `https://ngo-website-gamma-livid.vercel.app/thanks`
   (update this if a custom domain is added later).
3. **Respondent notifications / autoresponse** → optional. Nice touch: a short
   "we've got your message, we'll reply within one working day" email.

## Optional: mirror everything into a Google Sheet
Tally → form → Integrations → Google Sheets. Every submission also lands as a row.
Free, and gives a second copy in case anything ever happens to the Tally account.

---

## Then hand back
The embed URL looks like `https://tally.so/embed/wAbCdE`. The bit after `/embed/` is the form ID.
Paste that over `REPLACE_WITH_TALLY_FORM_ID` in `index.html` and push — Vercel redeploys in ~30s.

## Known limitation
Free plan shows a small **"Made with Tally"** mark on the form. Removing it is the Pro plan
($24/mo as of 30 Aug 2026). Everything else needed here is free.
