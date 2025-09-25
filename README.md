# The Literary Haven

## Short description (concept & design choices)

The Literary Haven is a JavaScript‑free, HTML+CSS microsite that showcases a thoughtfully curated collection of books with highly expressive, tactile interactions. The basic premise is to make it feel like flipping through physical book covers: each “card” will respond to touch with a subtle 3D tilt and levitation, a sprightly hero title invites discovery, and a warm color palette of bookbinding browns with gilding evokes traditional‑style contemporary bookstores.

Design choices favor progressive enhancement and accessibility. Movement is CSS‑only (scroll‑reveal via View Timelines with graceful fallbacks), smooth anchor navigation respects reduced‑motion settings, and interactive cards remain keyboard‑focusable with visual affordances that won’t rely exclusively on hover. A responsive CSS Grid layout allows the catalog to size well from mobile to desktop without scripting.

## Project structure

```
/ (project root)
├─ index.html      # Markup for hero, featured books, about, contact, footer
└─ style.css       # Theme tokens, 3D cards, scroll‑reveal, responsive layout
```

* `index.html` wires fonts, sections, and the 3D book‑card grid.
* `style.css` defines the color system, animations (hover & scroll), and component styles.

---

## How to run

1. Download both files into the same folder.
2. Open `index.html` in any modern browser.

*No build tools or servers required.*

---

## Key features

* **3D Book Cards (CSS‑only):** 3×3 invisible hover zones drive tilt and depth using `:has()` and CSS custom properties (`--rx`, `--ry`, `--tz`). Keyboard focus triggers a gentle tilt for parity.
* **Scroll‑reveals with View Timelines:** Elements animate in as they enter the viewport via `animation-timeline` with `@supports` fallbacks to keep content visible on unsupported browsers.
* **Accessible & Motion‑aware:** `prefers-reduced-motion: reduce` disables smooth scrolling and heavy motion; interactive cards are focusable and labeled for assistive tech.
* **Responsive grid & type:** Auto‑fit CSS Grid for book tiles and fluid typography across breakpoints.
* **Cohesive visual identity:** Theme tokens (primary, secondary, accent, gradients, shadow) produce a warm, bookish atmosphere; the hero includes a subtle pattern overlay and headline shimmer.

---

## Accessibility notes

* **Keyboard support:** Cards have logical tab order, visible focus styles, and descriptive labels for each title/genre.
* **Reduced motion:** Smooth scrolling and reveal animations are disabled when users prefer less motion.
* **Contrast & hierarchy:** Serif display for headings and a clean sans for body improve readability; accent colors are reserved for focus and CTAs.

---

## Browser compatibility

* The experience is best in modern Chromium/Firefox/WebKit.
* `:has()` (3D hover zones) and View Timelines power enhancements; where unsupported, cards remain static and reveal animations are skipped via `@supports`—content stays fully readable and navigable.

---

## Customize

* **Change theme colors/gradients/shadows:** edit CSS variables in `:root` of `style.css`.
* **Update catalog:** duplicate a `.book3d-wrap` block in `index.html`, then modify title, author, and metadata.
* **Tweak motion intensity:** adjust `--rx/--ry` values and shadow levels in the `.book3d-wrap:has(...)` rules.
* **Alter reveal timing:** change `animation-range` and keyframe durations in the `.reveal-*` classes and `@keyframes`.

---

## Credits

* **Fonts:** Crimson Text & Source Sans Pro via Google Fonts (linked in `<head>`).
* **Design & code:** HTML structure in `index.html`; CSS theme and animations in `style.css`.

---

## License

Choose a license suitable for your use (e.g., MIT for open sharing). Add a `LICENSE` file to the project root.
