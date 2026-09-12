# NOTFLIX — Student Tailwind Project

NOTFLIX is a fictional streaming catalog built for a web-development class. It is not an official Netflix product, does not stream real films, and does not collect account or payment information.

## Design choice: Option C

This project reinterprets the browse mockup's **navigation + featured hero + horizontal content rows** structure with an invented entertainment concept, original parody titles, and original artwork. The marketing/email-capture option is not used. The site was not copied from a pre-built template or component library. AI assistance was used for artwork and implementation; the student should follow their course's disclosure requirements and understand the submitted code.

## Open the project

Download or clone the repository, keep its folders together, and open `index.html` in a browser. There is no build step or package installation. **Internet access is required for the Tailwind Play CDN and Google Fonts.** All movie images are local; the catalog does not use fetch requests or a backend. GitHub's file viewer shows source code, not a running website.

## Required files

- `index.html`: semantic page structure, Play CDN, and theme configuration.
- `js/script.js`: fictional catalog, mobile toggle, filters, local My List, dialogs, and previews.
- `images/`: 84 original artwork files for 28 fictional titles, plus an asset manifest.
- `docs/html-validation.png`: actual passing W3C Nu HTML Checker result.
- `docs/mobile.png`, `docs/tablet.png`, and `docs/desktop.png`: responsive checks.
- `docs/chrome-mobile.png`: Chrome mobile-width check.
- `README.md`: design choice, sources, setup, testing, and component recipes.

## Tailwind theme and responsiveness

