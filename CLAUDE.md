# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll theme repository that provides a GitBook-style theme for Jekyll sites. The theme allows users to create documentation sites with GitBook's appearance while leveraging Jekyll's static site generation capabilities and GitHub Pages deployment.


### Dependencies
- Ruby with Bundler (managed via Gemfile)
- Jekyll static site generator
- Theme uses remote_theme: sighingnow/jekyll-gitbook

## Architecture

### Core Structure
- `_layouts/` - HTML templates (home.html, post.html, search-base.html)
- `_includes/` - Reusable HTML components (head.html, footer.html, toc.html, etc.)
- `_posts/` - Blog posts/documentation pages in markdown
- `_pages/` - Static pages organized in collections
- `_others/` - Additional content collection
- `assets/gitbook/` - GitBook-style CSS, JS, and assets
- `_site/` - Generated static site (excluded from git)

### Key Features
- GitBook-style navigation and appearance
- Full-text search powered by gitbook-plugin-search-pro
- Table of contents generation via jekyll-toc
- Support for collections to organize content
- Mermaid.js diagram support
- Custom blocks (tips, warnings, dangers)
- Syntax highlighting with Rouge
- Optional analytics integration (Google Analytics, CNZZ, Application Insights)

### Configuration
- `_config.yml` - Main Jekyll configuration
- Collections: posts, pages, others (with custom permalinks)
- TOC enabled by default (h1-h3)
- Remote theme configuration for easy updates
- Markdown rendering with kramdown and GFM input

## Page Development

When working on creating or editing pages, **always read `gitbook-guidelines.md` first** for a comprehensive reference of:
- Available components (alert blocks, tables, math, diagrams)
- Front matter configuration options
- Layout choices and best practices
- Component usage examples and syntax
- Never add titles like #Welcome as title is always defined at the top of md file

```
// Example of embedding mermaid diagrams inside of html
<div class="language-mermaid">
    graph TD;
        A-->B;
        A-->C;
        B-->D;
        C-->D;
  </div>
```