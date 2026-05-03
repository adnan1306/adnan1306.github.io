# Mohammed Adnan — Academic Website

A minimal Jekyll academic website, inspired from [tomjacobs05.github.io](https://tomjacobs05.github.io/).

## Local Development (Docker)

Requires [Docker](https://docs.docker.com/get-docker/) to be installed. No Ruby setup needed.

### Start the server

```bash
docker compose up -d
```

First run installs all gems into `vendor/bundle` (~1 min). Subsequent starts are instant.
The site is served at **http://localhost:4000** with live-reload enabled.

### Stop the server

```bash
docker compose down
```

### View logs

```bash
docker compose logs -f
```

### Access from a remote machine via SSH tunnel

If the server is running on a remote machine, forward port 4000 to your laptop:

```bash
# Direct SSH access
ssh -L 4000:localhost:4000 <user>@<server-ip> -N

# Via a jump/bastion host
ssh -J <jump-host> -L 4000:localhost:4000 <user>@<server-ip> -N
```

Then open **http://localhost:4000** in your browser.

## Deploy to GitHub Pages

1. Create a repo named `adnan1306.github.io` on GitHub
2. Push this folder to the `main` branch
3. Go to Settings → Pages → Source: `main` branch → Save

Your site will be live at `https://adnan1306.github.io` within a minute.

## Customising Content

| What | Where |
|------|-------|
| Your name, email, photo path, nav links | `_config.yml` |
| Bio paragraphs | `index.md` |
| Updates list | `_data/updates.yml` |
| Publications | `_data/publications.yml` |
| CV text | `cv.md` |
| Awards | `awards.md` |
| Styling | `assets/css/main.css` |

## Adding Your Photo

Drop your headshot into `assets/images/headshot.png` (or update the path in `_config.yml`).
