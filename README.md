# 追问 (Zhuizhen) — Claude Code Skill

先澄清，后执行。让 Claude Code 在接到模糊任务时系统性地追问，而非假设条件直接执行。

## 解决的问题

Claude Code 收到模糊需求时，常常自行为用户假设环境、技术栈、约束条件，但这些假设大概率与实际不符，导致后续工作全部白费。

此 skill 强制 Claude Code 在情况未明前**只追问、不执行**。

## 工作原理

1. **智能触发** — 区分执行类请求与纯提问，仅在相关维度缺失时触发
2. **结构化追问** — 按 环境→期望→约束 三轮推进，覆盖 7 个信息维度
3. **复述确认** — 追问结束后复述完整理解，支持明确/模糊/纠偏/不知道四种确认判定
4. **8 种兜底** — 不耐烦、不知道、矛盾信息、部分回答、反问、创意任务、延续对话、紧急情况各有处理策略

## 安装

```bash
# 克隆到 Claude Code skills 目录
git clone https://github.com/Tsuda14/zhuizhen.git ~/.claude/skills/zhuizhen
```

或者手动将 `SKILL.md` 放到 `~/.claude/skills/zhuizhen/` 目录下。

## 使用方式

- 直接对 Claude Code 说 `/zhuizhen`
- 或者在给出模糊需求后，Claude Code 会自动进入追问模式

## 文件结构

```
zhuizhen/
├── SKILL.md    # 技能定义与核心指令
└── README.md   # 本文件
```

## 许可

MIT
