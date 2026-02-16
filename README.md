# 🦞 OpenClaw — 个人 AI 助手

<p align="center">
    <picture>
        <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/openclaw/openclaw/main/docs/assets/openclaw-logo-text-dark.png">
        <img src="https://raw.githubusercontent.com/openclaw/openclaw/main/docs/assets/openclaw-logo-text.png" alt="OpenClaw" width="500">
    </picture>
</p>

<p align="center">
  <strong>剥离繁琐，让 AI 为你所用！</strong>
</p>

<p align="center">
  <a href="https://github.com/openclaw/openclaw/actions/workflows/ci.yml?branch=main"><img src="https://img.shields.io/github/actions/workflow/status/openclaw/openclaw/ci.yml?branch=main&style=for-the-badge" alt="CI 状态"></a>
  <a href="https://github.com/openclaw/openclaw/releases"><img src="https://img.shields.io/github/v/release/openclaw/openclaw?include_prereleases&style=for-the-badge" alt="GitHub 版本"></a>
  <a href="https://discord.gg/clawd"><img src="https://img.shields.io/discord/1456350064065904867?label=Discord&logo=discord&logoColor=white&color=5865F2&style=for-the-badge" alt="Discord"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge" alt="MIT 许可证"></a>
</p>

**OpenClaw** 是一个在你自己设备上运行的*个人 AI 助手*。

它可以通过你已经在使用的渠道与你互动（WhatsApp、Telegram、Slack、Discord、Google Chat、Signal、iMessage、Microsoft Teams、WebChat），还支持扩展渠道如 BlueBubbles、Matrix、Zalo 等。它可以在 macOS/iOS/Android 上进行语音对话，还能渲染你可以控制的实时画布。Gateway 只是控制平面 —— 真正的产品是这个助手。

如果你想要一个感觉本地化、快速、始终在线的个人单用户助手，这就是你要找的。

[官网](https://openclaw.ai) · [文档](https://docs.openclaw.ai) · [DeepWiki](https://deepwiki.com/openclaw/openclaw) · [入门指南](https://docs.openclaw.ai/start/getting-started) · [更新指南](https://docs.openclaw.ai/install/updating) · [案例展示](https://docs.openclaw.ai/start/showcase) · [常见问题](https://docs.openclaw.ai/start/faq) · [配置向导](https://docs.openclaw.ai/start/wizard) · [Nix](https://github.com/openclaw/nix-openclaw) · [Docker](https://docs.openclaw.ai/install/docker) · [Discord](https://discord.gg/clawd)

推荐设置：在终端运行引导向导（`openclaw onboard`）。
向导会一步步引导你设置 gateway、工作空间、渠道和技能。CLI 向导是推荐路径，支持 **macOS、Linux 和 Windows（通过 WSL2；强烈推荐）**。
支持 npm、pnpm 或 bun。
新安装？从这里开始：[入门指南](https://docs.openclaw.ai/start/getting-started)

**订阅（OAuth）：**

- **[Anthropic](https://www.anthropic.com/)** (Claude Pro/Max)
- **[OpenAI](https://openai.com/)** (ChatGPT/Codex)

模型说明：虽然支持任何模型，但我强烈推荐 **Anthropic Pro/Max (100/200) + Opus 4.6**，因为长上下文能力更强，对提示注入的防护更好。详见[入门配置](https://docs.openclaw.ai/start/onboarding)。

## 模型（选择 + 认证）

- 模型配置 + CLI：[模型](https://docs.openclaw.ai/concepts/models)
- 认证配置轮换（OAuth vs API 密钥）+ 故障转移：[模型故障转移](https://docs.openclaw.ai/concepts/model-failover)

## 安装（推荐）

运行环境：**Node ≥22**。

```bash
npm install -g openclaw@latest
# 或：pnpm add -g openclaw@latest

openclaw onboard --install-daemon
```

向导会安装 Gateway 守护进程（launchd/systemd 用户服务），使其保持运行。

## 快速开始（简明版）

运行环境：**Node ≥22**。

完整新手指南（认证、配对、渠道）：[入门指南](https://docs.openclaw.ai/start/getting-started)

```bash
openclaw onboard --install-daemon

openclaw gateway --port 18789 --verbose

# 发送消息
openclaw message send --to +1234567890 --message "来自 OpenClaw 的问候"

# 与助手对话（可选地将结果返回到任意已连接渠道：WhatsApp/Telegram/Slack/Discord/Google Chat/Signal/iMessage/BlueBubbles/Microsoft Teams/Matrix/Zalo/Zalo Personal/WebChat）
openclaw agent --message "待办清单" --thinking high
```

升级？查看[更新指南](https://docs.openclaw.ai/install/updating)（并运行 `openclaw doctor`）。

## 开发渠道

- **stable**：标记版本（`vYYYY.M.D` 或 `vYYYY.M.D-<patch>`），npm dist-tag `latest`。
- **beta**：预发布版本（`vYYYY.M.D-beta.N`），npm dist-tag `beta`（macOS 应用可能缺失）。
- **dev**：`main` 分支的当前 HEAD，npm dist-tag `dev`（发布时）。

切换渠道（git + npm）：`openclaw update --channel stable|beta|dev`。
详情：[开发渠道](https://docs.openclaw.ai/install/development-channels)。

## 从源码构建（开发）

从源码构建时推荐使用 `pnpm`。Bun 可选，用于直接运行 TypeScript。

```bash
git clone https://github.com/openclaw/openclaw.git
cd openclaw

pnpm install
pnpm ui:build # 首次运行时自动安装 UI 依赖
pnpm build

pnpm openclaw onboard --install-daemon
```
