# Codex Remiel Theme

Codex Desktop 独立主题管理工具，并内置《绝区零》蕾米埃尔风格的「星芒圣翼」主题。主题背景、按钮图标、加载动画和页面适配全部封装在独立主题目录中；公共引擎只负责安装、切换、热重载和恢复官方外观。

> 非 OpenAI 或游戏官方项目。本仓库不包含 Codex 官方安装包，也不修改 `WindowsApps`、`app.asar` 或官方二进制文件。角色及相关名称权利归各自权利人所有。

## 一键安装

下载仓库后双击 `安装主题工具.cmd`。安装器会：

- 将稳定运行文件复制到 `%LOCALAPPDATA%\CodexDreamSkin\runtime`；
- 在 Codex 的 `设置 → 主题` 中安装主题管理页；
- 创建桌面和开始菜单的 `Codex 主题` 启动入口；
- 保留恢复官方外观入口，并在 Codex 更新后重新匹配已注册的 Store 包；
- 首次启动保持官方外观，由你在主题页安装并启用蕾米埃尔主题。

旧式兼容入口 `安装蕾米埃尔主题.cmd` 会安装主题管理页并打开 Codex，推荐优先使用 `安装主题工具.cmd`。

## 主题目录

```text
windows/themes/remiel-seraph-system-v1/
├── theme.json
├── theme.css
├── theme.js
└── background.jpg
```

主题使用粉红、星紫、珍珠白与深梅色构成可读表面；人物位于右侧，左侧保留项目和对话阅读区。按钮图标统一为星芒、机械圣翼和菱晶语言，发送与加载状态使用低成本旋转动画。

主题不捆绑宠物，避免额外精灵动画与主题背景同时运行造成性能压力。已有 Codex 宠物不会被删除或修改。

## GitHub 主题库

仓库根目录的 [`theme-library.json`](theme-library.json) 是公开主题索引。在 Codex 的 `设置 → 主题 → 从 GitHub 仓库安装` 中粘贴本仓库 URL，即可读取并安装主题。

远程主题包含可执行 JavaScript，只应安装可信来源。索引仅支持公开 HTTPS GitHub 仓库。

## 热重载

注入器会监听当前活动主题的 JSON、CSS、JS 和图片。保存文件后会重新校验并注入，无需重启 Codex；文件监听不可用时自动回退到轮询校验。

## 开发与验证

```powershell
powershell -NoProfile -File .\windows\tests\run-tests.ps1
node --check .\windows\scripts\injector.mjs
node --check .\windows\themes\remiel-seraph-system-v1\theme.js
```

主题包格式见 [`windows/THEME_FORMAT.md`](windows/THEME_FORMAT.md)，详细使用方式见 [`使用说明.md`](使用说明.md)。

## 致谢与许可

主题管理架构基于 [yanhuuo/Codex-Xuanling-Theme](https://github.com/yanhuuo/Codex-Xuanling-Theme)，其底层方案参考 [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin)。代码按 [`LICENSE`](LICENSE) 提供。
