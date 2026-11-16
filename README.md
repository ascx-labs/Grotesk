<div align="center">

# GROTESK

*A geometric stencil display font with a little bite.*

![Python](https://img.shields.io/badge/Python-1E202B?style=for-the-badge&logo=python&logoColor=3776AB)

</div>

## Overview

Hangry Grotesk is a custom display typeface for bold headlines, identities, and
short expressive text. It is built from the glyph outlines in the project SVG
and ships as a UFO source, a regular desktop TTF font, and WOFF/WOFF2 web fonts
conforming to the [Google Fonts Onboarding Guide](https://googlefonts.github.io/gf-guide/onboarding.html).

## Features

- **Distinctive stencil lettering** — Draw attention with geometric, cut-through forms.
- **Google Fonts Latin Core coverage** — Includes all 319 codepoints in `GF_Latin_Core` (A–Z, a–z, 0–9, extended Latin diacritics, punctuation, currency, and math symbols).
- **Five font families** — Grotesk, Grotesk Diamond, Grotesk Dotted, Grotesk Pixel, and Grotesk Serif.
- **Desktop, web, and UFO formats** — Outputs `sources/Grotesk.ufo`, `fonts/Grotesk/ttf/Grotesk-Regular.ttf`, `fonts/Grotesk/webfonts/Grotesk-Regular.woff2`, and `dist/` bundles.
- **Interactive specimen** — Preview the typeface, inspect individual glyphs, and adjust a sample.
- **OFL 1.1 licensed** — Use and distribute the font under the terms in [OFL.txt](OFL.txt).

## Preview

Build the project, then open [dist/preview.html](dist/preview.html). Click a glyph
to add it to the editable sample, adjust size and spacing, or copy the CSS declaration.

## Tech stack

- **Build runtime:** Python 3
- **Font compilation:** `fontTools`, `ufoLib2`, `ufo2ft`, `fontmake`
- **Quality assurance:** `fontbakery` (`check-googlefonts` profile)
- **Web delivery:** CSS `@font-face`, WOFF2 and WOFF

## Getting started

### Prerequisites

- Python 3.10 or newer

### Build the font files

```sh
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/python3 src/build_font.py
```

The build writes:
- `sources/Grotesk.ufo` and family UFO sources
- `fonts/` (OTF, TTF, variable, WOFF, and WOFF2 files for all five families)
- `dist/` (font files, family CSS files, HTML specimen, and family ZIP archives)

## Use from npm

Install the package:

```sh
npm install @ascx/fonts
```

Import one or more family stylesheets:

```js
import "@ascx/fonts/grotesk";
import "@ascx/fonts/groteskdiamond";
import "@ascx/fonts/groteskdotted";
import "@ascx/fonts/groteskpixel";
import "@ascx/fonts/groteskserif";
```

Then use the corresponding CSS family name:

```css
body {
  font-family: "Grotesk", sans-serif;
}

.diamond {
  font-family: "Grotesk Diamond", sans-serif;
}
```

## Use from downloaded files

Copy `dist/grotesk.css` and the adjacent `dist/fonts/` directory into
your site, then include the stylesheet:

```html
<link rel="stylesheet" href="/fonts/grotesk.css">
```

```css
body {
  font-family: "Grotesk", sans-serif;
}
```

## License

Copyright 2026 The Hangry Grotesk Project Authors (https://github.com/ascx-studio/HangryGrotesk).
Licensed under the [SIL Open Font License 1.1](OFL.txt).

## Publishing

The npm package is published automatically when a matching version tag is
pushed. Update `package.json`, create the tag, and push it:

```sh
git tag v0.2.0
git push origin v0.2.0
```

The `v*` tag must match the package version exactly. Configure
`@ascx/fonts` on npm to trust the `Publish package to npm` GitHub Actions
workflow before the first release.
