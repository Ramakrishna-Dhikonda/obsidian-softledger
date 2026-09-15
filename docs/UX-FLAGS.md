# Softledger UX flags (education 1.0)

Usability adaptations where soft-UI fidelity fights Obsidian use. **Keep visual language; change the minimum token/selector.** Design SoT: [`TOKENS.md`](TOKENS.md) + `docs/refs/v3`. Audited against theme **v1.0.0**.

**Fidelity lock (CoS):** active nav = **white pill**; primary CTA / selected tabs = **black solid pill**; pastel cards; indigo links; **no lime**. Finance lime parked in `docs/proposals/finance-lime/`.

Priority: P0 = fix before polish · P1 = next pass · P2 = comfort / a11y depth.

---

## P0 — Soft keyboard focus — DONE (Theme UI)

**Was:** Light `--sl-focus-ring` 0.16 ≈ 1.4:1; soft ring only; incomplete coverage.

**Landed:** `--sl-focus-ring` → 0.55 / 0.6; dual ring `0 0 0 2px var(--sl-text), 0 0 0 4px var(--sl-accent)` on inputs + checkbox + extended `:focus-visible` (ribbon, nav-action, settings nav, menu, suggestion, modal close). CTA `color: var(--text-on-accent)` → `--sl-pill-text` (≈18.9:1 on black). No lime.

---

## Already solid

- CTA / primary pill: white on `#111111` ≈ **18.9:1** (`color: var(--sl-pill-text)`)
- Links `--sl-link` `#5B5BD6` ≈ **5.4:1** on white
- Control heights 32 / 36 from tokens
- Editor body `line-height: 1.65` + primary text AAA
- Token-first `--sl-*` mapping
- Dual-ring keyboard focus + extended `:focus-visible` coverage

---

## P1 — Muted chrome (tabs/status) — DONE (Theme UI / Visual QA)

**Landed:** `--tab-text-color` → `--sl-text-secondary`; status bar `color: var(--sl-text-secondary)` + `min-height: var(--sl-control-h)` (32). Breadcrumbs may still use muted (OK for meta).

---

## P1 — Semantic text colors

**Issue:** `--sl-warning` `#D4A017` ≈ **2.4:1**, `--sl-success` `#2F9E6B` ≈ **3.4:1**, `--sl-danger` `#E05A5A` ≈ **3.6:1** on white — OK as fills/icons, weak as body text.

**Minimal adaptation:** Darker text companions for Obsidian `--text-warning` / `--text-success` / `--text-error`; leave fill tokens for chips/callouts/pastels.

---

## P1 — White nav pill vs lavender sidebar (selected clarity)

**Issue:** Active nav `#FFFFFF` on sidebar `#F0EFF5` — tiny fill delta; selection leans on `--sl-shadow-sm`. Hover wash can look similar.

**Minimal adaptation:** Keep white pill; strengthen selected cue only (slightly stronger shadow or 1px `--sl-border`). Don’t switch sidebar active to black (fidelity lock).

---

## P1 — Hit targets — PARTIAL

**Landed:** Status ≥32 (`--sl-control-h`); tag padding `var(--sl-space-1) var(--sl-space-3)` (4/12); badge `font-size: var(--sl-text-xs)` (11px).

**Open:** Checkbox visual still **16×16** — enlarge hit-area ≥24px (padding/hitbox OK).

---

## P2 — Editor measure (optional)

Line-height 1.65 is solid. Optional: preview max-measure ~40–48rem; code wash via `--sl-surface-alt` if code feels flat on white.

---

## Suggested implement order (Theme UI)

1. ~~Dual-ring focus~~ **done**
2. ~~Status/tabs → secondary + status 32~~ **done**
3. Semantic text companions
4. Stronger white-nav selected cue
5. Checkbox hit-area ≥24
6. Optional editor measure / code wash
