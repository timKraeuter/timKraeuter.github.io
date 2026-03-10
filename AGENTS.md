# AGENTS.md

> Instructions for AI coding agents working in this repository.

## Project Overview

This is a **Jekyll static site** (personal website / portfolio) for Tim Kraeuter, hosted on
**GitHub Pages**. Based on the [Indigo](https://github.com/sergiokopplin/indigo) theme. The site
uses Liquid templates, Sass/SCSS stylesheets, Markdown content, and YAML configuration. There is
no JavaScript application code, no TypeScript, and no Node.js tooling.

**Tech stack:** Ruby, Jekyll, Liquid, Sass (indented syntax), SCSS, Markdown, HTML, YAML, Docker.

## Build / Serve / Deploy Commands

### Local development (Docker -- preferred)

```bash
docker-compose up
```

Serves the site at `http://localhost:4000` using `bretfisher/jekyll-serve`.

### Local development (native Ruby)

```bash
bundle install
bundle exec jekyll serve
```

### Production build

```bash
bundle exec jekyll build
```

Output goes to `_site/` (gitignored). GitHub Pages builds and deploys automatically on push to
the default branch -- no custom CI/CD pipeline exists.

### Tests

There are **no tests** in this project. No test framework, no test files, no test commands.

### Linting / Formatting

There are **no linters or formatters** configured (no ESLint, Prettier, Stylelint, Rubocop, etc.).
The only code-quality enforcement is `.editorconfig`:

- Line endings: `lf`
- Final newline: `true`
- Charset: `utf-8`
- Indent size: `4`

## Project Structure

```
_config.yml              # Jekyll site configuration (feature flags, metadata)
_layouts/                # Template hierarchy: compress -> default -> page -> post
_includes/               # Reusable Liquid partials (header, nav, footer, etc.)
  style.scss             # Light theme Sass entry point (import order matters)
  style-dark.scss        # Dark theme Sass entry point
_posts/                  # Markdown content: YYYY-MM-DD-slug.markdown
_sass/                   # Sass stylesheets (3-tier architecture)
  base/                  #   Foundation: variables, normalize, syntax, general, helpers
  components/            #   UI components: header, nav, footer, social-links, etc.
  pages/                 #   Page-specific: home-blog-projects, page, post, tags
assets/                  # Static files
  images/                #   Images and favicons
  publications/          #   PDF research papers
index.html               # Home page
projects.html            # Projects listing
about.md                 # About page (publications, skills, bio)
404.html                 # Custom 404 page
docker-compose.yml       # Docker-based local development
Gemfile                  # Ruby dependencies
```

## Configuration

Most site features are **toggled via `_config.yml` booleans**. Before adding a new feature,
check whether it can be driven by config. Current toggleable features:

- `dark-theme` (true/false/auto), `blog`, `projects`, `about`
- `read-time`, `show-tags`, `related`, `show-author`, `animation`
- `post-advance-links`, `analytics-google`, `disqus`

## Code Style Guidelines

### Formatting

- **Indentation:** 4 spaces (all file types). No tabs.
- **Line endings:** LF (`\n`), never CRLF.
- **Final newline:** Always end files with a newline.
- **Charset:** UTF-8.

### Sass / SCSS

- **Indented Sass syntax** (`.sass`) for all custom styles -- no braces, no semicolons.
- **SCSS syntax** (`.scss`) only for the two entry-point files in `_includes/` and the
  vendored `normalize.scss`.
- **Import order** in `style.scss` is strict: base -> pages -> components. Do not reorder.
- **Sass variables:** Greek letters for colors (`$alpha`, `$beta`, `$omega`, `$zeta`, etc.),
  camelCase for fonts (`$fontSans`, `$fontMonospace`), kebab-case for misc (`$thin-font`).
- **Media queries:** Use the predefined variables `$mobile`, `$tablet`, `$above`, `$below`.
- **Dark theme:** Defined by overriding the same variables in `variables-dark.sass`. Do not
  add dark-theme-specific styles outside this pattern.
- **Selectors:** Use child combinators (`>`) for scoping within components. Class names are
  kebab-case (e.g., `.header-home`, `.post-tags`, `.social-links`).
- **One file per component/page** -- each `.sass` file maps to a single UI concern.

### Liquid Templates

- **Layout inheritance:** `compress.html` -> `default.html` -> `page.html` -> `post.html`.
  Do not break this chain.
- **Conditional rendering:** Always gate optional features with `{% if site.<feature> %}`.
- **Include references:** Flat filenames from `_includes/` (e.g., `{% include header.html %}`).
- **Strings:** Use double quotes in Liquid expressions (`"Home"`, `"%d-%m-%Y"`).

### HTML

- 4-space indentation.
- Double quotes for all attributes.
- Semantic HTML5 elements where possible.

### Markdown Posts

- **Filename format:** `YYYY-MM-DD-slug.markdown` (prefer kebab-case slugs).
- **File extension:** `.markdown` (not `.md`) for posts.
- **Required front matter:**
  ```yaml
  ---
  title: "Post title"
  layout: post
  date: YYYY-MM-DD HH:MM
  tag:
    - tag1
    - tag2
  image: <url-or-path>
  headerImage: true
  projects: true              # true for project posts
  hidden: false               # false = visible in pagination
  description: "Short summary"
  category: project           # or blog
  author: timKraeuter
  externalLink: false
  ---
  ```
- **Emoji:** Use jemoji shortcodes (`:fire:`, `:norway:`) rather than raw Unicode.
- **Embedded media:** Use raw HTML (`<iframe>`, `<img>` with inline styles) centered in
  `<div style="text-align:center">` blocks.

### YAML Configuration

- Indent with 4 spaces.
- Use kebab-case for config keys (`dark-theme`, `show-tags`, `read-time`).
- Single quotes for complex string values; leave simple values unquoted.
- Add a comment above each config section explaining its purpose.

### Naming Conventions

| Scope              | Convention   | Examples                                    |
|--------------------|-------------|---------------------------------------------|
| Files / folders    | kebab-case  | `social-links.html`, `home-blog-projects.sass` |
| CSS classes        | kebab-case  | `.header-home`, `.post-tags`, `.nav-home`   |
| Sass color vars    | Greek       | `$alpha`, `$omega`, `$zeta`                 |
| Sass font vars     | camelCase   | `$fontSans`, `$fontMonospace`               |
| Sass breakpoints   | lowercase   | `$mobile`, `$tablet`                        |
| YAML config keys   | kebab-case  | `dark-theme`, `show-tags`                   |
| Post filenames     | date-prefix | `2024-03-18-rust-bpmn-analyzer.markdown`    |

### Error Handling

- **404 page:** `404.html` provides a user-friendly error page. Keep it updated.
- **Defensive Liquid:** Always check for nil/empty before accessing optional values
  (e.g., `{% if page.previous.url %}`, `{% if post.title != null %}`).
- **Graceful degradation:** Wrap all optional features (analytics, disqus, social links)
  in `{% if %}` guards so the site renders correctly with missing config values.

### Comments

- **Sass:** Use `//` for inline comments; `/* ... */` block comments for section headers.
- **HTML:** Use `<!-- ... -->` for explanatory notes (e.g., "To add more icons...").
- **YAML:** Use `#` comments liberally to explain config sections.
- **Keep comments pragmatic** -- explain "why", not "what".
