---
name: Simulador de Lupa CVDentus
description: Provador de lupas odontológicas em AR facial, com visualizador 3D e simulador de magnificação
colors:
  signal-blue: "#2f5fc4"
  signal-blue-soft: "#eaf1fc"
  page-canvas: "#f4f5f7"
  card-white: "#ffffff"
  ink-primary: "#1c2130"
  ink-secondary: "#3d4457"
  ink-tertiary: "#4a5266"
  near-black: "#14161c"
  hero-scrim-top: "rgba(10,12,20,.30)"
  hero-scrim-bottom: "rgba(8,10,18,.62)"
  camera-overlay-cool: "rgba(69,96,143,.30)"
  camera-overlay-dark: "rgba(13,19,32,.55)"
  camera-overlay-dark-strong: "rgba(13,19,32,.75)"
  camera-chip-bg: "rgba(13,19,32,.6)"
  pure-black: "#000000"
  toast-bg: "rgba(20,28,46,.96)"
  hero-title-shadow: "rgba(0,0,0,.4)"
typography:
  display:
    fontFamily: "Montserrat, system-ui, sans-serif"
    fontSize: "clamp(1.625rem, 6.5vw, 2.25rem)"
    fontWeight: 700
    lineHeight: 1.08
    letterSpacing: "-0.3px"
  headline:
    fontFamily: "Montserrat, system-ui, sans-serif"
    fontSize: "21px"
    fontWeight: 700
    lineHeight: 1.3
    letterSpacing: "-0.2px"
  title:
    fontFamily: "Montserrat, system-ui, sans-serif"
    fontSize: "14.5px"
    fontWeight: 600
    lineHeight: 1.3
    letterSpacing: "0.1px"
  body:
    fontFamily: "Montserrat, system-ui, sans-serif"
    fontSize: "13px"
    fontWeight: 400
    lineHeight: 1.55
    letterSpacing: "0.1px"
  label:
    fontFamily: "Montserrat, system-ui, sans-serif"
    fontSize: "12px"
    fontWeight: 600
    lineHeight: 1.3
    letterSpacing: "1.2px"
  micro:
    fontFamily: "Montserrat, system-ui, sans-serif"
    fontSize: "10px"
    fontWeight: 500
    lineHeight: 1.3
    letterSpacing: "0.7px"
rounded:
  micro: "6px"
  xs: "13px"
  chip: "18px"
  sm: "20px"
  md: "26px"
  lg: "40px"
  pill: "999px"
spacing:
  xs: "8px"
  sm: "12px"
  md: "16px"
  lg: "24px"
  xl: "32px"
components:
  button-primary:
    backgroundColor: "{colors.signal-blue}"
    textColor: "#ffffff"
    rounded: "{rounded.pill}"
    padding: "13px 26px"
  button-hero-cta:
    backgroundColor: "#ffffff"
    textColor: "{colors.near-black}"
    rounded: "{rounded.pill}"
    padding: "13px 26px"
  button-ghost:
    backgroundColor: "#ffffff"
    textColor: "{colors.ink-primary}"
    rounded: "{rounded.pill}"
    padding: "12px 22px"
  card:
    backgroundColor: "{colors.card-white}"
    rounded: "{rounded.md}"
    padding: "24px"
  model-chip:
    backgroundColor: "{colors.card-white}"
    textColor: "{colors.ink-primary}"
    rounded: "{rounded.chip}"
    padding: "14px 10px 16px"
  model-chip-active:
    backgroundColor: "{colors.signal-blue-soft}"
    textColor: "{colors.ink-primary}"
    rounded: "{rounded.chip}"
    padding: "14px 10px 16px"
  advantage-icon:
    backgroundColor: "{colors.signal-blue-soft}"
    rounded: "{rounded.xs}"
    size: "42px"
---

# Design System: Simulador de Lupa CVDentus

## Overview

**Creative North Star: "The Quiet Instrument"**

This is a clinical tool wearing a calm, confident, technical face — not a marketing showcase. The interface gets out of the way of two things: the visitor's own live camera feed, and the six real loupe products it renders on top of it. Everything not directly in service of that (page chrome, supporting copy, secondary actions) is deliberately quiet: flat white cards on a barely-there gray canvas, one accent color spent with visible restraint, generous whitespace, and type that leans light rather than loud. The one place the system allows itself real drama is the hero — a looping product video with a dark scrim and white display type — because that's the single moment the product is allowed to perform before the tool-like interface takes over.

