# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Working conventions

- **Language:** talk to the user in Italian.
- **Branch:** work directly on `main`, which is the published branch. There is no `master`. Commit and push to `main` instead of creating feature branches. Every push to `main` goes live on the site.

## What this repository is

The personal landing page of Roberto D'Isanto, published with GitHub Pages from `main` on the custom domain in `CNAME` (`robertodisanto.it`). It is a single static page plus the CV as a PDF in `cv/`. Content is Italian.

There is no build step, package manager, linter, or test suite. Whatever is committed to `main` is what gets published. Preview locally from the repo root:

```sh
python3 -m http.server 8000
```

There is no `_config.yml` and no `.nojekyll`, so GitHub Pages runs its default Jekyll pass. Paths starting with `_` are not published.

## Structure

- **Template.** `index.html` is the HTML5 UP "Identity" template, licensed CC BY 3.0. Keep the "Design: HTML5 UP" credit in the footer.
- **Sass sources vs. compiled CSS.** `assets/sass/` holds the template's Sass sources, but no Sass compiler is configured. The page loads the committed `assets/css/main.css`, which also references the background image as `../../images/bg.jpg`. Editing a `.scss` file has no effect unless you recompile `main.css` yourself.
- **CV link.** The PDF in `cv/` may already be shared by URL. Don't rename or move it unless asked.

## History and archive

On 2026-10-17 the history was replaced by a single clean commit. Everything that used to live here is in the private repo `RobertoD91/temp-da-sistemare`:

- **Full old history,** including the former tags and pull request refs: branch `storico-robertod91-github-io`.
- **Old experiments and file drops,** such as iOS OTA installs, the ESP firmware installer, privacy policies, demos, and the 360° viewer: folder `github da spostare/` on `master`, with their original paths.

Don't re-add those files to this public repo.

## Things to be careful about

- **`robots.txt` disallows all crawlers.** Leave it unless told otherwise.
- **`CNAME` controls the custom domain.** Don't edit it unless asked.
