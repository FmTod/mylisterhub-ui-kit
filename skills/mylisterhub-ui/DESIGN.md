# Design System: MyListerHub

## 1. Visual Theme & Atmosphere

MyListerHub is a work tool for eBay sellers who manage hundreds or thousands of listings, so the
interface is **dense, calm and utilitarian**. It favours information over decoration: flat neutral
surfaces, hairline borders and a single confident blue that marks the one thing to do next. Pages
feel like a well-organised workbench. A thin top bar and a narrow icon rail frame every screen, and
the content fills everything else, with tables running edge to edge.

The personality comes from two places only:
- **Condensed, uppercase display type** on titles, which gives an industrial, label-maker character.
- **Brand pair:** Hub Blue for action and Deep Indigo for selection.

Everything else stays quiet so that status colours and the primary button carry meaning. Light and
dark modes are equal citizens. Dark mode is near-black with charcoal cards, not a dimmed light theme.

## 2. Color Palette & Roles

**Surfaces (light / dark)**
- **Soft Paper White** (#fafafa / Pure Black #000000): page background behind lists and settings.
- **Clean Card White** (#ffffff / Charcoal Ink #0f0f11): cards, sections, top bar, side rail, table rows, modals.
- **Whisper Grey** (#f4f4f5 / Graphite #18181b): muted surfaces. Table header band, the background behind record forms (so white sections lift off it), hover and selected rows.
- **Hairline Zinc** (#e4e4e7 / Smoke #27272a): every border and divider. Input borders darken to #3f3f46 in dark mode.
- **Ink** (#09090b / Snow #fafafa): primary text.
- **Slate Mute** (#71717a / Ash #a1a1aa): secondary text, helper text, column headers, inactive tabs.

**Brand**
- **Hub Blue** (#40acff): the primary action (one per screen), active nav item, active tab underline, focus rings, links, checked switches. Also used for "success" states, so success and brand read as the same confident blue.
- **Deep Indigo** (#38317f, lifts to #5b52b8 in dark): selected state in chip rows and segmented toggles, the "hub" half of the logo, secondary badges. Never used for a call to action.
- **Ember Orange** (#dc6225): high priority and needs-attention-soon markers. Used sparingly.

**Status** (badges, alerts, toasts; never for buttons)
- **Signal Teal** (#17a2b8): informational.
- **Amber Ochre** (#c98d04): warning, pending, out of stock.
- **Rose Alarm** (#dc4c64): error, failed, destructive actions.

Alerts tint their colour at 10% for the background and 30% for the border, with text mixed 60%
toward the foreground, so they stay legible in both modes.

## 3. Typography Rules

- **Body:** Roboto at a **light 300 weight**, 16px base. This gives the interface its airy,
  low-contrast reading texture. Tables and form controls run at 14px, buttons at 13px medium (500),
  badges at 12px medium.
- **Display:** Bebas Neue Pro (Bebas Neue as the free stand-in), weight 600, always **uppercase**.
  It's used for page titles (18px), section titles (16px) and modal titles. It's tall, condensed and
  compact, so a title takes little horizontal room and reads like a stencilled label.
- **Labels** sit above their control in Roboto 14px medium.
- **Helper text** is 13px in Slate Mute.
- **Copy** is sentence case everywhere except the display face, which uppercases itself.
- **Letter-spacing** is normal. Hierarchy comes from the face switch and weight, not from size jumps.

## 4. Component Stylings

* **Buttons:** Subtly rounded rectangles (10px corners), compact (32px tall, 12px horizontal padding, 13px medium text). The hierarchy is strict:
  * One **filled Hub Blue primary** per view, for the main action.
  * Everything else is a **hairline-outlined secondary**: card-coloured fill, Hairline Zinc border and a whisper shadow, which turns Whisper Grey on hover.
  * Destructive actions are filled Rose Alarm, or outlined in half-strength Rose for a remove icon.
  * Ghost buttons (no border) are for dense icon controls.
  * Cancel in a save row is muted, underlined text.
  * Small (24px) buttons are used in table rows and chip rows.
* **Badges:** Small (12px medium) solid-colour chips, 10px corners, or pill-shaped for counts. Status meaning follows the palette above.
* **Cards / sections:** Clean Card White panels with 12px corners, a hairline border and the faintest shadow (1px, 5% black). Each has an uppercase display title, an optional muted one-line description, and title-row actions on the right. Sections stack with 16px gaps on the Whisper Grey record background.
* **Inputs / forms:**
  * Controls are 32px tall, with 10px corners, a hairline Zinc stroke and a transparent fill (faintly lifted in dark mode).
  * On focus, the border turns Hub Blue and a soft 3px blue halo appears.
  * An invalid control gets a Rose border plus 12px Rose error text below it.
  * Fields are laid out in 2–4 column grids with 12px row and 16px column gaps.
* **Tables:**
  * The header band is Whisper Grey with 14px medium muted labels and inline filter controls underneath.
  * Rows are roughly 50px tall on card white, separated by hairlines.
  * Each row ends in a column of small secondary "View / Edit" and "Clone" buttons.
  * A selection checkbox column sits on the left.
* **Modals:** Card-white panels with 12px corners, a hairline border and a soft medium shadow over a 50% black scrim (70% in dark mode). They have 16px padding, an uppercase title with a ghost close button, and a footer that places Cancel (secondary) before the primary action.
* **Navigation:**
  * The icon rail is 80px wide, with icon-over-label items (18px icon, 11px label).
  * The active item is Hub Blue on a 12% blue wash, in rounded 8px tiles.
  * The top bar is 49px tall, with the logo on the left and the user on the right.
  * Section tabs sit inside the page header as 14px medium text with a 2px Hub Blue underline when active.

## 5. Layout Principles

- **Frame:** Every screen shares one frame: a 49px top bar, an 80px icon rail on the left, and a content area with no outer margin.
- **Page header:** Each page starts with a 48px header: back arrow and title (with section tabs and status badges) on the left, an optional centre slot, and the toolbar on the right (primary action first, then Filter and Columns).
- **List pages:** The table fills the remaining height edge to edge. Density is the point.
- **Record pages:** These centre a column at most 1140px wide on the grey background, with 16px padding and 16px between sections. Long forms add a 224px sticky jump-link column on the left. A sticky save bar is pinned to the bottom edge, with secondary actions left and Cancel / Save / Save & Close right.
- **Settings:** A second, 193px text sub-nav sits between the rail and the content. The content is a centred 1140px column of sections.
- **Spacing:** Spacing follows a 4px rhythm: 8px inside controls, 12–16px between fields, 16px around and between sections, 24px between page columns.
- **Alignment:** Left edges align down the page. Actions always sit on the right of their row.
