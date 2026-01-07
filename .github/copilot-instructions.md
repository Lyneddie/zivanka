# Zivanka Consulting Codebase Guide

## Project Overview
A static website for Zivanka Consulting built with vanilla HTML, CSS, and JavaScript. The site uses a luxury/professional aesthetic with a warm gold-brown color scheme (#d4a574, #c99456 primary).

## Architecture
- **Static Site Structure**: Multiple HTML pages (index, about, services, tools, thanks) each with embedded styles
- **Shared Styling**: Global styles in [style.css](../style.css) + page-specific inline styles within `<style>` tags
- **No Build Tools**: Direct HTML/CSS/JS, served via Python HTTP server or static hosting

## Key Design Patterns

### Color Scheme
- Primary gradient: `linear-gradient(135deg, #d4a574 0%, #c99456 100%)`
- Text/neutral: `#a1887f`, `#d7ccc8`, `#f5deb3`
- Dark background: `#3e2723`, `rgba(109, 76, 65, 0.95)`
- Page background: `#fffef7`

### Component Patterns
1. **Hero Sections**: Max-width 1400px container, centered text, gradient text headings
2. **Cards/Boxes**: Semi-transparent background `rgba(157, 130, 112, 0.2)`, border with gradient color, hover transforms
3. **Buttons**: Two styles - primary (solid gradient) and secondary (transparent with border)
4. **Navigation**: Sticky header with logo and nav links, mobile-responsive structure prepared

### Layout Convention
- All sections max-width 1400px centered with `margin: 0 auto`
- Consistent padding `2rem` horizontally on base container
- Backdrop blur effects on cards for depth

## Development Workflow
```bash
make run-server  # Starts Python3 HTTP server on localhost:8000
```

## File-Specific Notes
- **[index.html](../index.html)**: Homepage with hero section and inline styling (672 lines)
- **[about.html](../about.html)**: About/story section with philosophy grid cards (520 lines)
- **[services.html](../services.html)**: Service offerings page
- **[tools.html](../tools.html)**: Tools/resources page
- **[thanks.html](../thanks.html)**: Thank you/contact confirmation page
- **[style.css](../style.css)**: Global base styles, header/nav, footer (148 lines, "TODO everything between nav and footer" comment indicates incomplete nav styling)

## Important Notes
- Cache-busting: CSS linked with query param `?v=2` for version control
- **TODO item in [style.css](../style.css)** line 60: Mobile menu and content between nav/footer not fully styled
- HTML files include viewport meta and UTF-8 charset
- Logo files: `Zivanka Logo.png` and `Zivanka Logo (1).png` in `/img`

## Common Tasks
- **Adding new page**: Create HTML file with shared header nav and footer, link [style.css](../style.css)
- **Updating styles**: Keep global styles in [style.css](../style.css), page-specific in inline `<style>` tags
- **Color updates**: Search for hex values (#d4a574, #c99456, #a1887f) to keep consistency
