# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Type

This is a Zola static site generator project. Zola is a fast static site generator written in Rust that uses the Tera templating engine.

## Common Commands

### Development
- `zola serve` - Start the development server with hot reload (automatically rebuilds and reloads on changes)
- `zola serve --open` - Start dev server and open in browser
- `zola serve --port <PORT>` - Start dev server on specific port

### Building
- `zola build` - Build the site (deletes output directory and rebuilds)
- `zola build --output-dir <DIR>` - Build to a specific directory (default is `public/`)
- `zola build --base-url <URL>` - Override the base_url from config.toml

### Validation
- `zola check` - Validate project without rendering (checks links and structure)

## Architecture

### Directory Structure

- `config.toml` - Main configuration file containing site settings, markdown options, and custom variables
- `content/` - Markdown content files organized in sections; `_index.md` files define sections
- `templates/` - Tera templates (`.html` files) for rendering pages
- `sass/` - Sass/SCSS files (compiled automatically if `compile_sass = true` in config)
- `static/` - Static assets (images, fonts, etc.) copied as-is to output
- `themes/` - Theme directory if using external themes
- `public/` - Generated site output (created by `zola build`, not tracked in git)

### Template System

Zola uses Tera templating engine with the following key concepts:

- Base templates use `{% block content %}{% endblock %}` for inheritance
- Templates can access page variables via `{{ page.title }}`, `{{ section.pages }}`, etc.
- Front matter in markdown files is TOML between `+++` delimiters
- Templates are selected based on page/section type and can be overridden via `template` field in front matter

### Content Organization

- Content files are markdown with TOML front matter
- Sections are defined by `_index.md` files in subdirectories
- Pages can be co-located with assets in directories
- Taxonomies (tags, categories) are defined in config.toml

### Configuration Notes

Current config settings:
- `compile_sass = true` - Sass files are automatically compiled
- `build_search_index = true` - Search index is generated during build
- `highlight_code = true` - Syntax highlighting enabled for code blocks
