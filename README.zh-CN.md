# UI Improvements

[English README](./README.md)

UI Improvements 是面向 Codex 桌面端的 Codex++ tweak。它基于
[`b-nnett/codex-plusplus-bennett-ui`](https://github.com/b-nnett/codex-plusplus-bennett-ui)
本地 fork，保留 Bennett 原有的 UI 体验优化，并加入侧边栏、输入框、项目列表和响应式布局调整。

## 相对原项目的修改

- 将 tweak 元数据与 upstream 包分离，并指向当前 fork。
- 新增 `main-sidebar-layout`：隐藏主侧边栏中的 Codex++ tweak 页面入口，同时保留 Settings 导航。
- 为小窗口和可见侧边栏场景增加主内容区响应式留白，修复 root attribute selector 不匹配导致样式不生效的问题。
- 避免监听自身写入的 inline `style` 变化，修复布局反复触发造成的闪烁。
- 优化会话切换时的 composer loading 状态，使用更紧凑的动画 spinner，并适配窄布局位置。
- 扩展项目侧边栏体验：本地项目颜色偏好迁移、项目分组背景、聊天项目标签、复制项目路径。
- 继续保留并维护原项目中的 slash menu、usage、message metrics、settings search 和侧边栏聊天批量操作能力。

## 功能列表

- 隐藏 Codex upgrade 提示。
- 在侧边栏显示 5 小时和每周 usage。
- 鼠标悬停 assistant message 时显示 token metrics。
- 为 Codex Settings 增加搜索，并让 Settings 侧边栏宽度与主界面一致。
- 将主侧边栏的 New chat、Search、Plugins、Automations 调整为紧凑 2x2 网格。
- 为项目列表添加分组背景、项目颜色和聊天项目标签。
- 支持 Cmd/Ctrl-click 多选侧边栏聊天，并执行批量操作。
- 优化 composer slash menu：更紧凑的行距、favorites、更清晰的分区状态和键盘行为。
- 会话切换时在 composer 上方显示紧凑 loading spinner。
- 隐藏主侧边栏中的 Codex++ tweak 页面入口，并为主内容区增加响应式留白。

## 安装

将本仓库安装为一个 tweak 目录：

```sh
mkdir -p "$HOME/Library/Application Support/codex-plusplus/tweaks"
cp -R . "$HOME/Library/Application Support/codex-plusplus/tweaks/ui-improvements"
```

然后在 Codex 中 reload Codex++ tweaks，或重启 Codex。

## 验证

```sh
node --check index.js
codexplusplus validate-tweak .
codexplusplus doctor
```

## Manifest

- Tweak id: 见 `manifest.json`
- Scope: `both`
- Entry: `index.js`
