# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo-based static website for Pavel Kazutsin's blog (https://ktsin.github.io), focused on hosting archived Symbian SDK/PDK documentation and related technical content.

## Architecture

- **Static Site Generator**: Hugo
- **Theme**: "Paper" theme from https://github.com/nanxiaobei/hugo-paper (included as git submodule)
- **Content Structure**: 
  - Blog posts in `content/posts/`
  - Static documentation files in `s3/` directory (Symbian SDK/PDK docs)
- **Configuration**: `hugo.toml` for site settings
- **Deployment**: GitHub Pages (based on domain name)

## Key Components

### Configuration (`hugo.toml`)
- Site URL: https://ktsin.github.io/
- Theme: "paper" 
- Author: Pavel Kazutsin (.NET Software Engineer)
- Features: Comments disabled, math disabled, light color scheme

### Content Management
- **Posts**: Located in `content/posts/` using Hugo's markdown format
- **Static Assets**: Extensive Symbian documentation in `s3/pdk/` with thousands of HTML files and assets
- **Archetypes**: Default post template in `archetypes/default.md`

### Theme System
- Uses hugo-paper theme as git submodule in `themes/paper/`
- Theme repository: https://github.com/nanxiaobei/hugo-paper

## Common Commands

### Development
```bash
hugo server          # Start development server with live reload
hugo server -D       # Include draft posts
hugo server --bind 0.0.0.0  # Bind to all interfaces
```

### Build
```bash
hugo                  # Build static site to public/ directory
hugo -D               # Build including drafts
hugo --minify         # Build with minification
```

### Content Management
```bash
hugo new posts/post-name.md    # Create new blog post
hugo new site <name>           # Create new Hugo site (if needed)
```

### Theme Management
```bash
git submodule update --init --recursive    # Initialize theme submodule
git submodule update --remote              # Update theme to latest
```

## File Structure Notes

- The `s3/` directory contains archived Symbian documentation with thousands of HTML files
- Each HTML file follows GUID-based naming convention (e.g., `GUID-00011FDE-E8D9-3374-9006-823C83A326C1.html`)
- Documentation includes images (PNG/JPG), JavaScript files, and interconnected HTML pages
- Content is self-contained and doesn't require external dependencies to view

## Development Workflow

1. **Content Creation**: Add new posts to `content/posts/` following existing format
2. **Local Testing**: Use `hugo server` for development
3. **Building**: Run `hugo` to generate static files
4. **Deployment**: Built files should be deployed to GitHub Pages

## Important Notes

- No package.json or Node.js dependencies - pure Hugo site
- Theme is managed as git submodule, not as direct dependency
- Site serves both new blog content and archived Symbian documentation
- Static documentation in `s3/` should be preserved as historical reference