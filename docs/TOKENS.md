# Softledger design tokens (v1.1.0)

Single source of truth for CSS. **All component styles consume `--sl-*` only** (mapped to Obsidian vars). No scattered one-off hex in selectors.

Light is the hero (education/schedule soft UI from `docs/refs/v3`). Dark is a coherent soft twin — same structure, not a lazy invert.

**Fidelity lock:** active nav = **white pill**; primary selected / CTA = **black solid pill**; no lime accent.

## Surfaces

| Role | Token | Light | Dark | Use |
|------|-------|-------|------|-----|
| Base (canvas) | `--sl-app-bg` / `--sl-surface-base` | `#F4F4F7` | `#1A1B1F` | Workspace canvas, titlebar, status, tab strip |
| Secondary (sidebar) | `--sl-sidebar-bg` / `--sl-surface-secondary` | `#F0EFF5` | `#1E1F26` | Side docks, ribbon, settings nav rail |
| Elevated / main | `--sl-surface` | `#FFFFFF` | `#22232A` | Editor, main leaf, cards |
| Elevated overlay | `--sl-surface-elevated` | `#FFFFFF` | `#2A2B33` | Modals, menus, notices, prompts |
| Alt / wash | `--sl-surface-alt` | `#EEEEF0` | `#2F303A` | Inactive pills, inputs, code wash |
| Hover | `--sl-hover` / `--sl-surface-hover` | `rgba(17,17,17,0.04)` | `rgba(255,255,255,0.05)` | Quiet wash |
| Active / pressed | `--sl-active` / `--sl-surface-active` | `rgba(17,17,17,0.08)` | `rgba(255,255,255,0.1)` | Pressed rows |

## Borders

| Token | Light | Dark | Use |
|-------|-------|------|-----|
| `--sl-border` | `#E4E4E8` | `rgba(255,255,255,0.1)` | Input / stronger hairline |
| `--sl-border-subtle` | `#EEEEEE` | `rgba(255,255,255,0.06)` | Dividers, leaf edge, inactive pill edge |
| `--sl-inactive-pill-border` | → `--sl-border-subtle` | → `--sl-border-subtle` | Inactive control outline |

Prefer **surface shift + subtle 1px border** over heavy shadows.

## Text

| Token | Light | Dark | Use |
|-------|-------|------|-----|
| `--sl-text` | `#111111` | `#F2F2F4` | Primary copy, titles, active labels |
| `--sl-text-secondary` | `#6B6B73` | `#A0A0AB` | Nav default, descriptions |
| `--sl-text-muted` | `#8E8E93` | `#787884` | Breadcrumbs, section labels, table headers |
| `--sl-text-disabled` | `#B0B0B8` | `#5A5A66` | Disabled controls / labels |

AA companions (fills stay bright; body text uses companions):

| Fill | Text companion |
|------|----------------|
| `--sl-success` | `--sl-success-text` (`#1B7A4E` / `#7DDBB5`) |
| `--sl-warning` | `--sl-warning-text` (`#8A6508` / `#F0D070`) — ≥4.5:1 on white |
| `--sl-danger` | `--sl-danger-text` (`#C43D3D` / `#F5A0A0`) |

## Accent & selection

| Token | Light | Dark | Use |
|-------|-------|------|-----|
| `--sl-accent` | `#111111` | `#F2F2F4` | Primary accent (= black pill language) |
| `--sl-accent-hover` | `#2A2A2A` | `#FFFFFF` | CTA hover |
| `--sl-accent-soft` | `#EEEEF0` | `rgba(242,242,244,0.12)` | Soft accent wash |
| `--sl-pill-bg` / `--sl-pill-text` | `#111111` / `#FFFFFF` | `#F2F2F4` / `#111111` | **Black solid primary** tab/CTA |
| `--sl-nav-active-bg` / `--sl-nav-active-text` | `#FFFFFF` / `#111111` | `#2F303A` / `#F2F2F4` | **White pill** sidebar/explorer |
| `--sl-inactive-pill-bg` | → `--sl-surface-alt` | → `--sl-surface-alt` | Inactive gray pills |
| `--sl-badge-bg` / `--sl-badge-text` | `#111111` / `#FFFFFF` | inverse | Notification circles |
| `--sl-link` / `--sl-link-hover` | `#5B5BD6` / `#4848C7` | `#A5A6F0` / `#C0C1F8` | Links (not lime) |

## Pastels (cards / callouts / tags only)

| Token | Light | Dark (muted) |
|-------|-------|--------------|
| `--sl-pastel-lavender` | `#E8E0F8` | `rgba(200,180,240,0.18)` |
| `--sl-pastel-blue` | `#D8E4F8` | `rgba(160,190,240,0.18)` |
| `--sl-pastel-mint` | `#CFF0DD` | `rgba(140,220,180,0.16)` |
| `--sl-pastel-peach` | `#F8E8C8` | `rgba(240,200,140,0.16)` |
| `--sl-pastel-coral` | `#F5D0CC` | `rgba(240,160,150,0.16)` |
| `--sl-pastel-cream` | `#F5F0E6` | `rgba(230,220,190,0.12)` |

## Spacing (4px scale)

| Token | Value |
|-------|-------|
| `--sl-space-1` … `--sl-space-8` | `4 / 8 / 12 / 16 / 20 / 24 / 28 / 32` (`--sl-space-7` = 28) |
| `--sl-space-10` / `--sl-space-12` | `40 / 48` |

