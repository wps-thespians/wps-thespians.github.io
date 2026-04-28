---
name: wps-thespians
description: Work on the WPS Thespians website for wpsthespians.com in this repository. Use when Codex edits, debugs, validates, or reviews site content, theatre program pages, Jekyll posts, assets, redirects, Minimal Mistakes layouts/includes, navigation, homepage feature rows, GitHub Pages deployment, or any repo-specific website task for WPS Thespians.
---

# WPS Thespians

Use this skill with `$jekyll`. This site is a GitHub Pages Jekyll site for the WPS Thespians theatre program, using the Minimal Mistakes remote theme with a few local overrides.

## Site Map

- Core configuration: `_config.yml`, `Gemfile`, and `.github/workflows/jekyll.yml`.
- Content: `index.md`, top-level pages such as `tickets.md`, `_pages`, and `_posts`.
- Theme overrides: `_layouts`, `_includes`, `_sass`, and `assets`.
- Site data: `_data/navigation.yml`.
- Generated or local artifacts: `_site`, `.codex`, `.playwright`, `.playwright-cli`, and `test-results`.

## Conventions

- Treat `_site` and browser/test output directories as generated artifacts. Do not edit them as source.
- Preserve the GitHub Pages setup: `github-pages` gem, `remote_theme: mmistakes/minimal-mistakes`, repository `wps-thespians/wps-thespians.github.io`, and production URL `https://wpsthespians.com`.
- Keep `_pages` pages under `_pages` when they are normal site pages; `_config.yml` explicitly includes that folder.
- Use top-level Markdown pages for simple root-level routes or redirects when the repo already does so, such as `tickets.md`.
- Update `_data/navigation.yml` for main navigation changes.
- Keep homepage promotional sections in `index.md` front matter and render them with Minimal Mistakes `feature_row` includes.
- Preserve the custom `splash` layout and local `page__hero.html` behavior; the homepage hero headline is driven by `page.fname` when present.
- Store site media under `assets` or `assets/images`; do not ignore likely real site content images.

## Editing Guidance

- Keep the site voice practical and event-focused for students, families, and theatre program supporters.
- When adding posts, use Jekyll post filenames like `YYYY-MM-DD-title.md` and front matter consistent with existing posts.
- When adding event calls to action, prefer existing button classes such as `btn--primary` and existing Minimal Mistakes patterns.
- Check for duplicated front matter keys before editing `index.md`; repeated keys can make earlier values ineffective.
- For redirects, preserve the existing `layout: none` plus `redirect_to` style unless changing the redirect system intentionally.
- Avoid adding Jekyll plugins or build steps that could break GitHub Pages deployment unless explicitly requested.

## Validation

- Use `bundle exec jekyll build` for local validation when dependencies are available.
- The deployment workflow builds with Ruby 3.1 and `JEKYLL_ENV=production`, and deploys on GitHub release or manual workflow dispatch.
- For visual changes, inspect the generated site in a browser after building or serving.
- If validation is skipped, state why and name the command that should be run.
