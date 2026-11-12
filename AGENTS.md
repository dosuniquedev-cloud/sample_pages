# Project Frontend Design & Engineering Rules

This repository contains multi-page HTML5/CSS3/JavaScript web templates (`home.html`, `booking.html`, `login.html`, `register.html`, `adminlogin.html`, `contact.html`, `user_profile.html`) styled with Bootstrap, FontAwesome, and custom stylesheets (`css/main.css`, `css/style.css`).

Follow these senior UI/UX design and frontend engineering rules for all modifications and new features in this project.

---

## 1. Aesthetic & Anti-AI-Slop Guidelines
- **No Cliché Gradients:** Avoid generic indigo-to-purple gradients, excessive glow effects, and gratuitous glassmorphic cards unless explicitly requested.
- **Color Discipline (60-30-10 Rule):**
  - **60% Dominant Base:** Clean neutral background (crisp whites, slate tints, or purposeful dark tones).
  - **30% Structural Surface:** Cards, sidebars, borders, and section dividers with subtle contrast.
  - **10% Accent:** One purposeful primary brand accent reserved for primary CTAs, active indicators, and focus states.
- **Depth & Shadows:** Use layered, subtle shadows (e.g. `box-shadow: 0 1px 3px rgba(0,0,0,0.08), 0 4px 6px rgba(0,0,0,0.04)`) rather than heavy, harsh drop shadows.
- **Consistent Spacing Scale:** Stick strictly to an 8px grid (`4px`, `8px`, `16px`, `24px`, `32px`, `48px`, `64px`). Never use arbitrary margin/padding values like `13px` or `27px`.

---

## 2. Typography & Visual Hierarchy
- **Scale & Weight Contrast:** Pair clear weight differences (e.g., Bold 700 headings with Regular 400 body).
- **Line Heights & Readability:**
  - Headings (`h1`-`h3`): `line-height: 1.15` to `1.25`
  - Body text: `line-height: 1.5` to `1.65`
  - Form labels and small text: `line-height: 1.4`
- **Uppercase Labels:** If using uppercase for badges, table headers, or category tags, always add subtle letter spacing (`letter-spacing: 0.05em` to `0.08em`) and reduce font size (`0.75rem` - `0.85rem`).

---

## 3. Interaction & Micro-States (Mandatory)
Every interactive element must provide feedback across all 4 states:
1. **Default:** Clean, readable resting state.
2. **Hover:** Subtle elevation, background tint shift, or border highlight (`transition: all 0.2s ease`).
3. **Focus-Visible:** Prominent, accessible outline/ring (`outline: 2px solid var(--accent); outline-offset: 2px`). Never remove focus outlines without a replacement.
4. **Active/Pressed:** Visual compression (`transform: translateY(1px)` or slight darkening).
5. **Disabled:** Reduced opacity (`0.5 - 0.6`), `cursor: not-allowed`, no hover transformations.

---

## 4. Forms & Input UX
- Always pair form controls with explicit `<label for="...">` elements.
- Inputs must have clear placeholder text, consistent border radius, and defined focus rings.
- Group related controls with sensible spacing (minimum `16px` between form groups).
- Provide visual feedback for validation (error message beneath the input, red border highlight, error icon).

---

## 5. CSS Architecture & Bootstrap Integration
- **Custom Properties (Design Tokens):** Store reusable colors, radii, and shadows in CSS variables in `css/style.css` or `css/main.css`.
- **Avoid `!important` wars:** Override Bootstrap classes using clean specificity or custom utility classes rather than brute-force `!important`.
- **Responsive-First:** Test layout integrity at mobile (<576px), tablet (768px), and desktop (992px+). Ensure navigation, tables, and forms collapse gracefully on smaller viewports.
- **Semantic HTML5:** Use `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, and `<button>` (never `<div onclick>`).
