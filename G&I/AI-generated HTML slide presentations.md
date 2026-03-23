# The definitive guide to AI-generated HTML slide presentations

**Reveal.js paired with CSS custom properties and self-contained HTML architecture is the optimal stack for an AI coding assistant to generate stunning, brand-consistent slide decks that replace PowerPoint.** This report synthesizes research across 15 domains — frameworks, PDF export, CSS techniques, animations, accessibility, security, and AI generation patterns — into a comprehensive reference for building a Claude Code skill that produces single-file HTML presentations for Alkemy. The key insight: a well-structured skill file using Reveal.js v5.x with inline theming, CSS Grid layout templates, and base64-embedded assets can produce portable, professional presentations in a single `.html` file that works offline, prints to PDF, and rivals PowerPoint in visual quality while surpassing it in interactivity and version control.

---

## Reveal.js dominates the framework landscape for AI generation

After evaluating 12 major HTML slide frameworks, **Reveal.js** (hakimel/reveal.js, **~70,700 GitHub stars**, npm ~30–45K weekly downloads, MIT license, v5.2.1) emerges as the clear winner for programmatic generation. Its combination of simple HTML markup (`<section>` nesting), CDN-loadable architecture, CSS custom property theming via `--r-` prefixed variables, and the richest feature set of any framework makes it uniquely suited for AI output.

The critical advantage for AI generation is Reveal.js's **zero-build-step architecture**. An AI can produce a complete, functional presentation as a single HTML file with `<link>` and `<script>` tags pointing to jsDelivr CDN, or — for full portability — with the ~140KB minified framework inlined directly. The configuration system is a single `Reveal.initialize({...})` call covering transitions, slide numbering, auto-slide timing, and plugin registration. Theme customization requires no SCSS compilation: simply override `--r-heading-color`, `--r-background-color`, `--r-main-font-size`, and other CSS custom properties in a `<style>` block.

Key Reveal.js features the skill file should leverage include **auto-animate** (`data-auto-animate` on adjacent sections for automatic element morphing), **fragments** (`.fragment.fade-in`, `.fragment.fade-up` for build animations), **speaker notes** (`<aside class="notes">`), **code highlighting** via highlight.js with `data-line-numbers` for step-through highlighting, **vertical slides** for topic depth, and the **overview mode** (Escape key). The PDF export path uses `?view=print` (v5.x) with Chrome's print dialog, or the superior Decktape CLI tool.

The runner-up frameworks serve specific niches. **Marp** produces the highest-quality PDFs of any framework (purpose-built for Markdown→PDF conversion via `marp --pdf`), making it ideal for CI/CD pipelines where AI generates `.md` files. **Slidev** (35K+ stars, Vue 3 + Vite) excels for developer-focused presentations but requires a Node.js project — disqualifying it for single-file output. **WebSlides** offers the simplest HTML structure with 120+ utility classes but lacks animation depth. **Remark.js** enables Markdown-in-textarea single-file presentations with minimal JavaScript, serving as an excellent lightweight alternative. **Spectacle** (React-based, Formidable Labs) has a "One Page" template for single-file React presentations, but JSX is harder for AI to generate reliably than plain HTML. Legacy frameworks like Impress.js (3D coordinate systems too complex for AI), Deck.js, Bespoke.js, and S5 are not recommended.

---

## PDF export strategy combines Decktape with rigorous print CSS

The PDF export pipeline should use a two-pronged approach: **Decktape** for automated high-quality export, and **comprehensive `@media print` stylesheets** as a fallback for browser-native printing.

**Decktape** (github.com/astefanutti/decktape) is the purpose-built solution for HTML presentation PDF export. Built on Puppeteer/headless Chrome, it natively supports Reveal.js, Remark, Shower, WebSlides, and virtually any framework via its generic mode. Usage is straightforward: `decktape reveal http://localhost:8000 slides.pdf --size 1920x1080`. It produces PDFs with **embedded fonts, selectable/searchable text, preserved hyperlinks, and vector SVG graphics**. Docker support (`ghcr.io/astefanutti/decktape`) makes it trivially automatable in CI/CD pipelines.

For programmatic control, **Puppeteer or Playwright** provide the most flexible PDF generation. The critical configuration for slides:

```javascript
await page.pdf({
  width: '338.6mm',     // 16:9 widescreen
  height: '190.5mm',
  printBackground: true, // Essential — preserves background colors/images
  preferCSSPageSize: true,
  margin: { top: 0, right: 0, bottom: 0, left: 0 }
});
```

