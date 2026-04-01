# PRD Skill for Claude Code

需求文档生成技能。通过 brainstorming 对话澄清需求，由 Writer + Reviewer 双 agent 对抗生成符合公司标准的 PRD。

## 功能

- **自动触发**：当 agent 检测到需求信息不完整、存在歧义时自动建议进入 PRD 流程
- **手动触发**：输入 `/prd`
- **Brainstorming 澄清**：一次一个问题，围绕 CREA 框架逐步澄清需求，7 项清晰度标准全过才进入下一步
- **双 Agent 对抗**：Writer 写 PRD，Reviewer 从开发+测试视角审查，对抗直到 9 项通过条件全满足
- **Reviewer 进化**：用户每次审核反馈中的通用经验会追加到审查规则，Reviewer 越用越强
- **公司模板**：严格遵循 CREA 框架（Cause/Result/Effect/Action）+ 产出结果 + 用户故事 + 埋点规范 + 验收清单

## 安装

```bash
npx skills add wmr1027/prd -g -y
```

或手动复制 `prd/SKILL.md` 到 `~/.claude/skills/prd/SKILL.md`。

## PRD 模板结构

```
需求文档
├── 元信息表（产品、时间、人员等）
├── 需求简介
│   ├── Cause: 需求背景
│   ├── Result: 关键结果
│   ├── 产出结果（用户在哪里、做什么、看到什么）
│   ├── Effect: 业务影响
│   └── Action: 关键任务
├── 产品需求
│   ├── 需求描述（Testable/Economy/可读性）
│   ├── 用户故事（表格+场景叙事，验证流程可走通）
│   ├── 埋点需求
│   └── 主流程验收清单
└── 上线方案
```

## 使用流程

```
用户提出需求 → agent 建议进入 PRD 流程
    ↓
选择完整模式/精简模式
    ↓
阶段一：Brainstorming 澄清（清晰度 7 项全过）
    ↓
阶段二：Writer + Reviewer 对抗生成 PRD
    ↓
阶段三：用户审核确认 → 存入 docs/prd/
```

## License

MIT
