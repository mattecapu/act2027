# ACT 2027

Website for **ACT 2027**, the 10th International Conference on Applied Category Theory, hosted by Gioele Zardini's group at MIT (Cambridge, Massachusetts, USA).

Built with Jekyll and hosted on GitHub Pages. Dates and most other details are still **TBD**.

## Local preview with Docker

Install and start [Docker Desktop](https://www.docker.com/products/docker-desktop/) (using Linux containers), or Docker Engine with the Compose plugin on Linux. No local Ruby installation is needed.

From this repository's root, run:

```sh
docker compose up --build
```

Open **http://localhost:4000**. Edit files in your usual editor; Jekyll rebuilds and LiveReload refreshes the browser. Restart with `docker compose restart` after changing `_config.yml`. Stop with Ctrl+C, then `docker compose down` to remove the container.

Without Docker: `bundle install`, then `bundle exec jekyll serve`.

## Editing content

- **Conference facts** (location, dates, contact email): `conference:` in `_config.yml`.
- **Important dates:** `_data/dates.yml`. Entries with `cfp: true` also appear on the call for papers.
- **Navigation bar:** `_data/navigation.yml`. Items with `children` become dropdowns.
- **Pages:** home (`_layouts/home.html`), `programme.html`, `papers.html`, `invited.html`, `industry.html`, `cfp.html`, `local.html`. All except the home page use `_layouts/page.html`.
- **TBD markers:** write `<span class="tbd">TBD</span>` for anything not yet decided.

## Deployment

`.github/workflows/pages.yml` builds and deploys on every push to `main`. It passes the right `baseurl` for GitHub Pages automatically. Set `url` in `_config.yml` once the final address is known.
