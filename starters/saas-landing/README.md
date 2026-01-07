# SaaS Landing Page Starter

A complete starter template for building SaaS landing pages with parallel Claude workers.

## What You Get

- **19 pre-planned beads issues** organized into 5 waves
- **CLAUDE.md** with orchestration instructions
- **4-5 parallel workers** for maximum build speed
- **~15 minute build time** for a complete landing page

## Tech Stack

- Next.js 14+ (App Router)
- Tailwind CSS v4
- shadcn/ui components
- TypeScript

## Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `business_name` | Company name | Sunshine Rides |
| `tagline` | Company tagline | Your Journey, Our Priority |
| `industry` | Type of business | Transportation service |
| `location` | Primary location | Colorado |
| `primary_color` | Brand color | orange |
| `service_areas` | Service locations | Denver, Boulder, Fort Collins |
| `phone` | Contact number | 970-555-0199 |
| `features` | Key features | Wheelchair accessible, Medical transport |

## Usage

```bash
# From TabzChrome
/conductor:new-project --starter=saas-landing

# Fill in the variables when prompted
# Then run:
/conductor:bd-swarm-auto
```

## Wave Structure

| Wave | Issues | Focus |
|------|--------|-------|
| 0 | 1 | Asset generation (parallel with Wave 1) |
| 1 | 3 | Foundation - scaffolding, design system, layout |
| 2 | 10 | UI Components - header, hero, features, dashboards |
| 3 | 4 | Polish - dark mode, animations, mobile, SEO |
| 4 | 1 | QA checkpoint |

## Files Generated

```
project/
├── CLAUDE.md           # Orchestration instructions
├── AGENTS.md           # Agent definitions (optional)
├── .beads/
│   ├── issues.jsonl    # Pre-populated issues
│   ├── config.yaml     # Beads configuration
│   └── PRIME.md        # Workflow instructions
└── .mcp.json           # MCP server configuration
```

## Requirements

- Claude Code with conductor plugin
- beads MCP server
- shadcn MCP server (optional, for component installs)
- tabz MCP server (for browser automation)
