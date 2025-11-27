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

