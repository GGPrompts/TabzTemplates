# TabzTemplates

Reusable project starter templates for Claude Code with pre-configured workflows, beads issues, and plugin setups.

## Available Starters

| Starter | Description | Build Time |
|---------|-------------|------------|
| [saas-landing](starters/saas-landing/) | SaaS landing page with dashboards | ~15 min |
| [threejs-landing](starters/threejs-landing/) | Interactive 3D landing with R3F + scroll animations | ~20 min |

## Usage

```bash
# From any Claude Code session with conductor plugin
/conductor:new-project --starter=saas-landing

# Or manually copy and customize
cp -r starters/saas-landing/templates/* /path/to/new/project/
```

## Creating New Starters

1. Create a folder in `starters/`
2. Add `manifest.yaml` with variables, plugins, workflow config
3. Add templates in `templates/` folder with `.tmpl` extension
4. Use `{{variable_name}}` placeholders

### Manifest Structure

```yaml
name: my-starter
description: What this builds
version: 1.0.0

variables:
  project_name:
    prompt: "Project name"
    example: "My App"

plugins:
  - tabz-chrome:conductor

mcp_servers:
  - beads

workflow:
  model: opus
  review: code
  parallel_workers: 4

generates:
  - CLAUDE.md
  - .beads/issues.jsonl
```

## Template Syntax

Templates use simple `{{variable}}` replacement:

```markdown
# {{project_name}} - Built with Claude

Business: {{business_name}}
Location: {{location}}
```

## Component Libraries

These external repos provide UI components and design inspiration that can be layered on top of starters:

| Library | Content | Use Case |
|---------|---------|----------|
| [portfolio-style-guides](../portfolio-style-guides/) | 147 page templates + 44 UI components | SaaS, marketing, portfolio pages |
| [TUITemplate](../TUITemplate/) | Go/Bubbletea starters | Terminal UI applications |

**Note:** These are reference libraries, not beads starters. Copy components as needed during your build.

---

## Roadmap

- [ ] `cli-tool` - Command-line tool with tests
- [ ] `python-api` - FastAPI backend
- [ ] `chrome-extension` - Browser extension
- [ ] `monorepo` - Turborepo multi-package
- [ ] `mobile-app` - React Native
