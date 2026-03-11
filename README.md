# Logo Maker

An AI agent skill for designing and generating production-quality SVG logos. Give your AI coding agent the ability to create minimalist, scalable vector logos informed by world-class brand design patterns.

This skill follows the [Agent Skills](https://agentskills.io/) format.

## Available Skills

### svg-logo-maker

Design and generate production-quality SVG logos in modern minimalist style. Includes a reference library of 20+ SVG logos from leading global brands (Apple, OpenAI, Anthropic, Cursor, Google, Figma, Meta, Midjourney, etc.) that the agent studies before generating.

**Use when:**
- "Make me a logo"
- "Design an icon for my app"
- "Create a brand symbol"
- "I need a logo for..."
- "Generate SVG logo"

**Workflow:**
1. **Requirement Gathering** — Extracts brand name, industry, values, color preferences, and style cues
2. **Design Plan** — Produces a structured design plan covering concept, form language, typography, color strategy, and technical spec
3. **SVG Generation** — Generates optimized SVG following strict technical standards (minimal paths, `currentColor` theming, accessibility `<title>`, no raster/JS/animation)
4. **Output** — Writes a single clean SVG file, ready for use from favicon to billboard

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
