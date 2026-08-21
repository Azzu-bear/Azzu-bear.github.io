# azzu-bear.github.io

Personal site. Live at <https://azzu-bear.github.io/>.

Hand written HTML and CSS, no build step, no dependencies, no JavaScript.
GitHub Pages serves the repo root, so editing `index.html` and pushing to
`main` is the whole deploy process.

```
index.html    the entire site, styles inline in <head>
404.html      not-found page, served by Pages automatically
favicon.svg   tab icon
assets/       portrait, project tile art, social card
```

## Design

An engineering document rather than a product page: hairline rules instead of
cards, a spec table instead of stat tiles, numbered figures, and monospace
reserved for metadata (dates, stacks, labels) while headings stay in sans.

Projects are a horizontal **contact sheet** at `§1`. Each frame carries a
sprocket strip, a 290x150 figure, and the details below. Seven of the figures
are inline SVG drawings of the actual mechanism (floorplan, sleep list, VGA
beam, hop chain, locked BST, `select()` fan-out, ESP32 bus). The eighth is a
real photograph of the Sluggers chassis.

## Editing

Open `index.html` in a browser. Nothing to install.

Sections are `<section id="...">`: `projects`, `log`, `notes`, `stack`,
`contact`. The nav links to those ids, so a new section needs both the
`<section>` and an `<li>`.

To add a project, copy a `.frame-card` block inside `.sheet`. Cards with a repo
use `<a class="frame-card" href="...">`; cards without one use
`<div class="frame-card">`, which drops the arrow. Tile art lives in the
`.field` div: either an inline `<svg viewBox="0 0 290 150">` (add `fig-bg` to
the class for the graph-paper ground) or a `<picture>` for a photo.

## Palette

```
#0e0f10  background       #d29922  amber, the drawing ink and primary accent
#141517  raised panels    #3fb950  green, links and live elements
#26282b  rules            #e9e8e5  headings
#85857f  dimmed text      #b0b0ac  body
```

Amber carries the accent work; green is reserved for links and anything
depicting motion or a live state, so it stays meaningful.
