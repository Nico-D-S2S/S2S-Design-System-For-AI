# Components

This document provides human-readable component guidelines.  
Machine-readable specs live in `components.yaml`.  
Design tokens live in `tokens/tokens.yaml`.

---

# Button

Buttons trigger actions and must follow consistent spacing, radius,
typography, and color tokens. All buttons use the same core structure:
inline-flex container, 6px vertical padding, 12px horizontal padding,
4px corner radius, and 6px icon gap.

---

## Primary Button

### Purpose
The main call-to-action on a screen. Strongest visual weight.

### Anatomy
- Container (inline-flex)
- Label text
- Optional leading icon (16px)
- Optional trailing icon (16px)

### Visual Style
- Height: **32px**
- Padding: `6px 12px`
- Border radius: **4px** (`radius.button_corner`)
- Background (rest): `colors.brand.primary_rest` (#5B5FC7)
- Background (hover): `colors.brand.primary_hover`
- Text: `colors.neutral.foreground_on_brand_rest` (white)
- Disabled background: `colors.neutral.background_disabled`
- Disabled text: `colors.neutral.foreground_disabled`

### Typography
- Label: `typography.label_md` (14px / 500)

### States
- **Rest:** Primary brand color  
- **Hover:** Slightly darker brand color  
- **Active:** Same as hover, with pressed interaction  
- **Disabled:** Light grey background + muted text  

### Usage
Use for the **most important action** on the page or dialog.

---

## Secondary Button

### Purpose
A lighter-weight alternative used alongside a primary button or for less
prominent actions.

### Anatomy
- Same container, padding, radius as primary button
- Optional leading/trailing icon (16px)

### Visual Style
- Height: **32px**
- Border radius: **4px**
- Border: `borders.width.sm` (1px)
- Background (rest): `colors.button.secondary_rest` (#FFFFFF)
- Border (rest): `colors.neutral.stroke_grey_300`
- Text: `colors.neutral.text_primary`
- Hover background: `colors.button.secondary_hover` (#F5F5F5)
- Hover border: `colors.neutral.stroke_grey_400`
- Disabled background: `colors.button.disabled_rest` (#F0F0F0)
- Disabled border: `colors.neutral.stroke_disabled`
- Disabled text: `colors.neutral.foreground_disabled`

### Typography
- Label: `typography.label_md`

### Icon Rules
- 16px icon size
- 6px gap to label
- Icon-only variant allowed for toggle states

### States
- **Rest:** White background, grey-300 stroke  
- **Hover:** Light-grey background, darker grey-400 stroke  
- **Active:** Same as hover, with pressed interaction  
- **Disabled:** Soft grey background, disabled stroke + text  

### Usage
Use when:
- A primary button is already present  
- You need a less dominant action  
- You want a neutral button that blends into the layout  

---

# Input

Single-line text inputs are used for forms, filters, and search-like
fields. They follow the same 4px radius as buttons and use a 280px
fixed width by default.

### Variants / States
- **Default (rest)**
- **Focus**
- **Error**
- **Disabled**

### Anatomy
- Container (flex, vertical)
- Input field
- Placeholder / value text
- Optional helper or error text (not yet defined here)

### Visual Style

**Shared**

- Width: **280px**
- Height: **32px**
- Border radius: `radius.input_corner` (4px)
- Border width: `borders.width.sm` (1px)
- Background: `colors.surface.input_background` (white)
- Typography: `typography.input_md` (14px / 400)

**Rest**

- Border: `colors.neutral.divider_on_white_500`  
- Text / placeholder: `colors.neutral.text_tertiary`

**Focus**

- Border: `colors.neutral.divider_on_white_500`  
- Bottom underline: `colors.brand.primary_rest`  
- Text: `colors.neutral.text_primary`

**Error**

- Border: `colors.status.error_border`  
- Text: `colors.status.error_text`

**Disabled**

- Background: `colors.button.disabled_rest`  
- Border: `colors.neutral.stroke_disabled`  
- Text: `colors.neutral.foreground_disabled`

### Behavior

- Focus state emphasises the bottom edge (underline) with brand color.
- Placeholder uses tertiary text color until the user starts typing.
- Disabled state removes all interactive affordances; no focus/hover.

### Usage

Use this input for:

- Single-line text
- Filters and small forms
- Basic settings forms

Use textarea or a different component for multiline content.

---

# Data Table

The data table is composed of:

- Column headers  
- Body cells with different content types  
- A shared interaction model across all cells:
  - **Rest**
  - **Hover**
  - **Clicked**
  - **Disabled**

All table elements follow the same horizontal padding and 4px corner rounding where needed.

---

## Table Header Cell

### Purpose
Labels the column and indicates the type of content below.

### Visual

- Width: **144px**
- Height: **32px**
- Padding: `8px 12px` (top/bottom, left/right)
- Background: `colors.neutral.grey_50` (#F5F5F5)
- Text color: `colors.neutral.text_tertiary`
- Alignment: centered horizontally and vertically

### Typography
- `typography.table_header_sm` (12 / 400 / 16px line height)

### Usage
- One header per column.
- Keep labels short and descriptive.

---

## Cell Interaction Model (All Types)

All cell types use the same base interaction colors:

- **Rest**
  - Background: `colors.surface.input_background` (#FFFFFF)
- **Hover**
  - Background: `colors.neutral.grey_50` (#F5F5F5)
- **Clicked**
  - Background: `colors.neutral.grey_150` (#E1E1E1)
- **Disabled**
  - Background: `colors.surface.input_background` (#FFFFFF)  
  - Text/pills use disabled/subtle colors

Unless specified otherwise, text uses `colors.neutral.text_secondary` in interactive states and
`colors.neutral.foreground_subtle_disabled` when disabled.

---

## Text-Only Cell

### Purpose
Standard table cell showing a single line of text.

### Visual

- Height: **48px**
- Padding: `10px 12px`
- Layout: `inline-flex`, `align-items: center`
- Gap between potential icon/text: 6px

### States

- **Rest:** White background, secondary text  
- **Hover:** Grey-50 background  
- **Clicked:** Grey-150 background  
- **Disabled:** White background, subtle-disabled text  

### Typography
- `typography.table_cell_md` (14 / 400 / 20px line height)

### Usage
- Default for most table content.
- Use one line of text; truncate or wrap according to product rules.

---

## Icon Cell

### Purpose
Table cell containing an icon (e.g. checkmark) with optional text.

### Visual

- Same height and padding as text-only cell
- 16px icon size
- Icon and text aligned on a single row

### States

- **Rest / Hover / Clicked:**  
  - Background follows base interaction model  
  - Icon and text use `colors.neutral.text_secondary`
- **Disabled:**  
  - Background: white  
  - Icon and text: `colors.neutral.foreground_subtle_disabled`

### Usage
- Use for “selected”, “done”, or confirmation states.
- Keep text label short.

---

## Badge Cell (Outlined)

### Purpose
Shows a badge-style label (e.g., type, lightweight metadata) inside the cell.

### Container Visual

- Height: **48px**
- Padding: `10px 50px 10px 12px`
- Layout: `inline-flex`, `align-items: center`

Container background follows base interaction model.

### Badge Pill

- Height: **24px**
- Padding: `4px 8px`
- Layout: `flex`, centered
- Border radius: `radius.pill_md` (6px)
- Border: `borders.width.sm` in `colors.neutral.stroke_grey_300`
- Background: `colors.surface.card_subtle` (#FAFAFC)
- Text:
  - Rest: `colors.neutral.text_secondary`
  - Disabled: `colors.neutral.foreground_subtle_disabled`
- Typography: `typography.pill_sm`

### Usage
- Use for secondary metadata: small tags, non-critical labels.
- Works well when you want a subtle outlined style.

---

## Prefix Cell

### Purpose
Displays a bold prefix followed by regular text (e.g., **Label – Value**).

### Visual

- Same dimensions as text-only cell
- Layout: `inline-flex`, `align-items: center`
- Prefix visually stronger than the value

### States

- Background follows base interaction model.
- Text:
  - Prefix: `typography.label_md` / `colors.neutral.text_secondary`
  - Value: `typography.table_cell_md` / `colors.neutral.text_secondary`
  - Disabled: both use `colors.neutral.foreground_subtle_disabled`

### Usage
- Use when you need a short “label – value” pattern inside a single cell.
- Works well for showing paired information like “Owner – Name”.

---

## Status Cell (Filled Pill)

### Purpose
Shows a semantic status label (e.g., “Active”, “Pending”) in a filled pill.

### Container

- Height: **48px**
- Padding: `10px 50px 10px 12px`
- Layout: `inline-flex`, `align-items: center`
- Background follows base interaction model.

### Status Pill

- Height: **24px**
- Padding: `4px 8px`
- Layout: `flex`, centered
- Border radius: `radius.pill_md` (6px)
- Background: `colors.surface.card_subtle` (#FAFAFC)
- Text:
  - Rest: `colors.status.status_blue_text` (#444791)
  - Disabled: `colors.neutral.foreground_subtle_disabled`
- Typography: `typography.pill_sm`

### Usage
- Use for lifecycle or state values (e.g., Active, Draft, Archived).
- Keep to 1–2 words.

---

## Tag Cell (Tag + Counter)

### Purpose
Shows a primary tag (e.g., “SharePoint”) and an optional counter (e.g., “+2”).

### Container

- Same dimensions as status cell container.
- Background follows base interaction model.

### Primary Tag Pill

- Height: **24px**
- Padding: `4px 8px`
- Border radius: `radius.pill_md`
- Background: `colors.surface.card_subtle`
- Text:
  - Rest: `colors.status.status_blue_text`
  - Disabled: `colors.neutral.foreground_subtle_disabled`
- Typography: `typography.pill_sm`

### Counter Tag Pill

- Same size as primary tag
- Border radius: `radius.pill_md`
- Border: `borders.width.sm` / `colors.neutral.stroke_grey_300`
- Background: `colors.surface.card_subtle`
- Text:
  - Rest: `colors.neutral.text_secondary`
  - Disabled: `colors.neutral.foreground_subtle_disabled`
- Typography: `typography.pill_sm`

### Usage
- Use for knowledge sources, labels with overflow items, or grouped tags.
- Example: **SharePoint** `+2` for “plus two more sources”.

---

## Column Layout

### Purpose
Defines how header + cells stack vertically.

### Visual

- Layout: `flex`, `flex-direction: column`
- Alignment: `flex-start`
- Gap: `0` (row height defined by header/cell heights)
- Each column contains: one header cell + N body cells.

### Usage

- Use one column per data property.
- Keep each column width consistent (144px as a default; adjust per table if needed).

---

# Side Menu

The side menu provides navigation for configuration sections such as
Settings, Information, Governance, and Maintenance. It follows the same
typography and color system as the rest of the design system and
reuses new navigation tokens from `tokens.yaml`.

The side menu is composed of:

- Side-menu container
- Sections (group)
- Section title (number badge + label)
- Menu items (with optional icons and premium icon)
- Mode switcher (Simple / Expert) – separate component but visually
  aligned with the side menu

---

## Side Menu Container

### Purpose
Holds all sections and navigation items.

### Visual

- Component: `side_menu.container`
- Layout:
  - `display: inline-flex`
  - `flex-direction: column`
  - `align-items: flex-start`
- Shape:
  - Border radius: `radius.side_menu_corner` (rounded side-panel corners)
- Background:
  - `colors.navigation.side_menu_background` (white)
- Shadows:
  - Two drop shadows from Figma:
    - Shadow 1: `0px 6.4px 14.4px 0px rgba(0, 0, 0, 0.07)`
    - Shadow 2: `0px 1.2px 3.6px 0px rgba(0, 0, 0, 0.03)`

### Usage
Use this container for the left-hand configuration navigation only.  
Do not reuse as a generic card; use card components for that.

---

## Section

### Purpose
Groups a section title and its related menu items (e.g., “1 Settings”).

### Visual

- Component: `side_menu.section`
- Layout:
  - `display: flex`
  - `flex-direction: column`
  - `align-items: flex-start`
  - Vertical gap between title and items: **9px**
  - `align-self: stretch` (fills container width)

### Usage
Each major navigation group (Settings, Information, Governance,
Maintenance) should be its own section.

---

## Section Title

A section title contains a circular number badge and a text label,
e.g., “1 Settings”.

### Number Badge

- Component: `side_menu.section_title.number_badge`
- Layout:
  - `display: flex`
  - Width: **26px**
  - Height: **29px**
  - `flex-direction: column`
  - `justify-content: center`
  - `align-items: center`
- Shape:
  - Border radius: `radius.section_number_circle` (full circle)
- Colors:
  - Background: `colors.navigation.section_number_background`
    (reuses the primary brand color)
  - Text: `colors.neutral.foreground_on_brand_rest` (white)
- Typography:
  - `typography.navigation_section_md` (14 / 700 / 20)

### Label

- Component: `side_menu.section_title.label`
- Layout:
  - `display: flex`
  - Width: **167px**
  - Height: **26px**
  - `flex-direction: column`
  - `justify-content: center`
- Colors:
  - Text: `colors.navigation.section_title_text` (#242424)
- Typography:
  - `typography.navigation_section_md` (14 / 700 / 20)

### Row Layout

- Entire title row: `side_menu.section_title`
- Row layout:
  - `display: flex`
  - Height: **32px**
  - Padding: `1px 6px 1px 17px`
  - `align-items: center`
  - Gap between badge and label: **11px**
  - `align-self: stretch`

---

## Menu Item

A menu item contains an optional leading icon, text label, and optional
premium icon (diamond).

### Default State

- Component: `side_menu.item`
- Layout:
  - `display: inline-flex`
  - Height: **32px**
  - `flex-direction: column`
  - `justify-content: center`
  - `align-items: flex-start`
  - Vertical gap inside content: **10px**
- Inner content:
  - Horizontal layout for icon + label + premium icon
  - Gap: **8px**
- Icons:
  - Main icon: **20px** (e.g., gear)
  - Premium icon: **14px** (diamond)
- Typography:
  - Label: `typography.navigation_item_md` (14 / 400 / 20)
- Colors:
  - Text: `colors.navigation.menu_item_text_default` (#484644)

### Hover State

- Background: `colors.navigation.menu_item_background_hover`
  (same as `colors.neutral.grey_50`)
- Text: `colors.navigation.menu_item_text_disabled` (#D6D6D6)  
  *(matches your Figma where hover uses the lighter grey text; if
  you prefer darker hover text, update this mapping later).*

### Disabled State

- Text: `colors.navigation.menu_item_text_disabled` (#D6D6D6)
- No hover/active behavior.

### Usage

- Use menu items to navigate to sub-pages within a section
  (e.g., Welcome, Setup, Notifications).
- Keep labels concise (1–2 words where possible).
- Use the premium icon only for items that require a higher plan.

---

# Mode Switcher (Simple / Expert)

The mode switcher is a two-option segmented control placed above the
side menu. It allows users to toggle between **Simple mode** and
**Expert mode**.

It reuses navigation tokens and does **not** introduce new colors.

---

## Switcher Container

### Purpose
Provides the track around the segments.

### Visual

- Component: `mode_switcher.container`
- Layout:
  - Width: **280px**
  - Height: **30px**
  - Padding: **8px** on all sides (`8px 8px 8px 8px`)
  - `display: flex`
  - `align-items: center`
- Shape:
  - Border radius: `radius.segment_item`
- Colors:
  - Background: `colors.navigation.segment_unselected_background`
    (light grey, same as `colors.neutral.grey_50`)
  - Border: `colors.neutral.divider_on_white_500`

Place the container above the section list with a comfortable vertical
gap (e.g., using your standard vertical spacing token).

---

## Segment Option

Each option (Simple mode, Expert mode) shares the same base geometry
and typography.

### Shared Visual

- Component: `mode_switcher.option`
- Layout:
  - `display: flex`
  - Width: **140px** (half of the 280px container)
  - Height: **32px**
  - Padding: `8px 25px`
  - `flex-direction: column`
  - `justify-content: center`
  - `align-items: center`
  - Gap: **10px**
- Typography:
  - Label: `typography.segment_label_sm`
    - 12px / 600 / 16px line height
- Radius:
  - Selected uses `radius.segment_item` for a pill shape.
  - Unselected uses asymmetrical radius (0 on the shared edge, rounded
    on the outer edge).

---

### Selected State (e.g., Simple mode)

- Background:
  - `colors.navigation.segment_selected_background` (#E8EBFA)
- Border:
  - `borders.width.sm` in `colors.navigation.segment_selected_border`
    (#9299F7)
- Text:
  - `colors.brand.primary_rest` (#5B5FC7)

This creates the blue pill effect seen in Figma.

---

### Not-Selected State (e.g., Expert mode)

- Background:
  - `colors.navigation.segment_unselected_background` (#F5F5F5)
- Text:
  - `colors.navigation.segment_unselected_text` (#616161)
- Radius:
  - The option on the right has `border-radius: 0 12px 12px 0`  
    (outer corners rounded, inner corners square).  
  - The option on the left mirror this if it becomes unselected.

### Usage

- Use this control only for **mutually exclusive view modes** where
  both options are visible and obvious.
- Do not add more than two segments; if more views are required, use
  tabs or a different navigation pattern.

---


