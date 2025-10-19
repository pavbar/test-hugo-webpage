# Repository Guidelines

## Project Structure & Module Organization
This Hugo site keeps Markdown source in `content/`, grouped by section (e.g., `content/posts/`). New pages should start from the relevant archetype in `archetypes/`, which pre-populates TOML front matter. Theme-specific templates live in `themes/terminal/`; add custom overrides under `layouts/` instead of editing theme files directly. Static assets (images, downloads) belong in `static/`, while pipeline-ready SCSS or JS goes in `assets/`. The `public/` directory is build output and should not be hand-edited; treat `resources/` as Hugo’s cache.

## Build, Test, and Development Commands
- `hugo server -D`: Run the local preview with drafts enabled and live reload. Use `-p 1313` if you need a different port.
- `hugo`: Produce a production build into `public/` using the configuration in `hugo.toml`.
- `hugo --gc --minify`: Clean unused resources and emit a minified build before releasing.

## Coding Style & Naming Conventions
Keep Markdown headings incremental (`#`, `##`, …) and wrap paragraphs at ~100 characters for readability. Use TOML front matter delimited by `+++`, keeping keys alphabetical (`title`, `date`, `draft`, etc.) and dates in ISO-8601 with offset. Name posts with lowercase kebab-case slugs (`content/posts/feature-update.md`) that match the eventual URL. When authoring Go templates, prefer two-space indentation and rely on partials or blocks that already exist in the Terminal theme.

## Testing Guidelines
Run `hugo server` and inspect pages in multiple viewport sizes before opening a pull request. Check console output for warnings about missing shortcodes or layout errors. After `hugo --gc --minify`, spot-check the generated `public/index.html` and any new pages to confirm assets resolve and metadata is correct. If you add custom scripts or CSS, validate that the minified build still behaves as expected.

## Commit & Pull Request Guidelines
Follow the short, imperative style used in the history (`Add ...`, `Update ...`) and keep commits scoped to a single change. Reference related issues in the commit body or PR description using `Fixes #ID` when applicable. Pull requests should outline the change, list verification steps (commands run, browsers checked), and include screenshots for visual updates. Avoid committing generated output (`public/`, `resources/`) unless a release workflow explicitly requires it.

## Content Workflow
Generate new articles with `hugo new posts/<slug>.md`, then update front matter fields before publishing. Toggle `draft = false` only once the copy, links, and assets have been proofed. For scheduled posts, set `publishDate` in the front matter so the page remains hidden until release.
