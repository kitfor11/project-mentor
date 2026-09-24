# project-mentor —— 项目导师 skill

一个让 AI 从「任务执行器」变成「项目导师」的 Claude Code skill。

## 解决什么问题

AI 做项目时通常是"给定任务直接完成、中间过程略过"，这对需要学习完整项目流程的初学者不友好。
本 skill 让智能体在完成项目的过程中：

1. **对每个重要节点适当讲解**（为什么 → 是什么 → 怎么做 → 坑）
2. **把部分重要操作/代码交给用户亲手做**（带骨架提示、停下等待、事后审阅）

「重要操作」由两部分定义：
- **内置关键字段**（`references/important-points.md`）：项目结构、数据模型、接口设计、认证授权、状态管理、错误处理、测试、核心业务逻辑等通用类别。
- **用户自定义技术栈**（`references/user-tech-stack.md`）：用户填写自己想重点学习的技术，命中后优先讲解 + 优先交办。

此外支持：

- **教学强度三档**（初级 / 中级 / 高级）：调节讲解深度与交办频率，可对话切换或在 `references/config.md` 设默认。
- **两种场景**：工作目录已有项目 → 边读边讲帮你读懂；从零构建 → 从结构到实现逐步讲解。

## 目录结构

```
project-mentor/
├── SKILL.md                        # 核心指令：导师身份、工作流、讲解/交办规范
└── references/
    ├── important-points.md         # 内置关键字段（重要点目录），可扩充
    ├── user-tech-stack.md          # 用户自定义技术栈（用户编辑）
    ├── config.md                   # 教学配置（默认教学强度档位）
    └── scan-project.md             # 已有项目扫描讲解清单（场景 A）
```

## 安装

把 `project-mentor/` 目录复制到用户级或项目级 skills 目录：

- 用户级（所有项目可用）：`~/.claude/skills/project-mentor/`
- 项目级（仅当前项目）：`<project>/.claude/skills/project-mentor/`

## 使用

- 用 `/project-mentor` 显式开启，或在对话里说「边做边教」「给我留点代码自己写」等。
- 编辑 `references/user-tech-stack.md` 填写你想重点学的技术，或在对话里直接告诉智能体。
- 用「初级/中级/高级强度」切换教学强度（或编辑 `references/config.md` 设默认档）。
- 支持两种场景：**已有项目**（带你边读边讲）与**从零构建**（从结构到实现逐步讲解）。
- 随时可用「这个你来做 / 全部你自己做」退出或调节教学模式。

## 自定义

- **扩充内置重要点**：编辑 `references/important-points.md`，增补子项或新增类别。
- **调讲解深度**：修改 `SKILL.md` 中「讲解规范」的篇幅默认值。
