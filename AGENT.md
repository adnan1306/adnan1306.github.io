# Agent Context — adnan1306.github.io

Handoff file for Claude or other tools continuing work on this website.

---

## What this is

A minimal Jekyll academic website for Mohammed Adnan (PhD student, Vector Institute / U of Calgary). Modelled after tomjacobs05.github.io. Deployed at https://adnan1306.github.io via GitHub Pages.

---

## How to run locally

Requires Docker. No Ruby install needed.

```bash
docker compose up -d        # start (gems install to ./vendor/bundle on first run ~1 min)
docker compose down         # stop
docker compose logs -f      # tail logs
```

Site served at http://localhost:4000 with live-reload.

If running on a remote server, tunnel to your laptop:
```bash
ssh -L 4000:localhost:4000 <user>@<server-ip> -N
# or via jump host:
ssh -J <jump-host> -L 4000:localhost:4000 <user>@<server-ip> -N
```

---

## File map

| File / Dir | Purpose |
|---|---|
| `_config.yml` | Site metadata, author info (name, email, photo, socials), nav links |
| `_layouts/default.html` | Single layout wrapping all pages — nav, content slot, footer, accordion JS |
| `assets/css/main.css` | All styling (font, layout, nav, bio, accordion, updates, sidebar, publications) |
| `index.md` | Home page — bio paragraph, research interests accordion, updates feed |
| `publications.md` | Publications page |
| `cv.md` | CV page |
| `awards.md` | Awards page |
| `_data/research.yml` | Research interest questions + answers (drives accordion on home page) |
| `_data/updates.yml` | News/updates list (date + text) |
| `_data/publications.yml` | Publications list |
| `assets/images/headshot.jpg` | Profile photo (adnan_headshot.jpg copied here) |
| `docker-compose.yml` | Docker setup — jekyll/jekyll:4.2.2, user 1000008:1000001, gems in ./vendor/bundle |
| `Gemfile` | Ruby deps — jekyll ~> 4.2, webrick, jekyll-feed, jekyll-seo-tag |
| `vendor/` | Bundler gem cache (gitignored, auto-created on first run) |

---

## Design decisions / current state

- **Font**: Crimson Pro (Google Fonts), serif, weights 300/400
- **Colour**: background `#fbfbfb`, text `#3a3a3a`, accent `#0d1b4b` (dark navy)
- **Layout**: single `.page-wrap` (max 780px centred), two-column grid on home (content + sidebar)
- **No card border**: `.page-wrap` border and border-radius removed; nav border-bottom also removed
- **Section headers** ("Research Interests", "Updates"): `21px` — doubled from original `10.5px`
- **Bio**: single paragraph (line breaks between sentences removed)
- **Accordion**: clicking a research question dims the bio and updates, expands the answer

---

## Things still TODO (as of last session)

- Bio text placeholder — user said they will replace it later
- **Fix profile photo size** — currently `width: 170px; height: auto` (very vertical); user wants it slightly more square without cropping or morphing aspect ratio. Try `object-fit: cover` with a constrained height, or crop the source image.
- Photos page (`/photos/`) — nav link exists but page may be empty
- Content in `_data/research.yml`, `_data/updates.yml`, `_data/publications.yml` may need updating

---

## Docker gotchas

- Image `jekyll/jekyll:4.2.2` only has jekyll up to 4.2.x — Gemfile uses `~> 4.2` (not 4.3)
- Container runs as host user `1000008:1000001` so it can write to the mounted project dir
- `BUNDLE_PATH=/srv/jekyll/vendor/bundle` redirects gem installs into the project dir (avoids permission errors on `/usr/gem/cache/`)
- `vendor/` and `.bundle/` are gitignored
