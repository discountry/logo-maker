---
name: svg-logo-maker
description: Design and generate production-quality SVG logos in modern minimalist style. Use this skill PROACTIVELY whenever the user asks to create a logo, design a brand mark, generate an SVG icon, make a logomark, create a wordmark, build a brand identity symbol, or needs any kind of vector logo. Also triggers for requests like "make me a logo", "design an icon for my app", "create a brand symbol", "I need a logo for...", "generate SVG logo", or any task involving logo/icon/brand mark creation — even if they don't specifically mention "SVG" or "minimalist".
---

# SVG Logo Maker

Generate world-class minimalist SVG logos by first crafting a detailed design plan, then producing a single, clean SVG file as the sole deliverable.

## Reference Library

This skill bundles `assets/` containing SVG logos from leading global brands (Apple, OpenAI, Anthropic, Cursor, Google, Figma, Meta, Midjourney, Grok, DeepSeek, Ollama, Cloudflare, Microsoft, AWS, IBM, etc.). Read these files to study real-world SVG structure, path optimization, and design patterns before generating any logo.

The reference logos are located at: `{SKILL_DIR}/assets/`

## Workflow

### Phase 1 — Requirement Gathering

Extract the following from the user's request (ask for missing critical info):

| Dimension | What to capture |
|---|---|
| **Brand name** | Exact text if wordmark/lettermark is needed |
| **Industry / domain** | Tech, finance, health, food, education, creative, etc. |
| **Core values** | 2–3 keywords the brand represents (e.g. "trust", "speed", "innovation") |
| **Logo type** | Logomark (symbol only), Lettermark (initials), Wordmark (full name), or Combination |
| **Color preference** | Specific hex values, or mood-based ("warm", "corporate blue", "monochrome") |
| **Style cues** | Geometric / organic / angular / rounded / abstract / figurative |
| **Usage context** | App icon, website header, favicon, print, all-purpose |
| **Negative space** | Any clever use of negative space requested |

If the user gives minimal input (e.g., "make me a logo for a coffee shop called Bloom"), infer reasonable defaults and state your assumptions in the design plan.

### Phase 2 — Design Plan

Before writing any SVG code, produce a structured design plan. This plan is your thinking process — present it to the user for confirmation before proceeding.

#### Design Plan Template

```
## Logo Design Plan: [Brand Name]

### 1. Design Concept
- **Core metaphor**: [What real-world object/shape/idea the logo abstracts]
- **Visual narrative**: [One sentence describing what the viewer should "read" from the logo]
- **Inspiration sources**: [Which world-class logos inform this direction and why]

### 2. Form Language
- **Geometry**: [Geometric primitives used — circles, rectangles, triangles, curves]
- **Proportions**: [Grid system, golden ratio, modular scale, or freeform]
- **Negative space**: [How white space participates in the design]
- **Optical balance**: [Weight distribution and visual center of gravity]

### 3. Typography (if applicable)
- **Letterform treatment**: [Custom, geometric construction, rounded, angular]
- **Weight and spacing**: [Stroke width rationale, letter-spacing logic]

### 4. Color Strategy
- **Primary palette**: [Hex values with rationale]
- **Monochrome fallback**: [How it works in single color]
- **Color meaning**: [Psychological and cultural associations]

### 5. Technical Spec
- **viewBox**: [Dimensions, typically 0 0 24 24 or 0 0 512 512]
- **Scalability target**: [Favicon to billboard]
- **Path strategy**: [Single path vs. multi-shape, fill-rule]
```

### Phase 3 — SVG Generation

After the user approves (or if the request is straightforward enough to proceed), generate the SVG file.

#### Design Principles — Learn from the Best

Study the reference logos in `assets/` before generating. Key patterns observed:

**Apple** — The power of a single iconic silhouette. One path, one shape, universally recognized. The bite creates asymmetry that prevents confusion with a cherry.

**OpenAI** — Mathematical precision through a geometric knot/flower. Hexagonal symmetry, interlocking paths that suggest interconnection and complexity emerging from order.

**Anthropic** — Lettermark reduced to pure geometry. The "A" is constructed from three angular paths — bold, structural, unmistakable at any size.

**Cursor** — A 3D prism rendered flat. Single path creates the illusion of depth through strategic light/shadow division. The form suggests "looking into" something.

**Figma** — Modular building blocks. Five rounded rectangles in a 2×3 grid, each a different color, suggesting creative assembly and collaboration.

**Google** — The most complex letter "G" made from four simple arcs. Color segmentation creates brand recognition from pure geometry.

**Meta** — Infinity loop with gradient fills suggesting continuous flow and dimensionality.

