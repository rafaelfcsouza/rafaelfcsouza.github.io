# Site: Hugo-based personal website

## Framework
- **Hugo static site generator** (NOT Astro despite `.astro/` directory)
- `hugo.toml` contains site config (baseURL, title, locale)
- Uses **Docsy** theme via Hugo modules (`github.com/google/docsy`)
- `themes/` contains git submodules: `ananke` and `almeida-cv`

## Setup
```bash
go install                    # Required for Hugo modules
git submodule update --init --recursive  # Initialize theme submodules
npm install -D postcss postcss-cli autoprefixer  # Required for Docsy CSS
hugo mod tidy                 # Sync module dependencies
```

## Build
```bash
hugo                    # Build site (outputs to public/)
hugo server             # Local dev server at http://localhost:1313
```

## Known issues
- `.astro/` directory and `.vscode/launch.json` reference Astro (stale from previous setup)
- `themes/` submodules may not be initialized on first clone
- `hugo.toml` has placeholder values that need updating

## Content
- `content/` - Markdown content files
- `layouts/` - Custom layout overrides
- `archetypes/default.md` - New content template
