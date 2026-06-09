# michalcifra.com — personal scientist website

Single-file personal site for **Michal Cifra, Ph.D.** — senior scientist & team leader in
bioelectrodynamics (Institute of Photonics and Electronics, Czech Academy of Sciences),
speaker, author, team leader, and process architect / vibecoder.

## Files
- `index.html` — the entire site (self-contained: inline CSS, inline SVG icons, vanilla JS). No build step, no dependencies.

## Editing social links
All social links live in **one place**: the `SOCIALS` array near the bottom of `index.html`.

- `status:"ok"` → renders as a live link.
- `status:"todo"` → renders greyed/dashed as a placeholder.

The 8 platforms match the AutoVideoPosting / OneUp publishing targets. Four are confirmed:

| Platform  | Status | Link |
|-----------|--------|------|
| LinkedIn  | ✅ ok  | linkedin.com/in/michal-cifra-5a5a5437 |
| Bluesky   | ✅ ok  | bsky.app/profile/mcer33.bsky.social |
| Facebook  | ✅ ok  | facebook.com/884975894697262 (page "Michal Cifra — scientist") |
| X         | ⚠ todo | paste handle |
| Instagram | ⚠ todo | paste handle |
| Threads   | ⚠ todo | paste handle |
| YouTube   | ⚠ todo | paste handle |
| TikTok    | ⚠ todo | paste handle |

To finish a TODO: set its `url`, update `handle`, and change `status` to `"ok"`.
Source of truth for the missing handles = the OneUp connected accounts in the AutoVideoPosting setup.

## Preview locally
Just open `index.html` in a browser, or:
```
python -m http.server 8000
```
then visit http://localhost:8000.

## Domain
Intended domain: **michalcifra.com** (available as of 2026-06). See conversation notes for registrar options.

## Versioning
Tracked on GitHub under [@mcer33](https://github.com/mcer33).
