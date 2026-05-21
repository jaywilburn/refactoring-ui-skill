---
name: refactoring-ui
description: Comprehensive UI design guidance based on Refactoring UI principles covering design personality, color theory, layout strategy, visual hierarchy, typography, spacing, mobile-first responsive design, and writing copy that doesn't read like AI wrote it. Use this skill whenever the user is creating new pages, building components, making design additions or changes, reviewing UI code, asking about design decisions (colors, fonts, spacing, layout), writing or editing interface copy, or discussing visual improvements. Trigger for any design-related conversation including "how should this look", "what color", "font size", "spacing", "layout", "responsive", "mobile", "this copy", "headline", "button text", "microcopy", or when reviewing/critiquing existing interfaces.
---

# Refactoring UI Design System

## Core Philosophy

Design decisions should be made with intention, not decoration. Every visual choice—color, size, spacing, weight—communicates hierarchy and guides the user's attention. Start with too much whitespace, then remove it. Start with less contrast, then add it where needed.

Before writing any CSS, answer: **what should this feel like?** A financial dashboard and a children's learning app demand completely different visual treatments. The sections below move from strategic thinking (personality, color theory, layout strategy) down to tactical execution (spacing values, shadow syntax, animation timing).

---

# Design Thinking

## Design Personality & Tone

Every interface has a personality whether you choose one or not. Choosing intentionally is the difference between a design that feels right and one that feels generic.

### The Personality Spectrum

Plot your design on two axes:

- **Formal ↔ Casual**: How structured and serious vs relaxed and approachable
- **Reserved ↔ Expressive**: How restrained and minimal vs bold and vibrant

Four quadrants:

| | Reserved | Expressive |
|---|---|---|
| **Formal** | Banking, legal, enterprise, government | Luxury brands, high-end retail, fashion |
| **Casual** | Developer tools, documentation, utilities | Gaming, social apps, children's education |

### Mapping Design Signals to Personality

Each visual lever pushes the design toward a quadrant:

- **Border-radius**: 2-4px (formal) → 8-12px (moderate) → 16px+ (casual). Match to personality—don't default to max.
- **Font choice**: Geometric sans like Inter/Roboto (modern, neutral), humanist sans like Source Sans/Nunito (friendly, approachable), serif like Merriweather/Playfair (traditional, authoritative), monospace accents (technical, developer-oriented)
- **Color saturation**: Low/muted (reserved) → high/vibrant (expressive). See Color Theory section.
- **Whitespace density**: Generous (formal, premium) → tight (casual, energetic, data-dense)
- **Shadow style**: Subtle and diffused (reserved) → dramatic with strong offsets (expressive). Or no shadows at all for minimal/flat designs.
- **Imagery style**: Photography (authentic, serious) → illustration (approachable, playful) → icons only (utilitarian, technical)

### Domain Personality Anchors

Use these as starting points, not rigid rules. The specific product and audience always override.

**Fintech / Banking**: Formal + reserved. Muted blues and greens, small border-radius (4-6px), geometric sans-serif, dense data layouts, minimal decoration. Trust is communicated through restraint.

**Healthcare / Medical**: Formal + reserved. Calming blues, greens, or teals. Generous whitespace, clear section breaks, large touch targets. Accessibility is non-negotiable. Avoid anything that feels playful—patients want confidence.

**E-commerce**: Varies by market segment. Budget/mass-market = casual + expressive (bright colors, large CTAs, energy). Luxury = formal + expressive (muted palette, serif headings, dramatic whitespace, restrained CTAs).

**Creative Tools**: Casual + expressive. Bold accent colors against neutral backgrounds. Asymmetric layouts, personality in empty states and onboarding. The tool should feel inspiring, not corporate.

**Education**: K-12 = casual + expressive (warm colors, rounded shapes, friendly type, illustrations). Professional/adult learning = casual + reserved (clean, focused, minimal distraction from content).

**SaaS Dashboards**: Casual + reserved. Neutral base palette with functional color for data and states. Dense but organized. The interface should disappear—users are here for the data, not the design.

**Media / Content**: News = formal + reserved (classic typography, structured grids, minimal color). Entertainment = casual + expressive (bold imagery, vivid color, immersive layouts).

