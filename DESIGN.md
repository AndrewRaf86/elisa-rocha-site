# Design System Document: Boutique Editorial Luxury

## 1. Overview & Creative North Star
**Creative North Star: The Coastal Curator**
This design system is a digital translation of Lima’s refined coastal architecture—where the warmth of the desert sand meets the structured sophistication of high-end Barranco galleries. We are moving away from "App-like" interfaces toward a **High-End Editorial** experience. 

The system rejects the rigid, boxed-in nature of standard web design. Instead, it utilizes **intentional asymmetry**, expansive whitespace, and a "layered paper" philosophy. We do not use borders to define space; we use light and shadow, much like the sun hitting a lime-washed wall. The goal is to make the user feel they are flipping through a bespoke architectural monograph rather than browsing a database.

---

## 2. Colors & Surface Philosophy
The palette is grounded in organic, earthen tones that evoke luxury without relying on "gold" clichés.

### Surface Hierarchy & Nesting
We define depth through **Tonal Layering**. To create a high-end feel, treat the UI as stacked sheets of fine cotton paper.
- **Base Layer:** Use `surface` (#fbf9f5) for the primary canvas.
- **Sectioning:** Use `surface-container-low` (#f5f3ef) to define large content areas.
- **Focus Containers:** Place `surface-container-lowest` (#ffffff) cards on top of `surface-container-low` sections to create a soft, natural lift.

### The "No-Line" Rule
**Explicit Instruction:** Prohibit the use of 1px solid borders for sectioning. Boundaries must be defined solely through background color shifts. A transition from `surface` to `surface-container` is the only "line" allowed.

### The "Glass & Tone" Rule
For floating navigation or overlays, use **Glassmorphism**: 
- Background: `surface` at 80% opacity.
- Effect: `backdrop-filter: blur(12px)`.
- Use subtle gradients transitioning from `primary` (#835239) to `primary-container` (#c58b6e) *only* for high-impact CTAs to provide "visual soul."

---

## 3. Typography
Our typography is the primary vehicle for the "Editorial" feel. It balances the authority of a serif with the modern clarity of a sans-serif.

| Level | Token | Font Family | Size | Weight / Style |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Noto Serif | 3.5rem | Light / Leading 1.1 |
| **Headline** | `headline-md` | Noto Serif | 1.75rem | Regular |
| **Title** | `title-md` | Manrope | 1.125rem | Medium / Tracking 0.05em |
| **Body** | `body-lg` | Manrope | 1.0rem | Regular / Leading 1.6 |
| **Label** | `label-sm` | Manrope | 0.6875rem | Uppercase / Tracking 0.1em |

**Editorial Intent:** Use `display-lg` for hero statements, left-aligned with generous leading. The high contrast between the serif headlines and the Manrope body text creates an authoritative, curated voice.

---

## 4. Elevation & Depth
We eschew the "standard" Material Design shadow in favor of environmental lighting.

- **The Layering Principle:** Depth is achieved by stacking `surface-container` tiers. An inner container should always be one step lighter or darker than its parent.
- **Ambient Shadows:** For floating elements (e.g., a luxury property card), use a "Whisper Shadow": `0px 20px 40px rgba(45, 45, 45, 0.04)`. The shadow color must be a derivative of `on-surface`, never pure black.
- **The Ghost Border:** If a boundary is required for accessibility, use `outline-variant` at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons (Bespoke Implementation)
- **Primary:** Filled with `primary` (#835239), text in `on-primary` (#ffffff). Shape: `md` (0.375rem). No icons unless directional (e.g., a thin arrow).
- **Secondary:** Transparent background with a `Ghost Border`. Text in `primary`.
- **Tertiary:** Text-only, `label-md` style, uppercase with a 1px underline using `primary-container` set 4px below the baseline.

### Input Fields
- **Styling:** Abandon the 4-sided box. Use a "Minimalist Tray"—a `surface-container-highest` background with a `sm` radius and no border. 
- **States:** On focus, the background shifts to `surface-container-lowest` with a subtle `primary` underline (2px).

### Cards & Lists
- **Rule:** Absolute prohibition of divider lines. 
- **Spacing:** Use vertical white space (32px or 48px) to separate items. 
- **Imagery:** Real estate imagery should use the `lg` (0.5rem) corner radius to feel "held" rather than sharp.

### Signature Component: The Property "Folio"
Instead of a standard list, use an asymmetrical grid where text blocks overlap image containers by 24px. This creates the "Magazine" layout requested, breaking the vertical gutters of a standard web grid.

---

## 6. Do's and Don'ts

### Do:
- **Left-Align Everything:** Maintain a strong vertical axis on the left to ground the editorial feel.
- **Embrace the "Empty" Space:** If a section feels "too empty," leave it. Whitespace is a luxury signal.
- **Use Tonal Accents:** Use `tertiary` (#30666a) sparingly for interactive "status" elements or subtle highlights.

### Don't:
- **No Heavy Iconography:** Avoid thick, circular icon backgrounds. Use thin-stroke, "Line-Art" icons only.
- **No Purple or Neon:** The palette must remain organic. If a color isn't found in a Lima sunset or the cliffs of Chorrillos, don't use it.
- **No Centered Headers:** Centering text breaks the boutique editorial flow. Keep the "Golden Thread" of the left margin intact.
- **No Drop Shadows on Text:** Use high-contrast color pairings (`on-surface` on `surface`) for legibility instead.