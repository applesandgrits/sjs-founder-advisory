# Stephanie Shyu

Personal and professional site for Stephanie Shyu. The homepage covers all five
practices. The SJS Founder Advisory page (the Founder Clarity Sprint) lives at
`/advisory/`.

Static HTML and CSS. No build step, no dependencies, no framework. Served by GitHub
Pages from the `main` branch.

**Live:** https://applesandgrits.github.io/sjs-founder-advisory/
&nbsp;·&nbsp; **Advisory:** https://applesandgrits.github.io/sjs-founder-advisory/advisory/

---

## Outstanding before it goes to a real audience

- **Contact address.** `index.html` and `advisory/index.html` both point at
  `hello@sjscollective.com`, a placeholder. Note the consulting site's domain is
  `thesjscollective.com`. Search for `mailto:` and replace it with the real address,
  or with a Calendly or Tally link.
- **Facts to confirm.** Confirm these before launch:
  - MBA status: The SJS Collective lists it as pending.
  - Which NYU school the capstone course is in, and its start term. The page says
    "Upcoming" and "New York University".
  - Yoga details. stephshyu.yoga couldn't be read while this was built, so the yoga
    section uses what the other sites say: 200-hour RYT in vinyasa and restorative,
    Three Sisters Yoga, and Insight and Dzogchen meditation. It sends visitors to
    stephshyu.yoga for the schedule.

---

## Structure

| Path | What it is |
|------|------------|
| `index.html` | Homepage: hero, the five practices, advising, authentic relating, yoga & meditation, teaching & building, writing, about, contact |
| `site.css` | Styles for the homepage |
| `advisory/index.html` | SJS Founder Advisory, the Founder Clarity Sprint (inline styles, unchanged apart from paths and a link home) |
| `advisory/og.png` | Link-preview card for the advisory page |
| `og.png` | 1200×630 link-preview card for the homepage |
| `404.html` | Not-found page. Uses absolute `/sjs-founder-advisory/` paths, which GitHub Pages needs for a 404 page |
| `photos/`, `logos/` | Shared images |
| `fonts.css` + `fonts/` | Self-hosted Newsreader, Archivo, IBM Plex Mono |
| `favicon.svg`, `robots.txt`, `sitemap.xml`, `.nojekyll` | Site plumbing |

### Where the homepage content comes from

| Section | Source |
|---------|--------|
| Startup advising | The Founder Clarity Sprint (`/advisory/`), plus the About and FAQ pages at thesjscollective.com: offerings, engagement types, who she works with, testimonials |
| Authentic relating | Her entry in the ART International certified-facilitator directory |
| Yoga & meditation | thesjscollective.com/about and the essay "Jack of All Trades, Master of Self" |
| Teaching & building | The advisory page's career history, plus the upcoming NYU adjunct course |
| Writing | The Steph Press (stephanieshyu.wordpress.com) and Medium (@sjshyu) |

To add a post, copy an `<li>` in the `#writing` section of `index.html`.

---

## Pointing a custom domain at it

1. Repo **Settings → Pages → Custom domain**: enter e.g. `stephanieshyu.com`.
2. At the DNS registrar, point the domain at GitHub Pages. For an apex domain, use
   the four `A` records in GitHub's docs. For a subdomain, use a `CNAME` to
   `applesandgrits.github.io`.
3. Tick **Enforce HTTPS** once the certificate is issued.
4. Find-and-replace `https://applesandgrits.github.io/sjs-founder-advisory` with the
   new origin across `index.html`, `advisory/index.html`, `robots.txt` and
   `sitemap.xml`. In `404.html`, replace `/sjs-founder-advisory/` with `/`.

---

## Design notes

- **Palette:** warm paper `#F7F3ED`, ink `#16130F`, rust accent `#B03A13`
  (`#8F2F0E` for text links), sand `#EAE3D7`. The yoga section switches to a
  night band (`#1F1A15`) with a lighter terracotta (`#E08A62`) to mark the shift
  from work to practice. Light theme only, by design.
- **Type:** Newsreader (display), Archivo (body), IBM Plex Mono (labels and
  numbering), Architects Daughter (the one handwritten note in the hero).
- **Numbering:** the five practices are numbered 01–05 in the hero index and
  in each section's kicker, so the index works as navigation.
