# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Book of Knowledge** site that presents different topics in a presentation-style format for customers. Each topic (left menu item) serves as a presentation explaining key concepts for both technical staff and managers. 

### Content Goals
- Present complex topics in an accessible, easy-to-understand format
- Target both technical and management audiences
- Use visual aids (Mermaid diagrams, charts) when appropriate
- Structure content as presentations rather than traditional documentation

### Example Topics
- Habits of highly performant teams
- DORA 2025 summary
- DevOps best practices
- Agile transformation strategies


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

## Content Development

When creating or editing presentation pages, **always read `gitbook-guidelines.md` first** for a comprehensive reference of available components and syntax.

### Presentation Guidelines
- Structure content as presentations with clear sections and takeaways
- Do not overuse headers, prefer longer sections if needed for easier navigation. Too many headings take too much space.
- Use Mermaid diagrams proactively to visualize concepts, workflows, and relationships
- Include practical examples and real-world applications
- Balance technical depth with managerial insights
- Use visual elements (charts, diagrams, callouts) to enhance understanding
- Never add titles like #Welcome as title is always defined at the top of md file

### Content Quality Standards
- **Research-Backed**: Every claim must be supported by real data, studies, or industry research (DORA metrics, DevEx research, Stack Overflow surveys, etc.)
- **Actionable Insights**: Each section must provide specific, implementable actions with clear next steps
- **Dense Information**: Eliminate academic language and filler content - every sentence should deliver high-value insights
- **Quantified Recommendations**: Include specific numbers, percentages, timelines, and measurable outcomes when available
- **Real-World Examples**: Use concrete case studies with measurable results (e.g., "Company X reduced deployment frequency by 40% using technique Y")
- **Immediate Applicability**: Readers should be able to implement recommendations within days/weeks, not months
- **Multi-Level Value**: Provide tactical details for implementers AND strategic insights for decision-makers
- **Evidence-Based**: Prefer industry data over anecdotal evidence - cite sources when making claims

### Recommended Content Structure
1. **Overview/Introduction** - Brief context and objectives
2. **Key Concepts** - Core principles explained clearly
3. **Visual Models** - Diagrams showing relationships and processes
4. **Practical Applications** - Real-world examples and use cases
5. **Implementation Guidelines** - Action items and best practices
6. **Takeaways** - Summary of key points for different audiences

### Development workflow
- [ ] Research the topic, browse web if needed.
- [ ] Give a structure proposal
- [ ] Implement the page/section/change
- [ ] Do not run any build/run commands as server is always running locally

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
- When using blocks like tip or danger, do not use "TIP" or "DANGER". Instead of ##### TIP use ##### Quick DORA Assessment. Or > ##### Danger should be > ##### The Cost of Low Performance