**Midjourney** — Organic, almost calligraphic curves suggesting a sail or wave. High path complexity that still reads as a single gesture.

#### SVG Technical Standards

1. **Root element**:
   ```xml
   <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" width="512" height="512">
     <title>[Brand Name]</title>
     <!-- paths here -->
   </svg>
   ```
   Use `viewBox="0 0 512 512"` as default for logo files (good resolution for all uses). Only use `0 0 24 24` if the user specifically wants an icon-sized asset.

2. **Path optimization**:
   - Minimize control points — every point must earn its place
   - Use relative commands (`m`, `l`, `c`, `a`) where they shorten path data
   - Close paths with `z`
   - Avoid unnecessary decimal precision (2 decimal places max)
   - Combine shapes into single paths with `fill-rule="evenodd"` where possible

3. **Color implementation**:
   - Monochrome: use `fill="currentColor"` for inheritable theming
   - Brand colors: use explicit hex values directly on paths
   - Gradients: define in `<defs>` with descriptive IDs, use `<linearGradient>` or `<radialGradient>`
   - Multi-color: separate `<path>` elements per color region

4. **Structural rules**:
   - Always include `<title>` for accessibility
   - No inline styles — use attributes (`fill`, `stroke`, `fill-rule`, `stroke-width`)
   - No `<text>` elements — convert all typography to paths for universal rendering
   - No raster images or external references
   - No JavaScript or animation (static logo only)
   - No unnecessary groups (`<g>`) — flatten structure

5. **Quality checklist before output**:
   - [ ] Renders identically at 16×16 and 512×512
   - [ ] Monochrome version is still recognizable
   - [ ] No overlapping paths creating unintended color mixing
   - [ ] Total SVG file size under 5KB (ideally under 2KB)
   - [ ] Valid SVG — parseable by any browser
   - [ ] Centered within viewBox with appropriate breathing room (8–12% padding)

#### Shape Construction Techniques

**Geometric logos**: Build from circles, rectangles, and their boolean operations (union, subtract, intersect). Use the golden ratio (1:1.618) for proportions where appropriate. Snap to a grid.

**Lettermark logos**: Construct letterforms from geometric primitives. An "A" is a triangle with a horizontal bar. An "M" is two overlapping peaks. Reduce to the essential strokes that maintain legibility.

**Abstract marks**: Start from a metaphor (connection = interlocking rings, growth = ascending curve, security = shield). Abstract it through 3–5 reduction passes until only the essential gesture remains.

**Negative space logos**: Design the positive and negative shapes simultaneously. The FedEx arrow, the Spartan Golf Club golfer — the empty space carries equal or greater meaning.

### Phase 4 — Output

The **only deliverable** is the SVG file. Write it using the Write tool to the user's desired location (default: current working directory, named `{brand-name}-logo.svg`).

Do not output:
- PNG/JPG conversions
- Multiple variations (unless explicitly requested)
- Style guides or brand documents
- Explanation of the SVG code after delivery

After writing the file, briefly confirm: "Logo saved to `{path}`. Open it in a browser or SVG editor to preview."

## Common Pitfalls to Avoid

- **Over-complexity**: If you need more than 5 `<path>` elements for a minimalist logo, you've gone too far. Simplify.
- **Tiny details that vanish at small sizes**: Test mentally at 16×16. If a detail disappears, remove it.
- **Generic shapes**: A circle with a line through it is not a logo. Every shape must carry brand-specific meaning.
- **Poor optical centering**: Geometric center ≠ optical center. Pointed shapes (triangles, arrows) need to shift slightly toward the point to appear centered.
- **Inconsistent stroke weights**: If mixing filled shapes with strokes, maintain consistent visual weight.
- **Forgetting monochrome**: Every logo must work in single color. Design for monochrome first, add color second.

## Style Direction by Industry

| Industry | Typical Form Language | Color Direction |
|---|---|---|
| Tech / AI | Geometric, angular, interconnected nodes | Blues, gradients, monochrome |
| Finance | Stable, symmetrical, strong horizontals | Navy, gold, dark green |
| Health | Organic curves, rounded, flowing | Greens, teals, warm whites |
| Food & Beverage | Warm, hand-crafted feel, circular | Earthy tones, reds, oranges |
| Education | Open, ascending, book/light metaphors | Blues, greens, warm yellows |
| Creative / Design | Asymmetric, bold, unconventional | Vibrant, multi-color, black |
| E-commerce | Dynamic, forward-moving, arrow motifs | Oranges, blues, clean whites |
| Gaming | Sharp, angular, energetic | Neons, dark backgrounds, high contrast |

These are starting points, not rules. Break conventions when the brand demands it.
