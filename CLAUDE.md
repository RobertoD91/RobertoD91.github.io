# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Working conventions

- **Language:** talk to the user in Italian.
- **Branch:** work directly on `main`, which is the published branch. There is no `master`. Commit and push to `main` instead of creating feature branches. Every push to `main` goes live on the site.

## What this repository is

The personal landing page of Roberto D'Isanto, published with GitHub Pages from `main` on the custom domain in `CNAME` (`robertodisanto.it`). It is a single static page plus the crawler files for the whole domain. Content is Italian.

There is no build step, package manager, linter, or test suite. Whatever is committed to `main` is what gets published. Preview locally from the repo root:

```sh
python3 -m http.server 8000
```

`.nojekyll` turns off Jekyll, so every file is served as is, including dot folders such as `.well-known/`. Don't remove it.

## Structure

- **Template.** `index.html` is the HTML5 UP "Identity" template, licensed CC BY 3.0. Keep the "Design: HTML5 UP" credit in the footer. The `$ whoami --verbose` button links to the full CV.
- **Sass sources vs. compiled CSS.** `assets/sass/` holds the template's Sass sources, but no Sass compiler is configured. The page loads the committed `assets/css/main.css`, which also references the background image as `../../images/bg.jpg`. Small page-specific styles live in a `<style>` block in `index.html`.
- **Favicon and social preview.** `favicon.svg` is the source icon. `favicon.ico` and `apple-touch-icon.png` were rendered from it, so regenerate them if it changes. The Open Graph tags in `index.html` use `images/avatar.jpg` as the preview image.
- **Avatar.** `images/avatar.jpg` is the 600×600 photo published by the CV site, plus an EXIF block that belongs to the hunt below. If the photo changes, insert that EXIF block again without re-encoding the image.
- **Full CV lives elsewhere.** `/curriculum-vitae/` is the GitHub Pages project site of the separate repo `RobertoD91/curriculum-vitae`. Every repo of this account with Pages enabled is served under `robertodisanto.it/<repo>/`.
- **Old CV PDF.** The PDF in `cv/` is a copy of the phone-less `/curriculum-vitae/cv-it.pdf`. It stays because its URL may already be shared: keep the file name, and refresh the copy when the CV changes.

## Facts about Roberto

Facts come from the CV, whose single source is `cv.yml` in the private repo `RobertoD91/curriculum-vitae`. That repo's `CLAUDE.md` lists the content rules agreed with the owner, and they apply here too. Take facts only from what the published CV site shows, never from the private repo's files, which hold confidential data.

- **Never public:** the phone number, address, date of birth and tax code. They must not appear on this site or in any PDF it serves.
- **Keep in sync:** the meta description, the `llms.txt` summary and the profile links follow the CV site.

## Crawler and AI files

Crawlers only read `robots.txt`, `llms.txt`, `humans.txt` and `.well-known/` at the domain root, so this repo holds them for the whole domain, `/curriculum-vitae/` included.

- **`robots.txt`** is open to every crawler, AI bots included. Keep a single `User-agent: *` group: a bot with its own group ignores the `*` rules.
- **`sitemap.xml`** lists the home page and the CV page.
- **`llms.txt`** is a short summary that links to the detailed one under `/curriculum-vitae/`.
- **`.well-known/security.txt`** follows RFC 9116. Its `Expires` date must be renewed before it passes.
- **`SECURITY.md`** explains how to report issues and warns about the old iOS builds in the archived history.

## Cyber HackAdemy hunt

`README.md` invites Cyber HackAdemy students to find three hidden pieces and use them to decrypt a message. Some files deliberately contain those pieces, and the git history does too. Don't "clean up" odd comments in `robots.txt`, image metadata, or old commits, and don't rewrite history. The solution is in the private repo `RobertoD91/temp-da-sistemare`.

## History and archive

On 2026-10-17 the history was restarted from a single clean commit. Everything that used to live here is in the private repo `RobertoD91/temp-da-sistemare`:

- **Full old history,** including the former tags and pull request refs: branch `storico-robertod91-github-io`.
- **Old experiments and file drops,** such as iOS OTA installs, the ESP firmware installer, privacy policies, demos, and the 360° viewer: folder `github da spostare/` on `master`, with their original paths.

Don't re-add those files to this public repo.

## Things to be careful about

- **`CNAME` controls the custom domain.** Don't edit it unless asked.
