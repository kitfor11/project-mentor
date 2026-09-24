# project-mentor —— 项目导师 skill

让 AI 从「任务执行器」变成「项目导师」：做项目时边做边讲，并把关键操作交给你亲手完成。

## 它解决什么问题

AI 做项目通常是「给定任务直接完成、中间过程略过」，这对需要学习完整项目流程的初学者不友好。
本 skill 让智能体在完成项目的过程中：

1. 对每个重要节点适当讲解（为什么 → 是什么 → 怎么做 → 坑）
2. 把部分重要操作/代码交给你亲手做（带骨架提示、停下等待、事后审阅）

## 安装
方式一：一行命令（推荐，跨 runtime）
打开你正在用的 agent（Claude Code、Codex、Cursor、OpenClaw、Hermes、CodeBuddy、Workbuddy、Gemini CLI、OpenCode 等），告诉它：

帮我安装这个 skill：`https://github.com/kitfor11/project-mentor`

方式二：把 `project-mentor/` 目录复制到：

- 用户级（所有项目可用）：`~/.claude/skills/project-mentor/`
- 项目级（仅当前项目）：`<project>/.claude/skills/project-mentor/`

## 使用

- 用 `/project-mentor` 显式开启，或在对话里说「边做边教」「给我留点代码自己写」等。
- 两种场景自动识别：
  - **已有项目** → 按 `references/scan-project.md` 边读边讲，带你读懂项目。
  - **从零构建** → 从结构到实现逐步讲解。
- 教学强度三档（初级 / 中级 / 高级），对话里说「用初级强度教我」，或编辑 `references/config.md` 设默认。
- 随时可用「这个你来做 / 全部你自己做」退出或调节教学模式。

## 重要点怎么定义

- **内置关键字段**：`references/important-points.md`（项目结构、数据模型、接口、认证授权、状态管理、错误处理、测试、核心业务逻辑等）。
- **用户自定义技术栈**：`references/user-tech-stack.md`，命中后优先讲解 + 优先交办。

## 目录结构

```
project-mentor/
├── SKILL.md                    # 核心指令：导师身份、强度档位、工作流、讲解/交办规范
└── references/
    ├── important-points.md     # 内置关键字段目录，可扩充
    ├── user-tech-stack.md      # 用户自定义技术栈，可编辑
    ├── config.md               # 教学强度默认档
    └── scan-project.md         # 场景 A（已有项目）扫描讲解清单
```

## 自定义

- 扩充内置重要点：编辑 `references/important-points.md`
- 设默认教学强度：编辑 `references/config.md`
- 填自己的学习目标：编辑 `references/user-tech-stack.md`