The print stylesheet every generated presentation must include handles five concerns: page sizing (`@page { size: 338.6mm 190.5mm; margin: 0; }`), color preservation (`print-color-adjust: exact` on all elements), animation removal (`animation: none !important; transition: none !important` on `*`), fragment visibility (`.fragment { opacity: 1 !important; }`), and UI hiding (`.controls, .progress, nav { display: none !important; }`). Each slide needs `break-before: page; break-inside: avoid;` with the first slide set to `break-before: auto`. The legacy `page-break-before: always` should be included as a fallback.

Client-side options like **html2pdf.js** produce raster output (text becomes images, unsearchable) and should be avoided for professional use. **Prince XML** offers the highest CSS Paged Media fidelity but costs $500–$3,800+ and lacks JavaScript rendering. **WeasyPrint** (Python, free) cannot handle JavaScript frameworks at all. For Alkemy's use case, Decktape + print CSS is the optimal combination.

---

## CSS architecture for stunning, themeable slide layouts

The brand system implementation should follow a **three-tier design token architecture**: global primitives (raw color values like `--color-blue-700`), semantic aliases (contextual names like `--color-primary: var(--color-blue-700)`), and component tokens (specific overrides like `--slide-title-bg`). This pattern, drawn from Material Design, IBM Carbon, and Salesforce Lightning, ensures that changing a single brand color propagates everywhere.

The complete token system for Alkemy presentations should define tokens across six categories:

- **Colors**: `--color-primary`, `--color-secondary`, `--color-accent`, `--color-text`, `--color-text-muted`, `--color-bg`, `--color-bg-alt`, `--color-surface`, `--color-border`, plus `--color-on-primary` (text color for primary backgrounds)
- **Typography**: `--font-heading`, `--font-body`, `--font-mono`, with a size scale from `--font-size-xs` (0.75rem) to `--font-size-4xl` (3.5rem for slide titles)
- **Spacing**: A 4px base unit (`--space-unit: 0.25rem`) with multiplied values from `--space-xs` (8px) through `--space-3xl` (64px)
- **Layout**: `--slide-padding`, `--content-max-width`, `--gutter`
- **Effects**: `--shadow-sm` through `--shadow-xl`, `--radius-sm` through `--radius-full`, `--transition-fast/normal/slow`
- **Theme modes**: Dark/light switching via `[data-theme="dark"]` selector overriding semantic tokens, with `@media (prefers-color-scheme: dark)` as automatic fallback

**CSS Grid powers the slide layout template system.** Each presentation should include **8–10 reusable layout classes** that the AI selects per slide: `.slide-title` (centered, brand-primary background), `.slide-section` (section divider with left border accent), `.slide-content` (standard content with heading + body), `.slide-two-column` (grid-template-columns: 1fr 1fr), `.slide-image-left` / `.slide-image-right` (2fr 3fr or 3fr 2fr grid), `.slide-comparison` (side-by-side cards), `.slide-quote` (large centered blockquote with decorative quotation mark), and `.slide-data` (chart/metric focus with data cards grid). Named grid areas make complex layouts readable: `grid-template-areas: "header header" "left right" "footer footer"`.

Advanced CSS techniques that elevate visual quality include **backdrop-filter** (`blur(12px) saturate(180%)` for frosted glass text overlays on images), **clip-path** transitions (`inset(0 100% 0 0)` → `inset(0)` for wipe reveals, `circle(0%)` → `circle(75%)` for circle reveals), **mix-blend-mode: difference** for guaranteed text contrast over any image, **CSS counters** for automatic slide numbering (`counter-reset: slide` on container, `counter-increment: slide` on each slide, `content: counter(slide)` in `::after`), and **aspect-ratio: 16/9** for maintaining proportions across viewport sizes. Container queries let slide content adapt to its container rather than the viewport, and CSS nesting (`& h1 { ... }`) keeps styles organized.

For navigation, **scroll-snap** provides the core CSS-only slide mechanism: `scroll-snap-type: y mandatory` on the html element with `scroll-snap-align: start; scroll-snap-stop: always` on each slide. This enables arrow-key and scroll-wheel navigation without JavaScript for the basic case. The **View Transitions API** (`document.startViewTransition(() => updateSlide())`) adds smooth, configurable transitions between slides with named elements (`view-transition-name: slide-title`) that morph across transitions.

