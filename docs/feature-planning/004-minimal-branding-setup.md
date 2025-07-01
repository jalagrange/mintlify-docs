# Feature Planning 004: Minimal Branding Setup

## Feature Overview

Make minimal but essential branding changes to remove Mintlify template references and set up basic project identity. Focus only on what's needed to start creating developer documentation professionally.

## Objectives

1. Remove obvious Mintlify starter template references
2. Update project name and basic identity
3. Set up navigation structure for technical documentation
4. Keep existing assets temporarily until proper branding is available

## Scope

**Minimal changes only:**
- Update project name and title
- Remove Mintlify external links
- Set up basic navigation for developer docs
- Keep existing colors/logos as placeholders

**Explicitly out of scope:**
- Custom logo design
- Complete color scheme overhaul
- Hero images and marketing assets
- Full branding guidelines implementation

## Technical Approach

### 1. Basic Configuration Updates (`docs.json`)

#### Project Identity (Minimal Changes)
```json
{
  "name": "Dynamic Quiz Generator",
  "colors": {
    "primary": "#0066CC",
    "light": "#3399FF", 
    "dark": "#0052A3"
  }
}
```

#### Navigation for Developer Focus
```json
{
  "navigation": {
    "tabs": [
      {
        "tab": "Getting Started",
        "groups": [
          {
            "group": "Overview", 
            "pages": ["index", "quickstart"]
          }
        ]
      },
      {
        "tab": "Technical Documentation",
        "groups": [
          {
            "group": "Architecture",
            "pages": ["technical/architecture/system-overview"]
          },
          {
            "group": "Development",
            "pages": ["technical/development/local-setup"]
          }
        ]
      },
      {
        "tab": "API Reference",
        "groups": [
          {
            "group": "Getting Started",
            "pages": ["api-reference/introduction"]
          }
        ]
      }
    ]
  }
}
```

#### Remove Mintlify Links
```json
{
  "navigation": {
    "global": {
      "anchors": [
        {
          "anchor": "GitHub",
          "href": "https://github.com/go1/dynamic-quiz-creator",
          "icon": "github"
        }
      ]
    }
  },
  "navbar": {
    "links": [
      {
        "label": "Support",
        "href": "mailto:support@go1.com"
      }
    ]
  },
  "footer": {
    "socials": {
      "github": "https://github.com/go1"
    }
  }
}
```

### 2. Content Updates (Essential Only)

#### Landing Page (`index.mdx`) - Basic Update
```mdx
---
title: Dynamic Quiz Generator
description: Technical documentation for the Dynamic Quiz Generator system
---

# Dynamic Quiz Generator

AI-powered assessment tool for personalized learning paths.

## Documentation Sections

<CardGroup cols={2}>
  <Card title="Architecture" href="/technical/architecture/system-overview" icon="sitemap">
    System design and component overview
  </Card>
  <Card title="API Reference" href="/api-reference/introduction" icon="code">
    API endpoints and integration guide
  </Card>
</CardGroup>

> **Note**: This documentation is actively being developed. Check back frequently for updates.
```

#### Quickstart (`quickstart.mdx`) - Developer Focus
```mdx
---
title: Quick Start
description: Get started with Dynamic Quiz Generator development
---

# Quick Start Guide

This guide helps developers understand and work with the Dynamic Quiz Generator system.

## Prerequisites

- Node.js 18+
- Understanding of REST APIs
- Familiarity with AI/ML concepts

## Next Steps

1. **Architecture Overview**: Understanding the [system architecture](/technical/architecture/system-overview)
2. **API Reference**: Explore the [API documentation](/api-reference/introduction)
3. **Development Setup**: Set up your [local environment](/technical/development/local-setup)
```

### 3. Clean Up Template Content

#### Files to Remove
- All Plant Store API examples in `/api-reference/endpoint/`
- Template content in `/essentials/` (keep structure, placeholder content)
- Sample OpenAPI specification

#### Files to Keep (Update Headers Only)
- Keep existing logo files as placeholders
- Keep favicon temporarily
- Keep color scheme (update to blue)

## Implementation Steps

### Day 1: Configuration
1. Update `docs.json` with minimal changes
2. Test navigation structure locally
3. Remove external Mintlify links

### Day 2: Content
1. Update landing page with basic project info
2. Update quickstart for developers
3. Remove Plant Store API examples

### Day 3: Clean Up
1. Remove unused template files
2. Test all navigation links
3. Verify no broken references

## Acceptance Criteria

### Must Have
- [ ] Project name updated to "Dynamic Quiz Generator"
- [ ] No external links to Mintlify documentation/community
- [ ] Navigation structure supports technical documentation  
- [ ] Landing page explains project purpose
- [ ] No Plant Store API examples remain

### Should Have
- [ ] Blue color scheme instead of green
- [ ] Working quickstart guide for developers
- [ ] All navigation links functional

### Nice to Have
- [ ] Placeholder content hints at future sections
- [ ] Clean, professional appearance

## Files to Modify

### Configuration
- `docs.json` - Update name, colors, navigation, external links

### Content  
- `index.mdx` - Basic landing page for developers
- `quickstart.mdx` - Developer-focused getting started
- `README.md` - Update project description

### Clean Up
- Delete `/api-reference/endpoint/*.mdx` (Plant Store examples)
- Delete `/api-reference/openapi.json` (Plant Store API)

## Testing Approach

1. Run `mintlify dev` after each change
2. Check all navigation links work
3. Verify no 404 errors
4. Test in both light/dark modes

## Timeline

**Total: 3 days maximum**
- Much faster than comprehensive branding
- Gets documentation ready for developer content
- Can iterate on branding later

## Benefits of Minimal Approach

1. **Speed**: Ready in days, not weeks
2. **Focus**: Prioritizes developer documentation needs
3. **Iterative**: Can enhance branding later without blocking development
4. **Professional**: Removes template appearance without major asset creation

## Next Steps After Completion

This minimal setup enables immediate work on:
- Technical architecture documentation
- API specifications
- Developer guides
- System design documentation

Comprehensive branding can be tackled later when assets and guidelines are available.