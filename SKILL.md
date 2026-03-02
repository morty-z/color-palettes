---
name: color-palettes
description: >
  30 pre-matched color palettes inspired by well-known products and design movements
  (Notion, Linear, Stripe, Cyberpunk, Nord, etc.). Each palette is a set of 10 harmonious
  hex colors: 3 backgrounds, 2 accents, 3 text colors, 2 border colors. Use when the user
  needs a color scheme for any project — websites, apps, dashboards, landing pages. Helps
  translate vague descriptions (e.g., "warm", "dark techy", "minimal", "cute pink") into
  concrete hex values that are verified to work well together.
---

# Color Palettes

30 pre-matched color combinations. Each palette has 10 hex colors that are tested to work together — proper contrast, visual harmony, consistent mood. All values extracted from production CSS.

## Palette Index

| Palette | Colors | Mode | File |
|---|---|---|---|
| Apple | White bg, blue accent (#0066cc), gray text hierarchy | light | themes/apple.md |
| Bauhaus | White bg, red (#e30613) + blue (#004d9f) + yellow (#f5a623) primary triad | light | themes/bauhaus.md |
| Bloomberg | Black bg (#000), green text (#15fa52), orange accent (#ff8c00) | dark | themes/bloomberg.md |
| Claude | Oat-beige bg (#f8f6f0), terracotta accent (#b75c3d) | light | themes/claude.md |
| Coffee | Parchment bg (#f5efe6), espresso browns (#4e342e, #6d4c41) | light | themes/coffee.md |
| Copper | Dark bronze bg (#1c1410), warm copper accent (#e8a87c) | dark | themes/copper.md |
| Cyberpunk | Deep purple bg (#0d0221), neon pink (#ff2a6d) + cyan (#05d9e8) | dark | themes/cyberpunk.md |
| Dracula | Purple bg (#282a36), multi-color: purple/pink/cyan/green/orange | dark | themes/dracula.md |
| Feishu | Light gray bg (#f7f8fa), bold blue accent (#3370ff) | light | themes/feishu.md |
| Forest | Dark green bg (#1a2e1a), leaf-green accent (#7dce82) | dark | themes/forest.md |
| GitHub | White bg, blue accent (#0969da), muted gray borders (#d1d9e0) | light | themes/github.md |
| Glacier | Ice-blue bg (#eef4fa), deep blue accent (#1565c0) | light | themes/glacier.md |
| Ink | White bg, pure black only (#000). Zero color. | light | themes/ink.md |
| Lavender | Light lavender bg (#f5f0ff), deep purple accent (#6b4c9a) | light | themes/lavender.md |
| Linear | Near-black bg (#101114), indigo accent (#5e6ad2) | dark | themes/linear.md |
| Medium | Off-white bg (#fcfcfc), green accent (#1a8917) | light | themes/medium.md |
| Mint | Mint-green bg (#f0faf5), teal accent (#1a7a5a) | light | themes/mint.md |
| Monokai | Dark olive bg (#272822), pink (#f92672) / green (#a6e22e) / yellow (#e6db74) | dark | themes/monokai.md |
| Nord | Blue-gray bg (#2e3440), frost-blue accent (#88c0d0) | dark | themes/nord.md |
| Notion | White bg, brown-black text (#37352f), red code accent (#eb5757) | light | themes/notion.md |
| NYT | Cream bg (#fdfaf6), steel-blue accent (#326891) | light | themes/nyt.md |
| Ocean | Dark navy bg (#0c2233), coral (#ff6b6b) + golden (#feca57) + blue (#54a0ff) | dark | themes/ocean.md |
| Pastel | Warm white bg (#fefcf8), pink/blue/green/amber multi-color | light | themes/pastel.md |
| Retro | Warm beige bg (#f4ecd8), seal-wax red accent (#8c2211) | light | themes/retro.md |
| Sakura | Pink-white bg (#fef7f9), cherry-pink accent (#c44569) | light | themes/sakura.md |
| Solarized | Cream bg (#fdf6e3), orange (#cb4b16) + blue (#268bd2) + cyan (#2aa198) | light | themes/solarized.md |
| Sspai | White bg, bold red accent (#d71a1b) | light | themes/sspai.md |
| Stripe | Blue-gray bg (#f6f9fc), purple accent (#635bff) | light | themes/stripe.md |
| Sunset | Warm cream bg (#fdf6ee), burnt orange accent (#c0582a) | light | themes/sunset.md |
| WeChat | White bg, WeChat green accent (#07c160) | light | themes/wechat.md |

## Workflow

1. **Match**: User describes a mood or names a product → scan the table above → present 2-3 matching palettes if vague, or match directly if specific.

2. **Load**: Read the selected palette's `.md` file from `themes/`.

3. **Output**: Give the user the 10 hex values. If they have a specific framework, output as:
   - CSS: `--color-primary: #value;`
   - Tailwind: `colors` in `tailwind.config.js`
   - JS object: for styled-components / Emotion
   - SCSS: `$color-primary: #value;`
   See `references/component-extension.md` for templates.

4. **Derive** (if needed): For component colors (button hover, card bg, input focus), derive from the palette using opacity variants. See `references/component-extension.md`.

## What Each Palette Contains

10 hex colors in a consistent structure:

| Token | What it is |
|---|---|
| background | Page background |
| surface | Card/section background |
| primary | Main accent (links, buttons) |
| accent | Secondary accent |
| text | Body text |
| text-secondary | Subheadings, captions |
| text-muted | Metadata, placeholders |
| border | Dividers, input borders |
| code-bg | Code block background |
| blockquote-border | Quote border |

## Notes

- All hex values are from verified production CSS. They are tested to work together.
- To mix palettes (e.g., "Nord backgrounds with Sakura accents"), load both files.
- For deriving component colors, read `references/component-extension.md`.
