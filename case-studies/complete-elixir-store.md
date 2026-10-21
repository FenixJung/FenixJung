# Complete Elixir online store

**English** · [한국어](complete-elixir-store.ko.md) · [Back to overview](../HOW-I-BUILD.md)

**What it is:** [completeelixir.com](https://completeelixir.com), a live skincare store on Shopify.

**My role:** I built the store end to end by directing AI: competitive analysis, design research, finding the problems, and a mobile-first design. I directed the AI to produce the product videos, photos and captions, flagged every issue, had the AI fix it, and tested all functions before launch.

**How the redesign ran:** five rounds of fixes. Each round was made on a copy of the live theme (CE v2 through CE v6), so the live store was never edited directly and every round could be rolled back. Publishing stayed a manual step.

## The process, step by step

Like every project, the store followed my step flow ([see How I Build](../HOW-I-BUILD.md)) and was managed in Jira.

| Step | In this project |
|---|---|
| **Plan:** find the problem → ideate → research | Competitive analysis, design research, and finding the problems with the old store. |
| **Plan:** app concept → logic → functions | The store's structure and features: best sellers with Add to cart on every card, reviews, shop-by-skin-concern tiles, Skin Read, the Product Navigator, the SHOP menu, and a footer that keeps the links to the journal, VIP and search. |
| **Design:** ideate → research → lo-fi → hi-fi | A mobile-first design, with a design system taken from the brand files: ink, gold, ivory and bronze, one button style, and measured spacing. |
| **Build:** functionality | Built on Shopify by directing AI, including the product videos, photos and captions. The redesign ran in five rounds, each on a copy of the live theme (CE v2 to CE v6). |
| **Testing,** throughout | Every function tested before launch. Then contrast scans (axe-core, WCAG 2.1 AA), an automatic tapped-button check on 39 pages, link checks, and layout checks at 1440px, 390px and 375px. |
| **Finish:** all tests pass | Live at [completeelixir.com](https://completeelixir.com). Round 5's four new checks on 50 desktop and 12 mobile pages all ended at 0. |

## Through four lenses

| Lens | What it shows |
|---|---|
| **Project management** | Managed in Jira. Five rounds of fixes, each on a copy of the live theme so any round can be rolled back, with publishing kept as a manual step. A 32-entry mistake log that turns into a checklist before every new round. |
| **UX design** | Mobile-first. Both main buttons now fit on the first phone screen, and the header shrank from 348px to 214px. Spacing, alignment and contrast are measured, not eyeballed. Tapped buttons no longer change color on phones, while keyboard focus outlines stay (WCAG 2.4.7). |
| **Marketing** | Competitive analysis first. AI-produced product videos, photos and captions. A brand color system taken from the logo files. Best sellers with Add to cart on every card, reviews moved right under them, and the footer links to the journal (209 articles), VIP and search kept for SEO. |
| **IT / software** | A Shopify theme (Responsive 9.1) with almost all style changes in one CSS file, versioned theme copies, and email addresses turned into mailto links automatically. Automated checks: axe-core contrast scans (WCAG 2.1 AA), a tapped-state check on 39 pages, link checks, and four layout checks on 50 desktop and 12 mobile pages. |

## In detail

### 1. A design system taken from the brand files

- The old accent color was a cobalt blue that wasn't part of the brand. Colors now come only from the logo and brand source files: ink `#1F2023`, gold `#E2AD5B`, ivory `#F3EBDD`, and bronze `#8A6420` for small text (5.4:1 contrast on white).
- Every button shares one style: Inter 600, 11.5px, square corners, ink by default and gold on hover.
- Section titles use one case style ("Shop by skin concern").

### 2. Measured, not eyeballed

- Section spacing went from anywhere between 15px and 183px to one value: 101px on desktop, 64px on mobile.
- Side-by-side photo and text blocks are aligned by measuring their top and bottom edges.
- On a 375×812 phone screen, the header went from 348px to 214px and both main buttons now fit on the first screen.
- No sideways scrolling at 1440px, 390px or 375px.

### 3. Automated checks

- **Contrast (axe-core, WCAG 2.1 AA):** 0 issues on 14 mobile pages, then every button and in-text link on desktop at 1440px, in both default and hover states.
- **Tapped buttons:** phones kept the hover color and focus ring on tapped buttons. Buttons were fixed by type, not one by one, and an automatic check across 39 pages now finds 0 buttons that change when tapped. Keyboard focus outlines stay, in brand colors (WCAG 2.4.7).
- **Round 5:** four new checks on 50 desktop pages and 12 mobile pages: buttons blending into their background, leftover black lines, off-center content inside centered sections, and the gap under the menu. All ended at 0.
- **Links and contacts:** 69 email addresses on 33 pages weren't clickable; they now become mailto links automatically. 37 internal links and 8 footer links checked.

### 4. A mistake log that becomes a checklist

Every issue gets an entry: what was wrong, why it was missed, and the rule for next time. After five rounds the log has 32 entries, 30 of them caught in my review. A few examples:

| Issue | Why it was missed | Rule now |
|---|---|---|
| An accent blue that isn't in the brand | Colors weren't checked against the brand files | Take colors only from the logo and brand source files |
| Removing one footer column also removed the only links to the journal (209 articles), VIP and search | The column's links weren't checked before removing it | Before deleting a link, check whether it exists elsewhere and what it does to SEO |
| One black line fixed, four more left on other pages | Only the reported spot was fixed | When one issue is reported, find every instance site-wide and fix them together |
| "Mobile is done" after checking a single phone width | Only one width (375px or 390px) was checked | Report which pages and widths were checked, and which weren't |
| Tapped buttons changed color, again and again | Buttons were fixed one at a time | Fix buttons by type, then check the tapped state on every page automatically |

The rules now run as a checklist before every new round.
