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
| App canvas | `#F5F7F8` (light) / `#1A1C1E` (dark) |
| Cards / panels | `#FFFFFF` / `#242628`, radius ~20px |
| Accent | Lime `#A3E635` — CTAs, focus, positive |
| Active tabs | Charcoal `#2D2D2D` **pill** + white text (light) |
| Depth | Soft diffused shadows over hard borders |
| Type | Inter / system UI via `--font-interface` / `--font-text` |
| Ribbon | Narrow, blended into canvas; active icon as pill/circle |

**Key CSS variables** (theme-owned `--sl-*`, mapped to Obsidian tokens):

- `--sl-canvas`, `--sl-card`, `--sl-subtle`
- `--sl-lime`, `--sl-lime-muted`, `--sl-forest`
- `--sl-charcoal` (active pill), heading/body/muted text tokens
- `--sl-success` / `--sl-warning` / `--sl-danger`
- `--sl-shadow-soft|float`, `--sl-radius-card|pill|control`

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
