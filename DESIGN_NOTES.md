# ZenErgo Solutions — Design Notes

## Reference System
Design inspired by Cal.com's marketing design system: white canvas, dark footer, generous section spacing (96px), card-based feature layout, and a strict two-font hierarchy. Departures from Cal.com are documented below.

---

## Color Palette

New palette built around cool greens and blues evoking a calm, clinical-but-warm professional environment. All values defined as CSS custom properties in `style.css`.

| Token | Hex | Use |
|---|---|---|
| `--c-primary` | `#1c3a4b` | Primary CTA buttons (deep navy-teal instead of Cal.com's near-black) |
| `--c-brand` | `#2e7d6c` | Brand teal — eyebrows, icons, check marks, focus rings |
| `--c-brand-light` | `#dceee9` | Tint — badge backgrounds, pull-quote bg, form focus glow |
| `--c-brand-bright` | `#4aaa92` | Brighter teal for use on dark backgrounds (stat numbers, nav CTA) |
| `--c-accent` | `#3d6fa3` | Slate blue — contact links, used sparingly |
| `--c-warm` | `#9e6b3a` | Bronze warm accent — reserved for future use |
| `--c-canvas` | `#ffffff` | Page floor |
| `--c-surface-soft` | `#f0f4f8` | Light-section backgrounds (alternating with white) |
| `--c-surface-card` | `#edf2f7` | Card backgrounds, hero credential card |
| `--c-surface-dark` | `#0f1c2e` | Navigation, footer, dark section bands |
| `--c-ink` | `#111827` | All headlines |
| `--c-body` | `#374151` | Default body text |
| `--c-muted` | `#6b7280` | Secondary text, subheadings |
| `--c-hairline` | `#d1dde8` | Borders, dividers |

**Departure from Cal.com:** Cal.com uses near-black (`#111111`) for primary CTAs. ZenErgo uses a deep navy-teal (`#1c3a4b`) that sits within the cool brand palette while maintaining strong contrast. The amber from the previous design is retired as a UI color (it remains in the logo asset).

---

## Typography

**Fonts chosen:** Outfit (display) + Inter (body) — both via Google Fonts, free, no attribution required.

- **Outfit** at weight 600 with negative letter-spacing (−0.025em to −0.03em) for all display headings (h1, h2, h3, section titles). Outfit is a geometric humanist sans-serif that reads as modern and authoritative while remaining approachable — well suited to a clinical professional services brand.
- **Inter** at weights 400/500/600 for body, buttons, nav, labels, captions.

**Departure from Cal.com:** Cal.com uses Cal Sans (proprietary) + Inter. Outfit is substituted for Cal Sans. It shares the geometric character and weight feel, but has a slightly softer humanist quality appropriate for a health-adjacent services brand. Previous site used Playfair Display (serif) + DM Sans — replaced entirely to match the modern-SaaS direction.

---

## Layout

- Max content width: 1200px, centered with `.container` wrappers.
- Section vertical padding: 96px (`--sp-section`) on desktop, collapsing to 48px on mobile.
- Hero uses a 7/5 column grid (content left, credential card right) per Cal.com's hero-band pattern.
- Feature cards use 2-up grid (appropriate for two service tiers, vs Cal.com's 3-up for more features).
- Process section uses 5-up horizontal step layout on desktop, collapses to 2-up on mobile.
- Footer: 4-column layout (brand + 3 link columns) on desktop, 2-up on tablet, 1-up on mobile.

---

## Section Rhythm (Alternating Surface Principle)

Each page alternates surface modes to avoid visual monotony:

**Home:** White hero → Dark trust bar → White services → Soft-gray about strip → White process → Soft-gray CTA → Dark footer

**About:** Dark page hero → White profile → Dark philosophy → Soft-gray CTA → Dark footer

**Contact:** Dark page hero → White contact form → Soft-gray service reminder → Dark footer

---

## Component Decisions

**Buttons:** Three variants — `btn-primary` (dark navy), `btn-secondary` (white with hairline border), `btn-ghost-light` (transparent, for use on dark backgrounds). Nav CTA uses `nav-cta-link` styled in brand teal.

**Hero card:** Styled as a `surface-card` (light blue-gray) rather than Cal.com's white-with-border, to distinguish it from the white canvas behind it on the home page.

**Service cards:** Level 1 head uses `surface-card` (light); Level 2 head flips to `--c-primary` (dark) as the featured/elevated tier signal — adapted from Cal.com's featured pricing tier pattern.

**Process steps:** Left-border treatment (2px `hairline-soft`) rather than numbered cards, for a cleaner, less decorated flow.

---

## Navigation

- Nav height: 68px (down from 220px in the previous build — the old height was caused by a 200px logo).
- Logo rendered at 46px height; the image `ZenErgo-wName.png` already contains the brand name so the redundant text `<span>` next to it has been removed.
- Hamburger opens a full-screen drawer (same as before) with `aria-expanded` toggle for accessibility.

---

## SEO Preservation

All existing `<title>`, `<meta name="description">`, canonical, Google Analytics, and JSON-LD tags preserved exactly. Google Search Console verification tag preserved on `index.html`. Page filenames unchanged.

---

## Testimonials Page

`testimonials.html` is a complete, styled placeholder page. It carries `<meta name="robots" content="noindex">` so it does not appear in search results while empty. It is not linked from any nav, footer, or in-page link on any other page.

---

## No Stock Photos Added

The brief permitted adding stock photography. This rebuild omits them — the credential card pattern (showing real data about Dr. Rabin) is more brand-specific and credible for a professional clinical services brand than generic office photography. The owner can add images to any section in the future.
