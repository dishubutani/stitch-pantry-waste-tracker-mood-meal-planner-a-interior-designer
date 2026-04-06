# Design System Strategy: The Nourished Narrative

## 1. Overview & Creative North Star: "The Living Editorial"
This design system rejects the "utility-first" rigidity of standard meal planners. Instead, it adopts a **Living Editorial** North Star. We treat every meal plan like a high-end food magazine—spacious, sensory, and deeply intentional. 

The goal is to move beyond a "grid of boxes" toward an organic, fluid interface that breathes. We achieve this through:
*   **Intentional Asymmetry:** Overlapping high-quality food photography with typography to create depth.
*   **Atmospheric Immersion:** The interface doesn't just display data; it shifts its entire tonal personality based on the user's mood selection (Zen, Boost, Brain Power, or Comfort).
*   **Organic Softness:** Utilizing the `xl` (3rem) and `lg` (2rem) corner radii to mimic the curves of ceramic plating and natural ingredients.

---

## 2. Colors: Tonal Mood-States
Color here is not decorative; it is functional biofeedback. We use the Material Design tokens to create "Mood Containers" that wrap the user in a specific atmosphere.

### The "No-Line" Rule
**Standard 1px borders are strictly prohibited.** They create "visual noise" that contradicts a calming experience. Use background shifts to define space:
*   **Sectioning:** Place a `surface-container-low` component against a `surface` background.
*   **Emphasis:** A `surface-container-highest` element provides enough contrast to indicate a "call to action" area without needing a stroke.

### Surface Hierarchy & Nesting
Treat the screen as a series of stacked, organic materials. 
*   **Base:** `surface` (#faf9f5) – The "fine paper" foundation.
*   **Subtle Depth:** Use `surface-container` tiers to nest content. A recipe card (`surface-container-lowest`) sitting on a mood-themed section (`surface-container-low`) creates a natural, soft-touch lift.

### Signature Textures & Glassmorphism
To create a premium feel, use **Glassmorphism** for floating navigation or overlays. Use `surface` colors at 70% opacity with a `24px` backdrop blur. 
*   **CTA Soul:** Apply a linear gradient from `primary` (#006f1d) to `primary-container` (#91f78e) at a 135-degree angle for "Zen" actions to give the button a tactile, glowing quality.

---

## 3. Typography: The Friendly Authority
We pair **Plus Jakarta Sans** (Display/Headlines) with **Be Vietnam Pro** (Body/Labels) to balance modern geometry with approachable warmth.

*   **Display-LG (3.5rem):** Reserved for mood titles (e.g., "Good Morning, Calm"). Use tight letter-spacing (-0.02em) to give it a curated, editorial look.
*   **Headline-MD (1.75rem):** Used for recipe names. This is the "hook" that leads the eye.
*   **Body-LG (1rem):** Set with generous line-height (1.6) for recipe instructions to ensure readability while cooking.
*   **Label-MD (0.75rem):** Used for nutritional data (Macros). Always uppercase with +0.05em tracking to differentiate from narrative text.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too "digital." We use **Ambient Softness** to create a high-end, physical feel.

*   **The Layering Principle:** Avoid shadows for static elements. Use color nesting (`surface-container-low` inside `surface-bright`).
*   **Ambient Shadows:** For "floating" elements like a Floating Action Button (FAB) or a Modal, use:
    *   `box-shadow: 0 20px 40px rgba(47, 51, 47, 0.06);` (A tinted version of `on-surface`).
*   **The "Ghost Border" Fallback:** If a divider is essential for accessibility, use the `outline-variant` (#afb3ad) at **15% opacity**. It should be felt, not seen.

---

## 5. Components: Organic Primitives

### Buttons
*   **Primary:** High-pill shape (`full` radius). Gradient fill from `primary` to `primary-dim`. No border.
*   **Secondary:** `surface-container-highest` background with `on-surface` text.
*   **Interaction:** On hover, a subtle scale-up (1.02) and a slight increase in shadow diffusion.

### Mood-State Cards (The "Core" Component)
*   **Structure:** Forbidden use of dividers. Separate the image from the text using a `1.5rem` (`md`) gap.
*   **The "Bleed" Effect:** Photography should often "bleed" to the edge of the card or even slightly overlap the container boundary to break the boxy feel.
*   **Radii:** Always use `lg` (2rem) for recipe cards to maintain the organic theme.

### Chips (Mood Selectors)
*   Use `surface-container-high` for unselected states. 
*   Selected states should use the specific mood color (e.g., `tertiary-container` for 'Brain Power') with a gentle scale-up.

### Input Fields
*   **Styling:** Large, rounded boxes (`md` radius). 
*   **State:** Use `outline` (#787c77) at 20% opacity for the resting state. On focus, transition to `primary` (#006f1d) with a soft 4px outer "glow" using `primary-container`.

---

## 6. Do’s and Don’ts

### Do:
*   **DO** use whitespace as a functional element. If a screen feels crowded, increase the vertical spacing before adding a line.
*   **DO** use "Hero Imagery." High-quality, macro-photography of ingredients should be the star of every major transition.
*   **DO** lean into asymmetry. A recipe title can slightly overlap a photo to create a layered, "collage" feel.

### Don’t:
*   **DON'T** use pure black (#000000). Use `on-surface` (#2f332f) for all text to maintain the "calming" ethos.
*   **DON'T** use 90-degree corners. Even the smallest UI element should have at least the `sm` (0.5rem) radius.
*   **DON'T** use standard dividers (`<hr>`). Use a `2rem` vertical gap or a subtle shift from `surface` to `surface-container-low` to denote a new section.
*   **DON'T** use high-velocity animations. All transitions should be "Lagom"—balanced and smooth (300ms-500ms ease-in-out).