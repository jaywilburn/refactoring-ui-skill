---
name: refactoring-ui
description: Comprehensive UI design guidance based on Refactoring UI principles covering visual hierarchy, color theory, typography, spacing, and mobile-first responsive design. Use this skill whenever the user is creating new pages, building components, making design additions or changes, reviewing UI code, asking about design decisions (colors, fonts, spacing, layout), or discussing visual improvements. Trigger for any design-related conversation including "how should this look", "what color", "font size", "spacing", "layout", "responsive", "mobile", or when reviewing/critiquing existing interfaces.
---

# Refactoring UI Design System

## Core Philosophy

Design decisions should be made with intention, not decoration. Every visual choice—color, size, spacing, weight—communicates hierarchy and guides the user's attention. Start with too much whitespace, then remove it. Start with less contrast, then add it where needed.

---

## Visual Hierarchy

Hierarchy is the foundation of good UI. Users should immediately understand what's important.

### The Hierarchy Toolkit

You have three primary tools to establish hierarchy:

1. **Size** — Larger elements draw more attention
2. **Weight** — Bolder text feels more important
3. **Color** — Higher contrast elements stand out

The key insight: **don't rely on size alone**. A common mistake is making primary content huge and secondary content tiny. Instead, use all three tools together.

### De-emphasize by Reducing Contrast

Instead of making important things bigger, try making unimportant things less prominent:
- Use lighter colors for secondary text (not smaller sizes)
- Reduce font weight for supporting information
- Use muted colors for metadata (dates, labels, counts)

### Semantic Color vs Visual Hierarchy

Don't let semantics override hierarchy. A "danger" action that's rarely used shouldn't be bright red if it competes with the primary action. Use muted reds for destructive secondary actions.

```css path=null start=null
/* Primary destructive action - prominent */
.btn-danger-primary { @apply bg-red-600 text-white; }

/* Secondary destructive action - muted */
.btn-danger-secondary { @apply text-red-600/70 bg-transparent; }
```

### Labels and Data

When showing label-value pairs, the data is usually more important than the label:
- De-emphasize labels (lighter color, smaller size, or all caps with letter-spacing)
- Let the values stand out naturally

```html path=null start=null
<!-- Labels de-emphasized, values prominent -->
<div>
  <span class="text-xs uppercase tracking-wide text-gray-500">Status</span>
  <span class="text-gray-900 font-medium">Active</span>
</div>
```

---

## Typography

### Font Size Scale

Use a modular scale with intentional jumps. Avoid arbitrary sizes.

Recommended scale (based on a ~1.25 ratio):
- **xs**: 12px — Fine print, captions
- **sm**: 14px — Secondary text, metadata  
- **base**: 16px — Body text (minimum for readability)
- **lg**: 18px — Emphasized body, lead paragraphs
- **xl**: 20px — Subheadings
- **2xl**: 24px — Section headings
- **3xl**: 30px — Page headings
- **4xl**: 36px — Hero text
- **5xl+**: 48px+ — Display text, marketing

### Line Height

Line height should decrease as font size increases:
- **Small text (12-14px)**: 1.5-1.75 (needs more breathing room)
- **Body text (16-18px)**: 1.5-1.65
- **Headings (24px+)**: 1.2-1.35 (tighter feels more refined)

### Letter Spacing

- **All-caps text**: Add 0.05-0.1em tracking (uppercase needs room)
- **Large headings**: Consider slight negative tracking (-0.02em)
- **Body text**: Leave default

### Font Weight Strategy

Avoid using too many weights. Pick 2-3:
- **Normal (400)**: Body text
- **Medium (500)**: Emphasis, UI elements
- **Semibold/Bold (600-700)**: Headings, strong emphasis

Using medium (500) for UI text often looks more refined than jumping straight to bold.

### Line Length

Optimal reading: **45-75 characters** per line. For a 16px font, that's roughly 20-35em or 320-560px.

```css path=null start=null
.prose { max-width: 65ch; } /* ch unit = width of '0' character */
```

---

## Color

### Building a Color Palette

Every color needs a full range of shades (typically 9-10):
- **50-100**: Backgrounds, subtle fills
- **200-300**: Borders, disabled states
- **400-500**: Icons, secondary text
- **600-700**: Primary text, buttons
- **800-900**: Headings, high-emphasis text

### Defining Colors with HSL

HSL (Hue, Saturation, Lightness) is more intuitive for building palettes:

```css path=null start=null
/* Base color */
--primary-600: hsl(220, 65%, 50%);

/* Lighter (increase lightness, slightly decrease saturation) */
--primary-100: hsl(220, 60%, 95%);

/* Darker (decrease lightness, can increase saturation slightly) */
--primary-800: hsl(220, 70%, 30%);
```

