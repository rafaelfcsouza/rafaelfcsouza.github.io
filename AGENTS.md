# Site: Hugo-based personal website

## Site Proposal

This personal website serves as a digital portfolio presenting myself as a software engineer through unconventional yet technically focused representation.

### Core Concept
- **Introduction**: Software engineer showcasing professional background, skills, and projects
- **Blog**: Future section for technical articles and sharing knowledge (not yet implemented)
- **CV as API**: Professional experience and skills presented using Docsy's API Documentation theme, leveraging the Table of Contents on the right and other built-in features

## Framework
- **Hugo static site generator**
- `hugo.toml` contains site config (baseURL, title, locale)
- Uses **Docsy** theme via Hugo modules (`github.com/google/docsy`)
- `themes/` contains git submodules (ananke, almeida-cv) - may need `git submodule update --init --recursive`

## Setup
```bash
go install                    # Required for Hugo modules
hugo mod get                  # Get all Hugo module dependencies
hugo mod tidy                 # Sync module dependencies
```

## Build
```bash
hugo                    # Build site (outputs to public/)
hugo server             # Local dev server at http://localhost:1313
```

## Customization
- **Custom CSS**: Add to `assets/scss/_styles_project.scss` (gets imported by Docsy)
- **Custom layouts**: Add to `layouts/` directory
- **Home page**: Create `content/_index.md` (not `content/en/_index.md` for root content)

## Known issues
- Docsy's fixed navbar overlaps content by default - use `.td-home .td-main { padding-top: 5rem; }` in custom CSS
- Use `[markup.goldmark.renderer.unsafe = true]` in hugo.toml to allow Docsy shortcodes in Markdown

## Content
- `content/` - Markdown content files
- `layouts/` - Custom layout overrides
- `archetypes/default.md` - New content template

---

**IMPORTANT**: When you discover something new about this repo (commands, quirks, gotchas), update this file to help future agents.