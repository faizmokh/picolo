# Zola Pico Theme

A minimal, semantic Zola theme built with [PicoCSS](https://picocss.com). This theme emphasizes clean, class-light HTML and automatic responsive design with built-in light/dark mode support.

## Features

- **Minimal & Semantic**: Built with PicoCSS's class-light philosophy
- **Responsive by Default**: Automatically adapts to all screen sizes
- **Dark Mode**: Automatic light/dark theme based on system preferences
- **Fast & Lightweight**: No JavaScript dependencies
- **Customizable**: Easy to customize via CSS variables and Sass
- **Syntax Highlighting**: Built-in code syntax highlighting
- **Blog-Ready**: Pagination, sections, and blog post structure included

## Installation

### Using this repository directly

1. Clone this repository
2. Run `zola serve` to preview locally
3. Customize `config.toml` to your preferences

### Using as a theme

1. Create a new Zola site or navigate to your existing one:
   ```bash
   zola init my-site
   cd my-site
   ```

2. Add the theme as a git submodule:
   ```bash
   git submodule add https://github.com/faizmokh/zola-pico themes/zola-pico
   ```

3. Update your `config.toml`:
   ```toml
   theme = "zola-pico"
   ```

4. Copy the theme's `config.toml` extra section to customize your site.

## Configuration

Customize the theme by adding these variables to your `config.toml`:

```toml
[extra]
# PicoCSS settings
pico_cdn_version = "2"
pico_use_cdn = true

# Site metadata
site_author = "Your Name"
site_description = "Your site description"

# Navigation
show_nav = true
nav_items = [
    { path = "/", name = "Home" },
    { path = "/blog", name = "Blog" },
    { path = "/about", name = "About" }
]

# Footer
footer_text = "© 2025 Your Name • Built with Zola & PicoCSS"
```

## Customization

### CSS Variables

Override PicoCSS CSS variables in `sass/_variables.scss`:

```scss
:root {
    --pico-font-size: 18px;
    --pico-spacing: 1.5rem;
    // Add more custom variables
}
```

### Custom Styles

Add your own styles in `sass/_custom.scss`. All Sass files are automatically compiled by Zola.

### Templates

Override templates by creating files with the same name in your site's `templates/` directory. Available templates:

- `base.html` - Base template with header/footer
- `index.html` - Homepage
- `page.html` - Individual pages
- `section.html` - Section listings (blog)
- `404.html` - Error page

### Using CDN vs Local PicoCSS

By default, the theme uses PicoCSS from CDN. To use a local copy:

1. Download PicoCSS to your `static/` directory
2. Set `pico_use_cdn = false` in `config.toml`
3. Update the stylesheet link in `templates/base.html`

## Content Structure

```
content/
├── _index.md          # Homepage
├── about.md           # About page
└── blog/
    ├── _index.md      # Blog section
    └── *.md           # Blog posts
```

## Shortcodes

### Note/Callout Box

Create highlighted callout boxes:

```
{{/* note(title="Important") */}}
This is a callout box for important information.
{{/* end */}}
```

## Development

1. Clone the repository
2. Run `zola serve` for live preview
3. Edit templates in `templates/`
4. Edit styles in `sass/`
5. Build with `zola build`

## Credits

- **Zola**: [getzola.org](https://www.getzola.org)
- **PicoCSS**: [picocss.com](https://picocss.com)

## License

MIT License - see LICENSE file for details.
