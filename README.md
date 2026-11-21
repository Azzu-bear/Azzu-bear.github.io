# azzu-bear.github.io

Personal site. Live at <https://azammohamed.com/>.

Hand written HTML and CSS with one small inline script. No build step and no
packages. GitHub Pages serves the repo root, so editing `index.html` and
pushing to `main` is the whole deploy process.

```
index.html    the entire site, styles and script inline
404.html      not-found page, served by Pages automatically
favicon.svg   tab icon
assets/       portrait, project photo, resume thumbnail, social card
```

## Design

Modeled on apple.com: a translucent blurred nav, one large centered headline
per section, pill buttons, generous whitespace, and a single blue accent.
It follows the system light or dark setting.

Figures sit on dark tiles in both themes, the way product shots do. The hero
tile is the ENTS data path with a packet travelling the hops. Projects are a
single shelf that pages sideways, three across with a slice of the next card
showing, edge arrows, and a "1–3 of 9" counter. Every card stays at full
brightness so the slice reads as more to see, not as disabled. Eight of the nine tiles are inline SVG
drawings of the actual mechanism and the ninth is a photograph of the Sluggers
chassis.

## Motion

Motion is kept quick so a fast scroll never lands on a blank section.

- `.reveal` fades an element in over 0.4s, starting just before it enters the
  viewport. Stagger siblings with `style="--d:80ms"` (scaled down in CSS).
- `.pop` is the slightly larger version used on the hero tile.
- Headlines are split into words by script and arrive in sequence.
- The nav highlights the section in view and carries a scroll progress line.
- Hero: drifting aurora, a colour ring on the portrait, a metal sheen on the
  tagline (`.metal`). `.grad` is the moving gradient headline.
- Cards and panels have a cursor spotlight; project cards tilt toward it.
- Two scroll-linked pieces (the stage growing into place and the resume page
  swinging flat) use CSS `animation-timeline` inside `@supports`.

All of it is switched off under `prefers-reduced-motion`, and without
JavaScript every element is simply visible and the shelf scrolls natively.

## Editing

Preview locally with any static server, for example:

```
python -m http.server 8787
```

Sections are `<section id="...">`: `work`, `projects`, `approach`, `stack`,
`resume`, `contact`. The nav links to those ids, so a new section needs both
the `<section>` and an `<li>`. Give the `<li>` `class="opt"` to hide it at
phone width, where only Projects, Resume and Contact are shown.

To add a project, copy a `.card` block inside `#rail`; the first three are
the ones seen without paging, so order matters. Cards with a link use `<a class="card" href="...">`;
cards without one use `<div class="card">` and leave the right side of the
footer empty. Tile art goes in the `.tile` div: an inline
`<svg viewBox="0 0 290 150">` or a `<picture>`. The counter reads the card
count itself; if the total changes, update the section headline.

## Palette

```
light                          dark
#fbfbfd  background            #000000
#f5f5f7  panels                #1c1c1e
#1d1d1f  headings              #f5f5f7
#424245  body                  #d6d6d8
#6e6e73  dimmed                #98989d
#d2d2d7  rules                 #2c2c2e
#0071e3  accent                #2997ff
```

Inside the dark figure tiles: `#0a84ff` is the drawing ink and `#30d158` is
reserved for anything depicting motion or a live state.

Type is the system SF Pro stack on Apple devices, with Inter (Google Fonts)
as the fallback everywhere else.
