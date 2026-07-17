# 一二布布 Codex Dream Skin · 项目记录

> 面向维护者的定制版说明。用户安装请从 [`../README.md`](../README.md) 开始。

## 定制基线

- 上游项目：[Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin)
- 固定提交：`a1c48b3a84cc64532196e624fdf33ee1277cb018`
- 引擎版本：`1.2.0`
- 定制主题 ID：`preset-yier-bubu-cozy`
- 中文名称：`一二布布 · 暖暖编码`

这是完整仓库级定制，不是单独图片包。它保留了 macOS 和 Windows 的安装、启动、持续注入、验证、暂停、恢复、主题仓库、菜单栏/托盘、测试和 CI。

## 主题设计决定

| 维度 | 决定 |
|---|---|
| 视觉主题 | 一二和布布在右侧书桌共同编码 |
| 画布 | `2560 × 1440` JPEG，不含应用 UI |
| 信息安全区 | 左侧，约 `x=0%～52%` |
| 色板 | 奶油 `#FFF7E6`、焦糖 `#E8A93D`、薄荷 `#A8D0B6`、深褐 `#4B3528` |
| 焦点 | `focusX=0.79`、`focusY=0.48` |
| 任务页 | `taskMode=ambient`，自动降低视觉干扰 |
| 外观 | `appearance=auto`，跟随原生/系统外观 |

## 双平台一致性

macOS 主题位于 `macos/presets/preset-yier-bubu-cozy/`。Windows 播种源位于 `windows/assets/theme.json` 和 `windows/assets/dream-reference.jpg`。两个 JPEG 必须字节级一致；两端保持相同的主题 ID、名称、外观和构图契约，Windows 另用 `palette.accent` 映射焦糖强调色。

## 验证要求

1. 每个 `preset-*` 都能通过 `injector.mjs --check-payload`。
2. macOS 运行 `cd macos && npm test`。
3. Windows 运行 `windows/tests/run-tests.ps1`，并同时覆盖 Windows PowerShell 5.1 和 PowerShell 7。
4. PowerShell 含非 ASCII 文字时保持 UTF-8 BOM。
5. 发行前比对 macOS / Windows 背景 SHA-256，并校验 `2560 × 1440`。
6. 实机验收时分别检查首页与普通任务页，包括输入框、项目菜单、侧边栏、滚动和水平溢出。

## 安全边界

- CDP 仅绑定 `127.0.0.1`。
- 不修改 `.app`、`app.asar`、WindowsApps 或官方签名。
- 不改写 API Key、Base URL、登录、任务、宠物或插件状态。
- 只结束与记录 PID、路径、启动时间和签名匹配的进程。
- 恢复必须可用，并保留可恢复配置备份。

## 素材边界

本仓库随附的一二布布项目原创主题图像与源码统一采用 MIT License，可免费使用、修改、发布和商用。MIT 不包含项目贡献者无权授予的第三方名称、商标、官方应用或用户自行导入的素材权利，详见 `macos/NOTICE.md`。
