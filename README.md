# azzu-bear.github.io

Personal site. Live at <https://azzu-bear.github.io/>.

Hand written HTML and CSS, no build step and no dependencies. GitHub Pages
serves the repo root directly, so editing `index.html` and pushing to `main` is
the entire deploy process.

```
index.html    the whole site, styles inline in <head>
404.html      not-found page, served by Pages automatically
favicon.svg   tab icon
```

## Editing

Open `index.html` in a browser to preview. Nothing to install.

Content sections are marked by `<section id="...">`: `about`, `work`,
`projects`, `toolbox`, `contact`. The nav links to those ids, so adding a
section means adding both the `<section>` and one `<li>` in the nav.

Projects are `.card` blocks inside `.grid`. Copy an existing card to add one.
Cards with a repo use `<h3><a href="...">`; cards without one use a plain
`<h3>`, which drops the arrow automatically.

## Palette

Matches the animated banner in the profile README repo, so both read as the
same person.

```
#0d1117  background        #3fb950  green, accents and prompts
#161b22  panels            #d29922  soil amber, secondary accent
#30363d  borders           #58a6ff  links
#c9d1d9  body text         #8b949e  dimmed text
```
