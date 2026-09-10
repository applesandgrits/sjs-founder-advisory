# SJS Founder Advisory

Marketing site for **SJS Founder Advisory** — Stephanie Shyu's early-stage founder
advising practice and the Founder Clarity Sprint.

One static HTML page. No build step, no dependencies, no framework. Served by
GitHub Pages from the `main` branch.

**Live:** https://applesandgrits.github.io/sjs-founder-advisory/

---

## Outstanding before it goes to a real audience

### Contact address

`index.html` points at `hello@sjscollective.com`. Search for `mailto:` and replace
it with the real address, or swap the whole `<a>` for a Calendly / Tally link.

---

## Pointing a custom domain at it

1. Repo **Settings → Pages → Custom domain**, enter e.g. `advisory.sjscollective.com`
2. At the DNS registrar, add:

   | Type  | Name       | Value                       |
   |-------|------------|-----------------------------|
   | CNAME | `advisory` | `applesandgrits.github.io`  |

3. Tick **Enforce HTTPS** once the certificate is issued (usually minutes).
4. Find-and-replace `https://applesandgrits.github.io/sjs-founder-advisory` with
   the new origin across `index.html`, `robots.txt` and `sitemap.xml` — those carry
   the absolute canonical and social-preview URLs.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire site — markup with inline styles |
| `404.html` | Not-found page |
| `photos/` | Panel, auditorium and portrait shots used in the hero, sessions band and About |
| `logos/` | NYU Stern Berkley Center, AdmitSee, Pioneer Fund, The SJS Collective |
| `og.png` | 1200×630 link-preview card for LinkedIn, Slack, iMessage |
| `fonts.css` + `fonts/` | Self-hosted Newsreader, Archivo, IBM Plex Mono (latin subsets) |
| `favicon.svg` | Tab icon: two lines converging into one |
| `robots.txt`, `sitemap.xml` | Search indexing |
| `.nojekyll` | Tells Pages to serve files as-is, no Jekyll processing |

The three main faces are self-hosted. Architects Daughter — used for the
handwritten annotation accents — is the one font still loaded from Google Fonts,
and so the page's only third-party request.

## Design notes

- **Palette** — warm paper `#F7F3ED`, near-black ink `#16130F`, rust accent
  `#B03A13` with `#8F2F0E` for text-safe links, sand surfaces `#EAE3D7` / `#EDE6DB`.
  Single light theme by design (`color-scheme: light`); there is no dark palette.
- **Type** — Newsreader (display), Archivo (body and UI), IBM Plex Mono (labels,
  session numbers, rates), Architects Daughter (annotations).
- **Structure** — the session numbering is real sequence, not decoration: each
  working session depends on what the previous one settled. The prework worksheets
  are deliberately unnumbered, since founders answer them in any order.

Session content and pricing come from the Founder Clarity Sprint proposal.
