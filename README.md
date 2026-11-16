# tabreturn Marp Theme

*Shared Marp theme (`tabreturn`) for tabreturn slide-decks -- one canonical copy, symlinked into each deck repo, with base64-embedded fonts so decks render fully offline*

---


## What's Here

| File              | Purpose                                                            |
|-------------------|--------------------------------------------------------------------|
| `marp-base.css`   | theme rules (extends gaia) -- edit this for styling                |
| `marp-fonts.css`  | `@font-face` blocks with base64-embedded fonts -- edit this for fonts |
| `title_bg.png`    | title-slide splash background, copied into each deck that uses it  |
| `template.md`     | starter deck source                                                |
| `package.json`    | pins `@marp-team/marp-cli`; one install here serves every consumer |

The fonts (NeueFaktumExtended, Montserrat, Recursive) are embedded as base64 data URIs, because Marp won't load local font files. A `section` rule in `marp-base.css` also overrides gaia's web-loaded Lato, so nothing in the rendered output depends on a network connection.


## Usage

Deck repos symlink this directory as `style_marp` (or `marp_style`):

```bash
ln -s ../marp-style style_marp
```

On machines where that isn't practical (no side-by-side clone, Windows symlink quirks), clone this repo into the deck repo under that name instead:

```bash
git clone https://github.com/tabreturn/marp-style style_marp
```

Install Marp once, here in the theme repo:

```bash
cd marp-style && npm install
```

Then render from any deck repo with its `./render` script -- live preview (watch + presenter view):

```bash
./render
```

Export PDF:

```bash
./render --pdf
```


## Replacing a Font

1. Place the `.woff2` file in this directory
2. Encode it: `base64 -w0 font.woff2`
3. Replace the `src: url(...)` value in `marp-fonts.css` with `url(data:font/woff2;base64,<base64-here>)`


## Consumers

- [writethedocs-torrenzo](https://github.com/tabreturn/writethedocs-torrenzo) -- `style_marp`
- [cc-fest-noc-py5](https://github.com/tabreturn/cc-fest-noc-py5) -- `marp_style`

