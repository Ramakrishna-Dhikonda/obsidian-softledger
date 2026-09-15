# Softledger Visual Spec v1.0.0

Source of truth: `docs/refs/v3/*.jpg` (education / schedule soft UI).  
When this conflicts with older lime-finance Softledger, **the refs win**.

## Aesthetic

| Trait | Spec |
|-------|------|
| Mood | Soft light UI, airy whitespace, large outer rounding feel |
| Depth | Soft diffused shadows — not hard borders |
| Icons | Thin-stroke Lucide (~1.5px visual weight via size/opacity) |
| Type | Inter / system sans; clear hierarchy; muted secondary |
| Dividers | 1px very subtle (`#EEEEEE` / `--sl-border-subtle`) |

## Surfaces (from refs)

| Role | Light | Notes |
|------|-------|-------|
| Outer / app canvas | `#F4F4F7` | Soft cool gray behind white cards |
| Sidebar | `#F0EFF5` → `#F5F5F7` | Light gray + soft lavender tint |
| Main content | `#FFFFFF` | White floating surfaces |
| Elevated (modals/menus) | `#FFFFFF` | Soft `--sl-shadow-lg` |
| Inactive control fill | `#EEEEF0` | Light gray pills |
| Hairline | `#EEEEEE` | 1px dividers / grid |

## Accent & selection (critical)

| Element | Treatment |
|---------|-----------|
| **Active sidebar / explorer nav** | **White pill** + dark icon/text (not charcoal) |
| **Primary filters / selected day / CTA / workspace tabs** | **Black solid pill** + white text (`#111111`) |
| Inactive pills | Light gray bg (`#EEEEF0`), dark text |
| Notification badges | Small **black circles**, white text |
| Links | Soft indigo `#5B5BD6` (readable on white; not lime) |

## Pastel palette (cards / callouts / chips)

| Token | Hex (light) | Use |
|-------|-------------|-----|
| Lavender | `#E8E0F8` | Cards, callout note |
| Blue | `#D8E4F8` | Cards, info |
| Mint | `#CFF0DD` | Success / confirmed |
| Peach | `#F8E8C8` | Warning / delayed |
| Coral | `#F5D0CC` | Danger soft / exams accent |
| Cream | `#F5F0E6` | Neutral pastel |

Status chips: pastel fill + matching-tint icon; optional white inner pill on colored cards.

## Typography

| Level | Size / weight | Color |
|-------|---------------|-------|
| Large title | ~20–24px / 700 | `--sl-text` |
| Section / H1–H2 | bold hierarchy | `--sl-text` |
| Body / nav | 13–14px / 500 | `--sl-text` or secondary |
| Breadcrumbs / meta | 12px / 400 | `--sl-text-muted` (`#8E8E93`) |
| Section labels | 11px muted (small-caps feel) | `--sl-text-muted` |

## Component map → Obsidian

| Ref component | Obsidian target |
|---------------|-----------------|
| App chrome + large rounding feel | Workspace canvas `--sl-app-bg`; leaf cards `--sl-radius-xl` + soft shadow |
| Sidebar lavender gray | Left/right split leaf + ribbon share `--sl-sidebar-bg` |
| Active nav white pill | `.nav-file-title.is-active`, `.tree-item-self.is-active`, settings vertical tabs |
| Black primary pills | `.workspace-tab-header.is-active`, `button.mod-cta`, toggles on |
| Inactive gray pills | Secondary buttons, inactive tabs hover |
| Pastel cards | Callouts, tags, embeds soft wash |
| Status chips | Tags / metadata pills |
| Black notification badge | Unread / count styling where CSS allows |
| Thin icons | `--icon-size` 18px, `--icon-opacity` ~0.75 default |
| Soft dividers | `--divider-color`, table borders, HR |
| Breadcrumbs muted | View header path / title secondary |
| Large bold titles | `.inline-title`, headings |
| Soft twin dark | Same structure: elevated soft surfaces, light pill for primary, muted pastels |

## Interaction states

| State | Pattern |
|-------|---------|
| Hover | `--sl-hover` wash; icons → full opacity / `--sl-text` |
| Active / pressed | `--sl-active` or brightness drop on black CTA |
| Selected (sidebar) | White pill + `--sl-text` |
| Selected (primary) | Black pill + white text |
| Focus | `0 0 0 3px var(--sl-focus-ring)` (soft black/lavender ring) |
| Disabled | `--sl-disabled-opacity` ~0.4 |

## Radii

| Token | Value | Use |
|-------|-------|-----|
| sm | 8px | Checkboxes, tooltips |
| md | 12px | Nav rows, callouts, menus items |
| lg | 16px | Cards, menus, notices |
| xl | 20px | Leaf panels, modals |
| pill | 999px | Tabs, buttons, inputs, badges |

## Known Obsidian limits

Documented in README — e.g. cannot fully recreate calendar grid / floating pastel FABs / multi-column schedule chrome; graph/canvas only via CSS variables.
