# Design System Specification: Editorial Neo-Brutalism

## 1. Overview & Creative North Star: "The Modern Architect"
This design system rejects the "polite" UI of the last decade. It is built on a Creative North Star of **The Modern Architect**: a philosophy where the structural bones of the interface are not hidden, but celebrated. 

We move beyond "standard" Neo-Brutalism by treating the screen as a physical broadsheet. We leverage intentional asymmetry, extreme contrast, and a "thick-stroke" aesthetic to create an experience that feels raw, functional, and authoritative. This is not just a digital interface; it is a high-end editorial statement. We break the template look by utilizing overlapping geometric containers and a typography scale that demands attention.

---

## 2. Colors & Surface Logic
The palette is rooted in a high-contrast relationship between deep indigo (`primary`) and a clean, sterile neutral base (`surface`).

### The Palette
- **Primary Base:** `#2c29bb` (Primary) | `#4647d3` (Primary Container)
- **Secondary/Accent:** `#7b41b4` (Secondary) | `#c185fd` (Secondary Container)
- **Neutrals:** `#f8f9fb` (Surface) | `#ffffff` (Surface Container Lowest)
- **The Ink:** `#191c1e` (On Surface / Border)

### The "Visible Skeleton" Rule
In this system, we ignore the industry trend of invisible borders. 
- **The Stroke:** Every major container must use a **2px or 3px solid black border** (`#191c1e`). 
- **The "No-Line" Exception:** Do not use 1px hairlines. If a border isn't thick and intentional, it shouldn't exist. Use background shifts between `surface-container-low` (`#f2f4f6`) and `surface-container-highest` (`#e0e3e5`) to define internal sub-sections without adding visual clutter.

### Signature Textures
To ensure the design feels premium rather than "cheap," apply a subtle linear gradient to main CTAs transitioning from `primary` (`#2c29bb`) to `primary-container` (`#4647d3`). This adds a tectonic depth to the otherwise flat geometry.

---

## 3. Typography: Editorial Authority
We utilize two distinct voices: **Space Grotesk** for structural impact and **Work Sans** for functional clarity.

- **Display & Headlines (Space Grotesk):** These are your "shouting" layers. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) to create a sense of massive scale. 
- **Titles & Body (Work Sans):** These provide the "architectural notes." Work Sans offers high legibility at `body-md` (0.875rem) and `title-sm` (1rem). 
- **The Label Logic:** All labels (`label-md`) should be set in Space Grotesk, Uppercase, with a slight tracking increase (+0.05em) to differentiate them from body content.

---

## 4. Elevation & Depth: The Hard-Shadow Principle
Traditional "soft" shadows have no place here. We communicate depth through **Hard-Cast Geometry**.

- **The Stacking Principle:** Use `surface-container-lowest` (`#ffffff`) for cards sitting on top of `surface` (`#f8f9fb`). 
- **Hard Shadows:** Instead of blurs, use an offset solid box. A "floating" card should have a 4px or 8px offset (bottom-right) filled with the `on-surface` color (`#191c1e`) at 100% opacity. 
- **The "Ghost Border" Fallback:** For disabled or secondary states, use the `outline-variant` (`#c7c4d7`) at 20% opacity.
- **Glassmorphism:** Reserved exclusively for navigation overlays. Use a `surface` color with 80% opacity and a 12px backdrop-blur to allow the bold underlying geometry to bleed through.

---

## 5. Components

### Buttons
- **Primary:** High-contrast `primary` background, white text, 2px black border. On hover, shift the hard shadow from 4px to 0px (simulating a physical "press").
- **Secondary:** `secondary_container` (#c185fd) background, black text, 2px black border.
- **Corner Radius:** Strictly `0px`. Everything is sharp.

### Input Fields
- **Default:** `surface_container_lowest` (#ffffff) background, 2px black border.
- **Focus State:** 4px hard shadow (`primary`) and a bold 3px border.
- **Error:** Background shifts to `error_container` (#ffdad6) with an `error` (#ba1a1a) border.

### Cards & Lists
- **Forbid Dividers:** Never use a line to separate list items. Use the **Spacing Scale** (specifically `spacing-4` / 1.4rem) to create vertical "breathing room." 
- **Nesting:** Place a `surface_container_high` card inside a `surface` section to create hierarchy via tonal shift rather than lines.

### Additional Component: The "Ticker"
Given the editorial nature, use a horizontal scrolling "Ticker" component for secondary labels or alerts, featuring `on_secondary_container` text on a `secondary_container` background with a 2px top/bottom border.

---

## 6. Do's and Don'ts

### Do:
- **Use Asymmetry:** Place a large `display-lg` headline off-center to create visual tension.
- **Exaggerate Spacing:** Use `spacing-20` (7rem) between major sections to let the bold elements breathe.
- **Overlap Elements:** Let a card or image partially "break" the border of its parent container for a custom, non-templated feel.

### Don't:
- **Don't Use Border-Radius:** Even a 2px radius destroys the "Architectural" North Star. Keep it `0px`.
- **Don't Use Soft Shadows:** Avoid CSS `box-shadow` with blur radii. If it’s not a hard-edge offset, it doesn’t belong.
- **Don't Mix Icons:** Use only high-stroke, geometric icon sets (2px minimum stroke weight) to match the border thickness of the UI.

### Accessibility Note:
While Neo-Brutalism is high-contrast by nature, always ensure that text over `primary` or `secondary` containers maintains a 4.5:1 ratio. Use `on-primary` (#ffffff) for dark backgrounds and `on-secondary-container` (#510c8a) for lighter accent backgrounds.