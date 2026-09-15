# Softledger 1.1.0 — measurable gaps vs `docs/refs/v3`

Theme Lead gap list for Theme UI. **SoT = refs/v3 only.** Score target ≥9 / category before PASS.

Baseline audited against current education `theme.css` + tokens (1.0.x lineage) translating education UI into Obsidian.

---

## P0 — must close this round

| # | Category | Gap vs refs | Measurable fix |
|---|----------|-------------|----------------|
| 1 | Surfaces | Canvas/sidebar/surface tokens exist but leaf “floating white card on soft gray” still reads flat in places; outer radius feel under-refs (~28–32px window) | Ensure workspace `--sl-app-bg`, sidebar `--sl-sidebar-bg`, editor `--sl-surface` + `--sl-radius-xl`/`2xl` + `--sl-shadow-md`; no lime leftover anywhere |
| 2 | Navigation | White nav pill must dominate explorer/settings; any charcoal/lime active is a fail | `--nav-item-background-active` = `--sl-nav-active-bg` `#FFFFFF`; text `--sl-nav-active-text`; pill radius + `--sl-shadow-md` |
| 3 | Tabs / CTA | Active tabs + CTA must be black `#111111` pills with white text | `--tab-background-active` / `button.mod-cta` → `--sl-pill-bg` / `--sl-pill-text` only |
| 4 | Token purity | Any raw hex/px outside `.theme-light/.theme-dark` token block | Refactor selectors to `--sl-*` only; bump package to **1.1.0** |
| 5 | Focus | Focus must be dual-ring `--sl-focus-shadow` everywhere interactive | Zero remaining `3px var(--sl-focus-ring)`-only usages |

---

## P1 — fidelity & polish

| # | Category | Gap | Fix |
|---|----------|-----|-----|
| 6 | Typography | Titles should feel ~20–24px bold; chrome 13px; editor 14/1.65 | Wire `--sl-text-xl/2xl`, `--sl-text-md`, `--sl-text-base` |
| 7 | Spacing | Uneven padding vs airy refs | Only 4px grid tokens; card pad space-5/6; control pad 2×4 |
| 8 | Borders | Prefer hairline `#EEEEEE`; avoid heavy chrome borders | `--sl-border-subtle` for dividers; cards use shadow |
| 9 | Icons | Stroke weight / opacity should read thin monoline | `--sl-icon-size: 18px`, idle opacity `0.72` → `1` hover |
| 10 | Pastels | Callouts/tags should use pastel set, not lime/acid | Map callout types → `--sl-pastel-*` |
| 11 | Overlays | Menus/modals/palette need elevated white + soft lg shadow | `--sl-surface-elevated` + `--sl-shadow-lg` + xl radius |
| 12 | Scrollbars / noise | Thin muted thumbs; kill extra rules/borders that add chrome noise | `--sl-scrollbar`; strip non-token decorations |
| 13 | A11y | Warning text AA if still <4.5:1 | `--sl-warning-text` ≥ `#8A6508` light |
| 14 | Status bar | Height 32; readable secondary (not muted) | `--sl-control-h` + `--sl-text-secondary` |

---

## Out of scope (Obsidian limits — score N/A, don’t fake)

- Multi-column schedule grid / time gutter / floating pastel FAB stack
- Exact marketing illustrations / avatars from refs
- Pixel-perfect calendar event geometry

Translate those into: pastel callouts, black/white pills, soft cards, thin icons.

---

## Theme UI work order (CoS)

1. Surfaces → 2. Typography → 3. Spacing → 4. Borders → 5. Geometry → 6. Icons → 7. States → 8. Editor → 9. Overlays → 10. Scrollbars/noise  
Bump **1.1.0** · install vault · capture `/workspace/softledger-qa/v110/` · hand Visual QA for scoring.
