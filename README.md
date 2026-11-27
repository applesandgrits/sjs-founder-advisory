# Steph Shyu

Personal site for Steph Shyu (Stephanie Shyu): one home page with two halves.

| Path | Page | Theme |
|------|------|-------|
| `/` | Home: who Steph is, both halves, ventures, selected writing | Ink |
| `/advisory/` | SJS Founder Advisory and the Founder Clarity Sprint | Plum |
| `/still-life/` | Still Life: Authentic Relating, writing, meditation (2027) | Moss |
| `/about/` | Story and career path | Ink |

Static HTML. No build step, no dependencies, no framework. Served by GitHub Pages
from the `main` branch.

**Live (until the domain moves):** https://applesandgrits.github.io/sjs-founder-advisory/

All internal links are relative, so the site works both under the GitHub Pages
project path and at the root of a custom domain.

---

## Before it goes to a real audience

1. **Contact address.** Every page uses `hello@sjscollective.com`, which is still a
   placeholder. Search for `sjscollective.com` and replace it, or swap the
   buttons for a Calendly / Tally link.
2. **Draft copy to review.** These lines were written for Steph and need her
   sign-off:
   - `about/`: the second paragraph ("the companies that struggled rarely failed
     on the product…"), and the photo note "usually outside, if I can be".
   - `still-life/`: the hero line, the Authentic Relating description, the
     meditation heading, and the one-line essay summaries.
   - `index.html`: the contact line "I read every note."
3. **Medium.** Featured essays all come from The Steph Press on WordPress.
   Medium posts were not reviewed.

---

## Moving to stephanieshyu.com

`stephanieshyu.com` may currently point at the WordPress blog (some posts link to
`stephanieshyu.com/2021/...`). Check before switching, or those essay links break.
If it does, map the blog to a subdomain such as `writing.stephanieshyu.com` in
WordPress first, then:

1. Repo **Settings → Pages → Custom domain**: enter `stephanieshyu.com`.
2. At the DNS registrar, point the apex at GitHub Pages (four `A` records:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`)
   and add `CNAME www → applesandgrits.github.io`.
3. Tick **Enforce HTTPS** once the certificate is issued.
4. Find-and-replace `https://applesandgrits.github.io/sjs-founder-advisory` with
   `https://stephanieshyu.com` in every `.html` file, `robots.txt` and
   `sitemap.xml` (canonical URLs, social previews, structured data).
5. Redirect `sjscollective.com` and `thesjscollective.com` to
   `https://stephanieshyu.com/` at their registrar, and `stephshyu.yoga` to
   `https://stephanieshyu.com/still-life/` until it lapses.
6. Update the ART facilitator directory listing to link to stephanieshyu.com.

---

## Files

| File | Purpose |
|------|---------|
| `index.html`, `advisory/`, `still-life/`, `about/` | The four pages |
| `assets/site.css` | Shared design system: tokens, three themes, components |
| `fonts.css` + `fonts/` | Self-hosted Newsreader, Archivo, IBM Plex Mono, La Belle Aurore |
| `photos/` | Portraits and event photos (owned by Steph) |
| `logos/` | NYU Stern Berkley Center, AdmitSee, Pioneer Fund, The SJS Collective |
| `og-home.png`, `og.png`, `og-still-life.png` | 1200×630 link previews for home, Advisory, Still Life |
| `favicon.svg` | Tab icon |
| `404.html` | Not-found page; sets its own base so it works at any depth |
| `robots.txt`, `sitemap.xml` | Search indexing |
| `.nojekyll` | Tells Pages to serve files as-is |

The advisory page still carries its original inline styles, recoloured to plum.
It loads `assets/site.css` only for the slim family bar at the top. Moving its
markup onto the shared classes is a good follow-up.

## Design system

- **Base (every page):** paper `#F7F3ED`, ink `#16130F`, rule `#E2DACE`, sand `#EDE6DB`.
- **Advisory:** plum `#74325C`, text-safe `#5F2849`, tint `#EEDFE7`. Precise, upright
  Newsreader, 4px corners.
- **Still Life:** moss `#4B5B34`, text-safe `#3C4A2A`, tint `#E3E6D6`, paper
  `#F5F3EA`. Italic Newsreader, round pills, more space.
- **Home and About:** ink only, so neither half dominates.
- **Type:** Newsreader (display), Archivo (body), IBM Plex Mono (labels and facts),
  La Belle Aurore (one handwritten margin note per screen).
- **Photos:** natural light, subject to one side, no text over faces. The studio
  portrait stays on the Advisory side.
- **Naming:** "Steph Shyu" everywhere visible; "Stephanie Shyu" in page titles and
  structured data so search connects the two.

The brand sheet with the full rationale is a separate published page, not part
of this repo.
