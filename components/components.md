# Components

This document describes the main UI components in human-readable form.
Machine-readable specs live in `components.yaml` and tokens in
`../tokens/tokens.yaml`.

---

## Button

### Overview
Buttons trigger actions. The primary button is used for the main
call-to-action on a page, dialog, or card. Buttons reuse spacing,
radius, color, and typography tokens defined in `tokens.yaml`.

---

### Anatomy
- Container (inline-flex)
- Label text
- Optional leading icon
- Optional trailing icon

---

### Primary Button

**Visual**

- Height: 32px
- Display: `inline-flex`
- Alignment: center (horizontal & vertical)
- Border radius: `radius.button_corner` (4px)
- Vertical padding: `spacing.vertical.snudge` (6px)
- Horizontal padding: `spacing.horizontal.m` (12px)
- Gap between icon and label: `spacing.horizontal.snudge` (6px)
- Background (rest): `colors.brand.primary_rest` (#5B5FC7)
- Text color (rest): `colors.neutral.foreground_on_brand_rest` (white)
- Label typography: `typography.label_md`

**States**

- **Rest**  
  Background: brand primary rest, text white.

- **Hover**  
  Background: `colors.brand.primary_hover` (slightly darker), text white.

- **Disabled**  
  Background: `colors.neutral.background_disabled` (light grey)  
  Text: `colors.neutral.foreground_disabled` (medium grey)  
  No hover or focus effects.

---

### Behavior

- Minimum tap target: 32×32px.
- Icons may appear before or after the label; always keep a 6px gap.
- On mobile, full-width buttons are allowed; on desktop, width should hug content.

---

### Usage

**Use primary button when:**

- You have a single main action on the screen or dialog.
- You want to visually emphasize the most important path.

**Avoid primary button when:**

- There are multiple competing actions on the same level.  
  → prefer secondary or tertiary button.
- The action is destructive.  
  → use a specific destructive variant.
