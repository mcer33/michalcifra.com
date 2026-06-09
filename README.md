# michalcifra.com — personal scientist website

Single-file personal site for **Michal Cifra, Ph.D.** — senior scientist & team leader in
bioelectrodynamics (Institute of Photonics and Electronics, Czech Academy of Sciences),
speaker, author, team leader, and process architect / vibecoder.

## Files
- `index.html` — the entire site (self-contained: inline CSS, inline SVG icons, vanilla JS). No build step, no dependencies.
- `assets/portrait.jpg` — hero portrait (Michal speaking at the 2024 World Congress on Electroporation).

## Design
"Ultra-weak photon emission" theme — luminous photon-cyan on near-black, Instrument Serif display +
IBM Plex Mono instrument labels. Hero uses the TEDxBratislava talk *"Light of living organisms"*
(YouTube `gezEio1mdjs`) as a dimmed ambient background, with a "Watch my TEDx talk" sound modal.

## Editing social links
All social links live in **one place**: the `SOCIALS` array near the bottom of `index.html`.

- `status:"ok"` → renders as a live link.
- `status:"todo"` → renders greyed/dashed as a placeholder.

The 8 platforms match the AutoVideoPosting / OneUp publishing targets. All confirmed:

| Platform  | Status | Link |
|-----------|--------|------|
| LinkedIn  | ✅ ok  | linkedin.com/in/michal-cifra-5a5a5437 |
| Bluesky   | ✅ ok  | bsky.app/profile/mcer33.bsky.social |
| Facebook  | ✅ ok  | facebook.com/michal.cifra.scientist |
| X         | ✅ ok  | x.com/mcer33 |
| Instagram | ✅ ok  | instagram.com/michal.cifra |
| Threads   | ✅ ok  | threads.com/@michal.cifra |
| YouTube   | ✅ ok  | youtube.com/@MichalCifra |
| TikTok    | ✅ ok  | tiktok.com/@michal.cifra |

To change any link: edit its `url`/`handle` in the `SOCIALS` array. `status:"todo"` greys an entry out.

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
