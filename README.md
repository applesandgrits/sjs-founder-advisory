# SJS Founder Advisory

Marketing site for **SJS Founder Advisory** — Stephanie Shyu's early-stage founder
advising practice and the Founder Clarity Sprint.

One static HTML page. No build step, no dependencies, no framework. Served by
GitHub Pages from the `main` branch.

**Live:** https://applesandgrits.github.io/sjs-founder-advisory/

---

## Before it goes to a real audience

Three things are still placeholders.

### 1. Contact address

`index.html` currently points at `hello@sjscollective.com`. Search for `mailto:`
and replace it with the real address, or swap the whole `<a>` for a Calendly /
Tally link.

### 2. Photos

The page has three image slots holding grey captioned placeholders:

| Location | Class | Crop |
|----------|-------|------|
| Hero, right column | `.photo` | 3:2 |
| Above the three sessions | `.photo.wide` | 21:9 |
| About section | `.photo.portrait` | 4:5 |

To fill one: upload the JPGs into a `photos/` folder (same Add file → Upload
files flow), then in `index.html` replace the placeholder div

```html
<div class="ph"><span>Photo: NYU Entrepreneurs Festival</span></div>
```

with an image

```html
<img src="photos/festival.jpg" alt="Stephanie Shyu speaking at the NYU Entrepreneurs Festival">
```

The CSS already handles cropping and aspect ratio — no other change needed.

---

## Pointing a custom domain at it

1. Repo **Settings → Pages → Custom domain**, enter e.g. `advisory.sjscollective.com`
2. At the DNS registrar, add:

   | Type  | Name       | Value                       |
   |-------|------------|-----------------------------|
   | CNAME | `advisory` | `applesandgrits.github.io`  |

3. Tick **Enforce HTTPS** once the certificate is issued (usually minutes).
4. Then find-and-replace `https://applesandgrits.github.io/sjs-founder-advisory`
   with `https://advisory.sjscollective.com` across `index.html`, `robots.txt`
   and `sitemap.xml` — those three carry the absolute canonical and social URLs.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire site — markup plus the CSS in one `<style>` block |
| `404.html` | Not-found page, same type and palette |
| `favicon.svg` | Tab icon: two lines converging into one |
| `robots.txt`, `sitemap.xml` | Search indexing |
| `og.png` | 1200×630 link-preview card for LinkedIn, Slack, iMessage |
| `fonts.css` + `fonts/` | Self-hosted Newsreader, Archivo, IBM Plex Mono (latin subsets) |
| `.nojekyll` | Tells Pages to serve files as-is, no Jekyll processing |

Fonts are self-hosted rather than pulled from Google, so the page makes no
third-party requests at all.

## Design notes

- **Palette** — spruce ink `#14231F` on a cool paper `#EDEFEA`, ochre accent
  `#C2761A`, chartreuse highlighter `#CEDE6E`. A full dark-mode palette follows
  the visitor's OS setting.
- **Type** — Newsreader (display and the prework questions), Archivo (body and
  UI), IBM Plex Mono (labels, session numbers, rates).
- **Structure** — the session numbering is real sequence, not decoration: each
  working session depends on what the previous one settled. The prework
  worksheets are deliberately unnumbered, since founders answer them in any
  order.

Session content and pricing come from the Founder Clarity Sprint proposal.
