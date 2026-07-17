# 一二布布 Codex Dream Skin

<p align="center">
  <strong>中文</strong> · <a href="./README.en.md">English</a>
</p>

<p align="center">
  <strong>一套可安装、可交互、可恢复的一二布布 Codex 桌面端主题。</strong><br>
  macOS + Windows · 本机 CDP 注入 · 不修改官方安装包
</p>

<p align="center">
  <img src="docs/images/presets/yier-bubu-concept-preview.png" alt="一二布布 Codex Dream Skin 概念预览" width="900"><br>
  <sub>概念预览：用于表达目标效果，不是可导入背景</sub>
</p>

## 这是什么

本项目是 [Codex Dream Skin](https://github.com/Fei-Away/Codex-Dream-Skin) 的一二布布主题版，固定在上游提交 `a1c48b3a84cc64532196e624fdf33ee1277cb018`（引擎版本 `1.2.0`）上制作。项目保留了原仓库的完整结构：

- macOS 安装、启动、验证、恢复、菜单栏和主题库；
- Windows 安装、启动、验证、恢复和系统托盘；
- 完整注入器、CSS、渲染脚本、测试、CI、Skill 和项目文档；
- 一二布布默认主题、`2560 × 1440` 纯背景与双平台一致的配色。

原生侧边栏、项目卡片、输入框和任务页仍然可交互；主题不是把整个窗口替换成一张假截图。

## 主题设计

<p align="center">
  <img src="docs/images/presets/yier-bubu-wallpaper-2560x1440.jpg" alt="一二布布可导入背景" width="900"><br>
  <sub>可导入纯背景：2560 × 1440，不含任何应用 UI</sub>
</p>

- 左侧大面积低对比留白，供 Codex 原生标题、卡片和输入框使用。
- 一二和布布的角色主视觉集中在右侧，避免遮挡交互区。
- 奶油、焦糖、薄荷绿配色同时覆盖背景、面板、强调色和辅助文字。
- `safeArea: left` 与 `taskMode: ambient` 会在任务页自动降低背景干扰。

## 快速安装

### macOS

1. 安装并至少启动过一次官方 Codex。
2. **完全退出 Codex**。
3. 打开 `macos/`，双击 `Install Codex Dream Skin.command`。

也可在终端执行：

```bash
cd macos
./scripts/install-dream-skin-macos.sh --no-launch
~/.codex/codex-dream-skin-studio/scripts/switch-theme-macos.sh \
  --id preset-yier-bubu-cozy
```

首次安装会默认选中「一二布布 · 暖暖编码」。之后可用菜单栏或 `switch-theme-macos.sh` 切换。

### Windows

1. 安装 Node.js 22 或更新版本，并完全退出 Codex。
2. 在 PowerShell 中执行：

```powershell
powershell -ExecutionPolicy Bypass -File .\windows\scripts\install-dream-skin.ps1
powershell -ExecutionPolicy Bypass -File .\windows\scripts\start-dream-skin.ps1
```

首次安装会把一二布布设为活动主题，同时加入托盘的「已保存主题」。

## 验证与恢复

macOS：

```bash
./macos/scripts/verify-dream-skin-macos.sh
./macos/scripts/restore-dream-skin-macos.sh --restore-base-theme --restart-codex
```

Windows：

```powershell
powershell -ExecutionPolicy Bypass -File .\windows\scripts\verify-dream-skin.ps1
powershell -ExecutionPolicy Bypass -File .\windows\scripts\restore-dream-skin.ps1
```

恢复脚本会停止主题注入并恢复官方外观配置，不会修改 `.app`、`app.asar` 或 WindowsApps。

## 开发与测试

```bash
cd macos
npm test
```

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\windows\tests\run-tests.ps1
```

GitHub Actions 还会运行 Shell / Node.js 语法、版本一致性、payload 和 Windows PowerShell 5.1 / PowerShell 7 回归测试。

本定制包的已执行检查见 [`docs/VALIDATION.md`](./docs/VALIDATION.md)。

## 安全边界

- CDP 只绑定 `127.0.0.1`；主题运行期间不要运行不可信的本机程序。
- 不修改 Codex 官方二进制、代码签名、API Key 或 Base URL。
- 安装前要完全退出 Codex；验证脚本可检查当前注入状态。
- 本项目非 OpenAI 官方产品。

## 授权与素材

- 本仓库的源码、文档和随附的项目原创主题素材统一采用 [MIT License](./LICENSE)，可免费使用、修改、发布和商用。
- 一二布布主题图像为本定制项目生成的素材，不代表 OpenAI 或任何第三方的官方背书。
- MIT 许可不授予 OpenAI/Codex 名称、商标、官方应用以及其他第三方权利；详见 [`macos/NOTICE.md`](./macos/NOTICE.md)。

## 仓库结构

```text
.
├── .github/                 # CI、Issue 与 PR 模板
├── docs/                    # 设计、平台与素材文档
├── macos/                   # macOS 完整引擎、预设、菜单栏和测试
├── windows/                 # Windows 完整引擎、托盘和测试
├── README.md
└── README.en.md
```
