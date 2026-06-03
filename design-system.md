# Digital Movement — "Maison" Visual Identity & Design System

A new, ultra-premium luxury identity for digitalmovement.uk. The reference is a
fashion house (Louis Vuitton / Hermès / Aesop): vast restraint, warm ivory,
near-black ink, a single champagne whisper, and unhurried motion. Nothing
shouts. Everything is considered.

> **Live homepage:** `index.html` (open it directly in any browser, or serve the
> folder and visit `http://localhost:8123`).

---

## 1. Mood

Selective, quiet, expensive. The page reads like a printed lookbook — a thin
gallery-mat frame insets the whole screen, type is large and light, and the
work is presented like objects in a vitrine rather than "case studies."

The page is **subtly branded with the real Digital Movement logo** — the colour
lockup in the nav, the negative lockup in the footer. The DM gradient appears
only as a whisper: the eyebrow rules, the scroll-progress bar, and link hovers.
Otherwise the canvas is pure white and monochrome — ultra-minimal, lowest
possible cognitive load.

---

## 2. Colour

| Token | Value | Use |
|---|---|---|
| `--bone` | `#FFFFFF` | Page canvas — clean white |
| `--bone-2` | `#F4F4F5` | Recessed panels (House section, browser bars) |
| `--paper` | `#FFFFFF` | Raised surfaces / cards |
| `--ink` | `#111113` | Near-black, neutral — all primary text, footer bg |
| `--ink-soft` | `#565659` | Secondary text |
| `--ink-faint` | `#98989C` | Labels, meta, placeholders |
| `--line` | `rgba(17,17,19,.12)` | Hairline rules, frame |
| `--gold` | `#9A2FC6` | **DM brand violet — whisper accent only** |
| `--gold-2` | `#EC178D` | DM brand magenta (progress bar, footer links) |

**Accent discipline:** the DM gradient appears only as the eyebrow rules, the
scroll-progress bar, and link/hover underlines. Gallery screenshots render in
**full colour**. The real DM logo sits in the nav (colour lockup) and footer
(negative lockup). If the gradient stops being a whisper, it stops working.

---

## 3. Type

- **Display / UI:** **Jost** — a geometric, Futura-lineage sans (the luxury-house
  staple, since the no-serif rule stands). Used light (300) at large sizes; 400–500
  with **wide tracking** for the wordmark, nav, eyebrows and captions.
- **Body:** **Inter** — neutral, invisible, readable.
- The wordmark and all small labels are **uppercase with 0.16–0.34em tracking** —
  the single strongest luxury cue on the page.

| Role | Spec |
|---|---|
| Hero H1 | Jost 300 · `clamp(46px, 9.4vw, 142px)` · line 0.98 · italic emphasis word |
| Section H2 | Jost 300 · `clamp(30px, 5.2vw, 76px)` |
| Eyebrow / label | Jost 500 · 11px · uppercase · 0.28em · ink-faint · preceded by a 34px gold rule |
| Lead | Inter 400 · `clamp(16px, 1.55vw, 20px)` · ink-soft |
| Body | Inter 400 · 16px · line 1.7 |
| Stat figure | Jost 300 · `clamp(38px, 4.4vw, 64px)` |

---

## 4. Layout

- Max width `1320px`, fluid gutter `clamp(22px, 6vw, 96px)`.
- A fixed **gallery-mat frame** (`.frame`) — a 1px hairline inset ~16px from every
  edge — wraps the whole page like a picture mount.
- Section rhythm: `clamp(96px, 15vh, 200px)` top and bottom. Whitespace *is* the
  decoration.
- Hairline dividers (`--line`) separate ideas; never boxes-within-boxes.
- **Mobile:** content centres (house rule). Nav collapses to a hamburger → a
  full-ivory drawer with big centred Jost links.

---

## 5. Motion (restrained)

- Reveal-on-scroll: opacity + 26px rise, `cubic-bezier(.16,1,.3,1)`, ~1.15s.
- Hero headline: per-line clip-mask rise on load (staggered).
- Counters count up once in view.
- DM-gradient scroll-progress hairline at the very top.
- Nav fades to a blurred white bar with a hairline after 24px of scroll.
- Gallery tiles render in **full colour**, with a slow 1.04 scale on hover.
- Full `prefers-reduced-motion` support (everything renders static).

---

## 6. Components

- **Nav** — real DM colour logo · centre links · outline "Enquire" pill.
- **Eyebrow** — DM-gradient rule + tracked caps (`01 — SELECTED WORK`).
- **Browser frame** (`.browser`) — macOS dots + a pill URL bar; holds a live
  website screenshot, in full colour.
- **Capability row** — index · title · description · right-aligned arrow, on a
  hairline; indents on hover.
- **Stat cell** — big Jost figure + tracked caps label, in a hairline grid.
- **Buttons** — outline pill (nav), solid-ink pill (Send enquiry), and the
  underlined arrow ghost-link. Form fields are bottom-hairline only.

---

## 7. Page structure (`index.html`)

1. **Hero** — eyebrow · *"Crafted to be unforgettable."* · lead · a one-line
   complimentary-audit email field (satisfies the form-in-hero rule, elegantly) ·
   "see the work" · an "At the service of" client roll.
2. **Work (01)** — featured **Cunos** in a browser frame + meta, then a greyscale
   gallery: Husband Retail · Address Bali · Puriva · CX-Experts · Azura Living ·
   "Yours, next".
3. **Capabilities (02)** — Websites · Search & AI · Advertising · Social.
4. **The House** — "Seven years. Three hundred brands." + 7 / 300+ / 5.0 / 90d.
5. **Enquire (03)** — headline + contact details + a clean enquiry form.
6. **Footer** — giant `DIGITAL MOVEMENT` wordmark on ink, hairline columns.

---

## 8. Decisions to confirm / easy levers

- **Branding:** the real DM logo sits in the nav (colour) + footer (negative); the
  DM gradient is the only accent — hairlines, progress bar, hovers — on a white
  monochrome canvas.
- **Clients shown:** Cunos (featured), Husband Retail, Address Bali, Puriva,
  CX-Experts, Azura Living. **Puriva** uses the GitHub homepage build (not the .id
  site). **Husband Retail** is a local build (`husbandretail.com` URL + link are
  placeholders) and **CX-Experts** is linked to `cx-experts.de` (not resolving
  yet). **Azura** was captured via a screenshot service (Cloudflare blocks
  automated browsers) and its hero photo didn't load — recapture when handy.
- **Hero:** pure white + quiet type — understated, "prestige doesn't show off."
  Could add a single full-bleed editorial image or slow video for a cinematic take.
- **Stats** (7 yrs · 300+ · 5.0 · 90d) are from the DM advantage profile — confirm
  the exact figures before this goes live.
- Real backend wiring for the two forms (currently graceful `mailto:` handoff).
