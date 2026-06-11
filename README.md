# michalcifra.com — personal scientist website

Single-file personal site for **Michal Cifra, Ph.D.** — senior scientist & team leader in
bioelectrodynamics (Institute of Photonics and Electronics, Czech Academy of Sciences),
speaker, author, team leader, and process architect / vibecoder.

**Live:** https://michalcifra.com · **Repo:** https://github.com/mcer33/michalcifra.com

## Files
- `index.html` — the entire site (self-contained: inline CSS, inline SVG icons, vanilla JS). No build step, no dependencies.
- `assets/portrait.jpg` — hero portrait (Michal speaking at the 2024 World Congress on Electroporation).
- `CNAME` — binds the custom domain `michalcifra.com`. **Do not delete** (it's what makes the domain work).

## Deploy / add a page — works from ANY machine
The site is a plain **GitHub Pages** static repo. The GitHub repo is the single source of truth — clone it
anywhere, you don't need this exact folder. (On the NTB it lives at `C:\MyCloud\OneDrive - UFE\15 mc web\`,
which is OneDrive-synced — that's just one local checkout.)

```bash
git clone https://github.com/mcer33/michalcifra.com   # if not already cloned on this machine
cd michalcifra.com
# add or edit any file, e.g. cv.html  or  talks/index.html
git add -A && git commit -m "…" && git push origin master
```

GitHub Pages auto-builds in ~1 min. **URL mapping:** `foo.html` → `https://michalcifra.com/foo.html`;
`foo/index.html` → `https://michalcifra.com/foo/`; `index.html` is the homepage.

Verify the deploy:
```bash
gh api repos/mcer33/michalcifra.com/pages/builds/latest --jq '.status'   # → "built"
curl -sI https://michalcifra.com/<path>                                   # 200 OK
```
Pages sends `Cache-Control: max-age=600`, so a browser may show the old copy for ≤10 min — hard-refresh or add `?v=N`.

**Constraints:** static only (no PHP/DB/server code — that's why the Biophotoniq site stays on Websupport).
Any machine pushing needs git creds / `gh` auth for the `mcer33` GitHub account.

**Relaying a page built by an ecosystem agent** (one command, any authed machine):
```bash
ecosystem/infra/deploy-to-web.sh <src-rel-to-ecosystem-root> <dest-rel-to-site-root> [commit msg]
# e.g.  …/deploy-to-web.sh agents/social-analysis/debiasify-agent/site/avcrdebiasify-tests/index.html \
#                          avcrdebiasify-tests/index.html "Add report (noindex)"
```
It pulls ecosystem, copies the file into a michalcifra.com checkout, commits+pushes to `master`, waits for the
Pages build, and curls the live URL. Set `MICHALCIFRA_WEB` to reuse an existing site checkout, else it clones to
`~/.cache/michalcifra.com`. (Exists because ufeclaude's deploy key is ecosystem-only and can't push here.)

## Editing content (all data-driven, one place each)
- **Social links** — the `SOCIALS` array near the bottom of `index.html` (8 platforms; `status:"ok"`/`"todo"`).
  Also a "Profiles & writing" row: Substack, Google Scholar, ORCID, ResearchGate, Institute page.
- **Talks** — the `TALKS` array near the bottom of `index.html`. Each entry is either a YouTube talk
  `{ id, title, src }` or a non-YouTube one `{ frame, thumb, title, src }` (e.g. SlidesLive embed).
  Cards open in an in-page modal via `openFrame(src)`. Keep them sorted newest→oldest; `src` carries the
  year and, for on-site talks, the country (online talks → organizer only).

| Platform  | Link |
|-----------|------|
| LinkedIn  | linkedin.com/in/michal-cifra-5a5a5437 |
| Bluesky   | bsky.app/profile/mcer33.bsky.social |
| Facebook  | facebook.com/michal.cifra.scientist |
| X         | x.com/mcer33 |
| Instagram | instagram.com/michal.cifra |
| Threads   | threads.com/@michal.cifra |
| YouTube   | youtube.com/@MichalCifra |
| TikTok    | tiktok.com/@michal.cifra |
| Substack  | michalcifra.substack.com |

## Design
"Ultra-weak photon emission" theme — luminous photon-cyan on near-black, Instrument Serif display +
IBM Plex Mono instrument labels. Hero uses the TEDxBratislava *"Bio Light"* talk (YouTube `gezEio1mdjs`)
as a dimmed ambient background; the "Watch my talks" button jumps to the Talks & media gallery.

## Domain & hosting
`michalcifra.com` registered via **Cloudflare Registrar** (personal account under GitHub-SSO `mcer33@gmail.com`).
DNS = CNAME flattening, DNS-only: `@` and `www` → `mcer33.github.io`. GitHub Pages serves it with an
auto-provisioned Let's Encrypt cert; Enforce HTTPS is on. To put Cloudflare's CDN in front later, flip the
DNS records to proxied (orange) + SSL/TLS = Full.
