# [ckv.gijs6.nl](https://ckv.gijs6.nl/)

At my school, everyone has to make a website for the subject CKV (*culturele en kunstzinnige vorming*, basically "culture and art") for all reports, reflections, and those kinds of things. The idea is to have a personal space everyone can update easily. Practically everyone just uses Wix because it's easy to use and requires no coding, but I built mine from scratch :D

## Development

This site is now a static site generated from Jinja2 templates.

### Commands

```bash
# Serve locally with live reload (development server)
python engine.py serve

# Or use the Bakefile wrapper
source Bakefile && serve

# Build the static site
python engine.py build

# Or use the Bakefile wrapper
source Bakefile && build

# Deploy to server
source Bakefile && deploy

# Format code
source Bakefile && format

# Publish (format, commit, push, and deploy)
source Bakefile && publish
```

### Structure

- `site/` - Source directory for the website
  - `site/*.html` - Page templates (home.html, blok-1.html, etc.)
  - `site/templates/` - Base Jinja2 templates (base.html, 404.html)
  - `site/assets/` - CSS, JavaScript, documents, and icons
  - `site/images/` - Image files organized by section
- `engine.py` - Static site generator (adapted from gijs6.nl)
- `build/` - Generated static site (gitignored)
  - `build/gijstenberg4a2/` - All HTML pages with clean URLs
  - `build/assets/` - Static assets
  - `build/images/` - Images
- `Bakefile` - Build script with serve, build, deploy commands
- `Caddyfile` - Caddy web server configuration for URL redirects
- `Liftfile` - Deployment configuration for static hosting
- `app.py.old` - Original Flask application (archived)
