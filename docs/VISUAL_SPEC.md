# Softledger Visual Spec v1.1.0

Source of truth: `docs/refs/v3/*.jpg` (education / schedule soft UI).  
When this conflicts with older lime-finance Softledger, **the refs win**.

Token companion: [`TOKENS.md`](TOKENS.md). Theme: `theme.css` @ **1.1.0**.

## Aesthetic

| Trait | Spec |
|-------|------|
| Mood | Soft light UI, airy whitespace, large outer rounding (~24px leaf) |
| Depth | Soft diffused shadows sparingly; prefer surface + subtle border |
| Icons | Thin-stroke Lucide (~18px, opacity ~0.72) |
| Type | Inter / system sans; hierarchy via size/contrast/spacing |
| Dividers | Mostly absent; when present 1px `--sl-border-subtle` (`#EEEEEE`) |

## Surfaces (from refs)

| Role | Light | Notes |
|------|-------|-------|
| Outer / app canvas | `#F4F4F7` | Soft cool gray behind white cards |
| Sidebar | `#F0EFF5` | Light gray + soft lavender tint — **not same as canvas** |
| Main content | `#FFFFFF` | White floating leaf / editor |
| Elevated (modals/menus) | `#FFFFFF` | Soft `--sl-shadow-lg` |
| Inactive control fill | `#EEEEF0` | Light gray pills + thin border |
| Hairline | `#EEEEEE` | 1px dividers / grid / inactive pill edge |

## Accent & selection (critical)

| Element | Treatment |
|---------|-----------|
| **Active sidebar / explorer nav** | **White pill** + dark icon/text + soft shadow (NOT charcoal) |
| **Primary filters / CTA / workspace tabs** | **Black solid pill** + white text (`#111111`) |
| Inactive pills | Light gray bg + **thin low-contrast border** |
| Notification badges | Small **black circles**, white text |
| Links | Soft indigo `#5B5BD6` (readable on white; not lime) |

## Pastel palette (cards / callouts / chips only)

| Token | Hex (light) | Use |
|-------|-------------|-----|
| Lavender | `#E8E0F8` | Cards, callout note |
| Blue | `#D8E4F8` | Cards, info |
| Mint | `#CFF0DD` | Success / confirmed |
| Peach | `#F8E8C8` | Warning / delayed |
| Coral | `#F5D0CC` | Danger soft |
| Cream | `#F5F0E6` | Neutral pastel / inline code |

## Typography

| Level | Size / weight | Color |
|-------|---------------|-------|
| Large title | ~20–24px / 700 | `--sl-text` |
| Section / H1–H2 | bold → semibold hierarchy | `--sl-text` |
| Body / nav | 13–14px / 500 | `--sl-text` or secondary |
| Breadcrumbs / meta | 12px / 400 | `--sl-text-muted` |
| Section / table labels | 11px muted, uppercase tracking | `--sl-text-muted` |

## Radii

| Token | Value | Use |
|-------|-------|-----|
| sm | 8px | Checkboxes, tooltips, inline code |
| md | 12px | Callouts, menus items, code blocks |
| lg | 16px | Cards, menus, notices |
| xl | 20px | Large cards |
| 2xl | 24px | Leaf panels, modals |
| pill | 999px | Tabs, buttons, inputs, badges, active nav |

## Interaction states

| State | Pattern |
|-------|---------|
| Hover | Quiet `--sl-hover` wash; icons → full opacity |
| Active / pressed | `--sl-active` or brightness drop on black CTA |
| Selected (sidebar) | White pill + soft shadow + subtle border |
| Selected (primary) | Black pill + white text |
| Focus | Dual ring via `var(--sl-focus-shadow)` |
| Disabled | `--sl-disabled-opacity` ~0.4 + `--sl-text-disabled` |

## Component map → Obsidian

| Ref component | Obsidian target |
|---------------|-----------------|
| App chrome + large rounding | Canvas `--sl-app-bg`; leaf `--sl-radius-2xl` + subtle border + soft shadow |
| Sidebar lavender gray | Left/right split + ribbon → `--sl-sidebar-bg` |
| Active nav white pill | `.nav-file-title.is-active`, `.tree-item-self.is-active`, settings vertical tabs |
| Black primary pills | `.workspace-tab-header.is-active`, `button.mod-cta`, toggles on |
| Inactive gray pills | Secondary buttons, inactive tab hover |
| Pastel cards | Callouts, tags |
| Status chips | Tags / metadata pills |
| Black notification badge | `.nav-file-tag`, `.tree-item-flair` |
| Thin icons | `--icon-size` 18px, `--icon-opacity` 0.72 |
| Soft dividers | `--divider-color`, table borders, HR |
| Breadcrumbs muted | View header path |
| Properties / frontmatter | Soft alt wash + subtle border |
| Soft twin dark | Same structure; elevated soft surfaces |

## Editor targets

H1–H6 hierarchy · lists · checkboxes (24px, black when checked) · indigo links · pastel tags · cream inline code · alt-wash code blocks · lavender-edge blockquotes · pastel callouts · muted uppercase table headers · subtle HR · soft embeds · frontmatter/properties wash.

## Overlay targets

Menus · command palette · suggestions · modals · tooltips (black pill language) · settings white-nav · quiet scrollbars.

## Known Obsidian limits

Cannot fully recreate calendar grid / floating pastel FABs / multi-column schedule chrome; graph/canvas only via CSS variables; OS window rounding not themeable.
