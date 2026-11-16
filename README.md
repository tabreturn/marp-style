# tabreturn Marp Theme

*Shared Marp theme (`tabreturn`) for tabreturn slide-decks -- one canonical copy, symlinked into each deck repo, with base64-embedded fonts so decks render fully offline*

---


## What's Here

| File             | Purpose                                                               |
|------------------|-----------------------------------------------------------------------|
| `marp-base.css`  | theme rules (extends gaia) -- edit this for styling                   |
| `marp-fonts.css` | `@font-face` blocks with base64-embedded fonts -- edit this for fonts |
| `title_bg.png`   | title-slide splash background, copied into each deck that uses it     |
| `demo.md`        | starter deck source                                                   |
| `package.json`   | pins `@marp-team/marp-cli`; one install here serves every consumer    |

The fonts (NeueFaktumExtended, Montserrat, Recursive) are embedded as base64 data URIs, because Marp won't load local font files. A `section` rule in `marp-base.css` also overrides gaia's web-loaded Lato, so nothing in the rendered output depends on a network connection.


## Demo

[demo.pdf](https://raw.githubusercontent.com/tabreturn/marp-style/main/demo.pdf) -- rendered from `demo.md`


