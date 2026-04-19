# Design System Document

## 1. Creative North Star: "The Ethereal Editorial"
This design system is built upon the concept of **The Ethereal Editorial**. We are moving away from the rigid, boxed-in layouts of traditional e-commerce and moving toward the fluid, airy feel of a high-end fashion magazine. The goal is to make the user feel like they are "glowing" from within.

We achieve this through:
*   **Intentional Asymmetry:** Breaking the grid with overlapping images and offset typography to create a sense of movement and "curated" art.
*   **Breathing Room:** Using extreme whitespace to signal luxury. If you think there is enough padding, add 24px more.
*   **Tonal Sophistication:** Moving beyond a flat pink-and-white palette into a world of layered "nude" tones and soft gradients.

---

## 2. Colors & Surface Philosophy

The palette is rooted in the skin’s natural luminosity. We use a range of "blush" and "sand" tones to create depth without visual noise.

### The "No-Line" Rule
**Strict Directive:** 1px solid borders are prohibited for sectioning. We do not "box" content. 
*   **Boundary Definition:** Transition between sections using background color shifts (e.g., moving from `surface` to `surface-container-low`).
*   **The "Ghost Border" Fallback:** If a border is required for accessibility in form fields, use `outline-variant` at **20% opacity max**.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked sheets of fine vellum. 
*   **Base:** `surface` (#fff8f8) — Use this for the primary canvas.
*   **Nesting:** Place a `surface-container-lowest` (#ffffff) card on top of a `surface-container-low` (#faf1f3) background to create a soft, natural lift.
*   **Glassmorphism:** For floating navigation or product filters, use the `surface` token with `80% opacity` and a `20px backdrop-blur`. This allows the "glow" of the product photography to bleed through the interface.

---

## 3. Typography: The Curated Voice

Our typography pairing balances the geometric modernity of **Manrope** with the approachable warmth of **Plus Jakarta Sans**.

*   **Display & Headlines (Manrope):** Use these for brand moments and product names. The tight tracking and generous leading of `display-lg` (3.5rem) should feel like a magazine masthead.
*   **Body & Labels (Plus Jakarta Sans):** Optimized for readability. Use `body-lg` (1rem) for product descriptions to maintain a premium feel.
*   **The Hierarchy Statement:** Always pair a `display-sm` headline with a much smaller `label-md` (all-caps, tracked out +10%) to create high-contrast, editorial tension.

---

## 4. Elevation & Depth: Tonal Layering

We reject traditional drop shadows. We convey "lift" through color and light.

*   **The Layering Principle:** Depth is achieved by "stacking" the surface-container tiers. High-priority items (like a "Current Routine" card) should sit on `surface-container-highest`, while background elements sit on `surface-dim`.
*   **Ambient Shadows:** For high-end "floating" elements (e.g., a cart modal), use an "Ambient Glow" rather than a shadow:
    *   **Blur:** 40px - 60px
    *   **Opacity:** 5%
    *   **Color:** Derived from `on-surface` (#1e1b1c) to mimic natural light casting through a soft-box.
*   **Signature Textures:** For Hero CTAs, use a linear gradient: `primary-container` (#f8c8dc) to `primary` (#795465) at a 135-degree angle. This adds a "silk-satin" finish that flat color lacks.

---

## 5. Components

### Buttons: The "Soft-Touch" Interaction
*   **Primary:** High-pill shape (`rounded-full`). Background: `primary` (#795465). Label: `on-primary` (#ffffff). No shadow.
*   **Secondary/Accent:** Gold accents using `tertiary` (#735c00). Use this sparingly for "limited edition" or "loyalty" callouts.
*   **Tertiary:** Text-only with a 2px underline using `outline-variant` at 40% opacity.

### Input Fields: "Invisible" Utility
*   **Style:** No background fill. Only a bottom border using `outline-variant` (#d2c3c7).
*   **Active State:** The bottom border transitions to `primary` (#795465) with a subtle 2px thickness. Label floats upward using `label-sm`.

### Cards & Product Grids
*   **Forbid Dividers:** Do not use lines to separate products. Use the `spacing-xl` (1.5rem) gap and subtle background shifts.
*   **Imagery:** All product photos should have slightly rounded corners (`rounded-lg`) and be shot on a `surface-variant` (#e9e0e2) background for seamless integration.

### High-End Editorial Components
*   **The "Floating Ingredient" Chip:** Small, `rounded-full` containers using `surface-container-highest` with `label-sm` text to highlight key ingredients (e.g., "Vitamin C").
*   **The "Glow" Loader:** A circular progress indicator using a gradient of `primary` to `tertiary-fixed-dim` (#e9c349).

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins. If the left margin is 24px, try a 48px right margin for a featured product.
*   **Do** use the `tertiary` (Gold) color only for high-value conversion points or "Glow Queen" status indicators.
*   **Do** prioritize "white-on-white" layering to create a sense of cleanliness and purity.

### Don’t:
*   **Don’t** use pure black (#000000). Always use `on-surface` (#1e1b1c) for text to keep the palette soft.
*   **Don’t** use sharp corners. Everything should have at least a `rounded-sm` (4px) radius to feel "approachable."
*   **Don’t** use standard "box-shadows" on cards. If a card needs to stand out, change its background color to `surface-container-lowest`.

---

## 7. Accessibility
While the aesthetic is "soft," we never sacrifice clarity.
*   Ensure all `on-primary` and `on-surface` text meets WCAG AA standards against their respective backgrounds.
*   Use `outline` (#817478) for focus states to ensure keyboard navigability is visible without breaking the "no-line" rule permanently.