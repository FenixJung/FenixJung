# Complete Elixir online store

**English** · [한국어](complete-elixir-store.ko.md) · [Back to overview](../HOW-I-BUILD.md)

**What it is:** [completeelixir.com](https://completeelixir.com), a live skincare store on Shopify.

**My role:** I built the store end to end by directing AI: competitive analysis, design research, finding the problems, and a mobile-first design. I directed the AI to produce the product videos, photos and captions, flagged every issue, had the AI fix it, and tested all functions before launch.

**How the redesign ran:** five rounds of fixes. Each round was made on a copy of the live theme (CE v2 through CE v6), so the live store was never edited directly and every round could be rolled back. Publishing stayed a manual step.

## 1. A design system taken from the brand files

- The old accent color was a cobalt blue that wasn't part of the brand. Colors now come only from the logo and brand source files: ink `#1F2023`, gold `#E2AD5B`, ivory `#F3EBDD`, and bronze `#8A6420` for small text (5.4:1 contrast on white).
- Every button shares one style: Inter 600, 11.5px, square corners, ink by default and gold on hover.
- Section titles use one case style ("Shop by skin concern").

## 2. Measured, not eyeballed

- Section spacing went from anywhere between 15px and 183px to one value: 101px on desktop, 64px on mobile.
- Side-by-side photo and text blocks are aligned by measuring their top and bottom edges.
- On a 375×812 phone screen, the header went from 348px to 214px and both main buttons now fit on the first screen.
- No sideways scrolling at 1440px, 390px or 375px.

## 3. Automated checks

- **Contrast (axe-core, WCAG 2.1 AA):** 0 issues on 14 mobile pages, then every button and in-text link on desktop at 1440px, in both default and hover states.
- **Tapped buttons:** phones kept the hover color and focus ring on tapped buttons. Buttons were fixed by type, not one by one, and an automatic check across 39 pages now finds 0 buttons that change when tapped. Keyboard focus outlines stay, in brand colors (WCAG 2.4.7).
- **Round 5:** four new checks on 50 desktop pages and 12 mobile pages: buttons blending into their background, leftover black lines, off-center content inside centered sections, and the gap under the menu. All ended at 0.
- **Links and contacts:** 69 email addresses on 33 pages weren't clickable; they now become mailto links automatically. 37 internal links and 8 footer links checked.

## 4. A mistake log that becomes a checklist

Every issue gets an entry: what was wrong, why it was missed, and the rule for next time. After five rounds the log has 32 entries, 30 of them caught in my review. A few examples:

| Issue | Why it was missed | Rule now |
|---|---|---|
| An accent blue that isn't in the brand | Colors weren't checked against the brand files | Take colors only from the logo and brand source files |
| Removing one footer column also removed the only links to the journal (209 articles), VIP and search | The column's links weren't checked before removing it | Before deleting a link, check whether it exists elsewhere and what it does to SEO |
| One black line fixed, four more left on other pages | Only the reported spot was fixed | When one issue is reported, find every instance site-wide and fix them together |
| "Mobile is done" after checking a single phone width | Only one width (375px or 390px) was checked | Report which pages and widths were checked, and which weren't |
| Tapped buttons changed color, again and again | Buttons were fixed one at a time | Fix buttons by type, then check the tapped state on every page automatically |

The rules now run as a checklist before every new round.