**Developer Tools**: Casual + reserved. Monospace accents, dark mode preference, minimal decoration. High information density done well. Let the content breathe but don't waste space on decoration.

### The "Who Is This For?" Checklist

Before making any visual choices, answer these:

1. **Who is the primary user?** (Age, technical literacy, context of use)
2. **What emotional response should this evoke?** (Trust, excitement, calm, urgency)
3. **What builds trust in this domain?** (Restraint? Polish? Friendliness? Data density?)
4. **What do competitors look like?** (And how should this differentiate without being alien?)
5. **Which personality quadrant does this land in?**

---

## Color Theory & Psychology

The existing Color section below covers *how* to build palettes with HSL and manage shades. This section covers *which* colors to choose and *why*.

### Color Wheel Fundamentals

Colors divide into warm and cool:

- **Warm side** (red, orange, yellow): These colors advance—they feel closer, more energetic, more urgent. Use them for elements that need attention.
- **Cool side** (blue, green, purple): These recede—they feel farther, calmer, more stable. Use them for backgrounds, containers, and trust signals.

This warm/cool dynamic is a fundamental tool. A dashboard with a cool blue background and warm orange alert badges creates natural visual hierarchy through color temperature alone.

### Color Harmony Schemes

How you combine colors determines the overall feel:

**Analogous** (adjacent hues on the wheel, e.g., blue + blue-green + green):
Cohesive and calm. Low internal contrast. Best for interfaces that should feel unified and serene—content apps, healthcare, meditation. Risk: can feel monotonous without a neutral or accent to break it up.

**Complementary** (opposite hues, e.g., blue + orange):
High energy and contrast. Best for elements that need to pop—CTAs against their background, marketing pages, attention-grabbing moments. Risk: can feel harsh if both colors are at full saturation. Mute one side.

**Split-complementary** (one hue + the two hues adjacent to its complement):
Vibrant but more balanced than straight complementary. Best for designs that need variety without chaos. Gives you a clear primary with two supporting accents.

**Triadic** (three equidistant hues, e.g., red + yellow + blue):
Vibrant and balanced. Best for playful, creative apps. Use with restraint—one dominant, two as accents at lower saturation. Full-strength triadic is overwhelming.

For most product interfaces, **analogous with one complementary accent** is the safest and most professional starting point.

### Color Psychology by Hue

Each hue carries associations. Use these as starting points, then adjust for your specific domain and audience:

**Blue**: Trust, stability, calm, professionalism. The most universally safe choice—which is also why it's overused. Finance, healthcare, enterprise, social media. If you reach for blue, make sure it's because it fits, not because it's default.

**Green**: Growth, health, money, nature, success. Fintech, wellness, sustainability, positive states. Pairs well with blue for trust + growth.

**Red**: Urgency, energy, passion, danger. Food and restaurant apps, entertainment, sale CTAs, error states. Use sparingly in interfaces—a little red goes far. As a primary color, it's intense; as an accent, it's powerful.

**Purple**: Luxury, creativity, mystery, spirituality. Beauty, premium products, creative tools. **Note: AI massively overuses purple/violet as a default.** Only reach for purple if the domain genuinely calls for it.

**Orange**: Warmth, enthusiasm, friendliness, affordability. Social apps, education, CTAs, construction/energy. Less aggressive than red, more energetic than yellow. Underused in product design.

**Yellow**: Optimism, attention, caution, warmth. Best as a highlight or accent—difficult as a primary color because of readability on white backgrounds. Works well for warnings, badges, and drawing focus.

**Neutrals** (grays, off-whites, near-blacks): Sophistication, content-first design. Photography portfolios, editorial sites, developer tools. Letting the content be the color is itself a design choice—and often the most elegant one.

### Cultural Context

Color associations vary by culture. Consider your audience:

- White: purity and cleanliness (Western) vs mourning (parts of East Asia)
- Red: danger and stopping (Western) vs luck and prosperity (Chinese, Indian)
- Green: nature and go (Western) vs Islam (Middle East)
- Yellow: happiness (Western) vs mourning (parts of Latin America)

For global products, lean on blues and greens (most universally positive) and test assumptions with your target audience.

### Saturation as a Design Lever

