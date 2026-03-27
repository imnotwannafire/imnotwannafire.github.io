# Copilot Workspace Instructions

This is a personal technical blog called **Learning in Public**, built with Jekyll and the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) `air` skin (light, minimal, modern). Deployed at `https://imnotwannafire.github.io`.

**Blog identity:** Self-learning sharing — tutorials, deep dives, tool notes, and learning logs written from a developer's perspective. Style: minimalist, light, positive, modern.

## Build & Development

```bash
# Install dependencies (first time)
bundle install

# Serve locally with live reload
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

> The `_config.yml` is **not** hot-reloaded. Restart the server after changing it.

## Project Structure

| Path | Purpose |
|------|---------|
| `_config.yml` | Site-wide settings, theme, author info, plugins |
| `_posts/` | Blog posts — filename drives date and URL slug |
| `_pages/` | Static pages (about, 404, archives) |
| `_data/navigation.yml` | Top-nav links |
| `assets/images/` | Images referenced in posts and config |
| `index.html` | Homepage — uses `layout: home` |

## Post Types

This is a self-learning blog. Posts fall into four patterns:

| Type | Use when… |
|------|-----------|
| **Tutorial** | Step-by-step — show end result first, list prereqs, runnable code blocks |
| **Deep Dive** | Concept or architecture — simplified mental model → mechanics → trade-offs |
| **Tool Note** | Honest impressions of a library, language, or dev tool |
| **Learning Log** | Rough notes from a course, book, or experiment — can be opinionated/incomplete |

## Post Conventions

### File naming
`_posts/YYYY-MM-DD-title-with-hyphens.md`

> URL shape: `/:year/:month/:title/` (e.g. `/2026/03/understanding-async-await/`)

### Required front matter
```yaml
---
title: "Post Title"
date: YYYY-MM-DDTHH:MM:SS-TZ
categories:
  - CategoryName
tags:
  - tag-one
  - tag-two
---
```

The defaults in `_config.yml` automatically apply to all posts:
- `layout: single`
- `author_profile: true`
- `read_time: true`
- `comments: true`
- `share: true`
- `related: true`

Override any default by setting it explicitly in the post's front matter.

### Optional front matter
```yaml
excerpt_separator: "<!--more-->"   # manual excerpt cutoff
header:
  image: /assets/images/header.jpg # hero image
  teaser: /assets/images/teaser.jpg
```

## Markdown

The site uses **kramdown**. Code blocks use triple backticks with a language hint:

~~~markdown
```ruby
puts "Hello"
```
~~~

## Site Configuration (`_config.yml`)

Key knobs to know:
- `minimal_mistakes_skin` — theme skin (`default`, `air`, `dark`, `mint`, etc.)
- `search: true` — Algolia search is configured via `jekyll-algolia`
- `paginate` — posts per page (currently 5)
- `author` — sidebar profile (name, avatar, bio, social links)

## Skills Available

Three agent skills are installed in `.agents/skills/`:

| Skill | Load when… |
|-------|-----------|
| `blog-writing-guide` | Writing or reviewing a Sentry-style engineering blog post |
| `technical-blog-writing` | Drafting any technical/developer-facing blog content |
| `GithubPages` | Configuring GitHub Pages, custom domains, Actions workflows |

## Plugins

| Plugin | Purpose |
|--------|---------|
| `jekyll-paginate` | Paginated home feed |
| `jekyll-sitemap` | Auto-generated sitemap.xml |
| `jekyll-feed` | RSS/Atom feed |
| `jekyll-gist` | Gist embed shortcode |
| `jemoji` | Emoji support |
| `jekyll-include-cache` | Performance: cache `{% include %}` calls |
| `jekyll-algolia` | Site-wide search indexing |

## Common Pitfalls

- **Date in filename must match `date:` in front matter** — mismatches cause posts to not appear.
- **Categories and tags are case-sensitive** — `Blog` and `blog` create separate archive pages.
- **Remote theme changes** require an internet connection during build; use `bundle exec jekyll serve` locally.
- **Images** must go in `assets/images/` and be referenced as `/assets/images/filename.ext`.
