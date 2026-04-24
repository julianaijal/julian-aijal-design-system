# Portfolio Website UI Kit

UI kit for [julianaijal.com](https://julianaijal.com) — Julian Aijal's personal portfolio and blog.

## Structure

```
index.html      — Full interactive click-thru prototype (home, scripting, ramblings, contact)
```

## Components (inline in index.html)

| Component | Description |
|---|---|
| `NavBar` | Sticky top nav, shadow on scroll, active page highlight |
| `Typewriter` | Animated role title — cycles Digital Marketer / SEO Specialist / Web Developer |
| `Hero` | Two-column hero with gradient name, typewriter, CTA buttons, illustration |
| `ShowcaseCard` | 360×280 project card with hover lift |
| `Showcase` | Centered grid of showcase cards |
| `ArticleCard` | Purple-border article row with icon, title, subtitle, read-more button |
| `Ramblings` | Two-column layout: label left, article list right |
| `Footer` | Three-col: "Ping me!" / logo / social icons |
| `BtnPrimary` | Gradient pill button |
| `BtnText` | Underlined purple text button |
| `BtnOutline` | Small purple outline button ("Read more") |

## Pages
- **Home** — hero + showcase + ramblings + footer
- **Scripting** — full project grid
- **Ramblings** — article list
- **Contact** — email CTA

## Design Width
1440px canvas; 9.75rem (~156px) horizontal padding.

## Notes
- Illustration (`julian-illustration.svg`) loaded from `../../assets/`
- Icons loaded from `../../assets/icons/`
- Logo from `../../assets/julian-aijal-logo.svg`
- Project card images use colored placeholder gradients (no real screenshots available in Figma export)