Saturation is the most underused tool for escaping generic AI design:

- **High saturation**: Energetic, playful, youthful, attention-grabbing. Use for consumer apps, children's products, marketing pages.
- **Low/muted saturation**: Sophisticated, calm, mature, professional. Use for enterprise, healthcare, finance, content-focused apps.
- **The muted palette trick**: Take any hue and reduce saturation by 20-40%. The result instantly looks more intentional and designed. Most AI-generated UIs use fully saturated colors—muting them is the single fastest way to escape the "AI look."
- **Mixed saturation strategy**: Muted base palette for backgrounds and containers, one saturated accent color for primary actions and key data. This creates focus without visual noise.

```css
/* AI default: fully saturated, feels generic */
--primary: hsl(250, 90%, 55%);

/* Muted: same hue, instantly more sophisticated */
--primary: hsl(250, 45%, 50%);

/* Even more restrained: works for enterprise/formal */
--primary: hsl(250, 30%, 45%);
```

### The Palette Decision Tree

1. **Determine personality** (from Design Personality section) → this sets your saturation range
2. **Pick dominant hue** based on color psychology and what your domain needs to communicate
3. **Choose harmony scheme** based on how much variety you need (analogous for calm, split-complementary for energy)
4. **Set saturation** to match personality (formal/reserved = muted, casual/expressive = vivid)
5. **Build the full palette** using the HSL shade-building mechanics in the Color section below

---

## Layout Decision Framework

Layout should be driven by content and user goals, not by template defaults.

### Content-First Layout Selection

Start by identifying the primary content type, then match the layout pattern:

**Long-form text** (articles, documentation, policies):
Narrow single column, 65ch max-width. Minimal sidebar distractions. Reading is linear—the layout should be too.

**Data comparison** (analytics, pricing, feature comparison):
Multi-column tables or side-by-side panels. Users need to scan horizontally. Dense but aligned.

**Status monitoring** (dashboards, ops consoles, admin overviews):
Dense card grids with visual indicators (color, icons, sparklines). Information density is a feature. Prioritize scanability over aesthetics.

**Media browsing** (galleries, portfolios, product catalogs):
Masonry or uniform grid. Let the content be the design. Minimal chrome, maximum visual real estate.

**Sequential workflow** (onboarding, checkout, multi-step forms):
Stepped/wizard layout. One task per screen. Progress indicator. Remove distractions—hide the main nav if needed.

**Exploration / discovery** (social feeds, marketplaces, content discovery):
Asymmetric layouts, varied card sizes, visual hooks. The layout should invite browsing. Infinite scroll or paginated based on content depth.

### Information Density Spectrum

How much to show at once depends on who's using it and what they need:

**Sparse** (marketing sites, onboarding flows):
Large type (18-24px body), generous whitespace (48-96px between sections), few elements per screen. Every element is a deliberate choice. Padding is a feature.

**Moderate** (most product interfaces):
Standard type (16px body), balanced spacing (24-48px between sections), clear grouping. The workhorse density for most apps.

**Dense** (dashboards, admin panels, developer tools, financial terminals):
Compact type (13-14px body), tighter spacing (12-24px between sections), more elements visible at once. Users are experts—they want data, not whitespace. Still needs clear hierarchy and grouping.

Each density level implies different defaults for your spacing scale, font sizes, component padding, and border-radius.

### Navigation Pattern Selection

Choose based on your app's structure:

- **Top horizontal nav**: Best for marketing sites and apps with fewer than 5 top-level sections. Clean, familiar, leaves vertical space open.
- **Sidebar nav**: Best for apps with 5+ sections, complex hierarchies, or where users switch contexts often. Persistent and scannable.
- **Tab bar**: Best for distinct content views within a section. Keep to 2-5 tabs.
- **Bottom nav (mobile)**: Best for mobile-primary apps with 3-5 core destinations. Thumb-friendly.
- **Hybrid** (top nav + sidebar): Best for documentation sites, complex SaaS. Section navigation up top, page tree in sidebar.

### Domain Layout Profiles

Concrete starting points that reinforce the personality anchors:

**Fintech dashboard**: Sidebar nav with icon + label. Main area: stat cards across the top row, data table or chart below. Dense grid. Muted palette with color reserved for data visualization and status indicators.