This system was arrived at, not assumed: an earlier glassmorphism pass (frosted panels over a blurred photo) was built, tested, and explicitly rejected as too busy and low-contrast for a tool meant to be read quickly, often on a phone, often mid-sales-conversation. The generic "sunglasses brand" aesthetic — bold color blocking, loud gradients — was rejected for the same reason: this is optical/dental equipment, not eyewear fashion.

**Key Characteristics:**
- Flat white cards, zero borders, one soft diffuse shadow vocabulary — depth by shadow, never by glass or gradient panels.
- A single accent color (Signal Blue) reserved for selection state, primary actions, and small functional accents — never used for large fills.
- Solid dark chips (near-black or blue-tinted, white text) exclusively where content sits over live camera, video, or 3D render — the one place the system trades "quiet" for "legible no matter what."
- Montserrat at every weight from 300 to 800 is the only typeface in the system; hierarchy comes from weight and letter-spacing, not from mixing families.

## Colors

One accent, spent sparingly, over a near-monochrome neutral scale — the palette itself enforces "quiet."

### Primary
- **Signal Blue** (`#2f5fc4`): the only accent in the system. Used for the active model chip's border, primary CTA fills, the step-number badge, slider thumbs, and link/hover states. Never used as a large background fill outside a button.
- **Signal Blue Soft** (`#eaf1fc`, border variant `rgba(47,95,196,.22)`): the tint form of Signal Blue — active model chip background, fine-tune hint background, "Ajuste fino" toggle pill. Signals "related to the accent" without spending full saturation.

### Neutral
- **Page Canvas** (`#f4f5f7`): the body background every card floats on.
- **Card White** (`#ffffff`): every card, chip, and pill's resting surface.
- **Ink Primary** (`#1c2130`): headings and primary text.
- **Ink Secondary** (`#3d4457`): step labels, slider labels, section body copy — the default "secondary text" tone.
- **Ink Tertiary** (`#4a5266`): tags, captions, footer copy — the quietest readable tone in the system.
- **Near-Black** (`#14161c`): the hero video card's own background/fallback, and the text color inside the white hero CTA pill — the system's one deliberately dark surface, reserved for the video-hero moment.
- **Pure Black** (`#000000`): the live-camera stage and the embedded magnification simulator's own background — distinct from Near-Black; these two containers hold third-party video/canvas content whose own color is unpredictable, so they get true black rather than the hero's tinted near-black.
- **Toast Background** (`rgba(20,28,46,.96)`): the near-opaque solid chip behind the "rastreio alinhado" calibration toast.
- **Hero Title Shadow** (`rgba(0,0,0,.4)`): the text-shadow under the hero's Display-scale title, keeping it legible over the video regardless of frame content.

### Named Rules
**The One Accent Rule.** Signal Blue appears in small, functional doses only — a border, an icon chip, a button fill, a slider thumb. It never becomes a large background surface; that would break the "quiet instrument" premise.

**The Solid-Chip Exception.** Any text or control that sits directly on top of live camera video, the looping hero video, or the 3D canvas gets a solid dark chip (near-black or blue-tinted rgba over near-black) with white text — never a translucent/glass treatment — because the content underneath is unpredictable and legibility cannot be negotiable there. The specific fills: `hero-scrim-top`/`hero-scrim-bottom` for the hero video's linear scrim, `camera-overlay-cool`/`camera-overlay-dark`/`camera-overlay-dark-strong` for the camera/3D/magnification empty-state gradients, and `camera-chip-bg` for small solid chips (viewer tag, viewer hint) floating over the 3D canvas.

## Typography

**Display/Body Font:** Montserrat (with `system-ui, sans-serif` fallback) — the only family in the system.

**Character:** One typeface carried across eight weights (300–800) lets hierarchy come entirely from weight, size, and letter-spacing rather than font-mixing — part of what keeps the system feeling like one calm instrument instead of a collage.