Key insight: **perceived brightness changes with hue**. Yellow appears brighter than blue at the same lightness. Adjust accordingly.

### Color for UI States

- **Hover**: Darken by one shade (500 → 600) or reduce lightness by 5-10%
- **Active/Pressed**: Darken another shade (600 → 700)
- **Disabled**: Reduce saturation significantly, increase lightness
- **Focus**: Use a ring/outline, don't change the element's color

### Grays Aren't Truly Gray

Add a hint of color to your grays for warmth or coolness:
- **Warm grays**: Add a touch of yellow/orange (better for friendly, approachable UIs)
- **Cool grays**: Add a touch of blue (better for professional, technical UIs)

```css path=null start=null
/* Cool gray (slight blue) */
--gray-600: hsl(215, 15%, 40%);

/* Warm gray (slight yellow) */
--gray-600: hsl(40, 10%, 40%);
```

### Accessible Color Contrast

- **Body text**: Minimum 4.5:1 contrast ratio (WCAG AA)
- **Large text (18px+ bold or 24px+)**: Minimum 3:1
- **UI components**: Minimum 3:1 against adjacent colors
- **Don't rely on color alone**: Use icons, text, or patterns alongside

### Don't Use Pure Black

Pure black (#000) feels harsh and unnatural. Use a very dark gray instead:

```css path=null start=null
/* Too harsh */
color: #000;

/* Better - dark but not absolute */
color: #1a1a1a; /* or hsl(0, 0%, 10%) */
```

---

## Spacing

### Spacing Scale

Use a consistent scale based on a base unit (typically 4px or 8px):

```
4, 8, 12, 16, 24, 32, 48, 64, 96, 128...
```

Avoid arbitrary values like 13px or 27px. Constraints create consistency.

### Spacing Relationships

- **Related items**: Closer together (8-12px)
- **Grouped but distinct**: Medium spacing (16-24px)
- **Separate sections**: Larger gaps (32-64px)

The principle: **proximity implies relationship**. Group related items tightly; separate unrelated items clearly.

### Start with Too Much Space

It's easier to remove whitespace than to add it later. Start generous, then tighten only where needed. Most designs are too cramped, not too airy.

### Padding Consistency

Buttons and inputs should have consistent internal proportions:
- Horizontal padding: 1.5-2x vertical padding
- Maintain aspect ratio across sizes

```css path=null start=null
/* Small */
.btn-sm { @apply px-3 py-1.5; }

/* Medium */  
.btn-md { @apply px-4 py-2; }

/* Large */
.btn-lg { @apply px-6 py-3; }
```

---

## Layout

### Don't Fill the Whole Width

Content shouldn't span edge-to-edge on large screens. Use max-width constraints:

```css path=null start=null
.container { 
  max-width: 1200px; 
  margin-inline: auto;
  padding-inline: 1rem;
}
```

### Grids Aren't Always the Answer

Not everything needs a 12-column grid. Simple layouts often work better with:
- Max-width containers
- Flexbox for alignment
- Natural content flow

### Give Elements Room to Breathe

Tight layouts feel cheap. Add generous padding to:
- Cards and panels (24-32px minimum)
- Sections (48-96px vertical)
- Page margins (16-24px on mobile, more on desktop)

### Alignment

- **Left-align most text** (easier to scan)
- **Center short headings and CTAs** (draws focus)
- **Right-align numbers in tables** (decimal alignment)

---

## Mobile-First Responsive Design

### Why Mobile-First

Start with the mobile layout, then add complexity for larger screens. Benefits:
- Forces prioritization of content
- Simpler base styles
- Progressive enhancement (works everywhere, better on larger screens)

### Breakpoint Strategy

Don't design for specific devices. Use content-based breakpoints:
- Add a breakpoint when the layout breaks, not at arbitrary screen sizes
- Common ranges: ~640px (sm), ~768px (md), ~1024px (lg), ~1280px (xl)

### Mobile-First Patterns

**Start simple, enhance up:**

```css path=null start=null
/* Mobile: stack vertically */
.card-grid {
  display: grid;
  gap: 1rem;
}

/* Tablet+: 2 columns */
@media (min-width: 768px) {
  .card-grid { grid-template-columns: repeat(2, 1fr); }
}

/* Desktop: 3 columns */
@media (min-width: 1024px) {
  .card-grid { grid-template-columns: repeat(3, 1fr); }
}
```

### Touch Targets

Mobile buttons and interactive elements need adequate tap targets:
- **Minimum**: 44×44px (Apple HIG) or 48×48px (Material)
- Add padding to small elements to increase hit area without visual bulk

### Typography Scaling

Reduce heading sizes on mobile—there's less room for drama:

```css path=null start=null
h1 {
  font-size: 1.875rem; /* 30px mobile */
}

@media (min-width: 768px) {
  h1 { font-size: 2.5rem; } /* 40px tablet+ */
}

@media (min-width: 1024px) {
  h1 { font-size: 3rem; } /* 48px desktop */
}
```

---

## Depth and Shadows

Shadows create depth and separate layers. Use them intentionally:

### Shadow Elevation System

Build a scale of shadows for different elevations:
- **sm**: Subtle, for cards and slight lifts
- **md**: Default, for dropdowns and popovers  
- **lg**: Prominent, for modals and dialogs
- **xl**: Dramatic, rarely needed

### Natural Shadow Direction

Light comes from above. Shadows should:
- Fall downward (positive Y offset)
- Be slightly diffused (blur radius)
- Use semi-transparent black, not gray

```css path=null start=null
/* Natural shadow */
box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1);

/* Unnatural (shadow going up) - avoid */
box-shadow: 0 -4px 6px rgb(0 0 0 / 0.1);
```

### Combining Shadows

Layered shadows look more realistic:

```css path=null start=null
/* Two shadows: soft ambient + sharper direct */
box-shadow: 
  0 1px 3px rgb(0 0 0 / 0.1),
  0 10px 20px rgb(0 0 0 / 0.05);
```

*Note: If your design system avoids shadows, use borders or background color differences to create separation.*

---

## Images and Icons

### Icon Sizing

Icons should feel balanced with adjacent text:
- For inline icons: slightly smaller than text line-height
- For standalone icons: size proportional to touch target

```html path=null start=null
<!-- Icon sized relative to text -->
<button class="flex items-center gap-2">
  <svg class="w-5 h-5">...</svg>
  <span class="text-base">Save</span>
</button>
```

### Icon Stroke Width

Thinner strokes feel more refined, thicker strokes feel friendlier:
- **1.5-2px**: Modern, elegant
- **2-2.5px**: Balanced, versatile  
- **3px+**: Bold, playful

Match stroke weight to your typography weight.

---

## Empty States

Don't leave empty states blank. They're an opportunity:
- Explain what will appear here
- Guide the user to take action
- Use illustrations or icons to soften the emptiness

```html path=null start=null
<div class="text-center py-12">
  <svg class="mx-auto h-12 w-12 text-gray-400">...</svg>
  <h3 class="mt-2 text-sm font-medium text-gray-900">No projects</h3>
  <p class="mt-1 text-sm text-gray-500">Get started by creating a new project.</p>
  <button class="mt-4">Create Project</button>
</div>
```

---

## Dark Mode Design

Dark mode isn't just inverting colors. It requires a different approach:

### Reduce Contrast, Not Invert

- **Don't use pure white text** on dark backgrounds—it's too harsh. Use `gray-100` or `gray-200`
- **Don't use pure black backgrounds**—use `gray-900` or `gray-950` (e.g., `#0f172a`)
- **Reduce elevation shadows**—they're less visible on dark; use subtle borders or lighter backgrounds instead

### Color Adjustments

```css path=null start=null
/* Light mode */
--bg-primary: #ffffff;
--text-primary: #111827;    /* gray-900 */
--text-secondary: #6b7280;  /* gray-500 */

/* Dark mode - not just inverted */
--bg-primary: #0f172a;      /* slate-900 */
--text-primary: #f1f5f9;    /* slate-100 */
--text-secondary: #94a3b8;  /* slate-400 */
```

### Saturation Shifts

Colors appear more vibrant on dark backgrounds. **Reduce saturation** slightly for primary colors in dark mode to avoid overwhelming the user.

### Surface Hierarchy

Use lighter surfaces (not shadows) to indicate elevation:
- **Base**: `bg-gray-900`
- **Raised card**: `bg-gray-800`
- **Modal/dropdown**: `bg-gray-700`

---

## Form Design Patterns

Forms are where users do work. Make them effortless:

### Input Styling

```css path=null start=null
/* Well-designed input */
.input {
  @apply w-full px-3 py-2
         text-gray-900 placeholder-gray-400
         bg-white border border-gray-300 rounded-lg
         focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent
         transition-shadow duration-150;
}
```

### Label Placement

- **Above the input** (not inline) for most forms—clearer scanning
- **Floating labels** only if space is extremely tight
- **Required indicators**: Use `*` after the label, not before

### Error States

- Change border to `border-red-500`
- Add error icon inside input (right side)
- Show error message below input in `text-red-600 text-sm`
- Don't just rely on color—add an icon or text

### Field Grouping

```html path=null start=null
<!-- Group related fields visually -->
<fieldset class="space-y-4">
  <legend class="text-sm font-medium text-gray-700">Billing Address</legend>
  <!-- address fields with tighter spacing -->
</fieldset>

<!-- Separate groups with more space -->
<fieldset class="space-y-4 mt-8">
  <legend class="text-sm font-medium text-gray-700">Payment Method</legend>
  <!-- payment fields -->
</fieldset>
```

### Button Placement

- Primary action on the **right** (or bottom-right for forms)
- Secondary/cancel action on the **left** with less visual weight
- Destructive actions should require confirmation

---

## Accessibility Beyond Contrast

Accessibility is design quality, not a checkbox:

### Focus States

**Every interactive element needs a visible focus state.** Don't remove outlines without replacing them:

```css path=null start=null
/* Bad - removes accessibility */
:focus { outline: none; }

/* Good - replaces with visible ring */
:focus {
  outline: none;
  ring: 2px;
  ring-color: blue-500;
  ring-offset: 2px;
}

/* Tailwind shorthand */
.btn { @apply focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2; }
```

### Motion Sensitivity

Respect `prefers-reduced-motion`:

```css path=null start=null
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Interactive Element Sizing

- **Minimum touch target**: 44×44px (48×48px preferred)
- **Adequate spacing** between clickable elements (at least 8px gap)
- **Large enough text** in buttons—minimum 14px

### Semantic HTML

- Use `<button>` for actions, `<a>` for navigation
- Use heading hierarchy (`h1` → `h2` → `h3`), don't skip levels
- Use `<nav>`, `<main>`, `<aside>`, `<footer>` landmarks
- Add `aria-label` when visual context isn't enough

---

## Subtle Animation & Transitions

Motion should feel natural, not distracting:

### Timing Principles

- **Micro-interactions**: 100-200ms (hover, focus, toggle)
- **Small transitions**: 200-300ms (dropdowns, tooltips)
- **Larger transitions**: 300-500ms (modals, page transitions)
- **Never exceed 500ms** for UI—it feels sluggish

### Easing Functions

```css path=null start=null
/* Enter: start fast, end slow (ease-out) */
.dropdown-enter { transition: all 200ms ease-out; }

/* Exit: start slow, end fast (ease-in) */
.dropdown-exit { transition: all 150ms ease-in; }

/* UI interactions: smooth (ease-in-out) */
.btn { transition: all 150ms ease-in-out; }
```

### What to Animate

**Do animate:**
- Background color on hover
- Transform (scale, translate) for emphasis
- Opacity for appear/disappear
- Box-shadow for elevation changes

**Don't animate:**
- Width/height (causes layout shift—use transform: scale instead)
- Anything that triggers layout recalculation
- Too many things at once

### Hover Feedback

```css path=null start=null
/* Subtle but noticeable */
.card {
  @apply transition-all duration-150 ease-in-out
         hover:shadow-md hover:-translate-y-0.5;
}

.btn {
  @apply transition-colors duration-150
         hover:bg-blue-600;
}
```

---

## Design Audit Checklist

Use this to review any interface:

### Hierarchy
- [ ] Can you identify the primary action in 2 seconds?
- [ ] Is there clear visual distinction between primary, secondary, and tertiary elements?
- [ ] Are labels de-emphasized relative to values?

### Typography
- [ ] Using a consistent type scale (no arbitrary sizes)?
- [ ] Line length constrained to 45-75 characters?
- [ ] Headings tighter, body text more relaxed line-height?

### Color
- [ ] No pure black (#000) or pure white (#fff) in the UI?
- [ ] Grays have subtle color tint (warm or cool)?
- [ ] All text passes WCAG AA contrast (4.5:1 body, 3:1 large)?

### Spacing
- [ ] Using a consistent spacing scale?
- [ ] Related items grouped tightly, sections separated clearly?
- [ ] Generous padding on cards and sections?

### Responsive
- [ ] Works on 320px screens?
- [ ] Touch targets at least 44×44px on mobile?
- [ ] Typography scales appropriately?

### Accessibility
- [ ] All interactive elements have visible focus states?
- [ ] Not relying on color alone to convey meaning?
- [ ] Semantic HTML structure?

---

## Quick Reference: Common Mistakes

1. **Too many font sizes** — Stick to your scale
2. **Not enough contrast** between hierarchy levels
3. **Cramped spacing** — When in doubt, add more
4. **Pure black text** — Use dark gray instead
5. **Border-heavy design** — Try spacing and background colors instead
6. **Inconsistent spacing** — Use your scale religiously
7. **Desktop-first thinking** — Start mobile, enhance up
8. **Arbitrary values** — Every number should come from a system
9. **Removing focus outlines** — Replace, don't remove
10. **Over-animating** — Subtle > flashy
