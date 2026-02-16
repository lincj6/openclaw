# 🦞 OpenClaw 中文版 — 个人 AI 助手

**OpenClaw** 是一个在你自己设备上运行的*个人 AI 助手*。

它可以通过你已经在使用的渠道与你互动：
- 💬 **即时通讯**: WhatsApp、Telegram、Slack、Discord、Google Chat、Signal、iMessage、Microsoft Teams
- 🔌 **扩展渠道**: BlueBubbles、Matrix、Zalo、网页聊天
- 🎤 **语音支持**: macOS/iOS/Android 上的语音对话
- 🎨 **实时画布**: 可控制的动态渲染界面

如果你想要一个**本地化、快速、始终在线**的个人单用户助手，这就是你要找的。

---

## 📋 目录

- [安装](#安装)
- [快速开始](#快速开始)
- [模型配置](#模型配置)
- [命令参考](COMMANDS.md)

---

## 🚀 安装

**环境要求**: Node.js ≥ 22

```bash
npm install -g openclaw@latest

# 运行引导向导（推荐）
openclaw onboard --install-daemon
```

---

## ⚡ 快速开始

```bash
# 启动 Gateway
openclaw gateway --port 18789 --verbose

# 发送消息
openclaw message send --to +1234567890 --message "你好！"

# 与助手对话
openclaw agent --message "今天天气怎么样？"
```

---

## 🤖 模型配置

推荐 **Anthropic Claude**：

```bash
# 配置 API Key
openclaw config set models.anthropic.apiKey "你的API密钥"

# 设置默认模型
openclaw models default anthropic/claude-opus-4
```

---

## 📖 更多文档

- [快速入门指南](QUICKSTART.md) - 5分钟上手
- [命令参考手册](COMMANDS.md) - 完整命令列表
- [英文文档](../../README.md) - 官方英文文档
