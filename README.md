# CodexWorkspace Methodology

最后更新时间：2026-06-10

CodexWorkspace Methodology 是一套面向 Codex/AI coding agent 的本地工作区管理方法论。它把分散在对话里的规则、项目迁移流程、命名规范、skills 清单、项目台账和问题复盘沉淀成一组可长期维护的 Markdown 文件。

这套方法适合希望把 AI 辅助开发从“临时对话”变成“可复利工作系统”的用户。

## 为什么需要它

使用 AI coding agent 时，很多问题不是代码能力问题，而是工作区管理问题：

- 项目散落在不同目录，路径和上下文经常混乱。
- 今天约定的规则，换个项目或新会话就丢失。
- 迁移项目、创建项目、归档项目没有统一流程。
- agent 犯过的错没有沉淀，下次还会再犯。
- skills、项目状态、常用入口靠记忆维护。

CodexWorkspace Methodology 用一组简单 Markdown 文件解决这些问题。

## 核心思想

- 只有一个工作根目录，所有项目都先进入这个工作区再处理。
- 强执行规则、总控入口、命名细则、项目 SOP、项目台账、问题复盘、skills 清单分文件维护。
- 每个文件只负责一个领域，避免规则在多个地方重复。
- 新建、迁移、归档项目都有固定流程。
- Codex 出错、不满意、返工或踩坑后，必须把经验写回日志。

## 推荐文件结构

```text
CodexWorkspace
├── AGENTS.md
├── codexworkspace-console.md
├── workspace-architecture-and-naming.md
├── new-project-sop.md
├── projects-index.md
├── codex-issue-log.md
├── codex-skills-inventory.md
├── projects/
├── shared/
├── archives/
└── temp/
```

## 文件职责

| 文件 | 职责 |
|---|---|
| `AGENTS.md` | Codex 强执行规则 |
| `codexworkspace-console.md` | 工作区总控入口 |
| `workspace-architecture-and-naming.md` | 目录架构与项目命名细则 |
| `new-project-sop.md` | 新建项目与迁移外部项目流程 |
| `projects-index.md` | 正式项目台账 |
| `codex-issue-log.md` | 错误、不满意点、返工和踩坑复盘 |
| `codex-skills-inventory.md` | Codex skills 清单 |

## 文档导览

- [方法论概览](docs/01-methodology.md)
- [文件系统设计](docs/02-file-system.md)
- [Codex 执行规则](docs/03-agent-rules.md)
- [项目生命周期](docs/04-project-lifecycle.md)
- [维护机制](docs/05-maintenance.md)
- [GitHub 发布清单](docs/publishing-checklist.md)

## 示例

- [最小工作区示例](examples/minimal-workspace/)

## 模板

`templates/` 目录提供可复制的 Markdown 模板：

- `AGENTS.template.md`
- `codexworkspace-console.template.md`
- `workspace-architecture-and-naming.template.md`
- `new-project-sop.template.md`
- `projects-index.template.md`
- `codex-issue-log.template.md`
- `codex-skills-inventory.template.md`

## 快速开始

1. 选择一个固定工作区目录，例如 `D:\CodexWorkspace`。
2. 将 `templates/` 中的文件复制到工作区根目录。
3. 按你的实际路径和命名规则调整模板。
4. 在全局 Codex 规则中要求所有外部项目先迁移到该工作区。
5. 新建或迁移项目时，按 `new-project-sop.md` 执行。
6. 每次项目状态变化、skills 变化或问题复盘后，更新对应文档。

## 适配方式

你可以按自己的工作习惯调整：

- 工作区根目录名称。
- 项目命名格式。
- 项目类型枚举。
- README 模板字段。
- skills 来源分组方式。
- 问题复盘字段。

## 适用场景

- 多个 Codex 项目需要统一管理。
- 经常在不同项目之间切换，需要避免路径混乱。
- 希望把 AI coding agent 的错误和经验持续复利。
- 希望将本地工作区规则沉淀成可复用、可发布的方法论。

## 贡献

欢迎贡献新的模板、真实使用案例、工作区规则、复盘模式和文档改进。请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。

## License

MIT License. See [LICENSE](LICENSE).
