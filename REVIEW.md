# Pure Herbal Liquids — infra/design review

## What was wrong

- **Mobile UX was overloaded**: every card carried three dense columns, which collapses into a wall of text on phones.
- **No real landing-page hierarchy**: the old page was more of a decorated menu than a conversion page.
- **SEO/social metadata was missing**: no description, Open Graph, Twitter card, canonical URL, or structured data.
- **PWA basics were missing**: no manifest, service worker, icons, or Apple mobile metadata.
- **Inline JS handlers**: add-ons used `onclick` attributes. Works, but sloppy and harder to maintain.
- **No H1**: bad for accessibility and search.
- **Medical-claim risk**: copy had strong treatment/cure claims. The redesign reframes them as wellness/traditional context and adds a disclaimer.
- **GitHub Pages live URL check**: repository metadata says Pages is enabled, but `https://ganapathygautam.github.io/pureherballiquids/` returned GitHub's 404 during review. That usually means Pages source/deployment is not fully attached yet or needs a fresh successful Pages deployment.

## What changed

- Rebuilt `index.html` as a modern responsive landing/menu page.
- Added sticky nav, strong hero, clear pricing, menu cards, add-ons, ordering flow, and fixed mobile WhatsApp CTA.
- Made product cards phone-first with compact summaries and expandable details.
- Added semantic HTML: `header`, `main`, `section`, `article`, `footer`, H1, accessible labels.
- Removed inline event handlers.
- Added SEO/social metadata and JSON-LD `FoodEstablishment` schema.
- Added PWA files:
  - `manifest.webmanifest`
  - `sw.js`
  - PNG/maskable icons under `assets/icons/`
  - Apple touch icon metadata
- Added `.nojekyll`, `robots.txt`, and `sitemap.xml`.

## Remaining recommendations

- Replace hotlinked product photos with owned/commercially-safe images under `assets/`. Hotlinking is fragile and can break or violate source policies.
- Confirm the real business name, location, delivery zone, opening hours, and Instagram/WhatsApp copy.
- Audit health claims with the owner before going public. Food businesses should not casually imply treatment for diabetes, cancer, IBS, etc. That's how you summon legal goblins.
- In GitHub repo settings, verify Pages source is GitHub Actions or `main`/root and rerun the Pages deployment.
