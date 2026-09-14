# Softledger

A lightweight [Obsidian](https://obsidian.md) community theme inspired by modern finance-dashboard soft UI — airy light-gray canvas, white floating cards, lime/acid green accents, and charcoal pill tabs.

**Author:** Ramakrishna Dhikonda · **License:** MIT

## Screenshots

| Light | Dark |
| --- | --- |
| ![Softledger light](docs/refs/ref-1.png) | *(dark mode keeps soft-card language)* |
| ![Softledger overview](docs/refs/ref-2.png) | ![Softledger cards](docs/refs/ref-3.png) |

> Reference mockups live in `docs/refs/`. Replace with live vault screenshots when publishing.

## Install

### Manual (local)

1. Open your vault’s config folder: **Settings → Community plugins → Open .obsidian folder** (or navigate to `<vault>/.obsidian/`).
2. Create `themes/Softledger/` if it does not exist:
   ```text
   .obsidian/themes/Softledger/
   ├── manifest.json
   └── theme.css
   ```
3. Copy `manifest.json` and `theme.css` from this repo into that folder.
4. In Obsidian: **Settings → Appearance → Themes** → select **Softledger**.
5. (Optional) Toggle light/dark under **Appearance → Base color scheme**.

### From a clone

```bash
git clone <this-repo> Softledger
cp Softledger/manifest.json Softledger/theme.css \
  "<vault>/.obsidian/themes/Softledger/"
```

Then enable the theme in **Settings → Appearance**.

## Design notes

Softledger maps a finance-dashboard soft-UI system onto Obsidian:

| Token / idea | Value / behavior |
| --- | --- |
| App canvas | `#F5F7FA` (light) / `#12141A` (dark) |
| Cards / panels | `#FFFFFF` / elevated dark surfaces, radius ~16–20px |
| Accent | Lime `#A3E635` / `#B1FF40` — CTAs, checkboxes, positive chips |
| Active tabs | Charcoal (or light-on-dark) **pill** with high contrast text |
| Depth | Soft drop shadows over hard borders |
| Type | Inter / system geometric sans via `--font-interface` / `--font-text` |
| Ribbon | Narrow, blended into canvas; active icon as pill/circle |

**Key CSS variables** (theme-owned `--sl-*`, mapped to Obsidian tokens):

- `--sl-bg-app`, `--sl-bg-card`, `--sl-bg-muted`
- `--sl-accent`, `--sl-accent-bright`, `--sl-accent-soft`
- `--sl-pill`, `--sl-pill-text`
- `--sl-text`, `--sl-text-secondary`, `--sl-text-muted`
- `--sl-success` / `--sl-warning` / `--sl-danger` (+ `*-bg`)
- `--sl-shadow-sm|md|lg`, `--sl-radius-*`, `--sl-radius-pill`

Obsidian mappings include `--background-primary|secondary`, `--interactive-accent`, `--text-*`, `--nav-item-*`, `--ribbon-background`, tab radii, and modal radii.

## Performance

- Pure CSS — no build step, no background images, no base64 blobs
- Lean selector set; no expensive universal `*` rules
- Target size well under ~80KB (`theme.css` is typically ~30KB)

## Structure

```text
obsidian-softledger/
├── manifest.json
├── theme.css
├── versions.json
├── README.md
├── LICENSE
└── docs/
    ├── .gitkeep
    └── refs/          # UI reference images
```

## Compatibility

- `minAppVersion`: **1.5.0**
- Desktop & mobile (CSS-only theme)

## License

MIT © Ramakrishna Dhikonda — see [LICENSE](LICENSE).
