# Logo Plan

## 1. Brand essence
- **Promise:** Protection before payment.
- **Personality:** Trustworthy, calm, smart, human — not scary, not "cybersecurity-bro".
- **Feeling:** "Someone's got my back."
- **Must feel:** Africa-ready, mobile-first, simple enough to recognize at 16 px.

## 2. Naming & lockup
- Wordmark: **MoMo Guardian** (capital M in both "MoMo" — matches the industry spelling, clear readable pair).
- Tagline options (pick one): "Safer before you send." · "Pause. Check. Send safely." · "Every payment, protected."
- Lockups: horizontal (icon + wordmark), stacked, icon-only.

## 3. Concept directions (design 3, pick 1)
| Concept | Idea | Risk |
|---|---|---|
| **A. Shield + Check-Pause** | Shield containing a check mark whose stem hints at a "pause" gesture | Shields are common; differentiate via shape/color |
| **B. Shield + Phone** | Rounded-phone silhouette forming the shield | Can get busy at small sizes |
| **C. Guardian "G" + Signal** | Monogram G whose inner curve is a protective arc / signal wave | Needs careful execution |
| D. (optional) Hand + Coin halt | Open palm shielding a coin — "stop and think" | Can read as "stop/ban"; too negative |

**Recommendation:** start with **A** or **C**. Must work as a single-color mark.

## 4. Visual rules
- **Avoid MTN's identity:** do not use MTN yellow as the brand color, the MTN logo, or oval-like MTN shapes. We are an *independent* layer that works with mobile money. **[ASSUMPTION]** check hackathon branding rules.
- Avoid red as primary (reads as alarm/error); reserve it for critical-risk states.
- Geometry: rounded corners, 2–3 weights max, optical balance; no gradients required.
- Must read at: 16 px (favicon), 32 px (app bar), 512 px (store/social).

## 5. Color system (proposal — tokens for the frontend)
| Token | Hex | Use |
|---|---|---|
| `guardian-navy` | `#0B2545` | Primary brand, text on light |
| `guardian-teal` | `#13A89E` | Accent / "safe" actions |
| `safe-green` | `#2E9E5B` | Low risk |
| `caution-amber` | `#F2A900` | Medium risk (use sparingly near MTN-yellow association; pair with icon + label) |
| `alert-orange` | `#E8590C` | High risk |
| `critical-red` | `#C92A2A` | Critical risk |
| `mist` | `#F4F7FA` | Backgrounds |
| `ink` | `#1B1F24` | Body text |
Always pass WCAG AA contrast (4.5:1 body text). Never rely on color alone — pair with icon + label.

## 6. Typography
- Logo wordmark: geometric/humanist sans (e.g., **Plus Jakarta Sans**, **Poppins**, or **Sora**) — all free (Google Fonts).
- UI: **Inter**. Numbers: tabular figures for amounts.

## 7. Deliverables
| File | Format | Notes |
|---|---|---|
| `logo-primary-horizontal` | SVG + PNG | Icon + wordmark, color |
| `logo-stacked` | SVG + PNG | For square spaces |
| `logo-icon` | SVG + PNG (512, 192, 64) | App icon / avatar |
| `logo-mono-dark` / `logo-mono-light` | SVG | One-color versions |
| `favicon` | `.ico`, 32 & 16 PNG | |
| `social-avatar`, `social-banner` | PNG | GitHub org, slides |
| `brand-kit.pdf` | PDF | 1-pager: logo, colors, fonts, do/don't |
File naming: lowercase-kebab, e.g. `momo-guardian-logo-primary-horizontal.svg`.
Place sources in `04-brand/assets/logo/`, exports in `04-brand/exports/`.

## 8. Clear space & minimum size
Clear space = height of the "G"/shield inner check on all sides. Min size: icon 16 px; horizontal lockup 120 px wide.

## 9. Do / Don't
**Do:** use on light `mist` or navy; keep proportions; use mono version on busy images.
**Don't:** stretch, add shadows/outlines, recolor outside tokens, place on low-contrast backgrounds, imitate MTN marks.

## 10. Production process & timeline
1. **Brief (30 min):** confirm this doc. 2. **Sketch (1–2 h):** 10+ thumbnails per concept on paper.
3. **Vectorize (2–3 h):** top 3 in Figma/Inkscape. 4. **Vote:** team picks 1; test at 16 px and in mono.
5. **Finalize & export (1 h).** 6. **Apply:** READMEs, org profile, favicon, deck, frontend header.
Tools: Figma (free), Inkscape, Canva (quick), SVGOMG for optimization.

## 11. AI-assisted exploration prompt (for ideation only — always redraw/vectorize for final)
> "Minimal vector logo icon, protective shield merged with a check mark and a subtle mobile-phone curve, flat design, navy (#0B2545) and teal (#13A89E), rounded geometry, works at small sizes, no text, white background."
Verify you have the right to use any AI-generated output per tool terms and hackathon rules.

## 12. Acceptance criteria
- [ ] Recognizable at 16 px · [ ] Works in one color · [ ] Distinct from MTN branding · [ ] AA contrast on both backgrounds · [ ] Team vote recorded in an issue · [ ] Exported set committed
