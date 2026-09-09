# SJS Founder Advisory

Marketing site for **SJS Founder Advisory** — Stephanie Shyu's early-stage founder
advising practice and the Founder Clarity Sprint.

One static HTML page. No build step, no dependencies, no framework. Served by
GitHub Pages from the `main` branch.

**Live:** https://applesandgrits.github.io/sjs-founder-advisory/

---

## Before it goes to a real audience

### Contact address

`index.html` currently points at `hello@sjscollective.com`. Search for `mailto:`
and replace it with the real address, or swap the whole `<a>` for a Calendly /
Tally link.

### Photo captions

The photos are in place, but two captions are written only from what is visible
in the frame, because the exact events were not confirmed:

- Hero — "On a panel at the NYU Entrepreneurial Institute." Taken from the
  banners behind her.
- Wide band — "In the audience at an NYU Stern event." Taken from her name badge.

If you know the actual event and date, put them in.

### Layout switcher

A floating control at the bottom right switches between three layouts: Current,
Ledger and Cards. It is a preview tool for choosing a direction, not a shipping
feature. Once a direction is picked, fold its rules into the base styles and
delete the preview block in the `<style>`, the `.lswitch` rules, the `.lswitch`
markup and the two small scripts. All four are marked with comments.

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

## Photos

| Slot | File | Delivered crop |
|------|------|----------------|
| Hero, right column | `photos/panel-nyu.jpg` | 3:2, 1400×933 |
| Above the three sessions | `photos/audience-nyu-stern.jpg` | 21:9, 1620×694 |
| About section | `photos/stephanie-shyu.jpg` | 1:1, 712×712, rendered round |

Each file is cropped to exactly the ratio its slot renders at, so `object-fit`
never has to crop further and the framing is what you see here. To swap one,
match the ratio and keep the `width`/`height` attributes on the `<img>` in sync
so the page reserves the right space while the image loads.

The about portrait is a circular studio headshot. The file is the circle's
bounding box and the CSS rounds it with `border-radius`, so a replacement should
either be another circular crop or a square one that reads well as a circle.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire site — markup plus the CSS in one `<style>` block |
| `photos/` | The three photographs, cropped and compressed for the web |
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
  `#C2761A`, chartreuse highlighter `#CEDE6E`. Light only: the page declares
  `color-scheme: light` so it renders the same whatever the visitor's OS is set
  to.
- **Type** — Newsreader (display and the prework questions), Archivo (body and
  UI), IBM Plex Mono (labels, session numbers, rates).
- **Structure** — the session numbering is real sequence, not decoration: each
  working session depends on what the previous one settled. The prework
  worksheets are deliberately unnumbered, since founders answer them in any
  order.

Session content and pricing come from the Founder Clarity Sprint proposal.
