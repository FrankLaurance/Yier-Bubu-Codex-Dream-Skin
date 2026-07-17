# Codex Dream Skin Wallpaper Generation Guide

Generate **UI-free wallpaper art only** for use beneath real Codex controls. A screenshot, mock window, sidebar, card, composer, or readable text is not a usable wallpaper.

Chinese guide: [`reference-background-prompt-guide.md`](./reference-background-prompt-guide.md)

## Bundled Yier & Bubu assets

| Type | Path | Runtime-ready? |
|---|---|---|
| macOS preset | `macos/presets/preset-yier-bubu-cozy/` | **Yes** |
| Windows default | `windows/assets/theme.json` + `windows/assets/dream-reference.jpg` | **Yes** |
| High-resolution wallpaper | `docs/images/presets/yier-bubu-wallpaper-2560x1440.jpg` | Image only |
| Generated source | `docs/images/presets/yier-bubu-wallpaper-source.png` | Needs theme metadata |
| Concept preview | `docs/images/presets/yier-bubu-concept-preview.png` | **No; contains UI** |

## Composition contract

- `2560 × 1440`, 16:9, opaque, edge-to-edge continuous art.
- Reserve `x=0%–52%` as a low-information safe area.
- Place the main subjects around `x=68%–80%`; keep critical details inside `x=60%–90%` and `y=16%–72%`.
- Keep important details at least 8% from every edge.
- Retain midtone texture for both light and dark shell treatments.
- No app chrome, UI, text, logo, watermark, cards, or device frame.

## Copy-ready prompt

```text
Create one standalone 2560x1440, 16:9 desktop wallpaper as opaque, edge-to-edge continuous artwork. This is the wallpaper beneath a real Codex interface, not a screenshot, window mockup, poster, or UI concept.

Reserve x=0%-52% as a calm warm-cream safe area with very low visual information and low local contrast. Place the two simplified Yier-and-Bubu-inspired animal mascots at x=68%-86%, working together at a small wooden desk with one laptop, a mint-green mug, two books, one small star decoration, and a tiny plant. Keep all important details inside y=16%-72% and at least 8% away from every edge.

Style: soft hand-drawn stationery illustration, clean rounded outlines, matte paper texture, warm cream, caramel brown, butter yellow, and muted mint green. Keep the characters faithful to the supplied authorized visual references. Use one coherent perspective and a quiet, friendly coding mood. The left side must remain a believable continuation of the same room rather than a blank rectangle.

Output only the clean wallpaper. No application window, sidebar, panel, card, button, icon, input box, code editor, readable text, signature, logo, watermark, split screen, or border.
```

Validate the result with:

```bash
node macos/scripts/injector.mjs \
  --check-payload \
  --theme-dir macos/presets/preset-yier-bubu-cozy/
```

See `macos/NOTICE.md` for character and redistribution boundaries.