### Hierarchy
- **Display** (700, `clamp(26px,6.5vw,36px)`, line-height 1.08): the hero video card's title only — the one place the system is allowed to be loud, set in white with a soft text-shadow for legibility over the video.
- **Headline** (700, 21px, letter-spacing −0.2px): section titles like "Vantagens de usar a lupa."
- **Title** (600, 14–14.5px): model chip names, advantage-item titles — short, confident labels.
- **Body** (400–500, 12.5–14.5px, line-height 1.55): all supporting copy — hero subtitle, advantage descriptions, card notes, footer text.
- **Label** (600, 12px, uppercase, letter-spacing 1.2px): step labels/headings ("1 ESCOLHA O MODELO").
- **Micro** (500, 10px, uppercase, letter-spacing 0.7px): the smallest tags and hints — model tags ("TTL · FIXA"), the 3D viewer's tag/hint chips.

### Named Rules
**The Weight-Not-Family Rule.** Never introduce a second typeface for emphasis or hierarchy; reach for a heavier or lighter Montserrat weight and adjusted letter-spacing instead.

## Layout

Single-column, card-stacked flow, centered in a `max-width: 820px` main column (the hero header uses a narrower `640px`). Cards stack vertically with consistent `20px` gutters; there is no multi-column desktop layout — the tool is designed mobile-first and simply centers with breathing room on wider viewports rather than reflowing into columns.

Internal grids (model picker, advantages) use flexbox with `flex-wrap` and `justify-content: center` rather than CSS Grid's `auto-fit` — deliberately, so an incomplete last row of chips centers itself as a group instead of the leftover item(s) hugging the left edge under column 1.

Spacing rhythm is dense-but-airy: `8–14px` inside compact controls (slider rows, chip padding), `16–24px` between related elements inside a card, `28–34px` between major page sections.

## Elevation & Depth

Hybrid by design, not accident. Content cards (the white "Escolha o modelo," "Ative sua câmera," "Vantagens," etc. panels) float with a soft, low-opacity, wide-blur ambient shadow and no border at all — depth reads as "resting on the canvas," not "boxed in." Anywhere content sits over unpredictable imagery instead — the live camera stage, the hero video, the 3D viewer, the calibration toast — the system switches to solid dark chips instead of shadow-based elevation, because legibility there cannot depend on what's rendering underneath.

### Shadow Vocabulary
- **Ambient resting shadow** (`0 1px 2px rgba(16,24,40,.03), 0 14px 34px rgba(16,24,40,.07)`): the default for every card, chip, and pill button at rest.
- **Lifted hover shadow** (e.g. `0 10px 24px rgba(16,24,40,.08)`): model chips and footer link pills on hover — slightly wider spread, paired with a `translateY(-2px)` lift.
- **Accent glow** (`0 8–12px 20–26px rgba(47,95,196,.22–.28)`): reserved for Signal Blue buttons (primary CTA, catalog link) — the shadow itself is tinted, not neutral gray, reinforcing which controls are the accent.
- **Video/hero shadow** (`0 12px 26px rgba(0,0,0,.35)`): the white CTA pill sitting on the dark hero card — a heavier, near-black shadow appropriate to a dark surface.

### Named Rules
**The Ambient-By-Default Rule.** Shadows are soft, wide, and low-opacity at rest everywhere except the dark hero/camera/3D surfaces. A harder or tinted shadow is a deliberate signal (hover state, accent action), never a resting default.

## Shapes

Rounded and border-free is the rule: nothing in the system has a visible stroke border at rest (the one conditional exception is the 1.5px transparent border reserved on model chips purely to hold layout space for the active-state blue border, so selecting a chip never shifts its neighbors). Corner radius scales with a component's size and prominence rather than using one fixed value everywhere: the scan-frame's corner brackets use `rounded.micro` (6px) — deliberately tighter than any chip, since they're a viewfinder reticle, not a card; icon-scale chips and small solid chips (the calibration toast, the fine-tune hint) use `rounded.xs` (13px), model chips use `rounded.chip` (18px), the camera/viewer/magnification stages use `rounded.sm` (20px), content cards use `rounded.md` (26px), and the hero video card — the single largest, most prominent surface — gets the system's largest radius, `rounded.lg` (40px). Every button and pill-shaped chip (CTA, ghost button, footer link, badge) uses full pill radius (999px).

## Components

