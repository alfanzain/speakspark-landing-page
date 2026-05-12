# Repository Guidelines

## Project Structure & Module Organization

This repository contains a static landing page for SpeakSpark. There is no build system, package manager, or app framework.

- `index.html` is the canonical production page.
- `bkindex.html`, `bk2index.html`, and `bk3index.html` are backup or alternate page versions. Do not update them unless the task explicitly asks for variant work.
- `images/` contains screenshots, founder photo, and logo.
- `PRODUCT.md`, `BACKSTORY.md`, `HOW_TO_USE.md`, `NOTES.md`, and `CLAUDE.md` provide product and implementation context.

## Build, Test, and Development Commands

No install step is required. Dependencies load from CDNs at runtime: Tailwind CSS, Alpine.js, and Google Fonts.

- Open locally: `open index.html`
- Serve locally if browser security or previews require HTTP: `python3 -m http.server 8000`
- Check tracked changes: `git status`

Before publishing, preview `index.html` on mobile and desktop widths and verify external links, WhatsApp/payment CTAs, social preview metadata, and image paths.

## Coding Style & Naming Conventions

Keep the project simple and inline with the existing file:

- Use 2-space indentation for HTML, CSS, and JavaScript.
- Prefer Tailwind utility classes for layout and spacing.
- Keep small custom CSS in the existing `<style>` block when utilities are not practical.
- Use Alpine.js attributes (`x-data`, `x-show`, `@click`, `x-cloak`) for lightweight interaction.
- Keep copy in Indonesian unless a section is intentionally English.
- Use descriptive asset names in `images/`, for example `hero-screenshot-speakspark.png`.

Avoid adding build tooling, npm dependencies, or large JavaScript abstractions unless the project direction changes.

## Testing Guidelines

There is no automated test suite. Validate changes manually:

- Load `index.html` without console errors.
- Test responsive behavior at mobile, tablet, and desktop sizes.
- Confirm navbar, FAQ accordion, anchors, floating CTA, and purchase/onboarding links work.
- Check that images render and include meaningful `alt` text.

## Commit & Pull Request Guidelines

Recent history mostly uses Conventional Commit prefixes such as `feat:`, `fix:`, and `refactor:`. Follow that pattern:

- `feat: update pricing section copy`
- `fix: correct WhatsApp CTA link`
- `refactor: simplify hero CTA styles`

Pull requests should include a short description, screenshots for visual changes, tested viewport sizes, and any changed external URLs or CTA destinations. Link related issues when available.

## Agent-Specific Instructions

Respect the static HTML architecture. Make focused edits to `index.html` and related assets only, preserve user-authored backup files, and avoid unrelated formatting churn.