**Creative portfolio**: Full-bleed hero image. Asymmetric project grid below. Minimal nav (logo + hamburger, or a few text links). Generous whitespace between projects. Let the work speak.

**Healthcare portal**: Centered layout, max-width ~720px. Clear section headings. Generous padding on form groups. Step-by-step flows for complex tasks. Obvious "next" actions. No dense data on patient-facing screens.

**E-commerce storefront**: Product grid with filters sidebar (collapsible on mobile). Sticky header with cart. Prominent "Add to Cart" CTAs. Quick-view modals for product details. Visual hierarchy: image → price → name → reviews.

**Developer documentation**: Fixed sidebar with collapsible page tree. Narrow content column (~65ch). Code blocks with syntax highlighting and copy button. "On this page" section for long docs. Version selector in top nav.

**Social / community app**: Single-column feed, max-width ~600px. Floating compose button. Inline interactions (like, reply) without page transitions. Infinite scroll. Minimal nav—the feed is the experience.

**Admin panel**: Sidebar nav with grouped sections. Data tables with sort, filter, bulk select. Settings as grouped form sections, not individual pages. Breadcrumbs for deep hierarchies.

**Content / media app**: Wide content area for articles or video. Minimal chrome during consumption. Related content below or in a minimal sidebar. Reading/viewing mode that strips away UI.

### Breaking the Single-Page-App Trap

Not everything belongs on one screen:

- **Multi-step processes**: Use wizard flows. Don't make the user see steps they haven't reached.
- **Infrequent settings**: Separate page or dedicated panel. Don't clutter the main view with rarely-used controls.
- **Complex detail views**: Dedicated page, not inline expansion, when the detail has its own depth (sub-items, related content, actions).
- **Rule of thumb**: If you're scrolling more than 3 viewport heights, the page is doing too much. Consider splitting.

---

## Breaking AI Defaults

AI agents gravitate toward the statistical average of their training data. This section names those defaults explicitly so you can avoid them.

### The Usual Suspects

These are the patterns that make users say "this looks AI-generated":

1. **Purple/blue gradient backgrounds** — Applied to headers, heroes, cards, buttons, everything
2. **Maximum border-radius everywhere** — `rounded-2xl` or `rounded-full` on every element regardless of context
3. **Generic SaaS hero** — Gradient text headline, vague subheading, "Get Started" button, decorative blobs
4. **The 3-card grid** — Three identical cards in a row for every feature/benefit/pricing section
5. **Shadows on everything** — Every card and button has `shadow-lg`, creating a "everything floats" look
6. **Indigo/violet as the default color** — When no color is specified, AI reaches for purple
7. **SaaS landing page template** — Hero → features grid → testimonials → CTA. Applied to every project regardless of what it actually is
8. **Uniform rhythm** — Every section has identical spacing, creating a monotonous visual beat

### Why This Happens

Training data is heavily weighted toward SaaS marketing sites, Tailwind UI examples, and component libraries. These are well-designed in context, but when every project draws from the same well, everything looks the same. The agent produces the statistical average of "modern web design."

### The Antidote

For each default, a concrete alternative:

**Gradients** → Use solid colors. If you want depth, try subtle texture, a single-tone background with a contrasting element, or reserve gradients for one small accent (a progress bar, a status indicator) rather than a full section.

**Max border-radius** → Match radius to personality. A formal financial app: 4-6px. A friendly consumer app: 8-12px. Full rounding only for specific elements like avatars and tags. Consistency matters more than roundness.

**Generic heroes** → Design the hero around the actual product. Show the product, show a real use case, or skip the hero entirely. The best hero is often just a clear headline and a focused CTA with no decorative elements.

**3-card grid** → Ask what the content actually is. Features might work as an icon list. Pricing works as a comparison table. Testimonials work as a single rotating quote. Use the layout that serves the content, not the template that's familiar.

**Shadows everywhere** → Use borders, background color differences, or just whitespace to create separation. Shadows should indicate *elevation*—interactive elements that float above the page (dropdowns, modals). If everything has a shadow, nothing is elevated.

