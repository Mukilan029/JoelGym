# Design System Document: The Cinematic Athlete

## 1. Overview & Creative North Star
**Creative North Star: "The Private Gallery"**
This design system moves away from the "utility-first" look of standard fitness apps and enters the realm of high-end editorial curation. We are not building a gym interface; we are designing a digital private club. The experience must feel like walking through a dimly lit, premium fitness studio where light only hits what is essential.

To achieve this, the system breaks the "template" look through:
*   **Intentional Asymmetry:** Hero elements and typography should use offset alignments (e.g., a `display-lg` heading overlapping a high-contrast monochromatic image).
*   **Dramatic Chiaroscuro:** We use deep blacks and charcoals to create "voids," allowing our brushed gold (`primary`) and neon-white (`on-surface`) elements to appear as if they are emerging from shadows.
*   **The Editorial Scale:** Extreme contrast between massive, serif display type and tiny, widely-tracked sans-serif labels creates a sophisticated, fashion-magazine hierarchy.

---

## 2. Colors & Tonal Depth

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** Physical lines feel "cheap" and clinical. Boundaries must be defined solely through background color shifts.
*   *Implementation:* A `surface-container-low` section should sit directly against a `surface` background. The eye will perceive the edge through the shift from `#1c1b1b` to `#131313`.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of black obsidian and frosted glass.
*   **Base Layer:** `surface` (#131313) for the main background.
*   **Floating Elements:** Use `surface-container-highest` (#353534) for cards or elements that need to feel "closer" to the user.
*   **The Inset Depth:** Use `surface-container-lowest` (#0e0e0e) for input fields or "recessed" areas to create a sense of carved-out space.

### The "Glass & Gradient" Rule
To evoke "exclusive lighting," use Glassmorphism for floating navigation bars and modals.
*   **Glass Recipe:** Background `secondary-container` at 40% opacity + `backdrop-blur` (20px).
*   **Signature Textures:** Use a subtle linear gradient for primary CTAs: `primary` (#f2ca50) to `primary-container` (#d4af37) at a 135-degree angle. This mimics the sheen of brushed gold rather than a flat yellow.

---

## 3. Typography
The interplay between the "humanist" serif and the "technical" sans-serif is the heartbeat of this system.

*   **Display & Headlines (Noto Serif):** These are the "Art Pieces." Use `display-lg` for high-impact motivation or section titles. They should feel authoritative and timeless. 
*   **Body & UI (Manrope):** This is the "Precision Tool." All functional information—workout stats, durations, and descriptions—uses Manrope. It is clean, modern, and high-readability.
*   **The Signature Label:** Use `label-md` with `letter-spacing: 0.15em` and `text-transform: uppercase`. This creates an "Ultra-Luxurious" metadata feel for small details like "REPS" or "DURATION."

---

## 4. Elevation & Depth

### The Layering Principle
Depth is achieved through **Tonal Layering**. Instead of shadows, use the color scale:
*   **Level 0 (Background):** `surface`
*   **Level 1 (Section):** `surface-container-low`
*   **Level 2 (Card):** `surface-container-high`

### Ambient Shadows
When an element must float (e.g., a floating action button or a modal), shadows must be "Ambient":
*   **Shadow Specs:** Blur: 40px–60px | Opacity: 8% | Color: `on-surface` (#e5e2e1).
*   **The Ghost Border Fallback:** If a border is required for accessibility, use the `outline-variant` token at 15% opacity. Never use 100% opaque borders.

---

## 5. Components

### Buttons: The "Gold Standard"
*   **Primary:** Gradient fill (Brushed Gold). `0.25rem` (sm) corner radius. Label: `title-sm` (Manrope), Bold.
*   **Secondary:** Ghost style. No fill, `outline-variant` (20% opacity) border. High-interaction hover state: Fill shifts to `surface-bright`.
*   **Tertiary:** Text only. `label-md` with a gold underline that expands on hover.

### Cards: The "Frameless" Look
*   **Rules:** No borders. No dividers. 
*   **Separation:** Use `spacing-8` (2.75rem) of vertical whitespace or a background shift to `surface-container-lowest`.
*   **Interactive State:** On hover, a card should shift from `surface-container` to `surface-bright` with a subtle scale-up (1.02x).

### Inputs: "The Recessed Path"
*   Fields should use `surface-container-lowest` (#0e0e0e) to look like they are carved into the interface.
*   **Active State:** The bottom border glows with `primary-fixed` (#ffe088) with a 2px height.

### Specialized Component: The "Performance Halo"
*   **The Halo:** For workout progress or active timers, use a semi-transparent `primary` glow (neon-gold) behind the element to simulate a backlit high-end gym machine.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use extreme whitespace. Luxury is defined by the space you "waste."
*   **Do** use high-quality, desaturated imagery. Photos should feel like cinematic stills, not stock photography.
*   **Do** use `0.25rem` (DEFAULT) for most containers to keep the look sharp and architectural.

### Don’t:
*   **Don’t** use pure white (#FFFFFF). Always use `on-surface` (#e5e2e1) or `neon-white` highlights to keep the "dark room" aesthetic intact.
*   **Don’t** use standard "Drop Shadows." They break the cinematic immersion.
*   **Don’t** use standard icons. Use thin-stroke (1px or 1.5px) icons that match the `outline` token color.
*   **Don’t** use divider lines to separate list items. Use the spacing scale `3` (1rem) or subtle background shifts.