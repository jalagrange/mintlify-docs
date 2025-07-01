# Mintlify Usage Guide

This document provides guidance on using Mintlify for the Dynamic Quiz Generator documentation project.

## What is Mintlify?

Mintlify is a modern documentation platform built on React that transforms MDX files into beautiful, interactive documentation sites. It's designed for developer-focused documentation with features like API references, code highlighting, and responsive design.

## Key Concepts

### MDX Format
- **Markdown + JSX**: All documentation pages use `.mdx` extension
- **React Components**: Can embed interactive elements directly in markdown
- **Frontmatter**: YAML metadata at the top of each file

### Configuration
- **docs.json**: Main configuration file (replaces legacy `mint.json`)
- **Navigation**: Defined in docs.json with tabs, groups, and pages
- **Theming**: Colors, logos, and styling configured in docs.json
- **Valid Themes**: 'mint', 'maple', 'palm', 'willow', 'linden', 'almond', 'aspen'

### File Structure
```
/mintlify-docs/
├── docs.json              # Main configuration
├── index.mdx              # Homepage
├── quickstart.mdx         # Getting started
├── api-reference/         # API documentation
├── technical/             # Technical docs
├── images/                # Static assets
└── logo/                  # Logo files
```

## Essential Commands

### Local Development
```bash
# Install Mintlify CLI globally (one-time setup)
npm i -g mintlify

# Start local development server (default port 3000)
mintlify dev

# Run on custom port
mintlify dev --port 3333

# Validate all documentation links
mintlify broken-links

# Reinstall dependencies if dev environment fails
mint install
```

### Development Workflow
1. Edit `.mdx` files or `docs.json`
2. Run `mintlify dev` to preview changes
3. Test navigation and links
4. Commit changes when satisfied

## Configuration Reference

### docs.json Structure
```json
{
  "$schema": "https://mintlify.com/docs.json",
  "name": "Project Name",
  "theme": "mint",
  "colors": {
    "primary": "#0066CC",
    "light": "#3399FF",
    "dark": "#0052A3"
  },
  "logo": {
    "light": "/logo/light.svg",
    "dark": "/logo/dark.svg"
  },
  "favicon": "/favicon.svg",
  "navigation": {
    "tabs": [
      {
        "tab": "Tab Name",
        "groups": [
          {
            "group": "Group Name",
            "pages": ["page1", "page2"]
          }
        ]
      }
    ]
  }
}
```

### MDX Page Structure
```mdx
---
title: Page Title
description: Page description for SEO
---

# Page Heading

Content goes here with **markdown formatting**.

<Card title="Interactive Component" icon="star">
  This is a Mintlify component
</Card>
```

## Mintlify Components

### Navigation and Layout
- `<Card>` - Feature cards with icons
- `<CardGroup>` - Grid layout for cards
- `<Tabs>` - Tabbed content sections
- `<Tab>` - Individual tab content

### Content Organization
- `<Accordion>` - Collapsible content sections
- `<AccordionGroup>` - Multiple accordions
- `<Steps>` - Sequential numbered steps
- `<Callout>` - Important notes and warnings

### Code and API
- Code blocks with syntax highlighting
- `<CodeGroup>` - Multiple code examples
- OpenAPI integration for API documentation
- Request/response examples

### Example Usage
```mdx
<CardGroup cols={2}>
  <Card title="Architecture" href="/technical/architecture" icon="sitemap">
    System design overview
  </Card>
  <Card title="API Reference" href="/api-reference" icon="code">
    API endpoints and examples
  </Card>
</CardGroup>

<Callout type="warning">
  Important configuration note
</Callout>

<Steps>
  <Step title="Install Dependencies">
    Run `npm install` to get started
  </Step>
  <Step title="Configure Settings">
    Update your docs.json file
  </Step>
</Steps>
```

## Best Practices

### File Organization
- Use clear, descriptive file names
- Organize content in logical directories
- Keep URLs simple and readable
- Use consistent naming conventions (kebab-case)

### Navigation Design
- Limit navigation depth (max 3 levels recommended)
- Group related content together
- Use descriptive group and page names
- Consider user journeys when organizing

### Content Writing
- Start with frontmatter (title, description)
- Use clear headings (H1, H2, H3)
- Include code examples where relevant
- Test all internal links regularly

### Performance
- Optimize images (WebP format recommended)
- Keep pages focused and scannable
- Use components to avoid repetition
- Test mobile responsiveness

## Troubleshooting

### Common Issues
```bash
# Development server won't start
mint install
mintlify dev

# Broken links
mintlify broken-links

# Navigation not updating
# Check docs.json syntax and restart dev server

# Components not rendering
# Verify MDX syntax and component names
```

### Link Validation
- Run `mintlify broken-links` regularly
- Check for typos in page names
- Verify internal links use correct paths
- Test external links periodically

## Deployment

### Auto-Deployment
Mintlify supports automatic deployment through:
- GitHub integration
- Vercel deployment
- Custom domains

### Manual Deployment
- Push changes to main branch
- Mintlify handles build process
- No manual build steps required

## Resources and Documentation

### Official Mintlify Resources
- **Documentation**: [https://mintlify.com/docs](https://mintlify.com/docs)
- **Component Library**: [https://mintlify.com/docs/components](https://mintlify.com/docs/components)
- **Examples**: [https://mintlify.com/showcase](https://mintlify.com/showcase)
- **Community**: [https://mintlify.com/community](https://mintlify.com/community)

### Technical References
- **MDX Documentation**: [https://mdxjs.com/](https://mdxjs.com/)
- **React Components**: [https://react.dev/](https://react.dev/)
- **OpenAPI Specification**: [https://swagger.io/specification/](https://swagger.io/specification/)

### Support Channels
- GitHub Issues: For bug reports and feature requests
- Discord Community: For real-time help and discussions
- Documentation: For comprehensive guides and references

## Dynamic Quiz Generator Specific Notes

### Our Configuration
- Uses modern `docs.json` format (not legacy `mint.json`)
- Blue color scheme aligned with Go1 branding
- Developer-focused navigation structure
- Technical documentation emphasis

### Custom Conventions
- Feature planning documents numbered (FP-001, FP-002, etc.)
- Technical documentation under `/technical/` directory
- API reference auto-generated from OpenAPI spec
- Development workflow documented in CLAUDE.md

### Project-Specific Commands
```bash
# Validate project-specific links
mintlify broken-links

# Preview with Go1 branding
mintlify dev

# Check documentation completeness
# (Custom script - to be developed)
```

## Maintenance Tasks

### Regular Maintenance
- [ ] Run `mintlify broken-links` monthly
- [ ] Update Mintlify CLI when new versions available
- [ ] Review and update documentation quarterly
- [ ] Test all external links quarterly

### Content Updates
- [ ] Keep API documentation in sync with implementation
- [ ] Update screenshots when UI changes
- [ ] Refresh code examples with current syntax
- [ ] Archive outdated content appropriately

## Getting Help

### Internal Team
- Check CLAUDE.md for project-specific workflows
- Review feature planning documents in `/docs/feature-planning/`
- Consult development backlog for current priorities

### External Resources
- Mintlify official documentation for platform features
- MDX documentation for syntax and component usage
- React documentation for custom component development