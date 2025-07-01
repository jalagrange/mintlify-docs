# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Mintlify documentation site, currently using the starter template. Mintlify is a React-based documentation framework that uses MDX (Markdown with JSX) for content.

## Essential Commands

```bash
# Install Mintlify CLI globally (required for development)
npm i -g mintlify

# Run local development server (default port 3000)
mintlify dev

# Run on custom port
mintlify dev --port 3333

# Validate all documentation links
mintlify broken-links

# Reinstall dependencies if dev environment fails
mint install
```

## Codebase Analysis

### vibe-tools Repository Analysis
Use `vibe-tools repo "<question>"` for **large-scale codebase analysis** and understanding complex systems:
- `vibe-tools repo "Analyze the upload system implementation"` - Understand complex workflows across multiple files
- `vibe-tools repo "How does thumbnail generation work?"` - Trace features spanning multiple services
- `vibe-tools repo "Explain the authentication flow"` - Understand system architecture
- `vibe-tools repo "Find files related to pricing and list the most relevant ones"` - Locate components across the codebase

**Important**: vibe-tools repo is slow and resource-intensive. Use it to:
- ✅ Gain general understanding of large, complex systems
- ✅ Get file paths and architectural overview
- ✅ Understand multi-component workflows
- ❌ **Don't use** for analyzing just a few specific files - read those files directly instead
- ❌ **Don't use** when you already know which files to examine

After getting the overview and file list from vibe-tools, examine the specific files yourself using the Read tool for faster, more focused analysis.

## Project Documentation & Status Tracking

### Development Status Documents
Always update these three key documents when working on features to maintain clear project status:

**1. Development Backlog** - `docs/development-backlog.md`
- Master list of all remaining development work organized by priority
- Update task status: `[ ]` (pending) → `[x]` (completed) 
- Add completion details and notes for finished items

**2. Legacy Feature Parity** - `docs/legacy-feature-parity.md`  
- Comprehensive feature-by-feature comparison with legacy system
- Update status: ❌ (not started) → 🚧 (in progress) → ✅ (completed)
- Record testing results and implementation notes

**3. Feature Planning** - `docs/feature-planning/`
- Individual numbered planning documents (e.g., `001-feature-name.md`)
- Each document contains detailed technical planning for a specific feature
- Reference these in the backlog using [FP-XXX] notation
- Structure for each planning document:
  - Feature overview and objectives
  - Technical approach and architecture
  - Implementation steps
  - Acceptance criteria
  - Files to be created/modified
  - Testing approach

**Development Workflow**: Follow this process when working on new features or fixes:

1. **Select Task** - Choose item from development backlog (`docs/development-backlog.md`)
2. **Create Planning Document** - If task has [FP-XXX] reference, create corresponding numbered planning document in `docs/feature-planning/XXX-feature-name.md`
3. **Execute Implementation** - Follow the planned approach and technical solutions
4. **Update Documentation** - Mark tasks complete in backlog and update implementation status in planning docs

This workflow ensures proper planning, execution tracking, and comprehensive documentation.

## Commit Message Guidelines

When creating commits, avoid mentioning Claude, Anthropic, or AI assistance in commit messages. Keep commit messages focused on the technical changes and business value delivered.

## Project Structure

```
/mintlify-docs/
├── api-reference/          # API documentation section
│   ├── endpoint/          # Individual endpoint docs (get.mdx, create.mdx, delete.mdx, webhook.mdx)
│   ├── introduction.mdx   # API overview page
│   └── openapi.json       # OpenAPI specification (currently sample Plant Store API)
├── essentials/            # Documentation best practices
│   ├── markdown.mdx       # MDX syntax guide
│   ├── code.mdx          # Code block formatting
│   ├── images.mdx        # Image handling
│   ├── settings.mdx      # Configuration guide
│   ├── navigation.mdx    # Navigation structure
│   └── reusable-snippets.mdx  # Content reusability
├── images/                # Image assets (hero-light.png, hero-dark.png, checks-passed.png)
├── logo/                  # Logo variations (light.svg, dark.svg)
├── snippets/              # Reusable content (snippet-intro.mdx)
├── docs.json             # Main configuration file
├── index.mdx             # Homepage
├── quickstart.mdx        # Quick start guide
└── development.mdx       # Development setup guide

## Key Configuration

- **docs.json** - Main configuration file controlling:
  - Navigation structure
  - Theme and colors
  - Site metadata
  - API reference settings
- **openapi.json** - OpenAPI specification for API documentation (currently contains sample Plant Store API)

## Development Requirements

- Node.js v19 or higher
- Mintlify CLI installed globally
- Uses `docs.json` (not the legacy `mint.json`)

## Architecture Notes

1. **Content Format**: All documentation pages use MDX format, allowing React components within Markdown
2. **Navigation**: Defined in `docs.json` under the `navigation` array with two tabs:
   - "Guides" tab: Get Started section (index, quickstart, development) and Essentials
   - "API Reference" tab: API documentation generated from OpenAPI spec
3. **API Documentation**: Automatically generated from `openapi.json` specification
4. **Snippets**: Reusable content stored in `/snippets/` and included via `<snippets-file>` tags
5. **Theme Support**: Separate assets for light/dark themes (logos, images)
6. **No Build Directory**: Mintlify handles build process internally; no dist/ or build/ folders

## Important Context

This appears to be the documentation component of a larger "dynamic-quiz-creator" project. The current content is from the Mintlify starter template and would need to be replaced with actual quiz creator documentation.