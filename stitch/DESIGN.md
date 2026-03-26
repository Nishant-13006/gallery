# Design System Document: The Cinematic Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Obsidian Gallery"**

This design system is engineered to disappear, acting as a sophisticated stage for high-end imagery and cinematic content. We are moving away from the "web-as-a-document" mental model and toward "web-as-an-experience." By utilizing a true black base (`#000000`) and a monochromatic palette, we create an environment where light and shadow define the architecture rather than lines and boxes.

The system breaks traditional template constraints through **intentional asymmetry** and **tonal layering**. Elements should feel like they are floating in a void, organized by visual weight and proximity rather than rigid containers. The goal is a digital experience that feels as tactile and premium as a luxury physical exhibition.

---

## 2. Colors & Surface Philosophy
The palette is rooted in deep neutrals, using a spectrum of greys to simulate depth and atmospheric perspective.

### The Surface Hierarchy
We do not use borders to define space. We use "The No-Line Rule." 
- **Base Layer:** Always `surface_container_lowest` (#000000) or `surface` (#0e0e0e).
- **Nesting:** To elevate an element, move up the surface scale. A card should sit on `surface_container_low` (#131313) while its parent section is `surface` (#0e0e0e).
- **Glassmorphism:** For floating navigation or modal overlays, use `surface_bright` (#2c2c2c) at 60% opacity with a `24px` backdrop-blur. This allows the cinematic content to bleed through, maintaining an integrated feel.

### Signature Textures
- **The Obsidian Glow:** Use a subtle radial gradient for primary CTAs, transitioning from `primary` (#c6c6c7) to `primary_container` (#454747). This provides a metallic, satin-like finish that flat colors cannot replicate.
- **Tonal Transitions:** Instead of hard section breaks, use a vertical gradient mask that transitions from `surface` to `surface_container_high` (#1f1f1f) over a `20` (7rem) spacing unit.

---

## 3. Typography: The Minimalist Voice
Typography in this system is secondary to the image. It must be authoritative but quiet.

- **The Display Scale:** Use `display-lg` (Manrope, 3.5rem) with `-0.04em` letter spacing for hero moments. It should feel like a masthead.
- **The Information Hierarchy:** 
    - **Headlines:** `headline-sm` (1.5rem) provides enough presence without crowding the frame.
    - **Labels:** Use `label-md` (Inter, 0.75rem) with `0.1em` letter spacing and all-caps for metadata. This "utilitarian" contrast against the fluid Manrope headers creates a premium, curated feel.
- **Editorial Breathing Room:** Always pair `body-lg` text with a minimum leading of 1.6x to ensure the deep black background doesn't "choke" the glyphs, maintaining high legibility in low-light UI.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are too heavy for a cinematic black UI. We achieve depth through light, not darkness.

- **The Layering Principle:** Stack `surface_container` tiers to create "soft lift." 
    - Level 0: `surface_container_lowest` (#000000)
    - Level 1: `surface_container_low` (#131313)
    - Level 2: `surface_container` (#191919)
- **Ambient Shadows:** For high-priority floating elements, use a shadow with a `40px` blur and `4%` opacity. The shadow color must be `on_surface` (#e5e5e5) rather than black, creating a subtle "rim light" effect that makes the element pop from the void.
- **The Ghost Border:** If a boundary is required for accessibility, use `outline_variant` (#484848) at 15% opacity. It should be felt, not seen.

---

## 5. Components

### Interactive Elements
- **Buttons (Primary):** Use the `primary` (#c6c6c7) token with `on_primary` (#3f4041) text. Apply a `md` (0.375rem) corner radius. On hover, transition the background to `primary_fixed_dim` (#d4d4d4) with a fluid `300ms` cubic-bezier ease.
- **Buttons (Tertiary):** No background or border. Use `on_background` (#e5e5e5) text with a `label-md` style. Animate a 1px underline that expands from the center on hover.

### Content Containers
- **Cards:** Forbid divider lines. Use `surface_container_low` for the card body and `surface_container_high` for the hover state. Use `spacing-5` (1.7rem) for internal padding to give the content "gallery-style" margins.
- **Input Fields:** Use a "minimalist underline" approach. A `surface_variant` (#262626) background with a `sm` (0.125rem) bottom-only border using `outline_variant`. On focus, the border shifts to `primary`.

### Specialized Components
- **The Filmstrip Scroller:** A horizontal list component with no visible scrollbar. Use `spacing-8` (2.75rem) between items. The edges of the container should have a `surface_container_lowest` to transparent gradient mask to simulate images emerging from the shadows.
- **Image Overlays:** Use a `0.5` (0.175rem) "Ghost Border" inside the image frame using `inverse_on_surface` at 10% opacity to give photos a polished, "framed" look.

---

## 6. Do's and Don'ts

### Do
- **Do** use `surface_container_highest` (#262626) for subtle highlights on active states.
- **Do** leverage the `20` and `24` spacing tokens for massive top/bottom margins in hero sections to create a sense of luxury.
- **Do** use `tertiary` (#eff8ff) sparingly for interactive "glimmer" or success states—it provides a crisp, cool-toned contrast to the warm greys.

### Don't
- **Don't** use 1px solid borders to separate content blocks; it breaks the cinematic immersion.
- **Don't** use pure white (#ffffff) for body text; use `on_background` (#e5e5e5) to reduce eye strain against the deep black.
- **Don't** use standard "drop shadows." If an element needs to feel elevated, use tonal shifts or ultra-diffused ambient glows.
- **Don't** crowd the interface. If you are unsure, add more `spacing-12` (4rem). Space is the ultimate luxury.