---

## Inline SVG and animations bring presentations to life

For charts and diagrams, **programmatic inline SVG generation** eliminates external dependencies while producing crisp vector graphics at any resolution. The skill file should include generation patterns for three chart types:

**Bar charts** use `<rect>` elements positioned on a calculated grid, with `viewBox` for responsive scaling and `fill="var(--color-primary)"` to participate in the theme system. **Pie charts** use the stroke-dasharray technique on `<circle>` elements — each slice is a circle with `stroke-dasharray="${sliceLength} ${circumference - sliceLength}"` and an offset. **Line charts** use `<polyline>` with calculated points and `<circle>` dots at data positions. All three patterns require **fewer than 20 lines of generative code each** and produce zero-dependency SVG that scales perfectly and prints at any resolution.

SVG animations serve two purposes: **decorative flourishes** (SMIL `<animate>` and `<animateTransform>` for looping effects that work even in `<img>` tags) and **reveal effects** (CSS `stroke-dasharray`/`stroke-dashoffset` animation for "line drawing" effects on diagrams). SVG filters like `<feDropShadow>`, `<feGaussianBlur>`, and the gooey effect (`feGaussianBlur` → `feColorMatrix` with high contrast) add depth. `<textPath>` enables curved text for creative typography.

For complex animations, **pure CSS @keyframes** should be the default choice for AI-generated presentations — they're self-contained, performant, and printable (easily disabled via `@media print`). Key patterns include staggered builds (`.build-item:nth-child(n) { animation-delay: calc(n * 0.15s) }`), typing effects (`overflow: hidden; white-space: nowrap; border-right: 3px solid; animation: typing 2s steps(30)`), bounce-in entrances, and the `@property`-based counter animation that animates integer values with `content: counter(num)`. **GSAP** (now fully free, ~80KB from CDN) provides timeline-based sequencing for complex multi-element choreography when CSS alone is insufficient. **Lottie** animations (After Effects → JSON via Bodymovin) add high-quality pre-made motion graphics at roughly half the file size of equivalent GIFs. The newer **CSS animation-timeline: scroll()** enables scroll-driven progress bars and view-based entry animations without any JavaScript, with Chrome/Edge support since v115.

---

## JavaScript patterns for a complete presentation experience

The JavaScript layer handles keyboard navigation (ArrowRight/Space/PageDown for next, ArrowLeft/PageUp for previous, Home/End, Escape for overview, S for speaker notes, F for fullscreen, B for blackout), **touch/swipe detection** (tracking `touchstart`/`touchend` coordinates with a 50px threshold, using Pointer Events as the modern unified approach), and **hash-based deep linking** (`#/slide-3` with `hashchange` listener).

The **presenter notes view** is a critical feature. The implementation opens a new window via `window.open()` displaying current slide, next slide preview, notes content, and elapsed timer. Communication between windows should use the **BroadcastChannel API** (`new BroadcastChannel('presentation-sync')`) — it's simpler than PostMessage (no window references needed), real-time, and same-origin. Reveal.js's notes plugin uses PostMessage with a handshake protocol (`connect` → `state` → `navigate` message types) as the proven production pattern.

**Fragment/build animations** follow the Reveal.js model: elements with `.fragment` class start with `opacity: 0`, receive `.visible` class on advance, with `data-fragment-index` for ordering. The navigation logic checks for unrevealed fragments before advancing to the next slide. **Lazy loading** uses `IntersectionObserver` with `rootMargin: '200px'` to pre-load images one slide ahead, preventing visible loading during transitions. The **Fullscreen API** (`document.documentElement.requestFullscreen({ navigationUI: 'hide' })`) rounds out the core interaction model. The **overview/grid mode** applies `transform: scale(0.25)` to all slides with grid positioning and click-to-navigate handlers.

---

## Self-contained HTML keeps presentations portable and secure

A well-optimized 20-slide self-contained presentation typically weighs **750KB–1.5MB**, often smaller than an equivalent PowerPoint file (5–20MB). The architecture embeds everything inline:

