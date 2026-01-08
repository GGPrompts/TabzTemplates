# Three.js Landing Page Starter

A complete starter template for building immersive 3D landing pages with React Three Fiber and parallel Claude workers.

## What You Get

- **19 pre-planned beads issues** organized into 5 waves
- **CLAUDE.md** with 3D development patterns and orchestration
- **4 parallel workers** for maximum build speed
- **~20 minute build time** for a complete 3D landing page

## Tech Stack

- Next.js 15+ (App Router)
- React Three Fiber (@react-three/fiber v9)
- @react-three/drei (helpers)
- @react-three/postprocessing (effects)
- GSAP + ScrollTrigger (animations)
- Tailwind CSS v4
- shadcn/ui components
- TypeScript

## Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `business_name` | Company name | Nebula Labs |
| `tagline` | Company tagline | Building the Future of Web3D |
| `industry` | Type of business | Creative technology studio |
| `primary_color` | Brand color | purple |
| `scene_style` | 3D visual style | particles, geometric, abstract, product, environment |
| `scroll_sections` | Number of 3D scroll sections | 3 |
| `features` | Key features/services | 3D Visualization, Interactive Experiences |
| `cta_text` | Call-to-action button text | Start Your Project |

## Scene Styles

| Style | Description | Best For |
|-------|-------------|----------|
| `particles` | Flowing particle systems with mouse interaction | Tech, creative agencies |
| `geometric` | Abstract 3D shapes with smooth animation | SaaS, modern brands |
| `abstract` | Shader-based generative visuals | Art, experimental |
| `product` | Centered product with orbit/rotation | E-commerce, product launches |
| `environment` | Immersive 3D world | Gaming, immersive experiences |

## Usage

```bash
# From TabzChrome with conductor plugin
/conductor:new-project --starter=threejs-landing

# Fill in the variables when prompted
# Then run:
/conductor:bd-swarm-auto
```

## Wave Structure

| Wave | Issues | Focus | Parallelism |
|------|--------|-------|-------------|
| 0 | 1 | Asset generation | Runs with Wave 1 |
| 1 | 3 | Foundation - Next.js, R3F, design system | 3 parallel |
| 2 | 8 | 3D scene + UI components | 8 parallel |
| 3 | 6 | Polish - animations, perf, mobile, SEO | 6 parallel |
| 4 | 1 | QA checkpoint | Sequential |

## Files Generated

```
project/
├── CLAUDE.md           # Orchestration + 3D patterns
├── AGENTS.md           # Agent definitions
├── .beads/
│   ├── issues.jsonl    # Pre-populated issues
│   └── config.yaml     # Beads configuration
└── .mcp.json           # MCP server configuration
```

## Key Packages Installed

```json
{
  "dependencies": {
    "three": "^0.170.0",
    "@react-three/fiber": "^9.0.0",
    "@react-three/drei": "^10.0.0",
    "@react-three/postprocessing": "^3.0.0",
    "gsap": "^3.12.0",
    "@gsap/react": "^2.1.0",
    "leva": "^0.10.0"
  }
}
```

## 3D Development Tips

### Performance
- Use `<PerformanceMonitor>` from drei to adapt quality
- Reduce particle count on mobile
- Instance repeated geometries
- Dispose resources on unmount

### Scroll Animations
- Use GSAP ScrollTrigger with `scrub: true`
- Connect scroll progress to R3F state via `useScroll`
- Keep scroll container separate from canvas

### Responsive 3D
- Detect device capabilities with `useDetectGPU`
- Provide fallbacks for non-WebGL browsers
- Test on real mobile devices

## Requirements

- Claude Code with conductor plugin
- beads MCP server
- shadcn MCP server (for component installs)
- tabz MCP server (for screenshots)

## Example Output

A fully functional 3D landing page with:
- Interactive hero 3D scene (particles/geometric/etc)
- Smooth scroll-triggered 3D transitions
- Glass morphism UI overlays
- Mobile-responsive design
- Dark/light mode support
- Optimized for 60fps performance
