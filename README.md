# Refactoring UI Design Skill

An opinionated agent skill for building professional UI without a designer, based on [Refactoring UI](https://www.refactoringui.com/) principles by Adam Wathan & Steve Schoger.

## What This Skill Covers

### Design Thinking
- **Design Personality & Tone** — Formal/casual, reserved/expressive framework with domain anchors
- **Color Theory & Psychology** — Color wheel, harmony schemes, hue psychology, saturation as a design lever
- **Layout Decision Framework** — Content-first layout selection, density spectrum, domain layout profiles
- **Breaking AI Defaults** — Named anti-patterns (purple gradients, SaaS templates) with concrete alternatives
- **Component Variation** — Same component, different design based on context

### Execution
- **Visual Hierarchy** — Size, weight, and color as tools for emphasis
- **Typography** — Modular scales, line height, letter spacing, weight strategy
- **Color** — HSL palettes, UI states, warm/cool grays, accessibility
- **Spacing** — Consistent scales, proximity relationships
- **Layout** — Max-width constraints, breathing room, alignment
- **Mobile-First** — Breakpoint strategy, touch targets, responsive typography
- **Depth & Shadows** — Elevation systems, natural shadow direction
- **Dark Mode** — Systematic approach (not just inverted colors)
- **Form Patterns** — Input styling, labels, errors, field grouping
- **Accessibility** — Focus states, motion sensitivity, semantic HTML
- **Animation** — Timing, easing, what to animate
- **Design Audit Checklist** — Structured review framework

## Installation

### Claude Code / Warp / Cursor

```bash
# Clone to your skills directory
git clone https://github.com/jaywilburn/refactoring-ui-skill.git ~/.agents/skills/refactoring-ui
```

Or copy `skills/refactoring-ui/SKILL.md` to your preferred skills location:
- Claude Code: `~/.claude/skills/refactoring-ui/`
- Codex CLI: `~/.codex/skills/refactoring-ui/`
- Cursor: `.cursor/skills/refactoring-ui/`

### Via npx (once indexed)

```bash
npx skills add jaywilburn/refactoring-ui-skill/refactoring-ui
```

## When It Triggers

The skill activates when you're:
- Creating new pages or components
- Making design additions or changes
- Asking about colors, fonts, spacing, layout
- Discussing "how should this look"
- Reviewing or critiquing existing interfaces
- Working on responsive/mobile design

## Example Prompts

```
"How should I style this card component?"
"What colors should I use for this dashboard?"
"Make this form look more professional"
"Review this page layout"
"Help me set up a consistent spacing system"
```

## Differentiators

Unlike other UI design skills, this one fights AI-generated sameness head-on:

1. **Design Thinking Layer** — Strategic decisions (personality, color theory, layout strategy) before tactical execution
2. **Anti-AI-Sameness** — Explicitly names and provides alternatives to common AI defaults (purple gradients, SaaS templates, uniform card grids)
3. **Color Theory & Psychology** — Full color wheel, harmony schemes, hue psychology, and saturation strategies — not just "pick a palette"
4. **Domain-Aware Design** — Personality profiles and layout patterns for fintech, healthcare, e-commerce, creative tools, dev tools, and more
5. **Component Variation** — Cards, navs, buttons, and tables styled differently based on context, not copied from a template
6. **Dark Mode Design** — Surface hierarchy, saturation shifts, proper dark palettes
7. **Form Design Patterns** — Complete form styling guidance
8. **Accessibility Section** — Beyond contrast ratios (focus, motion, semantics)
9. **Animation Principles** — Timing, easing, what to animate
10. **Design Audit Checklist** — Structured review process including personality and intent checks

## Credits

Based on [Refactoring UI](https://www.refactoringui.com/) by Adam Wathan & Steve Schoger. 

**This skill does not replace the book.** If you want to truly understand UI design as a developer, buy and read Refactoring UI — it's one of the most practical design resources available.

## License

MIT