- **Images**: Base64 data URIs (`data:image/webp;base64,...`). WebP produces ~40–60% smaller base64 strings than PNG for photos. Compress images before encoding. Target 50–100KB originals for backgrounds at 1920×1080. SVGs should be inlined directly (not base64'd) since they're already text and can reference CSS custom properties via `fill="var(--color-primary)"`.
- **Fonts**: `@font-face` with base64-encoded WOFF2 (`data:font/woff2;base64,...`). **Font subsetting is critical**: `pyftsubset` or Font Squirrel can reduce a 40KB font to 5–15KB by stripping unused glyphs. Two font families (heading + body) with 3 weights each typically cost 45–120KB base64.
- **JavaScript**: Reveal.js core (~140KB minified) inlined in a `<script>` tag, plus plugins (highlight: ~15KB, notes: ~10KB).
- **CSS**: Framework CSS + theme + custom styles in `<style>` tags, organized as Reset → Tokens → Framework → Theme → Layouts → Components → Utilities.

The **maximum practical file size** is 5–10MB before browsers struggle with initial parsing. Gmail's 25MB attachment limit is the practical upper bound. Pandoc generates self-contained Reveal.js with `--embed-resources --standalone -t revealjs`, and Quarto supports `embed-resources: true`.

Security for corporate sharing requires a **Content Security Policy via meta tag**: `<meta http-equiv="Content-Security-Policy" content="default-src 'none'; script-src 'unsafe-inline'; style-src 'unsafe-inline'; img-src data:; font-src data:; connect-src 'none'; frame-src 'none';">`. The `'unsafe-inline'` for scripts/styles is a necessary trade-off for single-file architecture — for stronger security, use SHA-256 hash-based CSP (`script-src 'sha256-...'`). All content should be self-contained with **zero external dependencies** to prevent supply chain attacks (the polyfill.io incident demonstrated this risk). HTML presentation content is plaintext-visible in View Source — never embed truly confidential data without additional encryption.

File sharing caveats: many corporate email systems block `.html` attachments (workaround: ZIP the file), SharePoint renders HTML in sandboxed iframes that may break JavaScript, and `file://` protocol triggers CORS restrictions. PDF export should always be available as a fallback.

---

## Accessibility and reduced motion are non-negotiable

Every generated presentation must include ARIA semantics: `role="group" aria-roledescription="slide"` on each slide container with `aria-label="Slide N of M: Title"`, `aria-hidden="true"` on non-visible slides, and an `aria-live="polite"` announcer element updated on navigation. Focus management must move focus to the new slide container on each transition (`newSlide.setAttribute('tabindex', '-1'); newSlide.focus()`), with `:focus-visible` styling for keyboard users and a skip-navigation link.

**`prefers-reduced-motion: reduce`** must disable all animations and transitions (set `animation-duration: 0.01ms !important; transition-duration: 0.01ms !important` on `*`). Per WCAG, "reduce" means minimize non-essential motion — fade/opacity transitions are generally safe, while scaling, panning, and parallax are vestibular triggers. High contrast support via `@media (prefers-contrast: more)` and `@media (forced-colors: active)` ensures readability in Windows High Contrast Mode using system colors like `CanvasText` and `Highlight`. Minimum font sizes: **24px for body text** on projected slides, with `rem` units respecting browser zoom to 200% (WCAG SC 1.4.4).

---

## Real-world adoption patterns and where HTML slides win

The **#1 driver** for switching from PowerPoint to HTML slides is **Git-based version control**. Conference speakers who present the same talk multiple times cite the elimination of "Talk_v2_final_FINAL.pptx" proliferation, clean diffs on text-based files, tagging per conference, and GitHub Pages hosting as transformative workflow improvements.

HTML presentations excel for **developer conference talks** (syntax-highlighted code, live demos in adjacent browser tabs, embedded iframes), **interactive presentations** (audience voting, live data, WebGL), **data-driven talks** (D3.js/Chart.js integration), and **persistent web resources** (slides that remain accessible at a URL indefinitely). PowerPoint retains dominance for **corporate environments** (mandated templates, WYSIWYG editing, non-technical collaborators), **real-time co-editing** (PowerPoint Online/Google Slides), **complex object-level animations**, and **universal file exchange** (PPTX as business lingua franca).

Common failure modes when teams adopt HTML slides include the impossibility of non-developer collaboration, missing auto-resize text behavior (PowerPoint automatically shrinks text to fit), no PPTX export path for stakeholders who demand it, and the procrastination risk of "spending effort on formatting instead of content." The hybrid approach — AI generates content, exports to both HTML and PPTX — may ultimately resolve the format debate.

---

## AI-generated presentations are an emerging paradigm shift

The **frontend-slides** Claude Code skill by Zara Zhang represents the state of the art for AI-generated HTML presentations. It went viral in early 2026, generating standalone HTML files with keyboard navigation, touch/swipe support, scroll animations, progress bars, and 10 visual style presets (Neon Cyber, Midnight Executive, Swiss Modern, etc.) — all in a single dependency-free HTML file. Its philosophy: "Dependencies are debt. A single HTML file will work in 10 years."

The broader ecosystem includes **Presenton** (4,300+ GitHub stars, supports Claude/GPT/Gemini/Ollama, exports HTML→PPTX/PDF), **SlideDeck AI** (Streamlit + python-pptx), and **nooqta/ai-presentation** (OpenAI→Reveal.js pipeline). Commercial tools like **Gamma.app** (web-native, card-based) and **Beautiful.ai** (smart layout auto-adjustment) demonstrate that AI presentation generation is commercially viable, though both suffer from "The Gamma Look" — formulaic aesthetics after repeated use — and poor PPTX export fidelity.

Claude-specific workflows span five methods: **python-pptx code execution** in sandbox (produces downloadable PPTX), **HTML Artifacts** (interactive preview in chat, available on free plan), **Projects with brand guidelines** (upload style guide, every output follows brand), **MCP integrations** (direct Google Slides creation from Claude Desktop), and **API pipelines** for scale. The official **Claude for PowerPoint add-in** (launched early 2026) reads slide masters, layouts, fonts, and color schemes to generate slides within corporate templates.

The effective prompting pattern for slide generation follows a structured approach: define role ("Senior presentation designer"), specify constraints (10–12 slides, bullets under 12 words, jargon-free), provide a slide sequence template (Title → Problem → Why Now → Core Idea → Architecture → Metrics → Use Cases → Risks → Roadmap → Call to Action), and request structured output (JSON array with title, subtitle, bullets, image descriptions). For brand compliance, uploading a blank PPTX from the corporate template with explicit instructions about margins, maximum bullets per slide, and font restrictions produces the best results.

---

## The Alkemy skill file architecture

For Alkemy's Claude Code skill, the recommended architecture follows the frontend-slides model of progressive disclosure: a main `SKILL.md` (~200 lines) covering the generation workflow, with supporting files loaded on-demand for specific concerns. The skill should instruct Claude Code to:

1. **Always generate single-file HTML** using Reveal.js v5.x with CDN links (or inline for full portability), Alkemy's brand tokens as CSS custom properties, and the complete layout template library
2. **Select layouts intelligently** per slide content: title slides for openers, two-column for comparisons, image-left/right for case studies, data slides for metrics, quote slides for testimonials
3. **Include print CSS** that preserves backgrounds, shows all fragments, hides UI, and sets `@page { size: 338.6mm 190.5mm; }` for 16:9
4. **Embed accessibility** from the start: aria-roledescription, keyboard navigation, prefers-reduced-motion, focus management
5. **Generate inline SVG charts** for data visualization rather than relying on external libraries
6. **Apply CSP meta tag** and avoid all external dependencies beyond CDN-loaded Reveal.js

The three-tier token system, slide layout templates, print stylesheet, and accessibility patterns documented in this report provide the complete technical foundation for generating presentations that are visually stunning, brand-consistent, fully portable, accessible, and secure — matching or exceeding PowerPoint quality for Alkemy's consulting use case while enabling version control, web hosting, and programmatic generation that PowerPoint cannot offer.

---

## Conclusion

The HTML presentation ecosystem has matured to the point where AI-generated slide decks can genuinely replace PowerPoint for specific, high-value use cases. Reveal.js's dominance (70K+ stars, 12+ years of development, the richest feature set) combined with modern CSS capabilities (custom properties for theming, Grid for layouts, scroll-snap for navigation, View Transitions for effects) creates a foundation that an AI can reliably generate. The self-contained single-file approach — typically under 1.5MB for a 20-slide deck — solves the portability problem that has historically limited HTML presentations. Decktape and comprehensive print CSS solve the PDF export gap. The key remaining limitations are non-technical collaboration (Git is required, no WYSIWYG), auto-sizing text (PowerPoint's adaptive layouts remain superior), and the PPTX export path for stakeholders who demand it. For Alkemy's consulting workflow, the optimal strategy is generating HTML as the primary format for presenting and web hosting, with Decktape-produced PDFs as the universal sharing format — eliminating PowerPoint from the creation workflow entirely while maintaining compatibility with clients who need static documents.