**Default indigo** → Run through the Color Theory section. Pick a hue based on what the product communicates, not what feels safe. An earth-tone palette, a warm gray with terracotta accents, or a monochrome scheme with one vivid accent all feel more intentional than indigo.

**SaaS template for everything** → Reference the Design Personality and Layout Decision Framework sections first. A healthcare portal doesn't need a hero section. A dashboard doesn't need testimonials. Build the layout around what the user needs, not what a landing page template provides.

**Uniform rhythm** → Vary section spacing based on content relationships. Related content sections: 48px gap. Major topic shifts: 96px gap. The most important section gets the most breathing room. Visual rhythm should have variation, like music.

### The AI Gut-Check

Before finalizing any design, ask:

> "If I showed this to a developer, would they guess an AI made it?"

If yes, identify the most generic element—it's usually the color scheme or the layout structure—and make it specific to the project using the frameworks above.

---

## Writing Copy That Doesn't Read Like AI

Visual choices give away AI-generated UI, but copy gives it away just as fast. The goal isn't "good marketing copy"—it's prose that reads like a writer at the New York Times wrote it, not a language model trying to sound polished.

### The Tells

The patterns that scream "AI wrote this":

1. **Em-dash addiction** — Every other sentence has one—often where a comma, period, or parenthetical would do the job better. AI reaches for the em-dash as a default rhythm break.
2. **Choppy sentence fragments. Used for emphasis. Way too often.** — Short staccato sentences strung together to feel punchy. Real writers vary cadence.
3. **"It's not just X, it's Y"** — And its cousins: "More than just X." "Not only X, but Y." These parallel constructions are a reflex, not a thought.
4. **"Whether you're X or Y"** — Followed by a list of two contrived audiences that supposedly both benefit. Almost always cut-able.
5. **"From X to Y"** — "From startups to enterprises." "From idea to launch." The lazy way to suggest range.
6. **Tricolons everywhere** — "Fast, simple, powerful." "Built for speed, scale, and security." Three-item lists in every sentence becomes a tic.
7. **Empty intensifiers** — "Truly," "genuinely," "incredibly," "seamlessly," "effortlessly." Words that add syllables but no meaning.
8. **Marketing clichés** — "Game-changer," "revolutionary," "cutting-edge," "best-in-class," "next-generation," "world-class." Drop them.
9. **The hollow opener** — "In today's fast-paced world..." "Imagine a world where..." "We live in an age of..." Nobody talks like this.
10. **Uniform sentence length** — Real writing has rhythm: a long winding sentence followed by a short one. Three medium-length sentences in a row is the AI default.
11. **Gerund-stacked bullets** — Every bullet starts with "Building," "Creating," "Designing," "Empowering." Parallel structure taken to the point of monotony.
12. **The mandatory CTA verb** — "Unlock," "discover," "transform," "elevate." Pick a real verb that describes what actually happens when they click.

### The Antidote

For each tell, the fix:

**Em-dashes** → Use commas when a comma works. Use periods when a period works. An em-dash is for a sharp aside or a dramatic break—not as a default connector. If you have more than one em-dash in a paragraph, you almost certainly have one too many. A single em-dash can be powerful; three in a row is a tic.

**Choppy fragments** → Let sentences breathe. A thought that could be expressed as one flowing sentence with commas usually should be, because chained fragments feel breathless and start to read like a press release written in a hurry. Vary length: short sentence after long, long after short. Read it aloud—if you can't get through it without sounding like you're delivering bullet points, rewrite.

**"It's not just X, it's Y"** → Just say Y. If X needs to be acknowledged, give it its own sentence with its own thought, not as a foil for the real point.

**"Whether you're X or Y"** → Pick the actual user. If the copy genuinely serves two distinct audiences, write to one at a time. Generic "whether you're" framing serves neither.

**"From X to Y"** → Name a specific example. "From small teams to Fortune 500" is generic; "Teams at Stripe and Notion use this" is concrete.

**Tricolons** → Use two-item phrases, or one strong adjective. "Fast and reliable" beats "fast, reliable, and powerful." A single well-chosen word beats three weak ones.

**Empty intensifiers** → Cut them. "Genuinely useful" → "useful." "Incredibly fast" → "fast" (or give a number). If the noun is doing its job, the intensifier is dead weight.