## Radii — **only** this scale

| Token | Value | Typical use |
|-------|-------|-------------|
| `--sl-radius-sm` | `8px` | Tooltips, checkboxes, inline code |
| `--sl-radius-md` | `12px` | Nav rows, callouts, menu items, code blocks |
| `--sl-radius-lg` | `16px` | Cards, menus, embeds |
| `--sl-radius-xl` | `20px` | Large cards |
| `--sl-radius-2xl` | `24px` | Main leaf panels, modals |
| `--sl-radius-pill` | `999px` | Tabs, buttons, inputs, badges, active nav |

## Shadows

| Token | Light | Dark |
|-------|-------|------|
| `--sl-shadow-sm` | `0 1px 3px rgba(17,17,17,0.04), 0 1px 2px rgba(17,17,17,0.03)` | `0 1px 3px rgba(0,0,0,0.3)` |
| `--sl-shadow-md` | `0 4px 16px rgba(17,17,17,0.06)` | `0 4px 16px rgba(0,0,0,0.4)` |
| `--sl-shadow-lg` | `0 8px 28px rgba(17,17,17,0.08)` | `0 8px 28px rgba(0,0,0,0.5)` |

Leaf panels: **subtle border + `--sl-shadow-md`**. Active white nav: `--sl-shadow-md` + subtle border. Overlays: `--sl-shadow-lg`.

## Type

| Token | Value |
|-------|-------|
| `--sl-font-ui` / `--sl-font-text` | Inter → system UI |
| `--sl-font-mono` | JetBrains Mono → SF Mono → ui-monospace |
| `--sl-text-xs` … `--sl-text-xl` / `--sl-text-2xl` | `11 / 12 / 13 / 14 / 16 / 20 / 24` |
| `--sl-weight-regular` … `--sl-weight-bold` | `400 / 500 / 600 / 700` |

Hierarchy via **size / contrast / spacing** — avoid excessive bold.

## Controls / icons

| Token | Value |
|-------|-------|
| `--sl-control-h` | `32px` |
| `--sl-control-h-lg` | `36px` |
| `--sl-checkbox-size` | `24px` |
| `--sl-badge-size` | `18px` |
| `--sl-icon-size` | `18px` |
| `--sl-icon-opacity` | `0.72` |

## Interaction recipes

| State | Recipe |
|-------|--------|
| Hover | `background: var(--sl-hover)` · icons → opacity 1 / `--sl-text` |
| Active / pressed | `background: var(--sl-active)` or CTA `filter: brightness(0.92)` |
| Selected (sidebar / settings) | `bg: var(--sl-nav-active-bg); color: var(--sl-nav-active-text); box-shadow: var(--sl-shadow-md); border: var(--sl-border-width) solid var(--sl-border-subtle)` |
| Selected (primary / tab / CTA) | `bg: var(--sl-pill-bg); color: var(--sl-pill-text)` |
| Inactive pill | `bg: var(--sl-inactive-pill-bg); border: 1px solid var(--sl-inactive-pill-border)` |
| Focus | `box-shadow: var(--sl-focus-shadow)` → `0 0 0 2px var(--sl-text), 0 0 0 4px var(--sl-focus-ring)` |
| Disabled | `opacity: var(--sl-disabled-opacity)` (~0.4) + `--sl-text-disabled` where color matters |

### Focus tokens

| Token | Value |
|-------|-------|
| `--sl-focus-ring` | Light `rgba(17,17,17,0.55)` · Dark `rgba(242,242,244,0.6)` |
| `--sl-focus-shadow` | Dual ring: `0 0 0 2px var(--sl-text), 0 0 0 4px var(--sl-focus-ring)` |

Apply broadly on `:focus-visible` (inputs, buttons, ribbon, nav-action, settings nav, menu, suggestion, modal close, tab headers).

## Supporting

| Token | Light | Dark |
|-------|-------|------|
| `--sl-overlay` | `rgba(17,17,17,0.35)` | `rgba(20,21,26,0.78)` |
| `--sl-selection` | indigo soft wash | indigo soft wash |
| `--sl-scrollbar` | muted thumb | muted thumb |
| `--sl-disabled-opacity` | `0.4` | `0.4` |
| `--sl-border-width` | `1px` | `1px` |
| `--sl-border-width-strong` | `2px` | `2px` |
| `--sl-accent-bar` | `3px` | `3px` |
| `--sl-scrollbar-size` | `8px` | `8px` |
| `--sl-textarea-min-h` | `80px` | `80px` |
| `--sl-header-height` | → `--sl-space-10` | → `--sl-space-10` |

Also: `--sl-danger`, `--sl-success`, `--sl-warning` (fills).

## Obsidian mapping

- Surfaces → `--background-primary|secondary*`, `--titlebar-*`, `--ribbon-*`, `--status-bar-*`
- Text → `--text-normal|muted|faint|accent|*`; `--text-success|warning|error` → `--sl-*-text`
- Accent → `--interactive-accent*` = black primary; links via `--text-accent` = `--sl-link`
- Nav → `--nav-item-background-active` = white pill
- Tabs → `--tab-background-active` = black pill
- Radii/shadows → `--radius-*`, `--input-radius`, `--modal-radius` (= `--sl-radius-2xl`), `--shadow-*`
