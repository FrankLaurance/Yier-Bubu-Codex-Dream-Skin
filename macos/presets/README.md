# 预设主题 · Preset packs

这个目录存放 Codex Dream Skin 的内置预设。安装时，`install-dream-skin-macos.sh` 会将每个 `preset-*/` 幂等地播种到 `~/Library/Application Support/CodexDreamSkinStudio/themes/`。用户可以从菜单栏「已保存的主题」或 `switch-theme-macos.sh --id <id>` 直接切换。

## 默认：一二布布 · 暖暖编码

`preset-yier-bubu-cozy/` 是本项目的默认主题。它包含：

- `background.jpg`：`2560 × 1440` 、16:9、不含窗口或应用 UI 的纯背景；
- `theme.json`：主题 ID、中英文案、焦点、安全区、任务页模式和十项色彩令牌。

左侧保留低信息区，一二和布布集中在右侧。概念效果图位于 `docs/images/presets/yier-bubu-concept-preview.png`，其中包含 UI，只作文档预览，不能导入为背景。

安装后切换：

```bash
~/.codex/codex-dream-skin-studio/scripts/switch-theme-macos.sh \
  --id preset-yier-bubu-cozy
```

## 预设结构

```text
preset-<slug>/
├── theme.json
└── background.jpg
```

- 目录名与 `theme.json` 的 `id` 必须相同，并使用 `preset-<slug>` 形式。
- `image` 只能是当前目录中的文件名，可使用 PNG / JPEG / WebP，大小不超过 16 MB。
- 建议使用 `2560 × 1440` 横向母版，左侧 50%～58% 保持平静，主视觉位于右侧。
- 不要把带窗口、侧边栏、卡片、按钮、输入框、可读文字或水印的效果图当成背景。

## 其他预设

`preset-midnight-aurora`、`preset-sakura-dawn`、`preset-amber-dusk`、`preset-forest-mist` 和 `preset-cyber-neon` 是从上游保留的程序化抽象预设。`generate-presets.mjs` 只会管理这些程序化主题，不会覆盖一二布布预设。

## 自检

```bash
node macos/scripts/injector.mjs \
  --check-payload \
  --theme-dir macos/presets/preset-yier-bubu-cozy/

cd macos && npm test
```

项目自带主题图像采用 MIT License；第三方权利边界见 [`../NOTICE.md`](../NOTICE.md)。
