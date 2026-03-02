# Applying Colors to UI

How to output palette colors in different frameworks, and how to derive UI component colors from the 10-color palette.

## Framework Output Templates

When outputting a palette's colors for a specific framework, use these templates:

### CSS Custom Properties

```css
:root {
  --color-background: {{background}};
  --color-surface: {{surface}};
  --color-primary: {{primary}};
  --color-accent: {{accent}};
  --color-text: {{text}};
  --color-text-secondary: {{text-secondary}};
  --color-text-muted: {{text-muted}};
  --color-border: {{border}};

  --font-heading: {{font-heading}};
  --font-body: {{font-body}};
  --font-code: {{font-code}};

  --radius-block: {{radius-block}};
  --radius-inline: {{radius-inline}};
}
```

### Tailwind Config

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        background: '{{background}}',
        surface: '{{surface}}',
        primary: '{{primary}}',
        accent: '{{accent}}',
        body: '{{text}}',
        secondary: '{{text-secondary}}',
        muted: '{{text-muted}}',
        border: '{{border}}',
      },
      fontFamily: {
        heading: [/* {{font-heading}} split into array */],
        body: [/* {{font-body}} split into array */],
        code: [/* {{font-code}} split into array */],
      },
      borderRadius: {
        block: '{{radius-block}}',
        inline: '{{radius-inline}}',
      },
    },
  },
};
```

### JS Theme Object (styled-components / Emotion)

```js
const theme = {
  colors: {
    background: '{{background}}',
    surface: '{{surface}}',
    primary: '{{primary}}',
    accent: '{{accent}}',
    text: '{{text}}',
    textSecondary: '{{text-secondary}}',
    textMuted: '{{text-muted}}',
    border: '{{border}}',
  },
  fonts: { heading: '{{font-heading}}', body: '{{font-body}}', code: '{{font-code}}' },
  radii: { block: '{{radius-block}}', inline: '{{radius-inline}}' },
};
```

### SCSS Variables

```scss
$color-background: {{background}};
$color-surface: {{surface}};
$color-primary: {{primary}};
$color-accent: {{accent}};
$color-text: {{text}};
$color-text-secondary: {{text-secondary}};
$color-border: {{border}};
$font-heading: {{font-heading}};
$font-body: {{font-body}};
$radius-block: {{radius-block}};
```

## Deriving Component Colors

The palette gives you 10 base colors. Use these rules to derive colors for UI components. **Never invent new colors — derive from the palette.**

### Buttons

- **Primary**: `background: primary`, `color: background`, `border-radius: radius-block`
- **Secondary/Outline**: `background: transparent`, `color: primary`, `border: 1px solid primary`
- **Ghost**: `background: transparent`, `color: text-secondary`, hover `background: surface`
- **Hover**: Light themes darken primary ~10%; dark themes lighten ~10%. Or use `accent`.
- **Disabled**: `opacity: 0.5`, `cursor: not-allowed`

### Cards

- `background: surface`, `border: 1px solid border`, `border-radius: radius-block`
- **Elevated**: Add subtle shadow matching the aesthetic's mood
- **Interactive**: hover `border-color: primary`

### Form Inputs

- `background: background`, `border: 1px solid border`, `border-radius: radius-inline`
- **Focus**: `border-color: primary`, `box-shadow: 0 0 0 3px {{primary}}20` (12% opacity)
- **Placeholder**: `color: text-muted`
- **Label**: `color: text-secondary`

### Navigation

- **Active link**: `color: primary`
- **Inactive link**: `color: text-secondary`, hover `color: text`
- **Nav background**: `background` or `surface`

### Badges & Tags

- Background: `primary` at 10% opacity (append `1A` to hex)
- Text: `color: primary`, `border-radius: radius-inline`

### General Principles

- **Opacity variants**: For lighter versions of any color, use hex alpha: 10%=`1A`, 20%=`33`, 30%=`4D`, 50%=`80`
- **Hover direction**: Light themes darken; dark themes lighten
- **Radius consistency**: Maintain the aesthetic's corner strategy everywhere. Sharp (0px) = sharp everywhere. Rounded (12px) = rounded everywhere.
- **Font inheritance**: If the aesthetic uses serif headings, UI headings (modal titles, card headers) should also use serif.
