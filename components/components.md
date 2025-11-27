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
- Border radius: **4px**
- Background (rest): **#5B5FC7**
- Text: **white**
- Background (hover): darker primary
- Disabled: grey background + grey text

### Typography
- Label: `typography.label_md` (14px / 500)

### States
- **Rest:** Primary brand color  
- **Hover:** Slightly darker  
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
- Optional leading/trailing icon

### Visual Style
- Height: **32px**
- Background (rest): **#FFFFFF**
- Border (rest): **1px grey-300**
- Text: `colors.neutral.text_primary`
- Hover: **#F5F5F5** + darker grey-400 border
- Disabled: **#F0F0F0** + disabled stroke

### Typography
- Label: `typography.label_md`

### Icon Rules
- 16px size
- 6px gap
- Icon-only variant allowed for toggle states

### States
- **Rest:** White background, grey-300 stroke  
- **Hover:** Light-grey background, darker grey stroke  
- **Disabled:** Soft grey background, disabled stroke + text  

### Usage
Use when:
- You already have a primary button on screen  
- You need a less visually dominant action  
- You want a neutral alternative that blends into layouts  

