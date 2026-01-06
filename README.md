Obsidian Protocol — docs scaffold

This folder is a scaffold for a separate repository you can create at e.g. `TechMechanik/obsidianprotocol-docs`.

Contents:
- `mkdocs.yml` — Material theme, site metadata
- `docs/` — markdown pages (index, setup, rules)
- `requirements.txt` — Python deps
- `.github/workflows/deploy-pages.yml` — builds site and uses `wrangler pages publish` to publish to Cloudflare Pages
- `CNAME` — `docs.obsidianprotocol.xyz`

Cloudflare Pages setup notes:
- Create a Pages project and *connect* it to this repository (or use GitHub Actions+wrangler as configured).
- Add repository secrets:
  - `CF_API_TOKEN` — API token with Pages/publish permissions
  - `CF_PROJECT_NAME` — Cloudflare Pages project name (used by the workflow)
- If your DNS is managed by Cloudflare, adding the custom domain is straightforward; otherwise add the required CNAME records as instructed by Pages.

To preview docs locally:
- python -m pip install -r requirements.txt
- mkdocs serve

When you are ready, push this folder into its own repo and connect it to Cloudflare Pages.
