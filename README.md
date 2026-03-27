# Refactoring UI Design Skill

An opinionated agent skill for building professional UI without a designer, based on [Refactoring UI](https://www.refactoringui.com/) principles by Adam Wathan & Steve Schoger.

## What This Skill Covers

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

Unlike other Refactoring UI skills, this one includes:

1. **Dark Mode Design** — Surface hierarchy, saturation shifts, proper dark palettes
2. **Form Design Patterns** — Complete form styling guidance
3. **Accessibility Section** — Beyond contrast ratios (focus, motion, semantics)
4. **Animation Principles** — Timing, easing, what to animate
5. **Design Audit Checklist** — Structured review process
6. **Mobile-First Focus** — Detailed responsive patterns

## Credits

Based on [Refactoring UI](https://www.refactoringui.com/) by Adam Wathan & Steve Schoger. 

**This skill does not replace the book.** If you want to truly understand UI design as a developer, buy and read Refactoring UI — it's one of the most practical design resources available.

## License

MIT
