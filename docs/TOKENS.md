# Softledger design tokens (v1.0.0)

Single source of truth for CSS. All component styles consume `--sl-*` (mapped to Obsidian vars). **No scattered one-off hex in selectors.**

Light is the hero (education/schedule soft UI from `docs/refs/v3`). Dark is a coherent soft twin — same structure, not a lazy invert.

**Fidelity lock:** active nav = **white pill**; primary selected / CTA = **black solid pill**; no lime accent.

## Color

| Token | CSS variable | Light | Dark | Use |
|-------|--------------|-------|------|-----|
| App bg | `--sl-app-bg` | `#F4F4F7` | `#1A1B1F` | Workspace canvas, ribbon, title/status |
| Sidebar | `--sl-sidebar-bg` | `#F0EFF5` | `#1E1F26` | Side docks (lavender-tint gray) |
| Surface | `--sl-surface` | `#FFFFFF` | `#22232A` | Main content, editor, cards |
| Surface elevated | `--sl-surface-elevated` | `#FFFFFF` | `#2A2B33` | Modals, menus, notices |
| Surface alt | `--sl-surface-alt` | `#EEEEF0` | `#2F303A` | Inactive pills, inputs wash |
| Border | `--sl-border` | `#E4E4E8` | `rgba(255,255,255,0.1)` | Input borders |
| Border subtle | `--sl-border-subtle` | `#EEEEEE` | `rgba(255,255,255,0.06)` | Hairlines, dividers |
| Text | `--sl-text` | `#111111` | `#F2F2F4` | Primary copy, titles |
| Text secondary | `--sl-text-secondary` | `#6B6B73` | `#A0A0AB` | Nav default, labels |
| Text muted | `--sl-text-muted` | `#8E8E93` | `#787884` | Breadcrumbs, meta, section labels |
| Accent (primary) | `--sl-accent` | `#111111` | `#F2F2F4` | CTA, focus, primary selected |
| Accent hover | `--sl-accent-hover` | `#2A2A2A` | `#FFFFFF` | CTA hover |
| Accent soft | `--sl-accent-soft` | `#EEEEF0` | `rgba(242,242,244,0.12)` | Soft washes |
| Link | `--sl-link` | `#5B5BD6` | `#A5A6F0` | Inline / external links |
| Danger | `--sl-danger` | `#E05A5A` | `#F08080` | Errors |
| Success | `--sl-success` | `#2F9E6B` | `#5DCEA0` | Success |
| Warning | `--sl-warning` | `#D4A017` | `#E8C04A` | Warnings |
| Pill primary bg | `--sl-pill-bg` | `#111111` | `#F2F2F4` | Black (light) / light (dark) solid pills |
| Pill primary text | `--sl-pill-text` | `#FFFFFF` | `#111111` | On primary pills |
| Nav active bg | `--sl-nav-active-bg` | `#FFFFFF` | `#2F303A` | **White pill** sidebar/explorer |
| Nav active text | `--sl-nav-active-text` | `#111111` | `#F2F2F4` | On white/elevated nav pill |
| Badge | `--sl-badge-bg` | `#111111` | `#F2F2F4` | Notification circles |
| Badge text | `--sl-badge-text` | `#FFFFFF` | `#111111` | On badges |

### Pastels

| Token | Light | Dark (muted) |
|-------|-------|--------------|
| `--sl-pastel-lavender` | `#E8E0F8` | `rgba(200,180,240,0.18)` |
| `--sl-pastel-blue` | `#D8E4F8` | `rgba(160,190,240,0.18)` |
| `--sl-pastel-mint` | `#CFF0DD` | `rgba(140,220,180,0.16)` |
| `--sl-pastel-peach` | `#F8E8C8` | `rgba(240,200,140,0.16)` |
| `--sl-pastel-coral` | `#F5D0CC` | `rgba(240,160,150,0.16)` |
| `--sl-pastel-cream` | `#F5F0E6` | `rgba(230,220,190,0.12)` |

Supporting: `--sl-overlay`, `--sl-hover`, `--sl-active`, `--sl-focus-ring`, `--sl-selection`, `--sl-scrollbar`, `--sl-disabled-opacity`.

## Spacing (4px grid)

| Token | Value |
|-------|-------|
| `--sl-space-1` … `--sl-space-8` | `4 / 8 / 12 / 16 / 20 / 24 / 32px` |

## Radii — use **only** these

| Token | Value | Typical use |
|-------|-------|-------------|
| `--sl-radius-sm` | `8px` | Tooltips, checkboxes |
| `--sl-radius-md` | `12px` | Nav rows, callouts |
| `--sl-radius-lg` | `16px` | Cards, menus |
| `--sl-radius-xl` | `20px` | Leaf panels, modals |
| `--sl-radius-pill` | `999px` | Tabs, buttons, inputs, badges |

## Shadows

| Token | Light | Dark |
|-------|-------|------|
| `--sl-shadow-sm` | `0 1px 3px rgba(17,17,17,0.04), 0 1px 2px rgba(17,17,17,0.03)` | `0 1px 3px rgba(0,0,0,0.3)` |
| `--sl-shadow-md` | `0 4px 16px rgba(17,17,17,0.06)` | `0 4px 16px rgba(0,0,0,0.4)` |
| `--sl-shadow-lg` | `0 8px 28px rgba(17,17,17,0.08)` | `0 8px 28px rgba(0,0,0,0.5)` |

## Type

| Token | Value |
|-------|-------|
| `--sl-font-ui` / `--sl-font-text` | Inter → system UI |
| `--sl-font-mono` | JetBrains Mono → SF Mono → ui-monospace |
| `--sl-text-xs` … `--sl-text-xl` | `11 / 12 / 13 / 14 / 16 / 20px` |
| `--sl-weight-regular` … `--sl-weight-bold` | `400 / 500 / 600 / 700` |

## Control system

| Token | Value |
|-------|-------|
| `--sl-control-h` | `32px` |
| `--sl-control-h-lg` | `36px` |
| `--sl-icon-size` | `18px` |
| `--sl-icon-opacity` | `0.72` (thin-stroke feel) |

## Interaction recipes

| State | Pattern |
|-------|---------|
| Hover | `--sl-hover` |
| Active | `--sl-active` or CTA brightness |
| Focus | `0 0 0 3px var(--sl-focus-ring)` |
| Disabled | `--sl-disabled-opacity` |
| Nav selected | `--sl-nav-active-bg` + `--sl-nav-active-text` (white pill) |
| Primary selected | `--sl-pill-bg` + `--sl-pill-text` (black pill) |

## Obsidian mapping

- Surfaces → `--background-primary|secondary*`, `--titlebar-*`, `--ribbon-*`, `--status-bar-*`
- Text → `--text-normal|muted|faint|accent|*`
- Accent → `--interactive-accent*` = black primary; links via `--text-accent` = `--sl-link`
- Nav → `--nav-item-background-active` = white pill
- Tabs → `--tab-background-active` = black pill
- Radii/shadows → `--radius-*`, `--input-radius`, `--modal-radius`, `--shadow-*`