### Buttons
- **Shape:** full pill (`border-radius: 999px`) for every button variant.
- **Primary** (`button-primary`): Signal Blue fill, white text, `13px 26px` padding, tinted blue glow shadow. Used for the catalog link.
- **Hero CTA** (`button-hero-cta`): white fill, near-black text — the inverse of Primary, used only inside the dark hero video card where a blue-on-dark button would lose the "quiet" restraint and a black-on-dark button would disappear.
- **Ghost** (`button-ghost`): white fill, ink text, no border — separation comes entirely from the ambient shadow; hover shifts text to Signal Blue and deepens the shadow slightly. Used for secondary actions like "Pausar giro" / "Vista inicial."
- **Hover / Active:** buttons lift 2px and deepen their shadow on hover; `scale(.97)` on active/press for tactile feedback. No color-shift on Primary hover beyond a slight brightness lift.

### Chips / Badges
- **Model chip** (`model-chip` / `model-chip-active`): the model picker's selectable unit — white card at rest, Signal-Blue-Soft background with a Signal Blue border when active. Holds a product thumbnail, a title-weight name, and an uppercase label-weight tag (e.g. "FLIP-UP").
- **Step label / section kicker:** label-weight uppercase text paired with a small filled circular step-number badge (Signal Blue fill, white numeral) — the system's wayfinding device through the linear flow.
- **Solid dark chips** (viewer tag, viewer hint): `camera-chip-bg` fill, white text, no ambient shadow needed since they already read as "floating over video." The calibration toast uses its own `toast-bg` (`rgba(20,28,46,.96)`) — near-opaque rather than translucent, since it's a fixed-position confirmation message rather than a chip resting on a canvas.
- **Advantage icon** (`advantage-icon`): a 42px Signal-Blue-Soft square at `rounded.xs` (13px) holding a single emoji glyph — the small icon-chip form the rounded scale's smallest step exists for.

### Cards / Containers
- **Corner Style:** 26px radius (`rounded.md`).
- **Background:** solid Card White — never translucent, never gradient (the hero card is the sole exception, as a video-background surface rather than a content card).
- **Shadow Strategy:** Ambient resting shadow (see Elevation & Depth); no border.
- **Internal Padding:** 24px.

### The Hero Video Card (signature component)
The system's one deliberately expressive surface: a looping, muted product video fills the entire card edge-to-edge, a dark linear scrim (`rgba(10,12,20,.3)` to `rgba(8,10,18,.62)`, top to bottom) sits above it for guaranteed text contrast, and the display-weight title, body-weight subtitle, and white hero CTA float centered on top, all in white with a soft text-shadow. This is the only place video, gradient scrims, and Display-scale type all appear together — everywhere else in the system stays flat, white, and quiet.

## Do's and Don'ts

### Do:
- **Do** spend Signal Blue only on small, functional elements (borders, icon fills, button fills, thumbs) — never as a large background.
- **Do** use a solid dark chip with white text for anything overlaid on live camera, video, or 3D canvas content.
- **Do** keep every card and pill border-free, relying on the ambient shadow vocabulary for separation.
- **Do** use flexbox with `justify-content: center` (not CSS Grid auto-fit) for any wrapping row of chips/cards, so an incomplete last row centers as a group.
- **Do** carry hierarchy through Montserrat weight and letter-spacing, not additional typefaces.
- **Do** render each social/platform logo in the footer (Instagram, TikTok, YouTube) in that platform's own official brand colors, not the system's palette — a logo rendered in Signal Blue would misrepresent the platform. These per-logo colors (e.g. `#FF1753`/`#00C9D0` for TikTok, `#C3271A` for YouTube) are an intentional exception to the palette above, scoped strictly to the real SVG logo marks.

### Don't:
- **Don't** reintroduce glassmorphism/translucent-over-photo panels — tested this session and rejected for busyness and poor contrast on a tool meant to be read quickly.
- **Don't** use a generic eyewear/sunglasses-brand visual language (bold color blocking, loud gradients) — this is dental/optical equipment, not fashion eyewear.
- **Don't** give any card or button a visible stroke border at rest; separation comes from shadow.
- **Don't** let the Display-scale hero typography or the video/scrim treatment leak into the functional cards below the hero — that expressive register is reserved for the hero moment only.
