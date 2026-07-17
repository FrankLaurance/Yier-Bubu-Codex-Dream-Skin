# Codex Dream Skin 纯背景生成指南

这份文档只用于生成铺在真实 Codex 控件下方的**纯背景图**。效果图、窗口截图、侧边栏、卡片、输入框与可读文字都不是背景素材。

English guide: [`reference-background-prompt-guide.en.md`](./reference-background-prompt-guide.en.md)

## 本项目中的一二布布素材

| 类型 | 路径 | 能否用于运行时 |
|---|---|---|
| macOS 完整预设 | `macos/presets/preset-yier-bubu-cozy/` | **可以** |
| Windows 默认主题 | `windows/assets/theme.json` + `windows/assets/dream-reference.jpg` | **可以** |
| 高清纯背景 | `docs/images/presets/yier-bubu-wallpaper-2560x1440.jpg` | **可以**，但只有图片 |
| 生成源图 | `docs/images/presets/yier-bubu-wallpaper-source.png` | 需组成主题包 |
| 概念效果图 | `docs/images/presets/yier-bubu-concept-preview.png` | **不可以**，其中包含 UI |
| 画廊效果图 | `docs/images/gallery/skin-01.jpg` ～ `skin-08.jpg` | **不可以** |

一套可播种主题必须把 `theme.json` 与背景图放在同一个 `preset-*` 目录中。

## 画布与构图规则

- 母版：`2560 × 1440`，16:9，不透明，边到边连续画面。
- 左侧 `x=0%～52%`：低信息、低局部对比、无人脸、无密集物体。
- 主视觉中心：`x=68%～80%`，所有关键细节位于 `x=60%～90%`。
- 关键竖向区：`y=16%～72%`，与画布四边至少保留 8% 安全距离。
- 浅/暗兼容：左侧保留连续中间调纹理，不用纯白或死黑。
- 输出不得含窗口边框、UI、文字、Logo、水印、卡片或设备外框。

## 一二布布风格模板

```text
Create one standalone 2560x1440, 16:9 desktop wallpaper as opaque, edge-to-edge continuous artwork. This is the wallpaper beneath a real Codex interface, not a screenshot, window mockup, poster, or UI concept.

Reserve x=0%-52% as a calm warm-cream safe area with very low visual information and low local contrast. Place the two simplified Yier-and-Bubu-inspired animal mascots at x=68%-86%, working together at a small wooden desk with one laptop, a mint-green mug, two books, one small star decoration, and a tiny plant. Keep all important details inside y=16%-72% and at least 8% away from every edge.

Style: soft hand-drawn stationery illustration, clean rounded outlines, matte paper texture, warm cream, caramel brown, butter yellow, and muted mint green. Keep the characters faithful to the supplied authorized visual references. Use one coherent perspective and a quiet, friendly coding mood. The left side must remain a believable continuation of the same room rather than a blank rectangle.

Output only the clean wallpaper. No application window, sidebar, panel, card, button, icon, input box, code editor, readable text, signature, logo, watermark, split screen, or border.
```

负面词：

```text
UI, GUI, software window, desktop screenshot, browser, mockup, title bar, sidebar, panel, card, button, icon, input box, composer, code editor, readable text, logo, signature, watermark, border, split screen, collage, duplicate character, extra limbs, malformed hands, cropped face
```

## 导出与验证

1. 在生成器中选择 16:9 最高质量横图。
2. 使用等比裁切，不要把非 16:9 图片直接拉伸。
3. 导出为 PNG 母版和 JPEG 运行副本，运行文件不超过 16 MB。
4. 用下列命令校验主题：

```bash
node macos/scripts/injector.mjs \
  --check-payload \
  --theme-dir macos/presets/preset-yier-bubu-cozy/
```

生成素材的角色与分发权利见 `macos/NOTICE.md`。