The Play CDN is intentionally used for this learning exercise. `tailwind.config` extends three colors: `brand-red` (#e50914), `screen-black` (#0b0b0b), and `panel-dark` (#181818). `font-display` uses **Archivo**, loaded from Google Fonts, with Arial and sans-serif fallbacks. These tokens style the logo, page background, panels, and text.

All layout and presentation use Tailwind utilities. There is no custom stylesheet or inline style attribute. Semantic class names such as `card` and `save-button` are JavaScript hooks only. Responsive `md:`, `lg:`, and `xl:` utilities adapt navigation, spacing, typography, and card widths. Content strips scroll internally; the page itself should not overflow horizontally.

The mobile menu uses a short vanilla-JavaScript handler that toggles Tailwind's `hidden` class and updates `aria-expanded`. Desktop navigation uses `md:flex`. All interactive elements have visible `focus:` ring utilities; buttons, navigation, and posters have `hover:` feedback.

## Artwork and functionality

All posters and banners were generated specifically for this project with OpenAI image generation from original parody scene descriptions. They are not official poster copies, official logos, or intended celebrity portraits. Portraits contain fictional titles; landscape artwork has no baked-in titles. The interface title is live text. The assignment mockups were structural references only, and their copyrighted poster images are not included.

Search matches titles, genres, and descriptions. Movies and Shows filter the catalog. My List is saved only in browser localStorage; blocked storage falls back to the current visit. Details display matching wide artwork. Play preview is a 24-second artwork-and-caption demo with pause, seek, and replay, not a full film. There is no audio, login, signup, analytics, database, or real backend.

## Validation and browser checks

- W3C Nu HTML Checker returned **zero errors and zero warnings** for `index.html`; screenshot saved in `docs/html-validation.png`.
- Tested at 375px, 768px, and 1440px in the Codex in-app browser: page width matched viewport width, the custom background/font applied, and mobile navigation opened and closed.
- Also tested in Google Chrome, including the mobile toggle. Both browser surfaces displayed the catalog. These are not claimed as two independent rendering-engine tests.
- No JavaScript errors were reported by the in-app browser. Chrome reported extension-style asynchronous message-channel errors in its existing profile; no site messaging API is used. A clean-profile Chrome console check remains recommended.
- Direct `file://` verification was blocked by the testing tool's URL policy. The student must complete the final double-click-open test with internet access.
- The repository contains no ZIP files.

## Git history and submission honesty

The initial completed site was imported as one commit. The repository was created **after** initial development, so the original setup/HTML/styling checkpoints were not separately committed at the time. Later commits record real rubric corrections and validation work; they are not a reconstructed or backdated history. This does not fully meet the assignment's original incremental-history requirement.

Before submitting, run `git log --oneline`, paste its actual output and the public repository URL into the course submission comment, complete the direct-file check, and confirm the course deadline. This project does not submit itself to the course platform.

Public repository: https://github.com/DaxtonZimmerman/Notflix

## Reused utility component recipes

The exact repeated class strings are listed below, including non-styling hooks. Keeping the recipes visible documents the utility-first repetition without introducing custom CSS or `@apply`.

### Shared keyboard focus

Used on every link, button, input, and select:

`focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-screen-black`

### Catalog/dialog recipe 1

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
card min-w-0 snap-start
```

### Catalog/dialog recipe 2

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-screen-black poster-button group/poster block aspect-[2/3] w-full overflow-hidden rounded-lg bg-panel-dark p-0 transition hover:-translate-y-1 hover:ring-2 hover:ring-brand-red motion-reduce:transform-none
```

### Catalog/dialog recipe 3

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
h-full w-full object-cover
```

### Catalog/dialog recipe 4

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
card-info flex items-start gap-2 pt-3
```

### Catalog/dialog recipe 5

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
card-title mb-1 text-xs font-bold leading-relaxed md:text-sm
```

### Catalog/dialog recipe 6

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
card-genre text-xs text-gray-400
```

### Catalog/dialog recipe 7

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-screen-black save-button ml-auto h-7 w-7 shrink-0 rounded-full border border-gray-500 bg-transparent text-lg text-white hover:bg-white/20 aria-pressed:border-green-400 aria-pressed:text-green-400
```

### Catalog/dialog recipe 8

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
row my-8 mb-12
```

### Catalog/dialog recipe 9

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
row-heading mb-4 flex items-center justify-between gap-3
```

### Catalog/dialog recipe 10

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
text-lg font-bold md:text-xl
```

### Catalog/dialog recipe 11

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
row-controls flex gap-2
```

### Catalog/dialog recipe 12

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-screen-black arrow hidden rounded bg-white/10 px-3 py-1.5 text-xl hover:bg-white/25 md:block
```

### Catalog/dialog recipe 13

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
cards grid grid-flow-col auto-cols-[44%] gap-3 overflow-x-auto px-1 pb-5 pt-2 snap-x md:auto-cols-[calc((100%-48px)/4)] md:gap-4 xl:auto-cols-[calc((100%-80px)/6)] ${grid?'!grid-flow-row grid-cols-2 md:grid-cols-4 xl:grid-cols-6 !auto-cols-auto !overflow-visible':''}
```

### Catalog/dialog recipe 14

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
empty rounded-lg border border-dashed border-white/30 px-5 py-16 text-center [&>p]:my-5 [&>p]:text-gray-400
```

### Catalog/dialog recipe 15

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-screen-black button inline-flex items-center justify-center gap-2 rounded px-5 py-3 text-sm font-bold transition hover:-translate-y-0.5 motion-reduce:transform-none primary bg-white text-black hover:bg-gray-200
```

### Catalog/dialog recipe 16

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
detail-art relative aspect-video overflow-hidden bg-black after:absolute after:inset-0 after:bg-gradient-to-t after:from-panel-dark after:via-transparent
```

### Catalog/dialog recipe 17

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
detail-body relative z-[1] -mt-5 px-5 pb-7 md:px-8 [&>p]:leading-relaxed [&>p]:text-gray-300 [&>h2]:mb-5 [&>h2]:text-3xl [&>h2]:font-black
```

### Catalog/dialog recipe 18

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
eyebrow mb-3 text-xs font-extrabold uppercase tracking-[0.2em] text-brand-red
```

### Catalog/dialog recipe 19

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
metadata flex flex-wrap items-center gap-3 text-xs text-gray-300
```

### Catalog/dialog recipe 20

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
match font-bold text-green-400
```

### Catalog/dialog recipe 21

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
rating border border-gray-500 px-1.5 py-0.5
```

### Catalog/dialog recipe 22

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
actions my-6 flex flex-wrap gap-3
```

### Catalog/dialog recipe 23

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-screen-black button inline-flex items-center justify-center gap-2 rounded px-5 py-3 text-sm font-bold transition hover:-translate-y-0.5 motion-reduce:transform-none secondary bg-white/20 text-white hover:bg-white/30
```

### Catalog/dialog recipe 24

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
demo-label my-4 text-xs text-gray-400
```

### Catalog/dialog recipe 25

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
preview-stage relative aspect-video overflow-hidden bg-black
```

### Catalog/dialog recipe 26

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
preview-caption absolute inset-x-0 bottom-0 bg-gradient-to-t from-black/90 to-transparent px-5 pb-5 pt-16 text-lg font-bold md:text-2xl
```

### Catalog/dialog recipe 27

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
detail-body relative z-[1] -mt-5 px-5 pb-7 md:px-8 [&>p]:leading-relaxed [&>p]:text-gray-300 [&>h2]:mb-5 [&>h2]:text-3xl [&>h2]:font-black !mt-0 pt-6
```

### Catalog/dialog recipe 28

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
preview-controls my-6 flex items-center gap-3 [&>input]:min-w-0 [&>input]:flex-1 [&>input]:accent-brand-red [&>span]:whitespace-nowrap [&>span]:text-xs [&>button]:rounded [&>button]:bg-white [&>button]:px-4 [&>button]:py-2 [&>button]:text-black [&>button:hover]:bg-gray-200
```

### Catalog/dialog recipe 29

Used by the matching generated catalog or dialog elements in `js/script.js`; card/row recipes repeat for the 28-title collection. Conditional expressions select the grid variant.

```text
focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-screen-black
```
