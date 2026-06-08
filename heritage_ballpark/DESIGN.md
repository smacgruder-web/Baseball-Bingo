---
name: Heritage Ballpark
colors:
  surface: '#fcf9f8'
  surface-dim: '#dcd9d9'
  surface-bright: '#fcf9f8'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f6f3f2'
  surface-container: '#f0eded'
  surface-container-high: '#eae7e7'
  surface-container-highest: '#e4e2e1'
  on-surface: '#1b1c1c'
  on-surface-variant: '#414941'
  inverse-surface: '#303030'
  inverse-on-surface: '#f3f0f0'
  outline: '#727971'
  outline-variant: '#c1c9bf'
  surface-tint: '#3d6748'
  primary: '#033016'
  on-primary: '#ffffff'
  primary-container: '#1d472a'
  on-primary-container: '#88b590'
  inverse-primary: '#a3d2ab'
  secondary: '#a43c2b'
  on-secondary: '#ffffff'
  secondary-container: '#fd7e67'
  on-secondary-container: '#71170a'
  tertiary: '#292923'
  on-tertiary: '#ffffff'
  tertiary-container: '#403f38'
  on-tertiary-container: '#acaaa1'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#bfeec5'
  primary-fixed-dim: '#a3d2ab'
  on-primary-fixed: '#00210c'
  on-primary-fixed-variant: '#254f31'
  secondary-fixed: '#ffdad4'
  secondary-fixed-dim: '#ffb4a6'
  on-secondary-fixed: '#3f0200'
  on-secondary-fixed-variant: '#842416'
  tertiary-fixed: '#e5e2d9'
  tertiary-fixed-dim: '#c9c6bd'
  on-tertiary-fixed: '#1c1c16'
  on-tertiary-fixed-variant: '#484740'
  background: '#fcf9f8'
  on-background: '#1b1c1c'
  surface-variant: '#e4e2e1'
typography:
  display-lg:
    fontFamily: Domine
    fontSize: 48px
    fontWeight: '700'
    lineHeight: 56px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Domine
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
  headline-lg-mobile:
    fontFamily: Domine
    fontSize: 28px
    fontWeight: '700'
    lineHeight: 36px
  headline-md:
    fontFamily: Domine
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
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
  label-md:
    fontFamily: Work Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
    letterSpacing: 0.05em
  stats-number:
    fontFamily: Domine
    fontSize: 36px
    fontWeight: '700'
    lineHeight: 44px
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  base: 8px
  xs: 4px
  sm: 12px
  md: 24px
  lg: 48px
  xl: 80px
  container-max: 1280px
  gutter: 24px
---

## Brand & Style
This design system captures the nostalgic essence of a vintage ballpark and reinterprets it through a sophisticated, modern lens. The brand personality is authoritative yet welcoming, evocative of classic sports journalism and the physical textures of a stadium. 

The aesthetic is a hybrid of **Minimalism** and **Glassmorphism**. We use expansive whitespace and refined typography to provide clarity for complex data, while employing "stadium-glow" effects—subtle, luminous backlighting—and glass-panel surfaces to create depth and modern polish. The emotional response should be one of timeless reliability and premium craftsmanship.

## Colors
The palette is rooted in the "Vintage Modern" aesthetic. 
- **Primary (Stadium Green):** Used for primary actions, headers, and brand-heavy backgrounds.
- **Secondary (Clay Red):** Reserved for highlights, notifications, and interactive accents that require contrast.
- **Background (Antique Cream):** Replaces pure white to reduce eye strain and reinforce the "aged paper" editorial feel.
- **Neutral (Charcoal):** Used for body text and structural borders to maintain high legibility against the cream background.
- **Stadium Glow:** A soft, diffused radial gradient using a lighter tint of the primary green, used behind glass panels to simulate evening stadium lights.

## Typography
Typography follows a strict hierarchy inspired by mid-century sports broadsheets. **Domine** is the cornerstone of the system, providing a sturdy, authoritative serif presence for all headings and key data points. 

**Work Sans** serves as the functional workhorse for body copy and UI labels, offering a clean, contemporary contrast that ensures the design doesn't feel overly "retro." Use all-caps with generous letter spacing for labels and utility text to mimic the feel of an old-school scoreboard.

## Layout & Spacing
The layout uses a **fixed grid** system for desktop (12 columns) to maintain an editorial, structured feel. On mobile devices, it transitions to a fluid single-column layout with 16px side margins.

Spacing follows an 8px base unit. We prioritize wide gutters and generous "stadium-floor" margins to prevent the interface from feeling cluttered, even when displaying dense statistics. Content should be grouped into distinct "sections" separated by significant vertical padding (lg or xl) to evoke the pacing of a printed newspaper.

## Elevation & Depth
Depth is achieved through the **Glassmorphism** model. 
- **Glass Panels:** Cards and forms use a semi-transparent fill of Antique Cream (85-90% opacity) with a `backdrop-filter: blur(12px)`.
- **Stadium Glow:** Important containers (like login forms and featured stats) should have a subtle outer glow using the primary green at a very low opacity (10-15%) and a high blur radius (40px+).
- **Outlines:** Instead of heavy shadows, use 1px inner borders with a light opacity to define the edges of glass surfaces, giving them a "etched" look.

## Shapes
The shape language is **Soft (0.25rem)**. This subtle rounding mimics the slightly worn corners of vintage ticket stubs and programs. We avoid fully round or "pill" shapes for primary containers to maintain the formal, structured feeling of a classic ballpark. Interactive elements like buttons may use `rounded-lg` (0.5rem) to differentiate them from static containers.

## Components
- **Buttons:** Primary buttons use a solid Stadium Green fill with white Work Sans text (bold). Secondary buttons use a Clay Red border with no fill.
- **Glass Cards:** Used for stats and profile information. Features a 1px border in a darker shade of Cream and the signature backdrop blur.
- **Input Fields:** Styled as "etched" into the background with a 1px bottom-border only, or a very light 4-sided border for the glass-panel login forms.
- **Stats Chips:** Small, rounded-sm containers with a Clay Red background and white text, used for high-priority live updates.
- **Data Tables:** Clean, no vertical lines. Horizontal dividers should be thin (1px) and use a light neutral tone. Header rows should use Domine in a smaller, bold size.
- **Login Forms:** Centered glass panels utilizing the "stadium-glow" effect to draw the eye. High contrast between the input labels and the semi-transparent surface is required for accessibility.