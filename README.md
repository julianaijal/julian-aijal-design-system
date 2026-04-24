# Julian Aijal Design System

A design system for **julianaijal.com** — the personal portfolio and blog of Julian Aijal.

**Preview:** [julian-aijal-design-system.vercel.app](https://julian-aijal-design-system.vercel.app)

## Sources

| Resource | Location |
|---|---|
| Figma file | [Julian Portfolio](https://www.figma.com/design/ghfGlEY2CRIkU4cBoDFMls/Julian-Portfolio) |
| Codebase | [github.com/julianaijal/julianaijal.com](https://github.com/julianaijal/julianaijal.com) |
| Live site | [julianaijal.com](https://julianaijal.com) |

The site is a **Next.js 15 / TypeScript** app with SASS modules, deployed to Vercel. Content is served via **Hygraph CMS** (GraphQL). There is one primary product: the personal portfolio website, containing a hero section, scripting (project) showcase, ramblings (blog), and contact/footer.

---

## CONTENT FUNDAMENTALS

### Voice & Tone
- **Personal, direct, and informal.** Julian speaks in first person — "Hi, I'm Julian" — and uses casual, inviting language like "Ping me!" instead of "Contact me" or "Get in touch."
- **Concise and confident.** Navigation labels are single words ("Scripting", "Ramblings") or short phrases. Headings are never long.
- **Typewriter effect** on the hero reveals job titles one at a time: "Digital Marketer" → "SEO Specialist" → "Web Developer" — suggesting multi-disciplinary identity without overwhelming.
- **No emoji** used anywhere in the UI. Icons are always SVG.
- **Casing**: sentence case for body copy; title case for proper names; nav items are single-word title-case or short phrases.
- **CTAs**: action-forward — "Mail me", "Download CV", "Read more", "Ping me!"
- **Article tone**: informational/educational. Titles are clear and descriptive (e.g. "What is a knowledge graph and how does one work?"). Subtitles/taglines are concise hooks (e.g. "It will do wonders for your SEO strategy.").
- No marketing fluff. No hyperbole. The writing is matter-of-fact and practical.

### Specific examples from the UI
- Hero: *"Hi, I'm Julian, Web developer."*
- CTA: *"Ping me!"*, *"Mail me"*, *"Download CV"*
- Section labels: *"Scripting"*, *"Ramblings"*
- Footer CTA: *"Ping me!"* (consistent, repeated)
- Article sample: *"What is a knowledge graph and how does one work?"*

---

## VISUAL FOUNDATIONS

### Color
The palette is bold and minimal — a very dark navy background (`#111827`) with a vibrant purple-to-blue gradient as the primary brand accent. There are secondary accent colors used for data/media categorization.

| Token | Hex | Role |
|---|---|---|
| `--color-bg` | `#111827` | Primary background (nav, hero, cards, footer — everything) |
| `--color-purple` | `#6f39ff` | Brand purple — buttons, borders, links, gradient start |
| `--color-blue` | `#35b8fe` | Brand blue — gradient end, highlights |
| `--color-purple-mid` | `#9747ff` | Stroke accent |
| `--color-orange` | `#ff641e` | Tertiary (media category, data viz) |
| `--color-yellow` | `#fbbc04` | Tertiary accent |
| `--color-teal` | `#71c8df` | Data/chart accent |
| `--color-mid-blue` | `#2a88c9` | Data/chart accent |
| `--color-grey` | `#858585` | Subtle text / metadata |

**Gradient**: `linear-gradient(86.58deg, #6f39ff 32.64%, #35b8fe 60.62%)` — applied to the hero name text and primary buttons.

### Typography
**Single font family: Inter** (Google Fonts). No serif, no display font.
- Weights used: 400 (Regular), 500 (Medium), 600 (SemiBold), 700 (Bold)
- Hero title: 56px / 4.4rem, weight 600
- Section headings: 40px, weight 700
- Card titles: 18px, weight 700
- Body/lead: 18–24px, weight 400
- Universal letter-spacing: `-0.01em` on headings/UI; `+0.02em` on small caps/labels
- All text on dark background in white or `rgba(255,255,255,0.75)` for secondary

### Backgrounds & Surfaces
- **Everything is dark.** There is no light mode. The entire page uses `#111827` as its background.
- **Cards** use `rgba(255,255,255,0.1)` — a subtle white overlay creating glassmorphism-lite.
- **Article cards** use a repeating texture/pattern image as background (`article-card-texture.png`) plus a `1px solid #6f39ff` purple border.
- No gradients used as backgrounds (only on text and buttons).
- No full-bleed photography backgrounds.

### Spacing & Layout
- Max content width: **70rem (1120px)**
- Desktop horizontal padding: **156px** on 1440px canvas (~10.8%)
- Section vertical padding: **96px** top and bottom
- Cards use **16px** internal padding, **24px** gap
- Navigation height: **80px**

### Buttons
Five types:
1. **Primary (gradient pill)**: 48px tall, `border-radius: 9999px`, gradient background (`#6f39ff` → `#35b8fe`), white bold text, 24px horizontal padding. Hover: reversed gradient (`#35b8fe` → `#6f39ff`).
2. **Secondary (dark ghost pill)**: 48px tall, `border-radius: 9999px`, `rgba(0,0,0,0.15)` background, white bold text.
3. **Text/link button**: 48px tall, no background, purple (`#6f39ff`) bold text with underline. Hover: underline removed.
4. **Outline button** ("Read more"): 30px tall, `border-radius: 3px`, purple border, `rgba(111,57,255,0.15)` fill, purple bold uppercase text, 14px font, `+0.02em` letter spacing. Hover: fill removed.
5. **Skill tag**: 30px tall, `border-radius: 3px`, orange (`#ff641e`) border and text, `rgba(255,100,30,0.15)` fill, bold uppercase 14px. Used for skill/category labels (e.g. "HTML", "CSS").

### Cards
- **Showcase card**: `360×280px`, `border-radius: 8px`, `rgba(255,255,255,0.1)` bg, `box-shadow: 0px 20px 24px rgba(0,0,0,0.1)`, contains a cover image, project name, category in muted text, and a `+` icon
- **Article (rambling) card**: `744×136px`, `border-radius: 6px`, `1px solid #6f39ff` border, texture bg, icon left + title + subtitle text, "Read more" pill button right

### Icons & Imagery
- SVG icons only. Custom set for social (GitHub, LinkedIn, X, Instagram, Bluesky, Threads, TikTok) plus UI icons (envelope, plus, chart, cloud, table).
- Hero illustration: custom SVG of Julian as a flat, vector character. Warm, friendly, hand-drawn feel.
- No stock photography in UI.
- Project/card images: real screenshots of projects. Overall image palette skews dark, matching the navy background.

### Animation & Interaction
- **Typewriter effect** on hero — cycles through job titles with character-by-character typing and deletion.
- **Fade-in on scroll** — hero title fades in with a 3s ease animation on first viewport entry.
- **Blinking cursor** (`|`) accompanies the typewriter, 1s step-end blink.
- **Nav shadow** on scroll — the sticky nav gains `box-shadow: 0 4px 6px -1px rgba(0,0,0,0.3)` when scrolled.
- No bouncy/spring animations. Easing is `ease` / `ease-in-out`. Subtle and professional.

### Hover States
- Nav links: subtle opacity shift
- Primary button: gradient reverses (`#35b8fe` → `#6f39ff`)
- Text button: underline removed
- Outline button: fill removed
- Cards: no hover state
- Footer "Ping me!": inherits link color

### Corner Radii
| Context | Radius |
|---|---|
| Pill button | 9999px (full pill) |
| Showcase card | 8px |
| Article card | 6px |
| Read-more button | 3px |
| Project image within card | 4px |

### Borders & Shadows
- Card shadow: `0px 20px 24px 0px rgba(0,0,0,0.10)` — soft, dark
- Article card border: `1px solid #6f39ff`
- No inner shadows. No outline/glow effects.
- Nav: scrolled state only — `0 4px 6px -1px rgba(0,0,0,0.3)`

---

## ICONOGRAPHY

### Approach
- **SVG only** — no icon font, no PNG icons, no emoji
- Stroke-based icons, `1.5px`–`2px` stroke weight, minimal/line style
- White fill/stroke on dark background
- Social icons are brand-accurate (official shapes) rendered as SVGs

### Icon sets
All icons copied from the production codebase into `assets/icons/`:

| File | Usage |
|---|---|
| `envelope.svg` | Contact / nav "Ping me!" |
| `github.svg` | Social footer |
| `linkedin.svg` | Social footer |
| `x.svg` | Social footer (Twitter/X) |
| `instagram.svg` | Social footer |
| `bluesky.svg` | Social footer |
| `threads.svg` | Social footer |
| `tiktok.svg` | Social footer |
| `chart.svg` | Article category icon |
| `chart-fig.svg` | Article category icon (Figma variant) |
| `cloud.svg` | Article category icon |
| `table.svg` | Article category icon |
| `plus.svg` | Showcase card CTA |
| `envelope-large.svg` | Large contact icon |
| `envelope-fig.svg` | Contact icon (Figma variant) |

Logo: `assets/julian-aijal-logo.svg` — horizontal wordmark "JA" monogram + name.

---

## FILE INDEX

```
README.md                    — This file
SKILL.md                     — Agent skill manifest (entry point for AI tooling)
colors_and_type.css          — All CSS custom properties + semantic type styles
index.html                   — Design system overview (all tabs/sections)
vercel.json                  — Vercel deployment config

assets/
  julian-aijal-logo.svg      — Brand logo (SVG)
  julian-illustration.svg    — Hero illustration (SVG)
  julian-illustration.png    — Hero illustration (PNG)
  article-card-texture.png   — Repeating texture used on article cards
  project-screenshot.jpg     — Sample project image for showcase cards
  icons/                     — All SVG icons (see ICONOGRAPHY above)

screenshots/                 — Reference screenshots
  01-colors-brand.png
  cards.png

preview/                     — Design system preview pages
  colors-brand.html
  colors-text.html
  type-scale.html
  type-specimens.html
  buttons.html
  cards.html
  navigation.html
  footer.html
  icons.html
  spacing.html
  project-detail.html

ui_kits/
  website/                   — Portfolio website UI kit
    index.html               — Full interactive prototype

app/                         — Next.js components (production codebase)
  _components/               — React components (Hero, NavBar, Footer, etc.)
  styles/                    — SCSS modules per component
```
