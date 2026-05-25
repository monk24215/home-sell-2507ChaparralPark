# 2507 Chaparral Rd · Manchaca, TX 78652

A single-page listing site for a for-sale-by-owner home in Hays County, Texas. Cinematic hero, animated stats, photo gallery with lightbox, SVG-rendered market charts, complete document library, and a hidden AI-agent reference section.

**Live site:** https://homesforsale.donateortrade.com/
**PDF brochure:** [2507-chaparral-rd.pdf](2507-chaparral-rd.pdf)

---

## What's on the page

A single `index.html` consolidating all the property's documents and images into one modern, immersive page:

1. **Hero** — Full-viewport image with cinematic Ken Burns zoom, large editorial typography (Fraunces), and the price chip floating in the corner.
2. **Stats strip** — Animated number counters: 4 bedrooms, 3 baths, 2,797 sq ft, 0.54 acres, 8 parking spaces.
3. **The Property** — Editorial story copy with a drop cap and sticky pull quote.
4. **Gallery** — Asymmetric grid of property photos with a full-screen lightbox (click any photo, keyboard nav with arrow keys and Esc).
5. **Property Details** — Three columns: Interior, Exterior & Lot, Parking & Inclusions.
6. **Market Position** — Animated bar chart comparing all five automated valuation models against the asking price, plus an SVG line chart of the 11-year tax history showing the 2023 peak and the subsequent correction.
7. **Comparable Sales** — Four cards with recent nearby sales.
8. **Location & Schools** — Embedded map, school list, and nearby cities as pills.
9. **Documents** — Three cards linking to the printable brochure (PDF), the Hays CAD tax appraisal (PDF), and the property knowledge base (PDF).
10. **Contact** — Final dark CTA section with email and brochure download.
11. **Agent Reference** — Collapsible section at the bottom with 20+ structured Q&A pairs optimized for AI agent retrieval (visible to crawlers, hidden by default for humans).

A floating "Inquire" button appears after the hero on scroll, persistent across all sections.

---

## Repository contents

```
.
├── index.html                                      # The listing page (single file, no build step)
├── 2507-chaparral-rd.pdf                           # 4-page printable brochure
├── 2507_Chaparral_Park_Hays_Country_Tax_Appraisal.pdf
├── 2507 Chaparral Rd · Property Knowledge Base c2390657e1fd820d81cb81fbc964f0a2.pdf
├── preview.jpg                                     # 1200×630 OG/social preview
├── images/
│   ├── photo1.jpg   # Front exterior (hero)
│   ├── photo2.jpg   # Property visualization
│   ├── photo3.jpg   # Landscaping detail
│   ├── photo4.jpg   # Side angle with detached garage
│   └── photo5.jpg   # Driveway and garage
├── 404.html
├── CNAME
├── README.md
└── LICENSE
```

No build step. No framework. Pure HTML + CSS + vanilla JS, with Google Fonts loaded from CDN. Charts are hand-rolled SVG — zero dependencies.

---

## Design system

- **Typography:** Fraunces (variable serif, display) + Inter (sans, UI) + JetBrains Mono (data/labels)
- **Palette:** cream `#F6F1E8`, ink `#1A1E1B`, sage `#475A42`, clay `#B8704E`
- **Layout:** CSS Grid with asymmetric photo gallery, sticky transparent header that transitions on scroll
- **Motion:** Intersection Observer for reveal-on-scroll, requestAnimationFrame for number counters, CSS transitions for hover states, `prefers-reduced-motion` respected throughout
- **Accessibility:** semantic HTML, schema.org structured data (`SingleFamilyResidence`), keyboard-navigable lightbox

All design tokens live in CSS custom properties at the top of `index.html` — change palette or fonts globally by editing the `:root` block.

---

## Before you publish — two edits

**1. Update the contact link.** Search `index.html` for `owner@example.com` and replace with your real email.

**2. Verify OG/social image URL.** The `og:image` meta tag points to `https://homesforsale.donateortrade.com/preview.jpg` — update if your domain differs.

---

## Deploy to GitHub Pages

Already deployed. Push to `main` and GitHub Pages serves it at the domain set in `CNAME`. Wait ~60 seconds after push for the cert to refresh.

```
git add .
git commit -m "Redesign: cinematic hero, charts, lightbox gallery, agent KB"
git push
```

---

## Customizing further

- **Photos:** drop replacements into `images/` keeping filenames `photo1.jpg`–`photo5.jpg`. `photo1.jpg` is the hero.
- **Sections:** each section is self-contained and styled independently — delete or reorder freely.
- **Charts:** the AVM bar chart and tax history line chart are inline SVG generated in JavaScript. Update data arrays in the `<script>` block at the bottom of `index.html`.
- **Agent FAQ:** the collapsible "Agent Reference" section at the very bottom is structured Q&A for AI retrieval. Add or edit entries inside the `<details>` block.

---

## Disclaimer

Information deemed reliable but not guaranteed. Listing is by owner — no real estate agent represents the seller. Buyers are responsible for their own due diligence including independent inspection and verification of square footage, lot dimensions, school zoning, and any restrictions or easements of record.

---

## License

Page template (HTML/CSS) released under the [MIT License](LICENSE). Property content (photos, address, listing details) is the homeowner's and is published here for the purpose of marketing this specific home.
