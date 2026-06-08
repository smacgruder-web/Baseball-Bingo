---
name: Vintage Modern Ballpark
colors:
  surface: '#f9faf5'
  surface-dim: '#d9dad6'
  surface-bright: '#f9faf5'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f3f4ef'
  surface-container: '#edeee9'
  surface-container-high: '#e8e9e4'
  surface-container-highest: '#e2e3de'
  on-surface: '#1a1c19'
  on-surface-variant: '#414941'
  inverse-surface: '#2f312e'
  inverse-on-surface: '#f0f1ec'
  outline: '#727971'
  outline-variant: '#c1c9bf'
  surface-tint: '#3d6748'
  primary: '#033016'
  on-primary: '#ffffff'
  primary-container: '#1d472a'
  on-primary-container: '#88b590'
  inverse-primary: '#a3d2ab'
  secondary: '#ab3334'
  on-secondary: '#ffffff'
  secondary-container: '#ff716d'
  on-secondary-container: '#700310'
  tertiary: '#735c00'
  on-tertiary: '#ffffff'
  tertiary-container: '#cea700'
  on-tertiary-container: '#4e3d00'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#bfeec5'
  primary-fixed-dim: '#a3d2ab'
  on-primary-fixed: '#00210c'
  on-primary-fixed-variant: '#254f31'
  secondary-fixed: '#ffdad7'
  secondary-fixed-dim: '#ffb3ae'
  on-secondary-fixed: '#410005'
  on-secondary-fixed-variant: '#8a1a1f'
  tertiary-fixed: '#ffe084'
  tertiary-fixed-dim: '#eec209'
  on-tertiary-fixed: '#231b00'
  on-tertiary-fixed-variant: '#574500'
  background: '#f9faf5'
  on-background: '#1a1c19'
  surface-variant: '#e2e3de'
typography:
  display-lg:
    fontFamily: Domine
    fontSize: 48px
    fontWeight: '700'
    lineHeight: 56px
    letterSpacing: -0.02em
  display-lg-mobile:
    fontFamily: Domine
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Domine
    fontSize: 24px
    fontWeight: '700'
    lineHeight: 32px
  headline-sm:
    fontFamily: Domine
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
  body-lg:
    fontFamily: Work Sans
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Work Sans
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  label-bold:
    fontFamily: Work Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
    letterSpacing: 0.05em
  caption:
    fontFamily: Work Sans
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 8px
  xs: 4px
  sm: 12px
  md: 24px
  lg: 48px
  xl: 64px
  grid-gutter: 16px
  grid-margin-mobile: 16px
  grid-margin-desktop: 32px
---

## Brand & Style
The brand personality balances the nostalgic, tactile warmth of a sunny afternoon at the stadium with the precision of a modern data-driven sports app. It is celebratory, athletic, and organized. The target audience includes both casual spectators and die-hard baseball fans who appreciate the ritual of scorekeeping.

The design style is a hybrid of **Minimalism** and **Tactile/Skeuomorphism**. We avoid heavy gloss in favor of "paper and ink" aesthetics. Surfaces utilize subtle pinstripe patterns and paper-grain textures to evoke vintage scorecards, while the UI logic remains strictly modern with generous whitespace and high-contrast interaction states. The emotional response should be one of "heritage meets playfulness."

## Colors
This design system uses a palette rooted in the natural landscape of a baseball diamond.

- **Primary (Stadium Green):** Used for key structural headers, primary action buttons, and "BINGO" success states.
- **Secondary (Clay Red):** Used for highlighting errors, urgent alerts, or "Away Team" markers.
- **Accent (Turf Yellow):** Reserved for high-priority interactive cues, gold-star moments, and "Free Space" indicators.
- **Background (Antique Cream):** A warm, non-white base that reduces eye strain and mimics the color of aged cardstock or felt.
- **Text (Off-Black):** A deep slate blue-black used to maintain high legibility against cream and green backgrounds.

## Typography
The typography system relies on **Domine** to provide the "Athletic Slab" feel. Its sturdy serifs evoke classic jerseys and newspaper headlines. For the body and functional labels, **Work Sans** provides a neutral, highly legible contrast that ensures the app remains accessible during fast-paced gameplay. 

Large display sizes should use tighter letter spacing to mimic vintage woodblock printing. Labels and small UI cues use increased letter spacing and uppercase styling to improve scan-ability against busy game backgrounds.

## Layout & Spacing
The layout follows a **Fixed Grid** philosophy for the Bingo card itself to maintain the iconic square proportions, while the surrounding UI uses a **Fluid Grid**.

- **Bingo Card:** Always centered. On mobile, the card scales to the width of the screen minus the `grid-margin-mobile`. On desktop, it is capped at 600px wide.
- **Rhythm:** An 8px base unit drives all padding and margins.
- **Gutters:** Standardized at 16px to ensure "tappability" of cells remains high, preventing accidental selections.
- **Responsive Behavior:** On mobile, secondary stats and "Recently Called" lists reflow below the bingo card. On desktop, these move into a side-rail (right-aligned).

## Elevation & Depth
This design system avoids realistic 3D shadows. Instead, it uses **Tonal Layers** and **Subtle Outlines** to create a "pressed paper" look.

- **Level 0 (Base):** Antique Cream with a very faint, repeating pinstripe pattern (opacity 5%) or a grain texture.
- **Level 1 (Cards/Tiles):** White-ish surfaces with a 1px solid border in a slightly darker cream or muted green.
- **Level 2 (Active/Pressed):** Elements that are "selected" (like a marked Bingo cell) should appear physically pressed into the surface. This is achieved with a subtle inner shadow (inset) rather than a drop shadow.
- **Level 3 (Modals):** Large, soft ambient shadows (15% opacity Primary Color) to lift them off the "paper" background.

## Shapes
We use a **Rounded** shape language (0.5rem base) to soften the industrial feel of the slab-serif typography. 

- **Bingo Cells:** Use `rounded-md` (8px) to create distinct individual units that feel like physical tokens.
- **Primary Buttons:** Use `rounded-xl` (24px) or full pill-shapes to differentiate them from the square-ish grid cells.
- **Input Fields:** Use `rounded-md` (8px) for a structured, scorecard feel.

## Components

### Bingo Cells
The core component. In its default state, it is a `Level 1` card with `body-md` text. When selected, it transitions to `Primary Green` background with white text and an `inset` shadow. The "Free Space" cell uses the `Turf Yellow` accent color by default.

### Buttons
- **Primary Action:** `Primary Green` background, white uppercase `label-bold` text. High-contrast and substantial.
- **Secondary Action:** Transparent background with a 2px `Primary Green` border. 
- **Tactile State:** On hover/active, buttons should shift 2px downward to mimic a physical "click" feel.

### Chips & Tags
Used for game categories (e.g., "In-field", "Batting"). These use `Secondary Clay Red` or `Primary Green` with 20% opacity backgrounds to remain legible but subordinate to the main bingo card.

### Input Fields
Stylized to look like a scorecard entry line. A bottom-only border is preferred for a "written-on" look, utilizing the `Off-Black` color for the label and input text.

### Progress Bars
Used for tracking "Games Won" or "Innings." These should use a "stitching" visual metaphor—dotted lines or segmented blocks rather than a smooth fluid fill—to stay within the vintage athletic aesthetic.