# Notices

Yier & Bubu Codex Dream Skin is an **unofficial** customization project. It is not affiliated with, endorsed by, or sponsored by OpenAI or the rights holders of the referenced characters.

## MIT license scope

The MIT License in the repository root and this directory applies to the project source code, documentation, and project-created bundled theme artwork, including:

- `presets/preset-yier-bubu-cozy/background.jpg`
- `../windows/assets/dream-reference.jpg`
- `../docs/images/presets/yier-bubu-wallpaper-source.png`
- `../docs/images/presets/yier-bubu-wallpaper-2560x1440.png`
- `../docs/images/presets/yier-bubu-wallpaper-2560x1440.jpg`
- `../docs/images/presets/yier-bubu-concept-preview.png`

These project files may be used, copied, modified, published, distributed, sublicensed, and sold under the MIT License. The license applies only to rights the contributors are legally able to license.

The MIT License does not grant rights to:

- OpenAI or Codex trademarks, product names, logos, or trade dress;
- official Codex / ChatGPT application binaries, `.app` bundles, `app.asar`, or WindowsApps packages;
- third-party names, characters, character likenesses, franchise art, or trademarks;
- user-supplied images or other third-party artwork added to a theme.

## Yier & Bubu theme artwork

These files were generated for this customized theme from user-supplied visual references and are included under the MIT terms above. They are not official Codex or OpenAI artwork and their inclusion does not imply endorsement by any third party.

The concept preview contains application-interface artwork and is documentation only. It must never be imported as a runtime wallpaper. The runtime wallpapers listed above are explicitly identified as UI-free.

## Other bundled presets

The procedural abstract presets and `assets/portal-hero.png` are inherited from the upstream Codex Dream Skin project and remain under its MIT license and notices.

## Runtime and security

The project does not redistribute Node.js. On macOS it validates and uses the runtime signed and bundled with official Codex; Windows requires a local Node.js 22+ installation.

Themes are applied through Chromium DevTools Protocol on loopback only. Treat the local debugging port as sensitive while a themed session is running, and use Restore when theming is no longer needed.
