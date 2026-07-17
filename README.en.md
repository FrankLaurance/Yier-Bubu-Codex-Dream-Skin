# Yier & Bubu Codex Dream Skin

<p align="center">
  <a href="./README.md">中文</a> · <strong>English</strong>
</p>

<p align="center">
  <strong>A complete, installable, interactive, and reversible Yier & Bubu theme for Codex desktop.</strong><br>
  macOS + Windows · local CDP injection · no mutation of the official package
</p>

<p align="center">
  <img src="docs/images/presets/yier-bubu-concept-preview.png" alt="Yier and Bubu Codex Dream Skin concept preview" width="900"><br>
  <sub>Concept preview only; do not import this UI mockup as a wallpaper</sub>
</p>

This repository is a themed edition of [Codex Dream Skin](https://github.com/Fei-Away/Codex-Dream-Skin), pinned to upstream commit `a1c48b3a84cc64532196e624fdf33ee1277cb018` and engine version `1.2.0`. It preserves the original full project structure, including both platform engines, tests, CI, docs, skills, menu-bar and system-tray controls.

The bundled theme uses a `2560 × 1440` UI-free wallpaper, a left-side safe area for native Codex controls, warm cream and caramel colors, and a quieter task-page treatment. Native cards, sidebar, project picker, composer, and task UI remain interactive.

## Quick start

### macOS

1. Launch official Codex at least once.
2. Quit Codex completely.
3. Open `macos/` and double-click `Install Codex Dream Skin.command`.

Or run:

```bash
cd macos
./scripts/install-dream-skin-macos.sh --no-launch
~/.codex/codex-dream-skin-studio/scripts/switch-theme-macos.sh \
  --id preset-yier-bubu-cozy
```

### Windows

Install Node.js 22 or newer, quit Codex, then run:

```powershell
powershell -ExecutionPolicy Bypass -File .\windows\scripts\install-dream-skin.ps1
powershell -ExecutionPolicy Bypass -File .\windows\scripts\start-dream-skin.ps1
```

Both platforms seed **Yier & Bubu · Cozy Coding** as the default theme and as a saved theme.

## Verify and restore

```bash
./macos/scripts/verify-dream-skin-macos.sh
./macos/scripts/restore-dream-skin-macos.sh --restore-base-theme --restart-codex
```

```powershell
powershell -ExecutionPolicy Bypass -File .\windows\scripts\verify-dream-skin.ps1
powershell -ExecutionPolicy Bypass -File .\windows\scripts\restore-dream-skin.ps1
```

## Development checks

```bash
cd macos && npm test
```

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\windows\tests\run-tests.ps1
```

See [`docs/VALIDATION.md`](./docs/VALIDATION.md) for the checks executed for this customized package.

## Safety and licensing

- CDP binds to `127.0.0.1` only.
- The project does not modify `.app`, `app.asar`, WindowsApps, signatures, API keys, or provider settings.
- It is unofficial and is not affiliated with or endorsed by OpenAI.
- Repository source, documentation, and bundled project-created theme artwork are released under the [MIT License](./LICENSE), including free personal and commercial use.
- The MIT License does not grant rights to OpenAI/Codex names, trademarks, official applications, or other third-party property; see [`macos/NOTICE.md`](./macos/NOTICE.md).
