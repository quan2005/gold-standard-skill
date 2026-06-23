# 得到金线 — 知识服务内容品控 Skill

将得到（罗振宇团队）的内容品控方法论「金线 9 条」封装为可复用的 AI 审稿能力。

## 它能做什么

当你把课程讲稿、专栏文章、知识付费内容等交给 Claude 审阅时，本技能会按照得到金线标准进行品控，输出结构化的审稿意见：

- 判断知识服务是否成立（内容能否促成认知改变）
- 检查核心逻辑线是否对称（问题 → 旧答案 → 新答案）
- 识别进场感、注意力管理、理解障碍等问题
- 严守边界：只诊断不代写，不干涉风格，尊重作者的场景判断

## 快速开始

本仓库本身就是一个 Claude Skill。把 `skills/gold-standard/` 目录放进 Claude Code 的技能目录即可启用：

```bash
git clone https://github.com/quan2005/gold-standard-skill.git
mkdir -p ~/.claude/skills
cp -r gold-standard-skill/skills/gold-standard ~/.claude/skills/
```

重新打开 Claude Code，技能自动加载。然后在对话里说一句「帮我看看这篇稿子怎么样」并贴上讲稿，它就会按金线 9 条给出品控意见。（Windows 用户把目标路径换成 `%USERPROFILE%\.claude\skills`。）

> 采用标准 SKILL.md 规范，同样兼容 Codex、Copilot CLI、Gemini CLI 等平台——把 `skills/gold-standard/` 放进对应平台的技能目录即可。

## 触发方式

以下场景会自动激活本技能：

- 明确要求审稿、品控、把关、评估内容质量
- 提到"金线""得到金线""得到标准"
- 说"帮我看看这篇稿子怎么样""这篇内容行不行""帮我把把关"

## 不适用场景

- 从零代写整篇稿件
- 纯文学作品的文笔润色
- 语法纠错
- 代码审查

## 项目结构

```
skills/
└── gold-standard/
    ├── SKILL.md              # 技能主文件（金线 9 条 + 工作流程）
    └── references/
        └── cases.md          # 校准案例库（5 个真实品控案例）
```

## 声明

本技能所有内容均基于公开资料（公开演讲、已发布文章、公开课程等）反推整理而成，不包含任何内部保密信息。若有侵权，请联系删除。
