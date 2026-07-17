# Validation report

Date: 2026-07-17 (Asia/Shanghai)

## Baseline

- Upstream repository: `Fei-Away/Codex-Dream-Skin`
- Upstream commit: `a1c48b3a84cc64532196e624fdf33ee1277cb018`
- Engine version: `1.2.0`
- Custom preset: `preset-yier-bubu-cozy`

## Passed checks

- `cd macos && npm test`
  - Shell and JavaScript syntax
  - All six bundled preset payloads
  - Preset seeding and atomic switching
  - Runtime-state identity checks
  - Theme staging and renderer behavior
  - UTF-8 / BOM / CRLF / TOML round trips
  - Signed Codex runtime discovery and doctor check with isolated test state
- Portable Node regressions
  - macOS: 4/4 passed
  - Windows: 4/4 passed, including the loopback one-shot CDP fixture
- Payload checks
  - macOS custom payload: passed
  - Windows custom payload: passed
  - Theme ID: `preset-yier-bubu-cozy`
  - Art metadata: `2560 × 1440`, 16:9, `safeArea=left`, `taskMode=ambient`
- Cross-platform asset parity
  - macOS and Windows runtime JPEG files are byte-identical
  - SHA-256: `67fc0c7d1cbd46e6a4c2dd91330aa67bf11756f151a4de89e530e4f06ea44e5c`
- Static repository checks
  - PowerShell files with non-ASCII text retain UTF-8 BOM
  - Engine version is consistent across `VERSION` and both injectors
  - 30 Markdown files have valid relative links
  - No removed upstream featured-theme names or paths remain
- Packaging
  - `macos/scripts/build-client-release.sh` completed successfully
  - The generated macOS package contains the Yier & Bubu preset and installer

## Environment-limited checks

- The full `windows/tests/run-tests.ps1` suite requires Windows PowerShell 5.1 or PowerShell 7 on Windows. It was not executed on this macOS machine. The repository keeps the original GitHub Actions matrix for both Windows shells, and all portable Windows Node regressions passed locally.
- Live visual injection into the user's current Codex session was intentionally not performed. Installation, payload, doctor, packaging, and restore code paths were checked without changing the user's active Codex state.

## Release acceptance still recommended

After installing on each target platform, run Verify and inspect both the home route and a normal task route. Confirm sidebar, project selector, composer, scrolling, text contrast, and restore behavior before public distribution.