**Marketing clichés** → Describe what the product actually does. Instead of "revolutionary platform," say what it replaces or what it lets the user do that they couldn't before.

**Hollow openers** → Start with the specific. The first sentence should contain a concrete noun, a specific verb, or a real claim. If the opener could apply to any product in the category, rewrite.

**Uniform rhythm** → Read the copy aloud. If every sentence lands at the same length, break the pattern. A short sentence after a long one creates emphasis. A long sentence after several short ones gives the reader room to settle in.

**Gerund-stacked bullets** → Vary the openings. Mix imperatives ("Ship faster"), nouns ("A real audit trail"), and full sentences. Bullets aren't a parallel-structure exam.

**Hollow CTA verbs** → Use the actual verb. "Start your free trial." "See pricing." "Read the docs." Plain language outperforms "Unlock your potential."

### The Reference Standard

Read a column from The New York Times, The Atlantic, or a writer you respect. Notice:

- Sentences vary in length and structure
- Commas do most of the rhythmic work; em-dashes are rare and load-bearing when they appear
- Specificity beats abstraction (a name, a number, a place, a concrete detail)
- The voice has a point of view—it's not trying to please everyone
- Adjectives are chosen carefully, not stacked

Then read your copy. If the gap is obvious, the copy needs another pass.

### The Copy Gut-Check

Before shipping any copy, ask:

> "If I read this aloud, does it sound like a person talking, or like a language model trying to sound polished?"

If it's the latter, the most common culprits are em-dashes, sentence rhythm, and clichéd phrasings. Fix those three and the copy usually snaps into something a human would actually write.

---

## Component Variation by Context

The same component type should look different depending on where it lives and what it's doing. A "card" on an e-commerce site and a "card" on a dashboard are fundamentally different designs that happen to share a name.

### The Principle

Before styling any component, ask: **"What is this component doing here?"** — not "What does a card/button/table look like?"

Context determines:
- Border treatment (none, subtle, prominent)
- Padding density (compact, standard, generous)
- Hover behavior (none, subtle lift, color change, expand)
- Content layout (vertical, horizontal, image-led, text-led)
- Visual weight (background, shadow, border, flat)

### Card Variations

**Product card** (e-commerce):
Image-dominant (60-70% of card height). Tight padding. Price visually prominent. Hover reveals quick-add or size selector. Border-radius matches brand personality.

**Stats card** (dashboard):
Number is the hero—large, bold, maybe colored by status. Compact padding. Optional sparkline or trend indicator. No hover effect needed. Minimal decoration; the data is the design.

**Profile card** (social/team directory):
Avatar-led. Can be horizontal layout (avatar left, info right). Action buttons inline (message, follow). Warmer, more personal treatment—maybe a subtle background color.

**Settings card** (admin/preferences):
Text-heavy, no imagery. Grouped with sibling cards in a stack. Toggle or input on the right. Minimal decoration—functional, not decorative. Consistent with form patterns.

**Content card** (blog, news, media):
Headline-dominant. Metadata (author, date, read time) de-emphasized. Generous whitespace. Hover may show a subtle underline on the title or a background shift. Image optional—not every content card needs a thumbnail.

### Navigation Variations

**Marketing site nav**: Minimal items (4-6 links). Often transparent, overlapping the hero. Logo left, CTA button right. May collapse to hamburger even on tablet for cleanliness.

**App dashboard nav**: Persistent sidebar. Icons paired with labels. Collapsible to icon-only for more content space. Active state clearly marked. Grouped sections with subtle dividers.

**Documentation nav**: Top bar for major sections or version selector. Left sidebar for the page tree with expandable/collapsible groups. "On this page" right sidebar for long documents.

**Mobile app nav**: Bottom tab bar with 3-5 items. Icons with short labels. Active state uses color, not just weight. Middle item can be a prominent action (compose, add). Avoid hamburger menus for primary navigation on mobile.

### Button Variations

**Dense data UI** (dashboards, tables, admin):
Smaller (text-sm, py-1.5 px-3). May be icon-only with tooltip. Ghost or outline style to reduce visual noise. Grouped buttons use a button group pattern.

