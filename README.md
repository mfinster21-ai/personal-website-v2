# Evidence to Lead, LLC — Single-Page Website

> *Bridging research, leadership, and practice.*

A high-end, single-page professional website for **Evidence to Lead, LLC** — designed to communicate boutique strategy firm positioning at the $50k+ engagement level.

---

## Design Direction: "Private Intelligence"

The aesthetic is inspired by McKinsey Global Institute publications, prestigious law firm annual reports, and high-end policy institute communications. The defining qualities:

- **Full dark-mode primary surface** — near-black navy (`#0F1923`) as the base
- **Warm cream light section** — breaking the dark mid-page like a page turn
- **Cormorant Garamond** — a refined, literary display serif for headlines and pull quotes
- **DM Sans** — a precise geometric sans-serif for UI, navigation, and body text
- **Copper/muted gold accent** used sparingly — never decorative, always intentional
- **Abstract SVG system diagram** in hero — precision line-work, no stock photos
- **One orchestrated page-load animation** — the hero diagram fades in with a subtle scale

---

## Structure

This is a **single-file website** — the complete HTML, CSS, and JavaScript live in `index.html`. No build tools, no dependencies, no CDN except Google Fonts.

### Page Sections

| Section | ID | Description |
|---|---|---|
| Navigation | `#nav` | Fixed top nav with scroll state change |
| Hero | (top) | Headline, sub, CTAs, abstract diagram |
| What I Do | `#what-i-do` | Three service area cards on cream bg |
| Selected Impact | `#impact` | Case study grid on dark bg |
| About | `#about` | Founder portrait, narrative, pull quote |
| CTA | `#contact` | Full-width dark section, email CTA |
| Footer | (bottom) | Minimal brand footer |

---

## File Structure

```
/
├── index.html      # Complete single-page website (HTML + CSS + JS)
├── README.md
├── LICENSE
└── .gitignore
```

---

## Design System

### Colors

| Variable | Value | Usage |
|---|---|---|
| `--ink` | `#0F1923` | Primary dark surface |
| `--ink-90` | `#172130` | Slightly lifted dark |
| `--ink-80` | `#1E2D3E` | Cards on dark bg |
| `--cream` | `#F4F1EB` | Light section bg |
| `--parchment` | `#F9F7F3` | Card surfaces on light bg |
| `--copper` | `#B08D57` | Accent — used sparingly |
| `--text-primary` | `#F0EDE6` | Body text on dark |
| `--text-dark` | `#1F2933` | Body text on light |

### Typography

| Role | Font | Weights Used |
|---|---|---|
| Display / Headings | Cormorant Garamond | 300, 400, 500, 600 + italic variants |
| Body / UI / Nav | DM Sans | 300, 400, 500, 600 |

### Spacing Scale

- Section vertical padding: `clamp(96px, 12vw, 144px)`
- Max content width: `1160px`
- Horizontal padding: `clamp(24px, 5vw, 64px)`

---

## Running Locally

No build step required:

```bash
# Python (built-in)
python3 -m http.server 3000

# Node
npx serve .

# Or simply open index.html directly in a browser
```

---

## Deployment

Static single file — deploy anywhere:

- **GitHub Pages** — enable Pages on the repo, point to `index.html`
- **Netlify** — drag and drop the folder
- **Vercel** — `vercel --prod`
- **Cloudflare Pages** — connect repo, no build command needed

---

## Customization Guide

### Replace Contact Email

Search for `info@evidencetolead.com` in `index.html` and replace with the real address.

### Add a Real Founder Photo

Locate the `<div class="about__portrait-frame">` block and replace the SVG placeholder:

```html
<!-- Replace the SVG placeholder with: -->
<img
  src="assets/matthew-finster.jpg"
  alt="Dr. Matthew Finster"
  style="width:100%;height:100%;object-fit:cover;object-position:top center;"
>
```

For a professional grayscale effect, add:
```css
.about__portrait-frame img {
  filter: grayscale(100%) contrast(1.05);
}
```

### Adjust the Hero Diagram

The hero SVG diagram is built inline in `index.html`. Each element is annotated:
- Outer circles control the systems motif scale
- Labels (`RESEARCH`, `EVIDENCE`, etc.) can be renamed
- Colors use `rgba(176,141,87,0.XX)` — adjust opacity to increase/decrease visibility

### Add a Contact Form

Replace the email `<a>` tag in the CTA section with a form. Recommended services:
- **Formspree**: `<form action="https://formspree.io/f/YOUR_ID" method="POST">`
- **Netlify Forms**: Add `netlify` attribute — works automatically on Netlify
- **EmailJS**: Client-side form delivery without a server

### Multi-Page Expansion

To expand into a multi-page site (Services, About, Insights, Contact pages), extract:
1. The CSS variables and base styles into a `style.css`
2. The nav and footer HTML into a shared `nav-footer.js` (see the `etl2/` build)
3. Split sections into separate `services.html`, `about.html`, etc.

---

## Phase 2 Enhancements

Suggested improvements for a future iteration:

1. **Case study modal/drawer** — clicking an impact card opens a full case study overlay
2. **Thought leadership / Insights section** — essays and frameworks hosted on the site
3. **Capability statement PDF** — downloadable one-pager linked from the hero
4. **Micro-typographic refinements** — optical sizing for the hero headline at large viewport widths
5. **Print stylesheet** — for exporting a clean one-pager from the browser
6. **Schema markup** — `Person`, `Organization`, and `ProfessionalService` JSON-LD for SEO
7. **Light/dark mode toggle** — the cream section already provides contrast rhythm; a full toggle is a natural next step
8. **Video background option** — a subtle looping abstract motion piece behind the hero (never distracting)

---

## Browser Support

All modern browsers. Requires `IntersectionObserver` (available in all evergreen browsers since 2018).

---

## License

MIT — see [`LICENSE`](./LICENSE)

---

*© 2025 Evidence to Lead, LLC.*
