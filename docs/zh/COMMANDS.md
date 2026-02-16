# 📚 OpenClaw 命令参考

## 🖥️ Gateway 管理

| 命令 | 说明 |
|------|------|
| `openclaw gateway status` | 查看状态 |
| `openclaw gateway start` | 启动 |
| `openclaw gateway stop` | 停止 |
| `openclaw gateway restart` | 重启 |

## 🤖 助手交互

| 命令 | 说明 | 示例 |
|------|------|------|
| `agent --message` | 发送消息 | `openclaw agent --message "你好"` |
| `--thinking` | 思考深度 | `--thinking high` |
| `--model` | 指定模型 | `--model anthropic/claude-opus-4` |
| `--file` | 附带文件 | `--file code.py` |

## 💬 消息发送

```bash
# 发送给个人
openclaw message send --to +8613800138000 --message "测试"

# 广播
openclaw message broadcast --message "公告" --channels telegram,discord
```

## 🛠️ 配置管理

```bash
openclaw config get models.default
openclaw config set models.anthropic.apiKey "sk-..."
```

## 🔧 系统维护

| 命令 | 说明 |
|------|------|
| `openclaw doctor` | 诊断问题 |
| `openclaw update` | 更新版本 |
| `openclaw status` | 系统状态 |
