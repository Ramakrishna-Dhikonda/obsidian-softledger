# Softledger design tokens (v0.2.0)

Single source of truth for the theme. All component styles consume `--sl-*` tokens (mapped to Obsidian CSS variables). **Do not scatter one-off hex in selectors.**

Light is the hero (finance-dashboard soft UI). Dark is a coherent soft-card twin — same structure, not a lazy invert.

## Color

| Token | CSS variable | Light | Dark | Use |
|-------|--------------|-------|------|-----|
| App bg | `--sl-app-bg` | `#F5F7F9` | `#141618` | Workspace canvas, ribbon, title/status bar |
| Surface | `--sl-surface` | `#FFFFFF` | `#1E2124` | Cards, editor, sidebars |
| Surface elevated | `--sl-surface-elevated` | `#FFFFFF` | `#25282C` | Modals, menus, notices |
| Border | `--sl-border` | `#E5E7EB` | `rgba(255,255,255,0.1)` | Inputs, secondary buttons |
| Border subtle | `--sl-border-subtle` | `rgba(0,0,0,0.05)` | `rgba(255,255,255,0.06)` | Hairlines, dividers, table rows |
| Text | `--sl-text` | `#1A1A1A` | `#F3F4F6` | Primary copy, headings |
| Text secondary | `--sl-text-secondary` | `#6B7280` | `#A1A1AA` | Labels, inactive tabs, icons |
| Text muted | `--sl-text-muted` | `#9CA3AF` | `#71717A` | Meta, status bar, faint |
| Accent | `--sl-accent` | `#A3E635` | `#A3E635` | Primary CTA, focus, positive |
| Accent hover | `--sl-accent-hover` | `#8FD62A` | `#BEF264` | CTA / accent hover |
| Accent soft | `--sl-accent-soft` | `#ECFCCB` | `rgba(163,230,53,0.16)` | Tags, soft washes |
| Danger | `--sl-danger` | `#EF4444` | `#F87171` | Errors, destructive |
| Success | `--sl-success` | `#22C55E` | `#4ADE80` | Success states |
| Warning | `--sl-warning` | `#EAB308` | `#FACC15` | Warnings |
| Pill bg | `--sl-pill-bg` | `#1A1A1A` | `#3F3F46` | Active tab / selected nav |
| Pill text | `--sl-pill-text` | `#FFFFFF` | `#FFFFFF` | On pill backgrounds |

Supporting: `--sl-forest`, `--sl-overlay`, `--sl-hover`, `--sl-active`, `--sl-focus-ring`, `--sl-selection`, `--sl-scrollbar`, `--sl-disabled-opacity`.

## Spacing (4px grid)

| Token | Value |
|-------|-------|
| `--sl-space-1` | `4px` |
| `--sl-space-2` | `8px` |
| `--sl-space-3` | `12px` |
| `--sl-space-4` | `16px` |
| `--sl-space-5` | `20px` |
| `--sl-space-6` | `24px` |
| `--sl-space-8` | `32px` |

Mapped onto Obsidian `--size-4-*` where useful.

## Radii — use **only** these

| Token | Value | Typical use |
|-------|-------|-------------|
| `--sl-radius-sm` | `8px` | Tooltips, checkboxes |
| `--sl-radius-md` | `12px` | Nav rows, menus items, callouts, textareas |
| `--sl-radius-lg` | `16px` | Menus, notices |
| `--sl-radius-xl` | `20px` | Leaf cards, modals, settings panels |
| `--sl-radius-pill` | `999px` | Tabs, buttons, inputs, toggles, tags |

## Shadows (soft, not harsh)

| Token | Light | Dark |
|-------|-------|------|
| `--sl-shadow-sm` | `0 1px 3px rgba(0,0,0,0.04), 0 1px 2px rgba(0,0,0,0.03)` | `0 1px 3px rgba(0,0,0,0.25)` |
| `--sl-shadow-md` | `0 4px 16px rgba(0,0,0,0.06)` | `0 4px 16px rgba(0,0,0,0.35)` |
| `--sl-shadow-lg` | `0 8px 28px rgba(0,0,0,0.08)` | `0 8px 28px rgba(0,0,0,0.45)` |

Prefer elevation via shadow over heavy borders.

## Type

| Token | Value |
|-------|-------|
| `--sl-font-ui` / `--sl-font-text` | Inter → system UI stack |
| `--sl-font-mono` | JetBrains Mono → SF Mono → ui-monospace |
| `--sl-text-xs` … `--sl-text-lg` | `11 / 12 / 13 / 14 / 16px` |
| `--sl-weight-regular` … `--sl-weight-bold` | `400 / 500 / 600 / 700` |

Interface chrome leans on `13–14px` medium/semibold; reading text uses Obsidian text font vars.

## Control system

| Token | Value | Notes |
|-------|-------|-------|
| `--sl-control-h` | `32px` | Icons, tab height, nav rows |
| `--sl-control-h-lg` | `36px` | Buttons, text inputs, search |
| `--sl-icon-size` | `18px` | Target icon optical size |

## Interaction states

| State | Pattern |
|-------|---------|
| Hover | `--sl-hover` bg (or `--sl-accent-hover` on primary) |
| Active / pressed | `--sl-active` wash, or slight brightness drop on CTA |
| Focus | `0 0 0 3px var(--sl-focus-ring)` + accent border on inputs |
| Disabled | `--sl-disabled-opacity` (~0.45 light / 0.4 dark) |
| Selected | `--sl-pill-bg` + `--sl-pill-text` (charcoal pill) |

## Obsidian mapping (high level)

- Surfaces → `--background-primary|secondary*`, `--titlebar-*`, `--ribbon-*`, `--status-bar-*`
- Text → `--text-normal|muted|faint|accent|*`
- Accent → `--interactive-accent*`, `--color-accent*`
- Radii / shadows → `--radius-*`, `--input-radius`, `--button-radius`, `--modal-radius`, `--shadow-*`
- Nav → `--nav-item-*`
- Tabs → `--tab-*` (active bg = pill)

## Component recipes

| Component | Recipe |
|-----------|--------|
| Active tab | Charcoal pill (`--sl-pill-bg`) + white text |
| Primary button | Lime pill + dark text |
| Secondary button | Surface pill + `--sl-border` |
| Search / inputs | Pill, `36px` height, soft focus ring |
| File explorer active | Charcoal pill row (`--sl-radius-md` for row, charcoal fill) |
| Ribbon active | Charcoal circular pill icon |
| Modal / menu | Elevated surface + `--sl-shadow-lg` + xl/lg radius |
