# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal academic website built with Hugo using the Hugo Blox Academic CV template. It's designed to showcase publications, projects, blog posts, courses, and professional experience.

## Tech Stack

- **Hugo**: Static site generator (version 0.152.2)
- **Hugo Blox Builder**: Theme framework for academic/research websites
- **Tailwind CSS v4**: Styling via `@tailwindcss/cli`
- **Package Manager**: pnpm (v10.14.0)
- **Deployment**: GitHub Pages (automated via GitHub Actions)

## Common Commands

### Development
```bash
# Start local development server with live reload
pnpm dev
# or
hugo server --disableFastRender

# Build for production (minified)
pnpm build
# or
hugo --minify
```

### Package Management
```bash
# Install dependencies
pnpm install

# Hugo modules (for theme updates)
hugo mod get -u
```

## Architecture

### Content Structure
Content is organized in `/content/` with the following sections:
- `authors/` - Author profiles and bios
- `blog/` - Blog posts
- `courses/` - Course materials and documentation
- `events/` - Events and talks
- `projects/` - Project showcases
- `publications/` - Academic publications
- `experience.md` - Professional experience timeline

Each content section uses Hugo's page bundles (index.md + assets in the same directory).

### Configuration
Configuration is split across `/config/_default/`:
- `hugo.yaml` - Core Hugo settings, taxonomies, and build options
- `params.yaml` - Site appearance, SEO, analytics, and feature toggles
- `module.yaml` - Hugo module imports and mounts for the Blox theme
- `menus.yaml` - Navigation menu structure
- `languages.yaml` - Internationalization settings

### Hugo Modules
The site uses Hugo modules for theming:
- `blox-plugin-netlify` - Netlify deployment optimizations
- `blox-tailwind` - Tailwind CSS integration

Hugo Blox components are mounted from `hugo-blox/blox/` (downloaded via Hugo modules) to:
- `layouts/_partials/blox/` - Template partials
- `assets/dist/community/blox/` - CSS assets

Custom layouts override theme defaults via `/layouts/`.

### Deployment
Automated deployment to GitHub Pages on push to `main`:
- Builds with Hugo extended version
- Generates Tailwind CSS
- Caches dependencies and Hugo resources for faster builds
- Deploys to GitHub Pages environment

## Content Guidelines

### Adding Content
Content files use YAML frontmatter for metadata. Common fields:
- `title`, `summary`, `date`
- `authors` - references to author IDs in `/content/authors/`
- `tags`, `categories`
- `featured` - boolean for highlighting

### Hugo Blox Sections
The homepage (`content/_index.md`) uses Hugo Blox "sections" (reusable page blocks). Each section has a `block: block-name` parameter that maps to a Blox component.

## Important Notes

- Hugo uses Go modules for dependency management (`go.mod`)
- The site requires Hugo Extended (for SCSS/Tailwind processing)
- Static assets go in `/static/` (served as-is) or `/assets/` (processed by Hugo Pipes)
- Custom CSS/JS should be added via Hugo Pipes in `/assets/`
- The theme is managed via Hugo modules, not as a Git submodule
