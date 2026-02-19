# Agent Operational Guidelines for ablzh.github.io

This document provides essential instructions, commands, and style guidelines for AI agents and developers working on this Jekyll-based static website (using the [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy/) theme).

## 1. Project Overview & Environment

- **Type:** Static Site Generator (Jekyll)
- **Language:** Ruby (Gemfile), HTML/Liquid, Markdown, SCSS, JavaScript
- **Theme:** `jekyll-theme-chirpy`
- **Dependency Manager:** Bundler

### Prerequisites
- Ruby (version specified in `.ruby-version` or compatible with Gemfile)
- Bundler (`gem install bundler`)
- Jekyll (`gem install jekyll`)

## 2. Operational Commands

The project includes helper scripts in the `tools/` directory to standardize common tasks. **Always prefer these scripts over raw Jekyll commands.**

### Build & Serve (Local Development)
To start the local server with live reload enabled:

```bash
bash tools/run.sh
```

- **Host:** `127.0.0.1`
- **Port:** `4000`
- **Behavior:** Incremental regeneration, live reload.

### Test & Validate (CI/Pre-commit)
To build the production site and run validation checks:

```bash
bash tools/test.sh
```

- **Actions:**
  1. Cleans `_site/` directory.
  2. Builds site in **production** mode (`JEKYLL_ENV=production`).
  3. Runs `html-proofer` to validate:
     - Broken internal links.
     - Valid HTML structure.
     - Missing images (alt tags, src).
     - External links are disabled by default for speed.

### Dependency Management
To install or update dependencies:

```bash
bundle install
```

## 3. Code Style & Formatting

Strict adherence to `.editorconfig` and `.vscode/settings.json` is required.

### General Rules
- **Indentation:** 2 spaces (soft tabs).
- **Line Endings:** LF (Unix-style).
- **Final Newline:** Insert at end of file.
- **Charset:** UTF-8.
- **Trailing Whitespace:** Trimmed (except in Markdown).

### Markdown (`.md`)
- **Front Matter:** Use YAML syntax between `---` delimiters.
  - `title`: String (quoted if contains special chars).
  - `date`: ISO 8601 format (`YYYY-MM-DD HH:MM:SS +/-TTTT`).
  - `categories`: `[Main, Sub]` (PascalCase).
  - `tags`: `[lowercase, kebab-case]` (lowercase).
- **Headers:** ATX style (`# Header`).
- **Lists:** Hyphens (`-`) for unordered lists.
- **Links:** `[Text](url)`. Relative links should be resolved correctly.
- **Quotes:** Standard Markdown blockquotes (`>`).

### Liquid & HTML (`.html`, `.liquid`)
- **Formatter:** `Shopify.theme-check-vscode` logic.
- **Tags:**
  - Objects: `{{ variable }}` (spaces inside braces).
  - Tags: `{% if condition %}` (spaces inside braces).
- **Attributes:** Double quotes for HTML attributes (`class="classname"`).

### YAML (`.yml`, `.yaml`)
- **Quotes:** Double quotes preferred for strings.
- **Structure:** 2-space indentation for nested items.
- **Keys:** `snake_case` generally used in `_config.yml`.

### Shell Scripts (`.sh`)
- **Formatter:** `shfmt`.
- **Interpreter:** `#!/usr/bin/env bash`.
- **Safety:** Use `set -eu` for strict error handling in logic scripts.

### JavaScript & CSS/SCSS
- **Quotes:** Single quotes (`'`) preferred.
- **Style:** Standard Prettier formatting.

## 4. Directory Structure

- `_posts/`: Blog posts (naming: `YYYY-MM-DD-title.md`).
- `_tabs/`: Static pages (About, Tags, Categories, Archives).
- `_config.yml`: Main site configuration (Title, URL, Authors, Plugins).
- `tools/`: Operational scripts (`run.sh`, `test.sh`).
- `assets/`: Images, CSS, JS.
  - `assets/img/`: Images for posts/pages.

## 5. Agent Directives

1.  **Safety First**:
    - Do not modify `_config.yml` unless specifically instructed to change site-wide settings.
    - Do not commit secrets or sensitive data.

2.  **Verification**:
    - After creating a new post, run `bash tools/test.sh` to verify that the file builds and links are valid.
    - If modifying layout or includes, run `bash tools/run.sh` to verify visual rendering if capability allows, otherwise rely on `test.sh`.

3.  **Content Creation**:
    - When creating posts, ensure the filename follows `YYYY-MM-DD-slug.md`.
    - Always include required Front Matter: `title`, `date`, `categories`, `tags`.
    - Use absolute paths for images relative to project root in tools, but Jekyll relative paths in markdown content (e.g., `/assets/img/pic.jpg`).

4.  **Refactoring**:
    - When moving files, update all internal links. `html-proofer` will catch broken links during `test.sh`.
    - Maintain the integrity of Liquid logic in `_layouts` and `_includes`.

5.  **Tool Usage**:
    - Use `grep` and `glob` to find existing patterns before introducing new ones.
    - Use `read` to check file content before `edit`.

## 6. Testing Strategy

### Single Unit/Post Test
Jekyll does not support running "one test" for a single file easily. However, you can verify a specific post by:
1.  Isolating it (drafts) or relying on the incremental build output.
2.  Running `bash tools/test.sh` which runs the global `html-proofer`. This is fast enough for this size of site.

### Continuous Integration
- GitHub Actions is configured in `.github/workflows/pages-deploy.yml`.
- It automatically builds and deploys on push to `main` (or `master`).
- Ensure local tests pass (`tools/test.sh`) before pushing to avoid CI failures.

---
*Generated by Agent for Agents.*
