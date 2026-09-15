# Softledger UX flags (education 1.0)

Usability adaptations where soft-UI fidelity fights Obsidian use. **Keep visual language; change the minimum token/selector.** Design SoT: [`TOKENS.md`](TOKENS.md) + `docs/refs/v3`. Audited against theme **v1.0.1** (`c32230a`).

**Fidelity lock (CoS):** active nav = **white pill**; primary CTA / selected tabs = **black solid pill**; pastel cards; indigo links; **no lime**. Finance lime parked in `docs/proposals/finance-lime/`.

Priority: P0 = fix before polish · P1 = next pass · P2 = comfort / a11y depth.

## Status (1.0.1)

**P0 closed.** P1 closed (tabs/status, semantic text, nav selected cue, hit targets). Optional polish: deepen `--sl-warning-text` past 4.5:1 (currently ≈4.39:1). P2 editor measure still optional.

---


## P0 — Soft keyboard focus — DONE (Theme UI)

**Was:** Light `--sl-focus-ring` 0.16 ≈ 1.4:1; soft ring only; incomplete coverage.

**Landed:** `--sl-focus-ring` → 0.55 / 0.6; `--sl-focus-shadow` = `0 0 0 2px var(--sl-text), 0 0 0 4px var(--sl-focus-ring)` on inputs + checkbox + extended `:focus-visible` (ribbon, nav-action, settings nav, menu, suggestion, modal close, tab headers). CTA `color: var(--text-on-accent)` → `--sl-pill-text` (≈18.9:1 on black). No lime.

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

## P1 — Semantic text colors — DONE

**Landed:** `--sl-*-text` companions mapped to `--text-success|warning|error`. Light ratios ≈ success 5.3 / danger 5.1 / warning **4.39** (AA normal is 4.5 — optional deepen warning-text slightly).

---

## P1 — White nav selected clarity — DONE

**Landed:** Active nav uses `box-shadow: var(--sl-shadow-md)` + `1px solid var(--sl-border)`; settings active keeps shadow-sm.

---

## P1 — Hit targets — DONE

**Landed:** Status 32; tag 4/12; badge 11px; checkbox **24×24**.

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
