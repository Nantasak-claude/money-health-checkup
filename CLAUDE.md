# Money Health Check-up — Project Context

A financial health check-up web app, framed like a **medical check-up** (the founder is a doctor).
User answers a questionnaire and gets a "lab report" style result: an overall health band,
financial vital signs vs reference ranges, and personalized prescriptions.

## Who / brand
- Founder: a government doctor in Thailand. TikTok: **@thefinancialdoc — "หมอเล่าเงิน · The Financial Doc"**.
- Edge: a doctor explaining money simply. Positioning = "financial check-up designed by a doctor."
- **UI language: Thai.**

## Tech (keep it simple — do NOT over-engineer)
- The entire app is ONE self-contained file: `index.html` (HTML + CSS + vanilla JS, no build, no deps).
- Works offline by opening the file. No backend. No data is stored or transmitted (client-side only).

## Locked product decisions (respect these)
- **No numeric X/100 score shown.** Result = a color band + verdict (medical-style), decided by
  severity-weighted internal logic. (The number felt arbitrary to users.)
- **Insurance + Goals = advisory only, NOT scored.** In Thailand everyone has baseline health
  coverage, so scoring insurance would mislead.
- **Retirement:** ask expected MONTHLY spending after retirement (a direct number), then nest egg
  = that × 12 × 25 (4% rule). Do NOT base it on today's expenses.
- Assets simplified: liquid cash + total investments (กบข./provident folded into investments).
- Net-worth-vs-age vital sign was dropped for MVP (no home value → distorted).
- Money input fields auto-format with commas (e.g. 120,000).

## Scoring (/100, ratio-based, age-adjusted where relevant)
Income 17 · Savings 22 · Emergency Fund 17 · Debt 22 · Investing 22.
CFP-standard ratios: savings rate ≥20%, emergency fund 3–6 mo (personalized), DTI <35%
(−4 if credit-card balance), investment rate ≥15%.
Bands: ≥80 แข็งแรง · 65–79 ดี · 45–64 ควรดูแลเพิ่มเติม · <45 ต้องดูแลเร่งด่วน.

## Design
Dark premium theme matching the TikTok brand: bg #0a0e16, surface #141c2b, teal #2dd4bf primary,
gold #fcd34d keyword highlights (.hl class). Bold Thai headlines with accent-colored keywords.

## Deploy
Live at **money-health.netlify.app** (Netlify). To update: deploy new index.html to the EXISTING
money-health Netlify project (do not create a new site). If linked to GitHub, pushes auto-deploy.

## Guiding principle
Validate whether people find value in the check-up BEFORE adding features. Current focus is
distribution via TikTok, not more features. AI summary / PDF are deprioritized.
