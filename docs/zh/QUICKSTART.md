# 🚀 快速入门指南

5 分钟上手 OpenClaw 中文版

---

## 第 1 步：安装

**系统要求**: Node.js ≥ 22

```bash
npm install -g openclaw@latest
```

---

## 第 2 步：初始化

```bash
openclaw onboard --install-daemon
```

---

## 第 3 步：验证

```bash
openclaw status
openclaw agent --message "你好，OpenClaw！"
```

---

## 第 4 步：配置模型

```bash
# Anthropic（推荐）
openclaw config set models.anthropic.apiKey "sk-..."
```

---

## 🎉 完成！

```bash
# 开始对话
openclaw agent --message "帮我写一段 Python 代码"
```

---

## ❓ 遇到问题？

```bash
openclaw doctor
```