**Marketing page**:
Larger (text-lg, py-3 px-8). Bold color fill. More horizontal padding for presence. May have an icon or arrow. Primary CTA is unmissable; secondary is clearly subordinate.

**Form context**:
Aligned with input heights. Same border-radius as inputs. Placed at the bottom-right of the form (or full-width on mobile). Submit button is primary; cancel is ghost/text-only.

**Destructive context**:
Muted by default—not screaming red. Use muted red text or outline style. On hover or in a confirmation dialog, the full red treatment appears. Never make destructive actions the most visually prominent element on the page.

### Table Variations

**Financial / numeric data**:
Right-aligned numbers for decimal alignment. Alternating row backgrounds for scannability. Compact row height. Fixed header on scroll. Monospace or tabular-nums font feature for number columns.

**Admin panel**:
Checkbox column for bulk selection. Action column with icon buttons or dropdown. Sortable column headers. Row hover highlights. Inline editing where appropriate.

**Comparison table** (pricing, features):
Highlighted "recommended" column. Sticky header row. Feature names in the left column. Check/cross icons for boolean features. Can alternate between rows and a card-based layout on mobile.

### The Component Context Checklist

Before styling any component, answer:

1. **What's the information density of this page?** (Sparse/moderate/dense → determines padding and size)
2. **What's the primary user action near this component?** (Component styling shouldn't compete with the main CTA)
3. **What personality did we establish?** (Formal components look different from casual ones)
4. **Is this the focus or supporting cast?** (Hero components get decoration; supporting components stay quiet)

---

# Execution

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

```css
/* Primary destructive action - prominent */
.btn-danger-primary { @apply bg-red-600 text-white; }

/* Secondary destructive action - muted */
.btn-danger-secondary { @apply text-red-600/70 bg-transparent; }
```

### Labels and Data

When showing label-value pairs, the data is usually more important than the label:
- De-emphasize labels (lighter color, smaller size, or all caps with letter-spacing)
- Let the values stand out naturally

```html
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

```css
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

```css
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

```css
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

```css
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

```css
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

```css
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

```css
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
- **Minimum**: 44x44px (Apple HIG) or 48x48px (Material)
- Add padding to small elements to increase hit area without visual bulk

### Typography Scaling

Reduce heading sizes on mobile—there's less room for drama:

```css
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

```css
/* Natural shadow */
box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1);

/* Unnatural (shadow going up) - avoid */
box-shadow: 0 -4px 6px rgb(0 0 0 / 0.1);
```

### Combining Shadows

Layered shadows look more realistic:

```css
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

```html
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

```html
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

```css
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

```css
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

```html
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

```css
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

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Interactive Element Sizing

- **Minimum touch target**: 44x44px (48x48px preferred)
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

```css
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

```css
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

### Personality & Intent
- [ ] Has the design personality been consciously chosen (not defaulted)?
- [ ] Does the color palette match the product's domain and audience?
- [ ] Could someone identify what kind of product this is from the design alone?
- [ ] Does this look like it was designed with intent, or assembled from defaults?
- [ ] Would someone guess an AI generated this? If yes, what's the most generic element?

### Copy
- [ ] Read aloud—does it sound like a person, or like a model trying to sound polished?
- [ ] More than one em-dash per paragraph? Replace with commas or periods.
- [ ] Any "It's not just X, it's Y" / "Whether you're X or Y" / "From X to Y" constructions? Cut or rewrite.
- [ ] Empty intensifiers ("truly," "seamlessly," "incredibly") and clichés ("game-changer," "cutting-edge") removed?
- [ ] Does sentence length vary, or is everything the same medium length?
- [ ] Do CTAs use real verbs ("See pricing") instead of marketing verbs ("Unlock potential")?

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

### Components
- [ ] Are components styled for their specific context, not generically?
- [ ] Do card, button, and nav styles vary based on where they appear?

### Responsive
- [ ] Works on 320px screens?
- [ ] Touch targets at least 44x44px on mobile?
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
11. **Defaulting to purple/blue gradients** — Pick colors based on domain and audience
12. **Same card style everywhere** — Vary components by context
13. **Picking colors without purpose** — Use color theory, not defaults
14. **SaaS template for everything** — Match layout to content type
15. **Choosing layout before understanding content** — Content drives layout, not the other way around
