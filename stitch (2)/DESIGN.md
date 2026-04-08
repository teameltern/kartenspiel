# Design System Specification: High-End Digital Play

## 1. Overview & Creative North Star

### Creative North Star: "The Modern Hearth"
This design system is built to bridge the gap between nostalgic, physical play and high-end digital editorial design. It moves away from the "clinical" feel of standard mobile apps, embracing a philosophy of **Tactile Sophistication**. By placing clean, vibrant digital components onto a warm, rustic wood texture, we create a "Modern Hearth"—a space that feels safe, premium, and deeply human for parents.

The design breaks the traditional grid through **intentional asymmetry** and **organic layering**. We do not "box" content; we float it. We do not "separate" sections with lines; we define them with light and depth. This approach ensures the interface feels like a collection of physical objects resting on a kitchen table, rather than a flat web page.

---

## 2. Colors & Atmospheric Depth

The palette is vibrant and diverse, yet anchored by deep oceanic tones and soft surface tints to ensure a premium feel.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or containment. Boundaries must be defined solely through background color shifts or tonal transitions. To separate a card from the background, use the `surface-container` hierarchy or elevation shadows—never a stroke.

### Surface Hierarchy & Nesting
Instead of flat grids, use the `surface-container` tiers to create "physical" nesting.
*   **Base Layer:** The rustic wood texture (Background).
*   **Secondary Layer:** `surface-container-low` (#e6f2ff) for large content areas.
*   **Action Layer:** `surface-container-lowest` (#ffffff) for active cards to provide maximum "pop" against the wood.
*   **Overlay Layer:** `surface-container-highest` (#bfe1ff) for modal elements or nested info-chips.

### The "Glass & Gradient" Rule
To elevate the "playful" nature, use Glassmorphism for floating UI elements (like navigation bars or scoreboards). Use `surface` colors with a **20px backdrop-blur** and 80% opacity. 
*   **Signature Gradients:** Apply a subtle linear gradient from `primary` (#a92659) to `primary-container` (#ff709e) on main CTAs. This adds a "soulful" glow that flat colors lack.

---

## 3. Typography: Editorial Sans

We utilize **Plus Jakarta Sans** as our signature typeface. It provides a "friendly-premium" aesthetic—clean enough for legibility but with enough character to feel playful.

*   **Display (Large/Med/Small):** Used for game titles and "big win" moments. High-contrast sizing creates an editorial feel.
*   **Headline (L/M/S):** Used for card titles. These should always be `on-surface` (#00324d) to maintain authority.
*   **Body (L/M/S):** Used for card descriptions and quotes. Increased line-height (1.6) is mandatory to ensure "breathability."
*   **Labels:** Reserved for metadata. Use `tertiary` (#8b3993) for labels to add a splash of sophistication.

---

## 4. Elevation & Depth: The Layering Principle

Depth is the primary communicator of hierarchy. We move beyond "drop shadows" into **Ambient Light Simulation**.

*   **Tonal Layering:** Avoid shadows on static sections. Simply placing a `surface-container-lowest` card on a `surface-container-low` background creates a natural, soft lift.
*   **Ambient Shadows:** For "floating" cards, use extra-diffused shadows. 
    *   *Values:* `0px 20px 40px` blur.
    *   *Color:* Use a 6% opacity version of `on-surface` (#00324d). This mimics natural light reflecting off the wood texture rather than a "dirty" grey shadow.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., in high-contrast modes), use the `outline-variant` (#8ab2d3) at **15% opacity**. High-contrast, 100% opaque borders are forbidden.

---

## 5. Components

### Cards (The Hero Component)
Cards are the heart of this system. 
*   **Radius:** Always use `xl` (1.5rem) for main game cards to emphasize playfulness.
*   **Content:** No divider lines. Use `body-lg` spacing to separate titles from body text. 
*   **Checkmarks:** Use a "Saftiges Grün" (Succulent Green) for emoji-style checkmarks, utilizing a custom gradient to give them a 3D-pop effect against the card surface.

### Buttons
*   **Primary:** A pill-shaped (`full` roundedness) button using the Primary Gradient. 
*   **Secondary:** Glassmorphic style. Semi-transparent `secondary-container` with a backdrop blur.
*   **Tertiary:** Text-only with an underline that uses `surface-tint` (#a92659) at 30% opacity.

### Input Fields
*   **Style:** Subtle "sunken" appearance. Use `surface-container-high` with a slight inner shadow. 
*   **Error State:** Use `error` (#b41340) for text, but the field background should shift to a soft `error_container` (#f74b6d) at 10% opacity.

### Chips & Tags
*   Use the diverse brand palette (Pink, Lilac, Petrol) to categorize cards. Each chip should be a low-saturation version of the color with high-saturation text for readability.

---

## 6. Do’s and Don’ts

### Do
*   **Do** let the wood texture breathe. Leave generous "gutter" space around the edges of the screen.
*   **Do** use asymmetrical layouts for card stacks (slightly tilted ±2 degrees) to mimic a real table.
*   **Do** use `plusJakartaSans` for all Sprüche (sayings) to keep the voice consistent and friendly.

### Don’t
*   **Don't** use pure black (#000000) for text. Use `on-surface` (#00324d) to keep the palette warm.
*   **Don't** use standard 1px dividers between list items. Use vertical whitespace or alternating `surface-container-low` / `surface-container-lowest` backgrounds.
*   **Don't** place vibrant cards directly on vibrant backgrounds. Always use a neutral "buffer" surface or the wood texture to prevent visual fatigue.