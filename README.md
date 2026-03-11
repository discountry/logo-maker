# Logo Maker

An AI agent skill for designing and generating production-quality SVG logos. Give your AI coding agent the ability to create minimalist, scalable vector logos informed by world-class brand design patterns.

This skill follows the [Agent Skills](https://agentskills.io/) format.

## Available Skills

### svg-logo-maker

Design and generate production-quality SVG logos in modern minimalist style using **svg.js** for programmatic construction and **browser-based visual verification**.

**Use when:**
- "Make me a logo"
- "Design an icon for my app"
- "Create a brand symbol"
- "I need a logo for..."
- "Generate SVG logo"

**Workflow:**
1. **Requirement Gathering** — Extracts brand name, industry, values, color preferences, and style cues
2. **Design Plan** — Produces a structured design plan covering concept, form language, typography, color strategy, and construction approach
3. **SVG Construction** — Creates a temporary HTML workspace using svg.js to programmatically draw the logo with high-level shape APIs (`rect()`, `circle()`, `polygon()`, `group()`, `gradient()`, `mask()`, `transform()`)
4. **Browser Preview & Iteration** — Opens the workspace in a browser, takes screenshots for visual verification, and iterates on the design until it matches the plan
5. **SVG Export & Cleanup** — Extracts the rendered SVG from the browser, cleans svg.js artifacts, and saves a production-ready `.svg` file

**Why svg.js instead of raw SVG?** AI excels at writing JavaScript function calls but struggles with precise SVG path coordinates. svg.js provides a high-level API that maps naturally to programmatic construction, while the browser rendering enables visual feedback loops — producing dramatically better results.

**Design coverage:**
- Logomarks (symbol only)
- Lettermarks (initials)
- Wordmarks (full name)
- Combination marks
- Industry-specific style guidance (Tech, Finance, Health, Food, Education, Creative, E-commerce, Gaming)

## Installation

```bash
npx skills add discountry/logo-maker
```

To install this specific skill:

```bash
npx skills add discountry/logo-maker --skill svg-logo-maker
```

## Usage

Once installed, the agent activates the skill automatically when you ask for logo-related tasks.

**Examples:**

```
Make me a minimalist logo for a coffee shop called Bloom
```

```
Design a geometric logomark for an AI startup called NexusAI, using monochrome
```

```
Create a lettermark logo for "DW" in corporate blue
```

## Skill Structure

```
skills/svg-logo-maker/
├── SKILL.md          # Agent instructions and design methodology
└── assets/           # 20+ reference SVG logos from world-class brands
```

## License

MIT
