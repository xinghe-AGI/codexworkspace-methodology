# CodexWorkspace Methodology

CodexWorkspace Methodology 是一套面向 Codex/AI coding agent 的本地工作区管理方法论。它用一组 Markdown 模板，把项目迁移、目录命名、执行规则、SOP、skills 清单、项目台账和问题复盘放进同一个可维护的工作区。

它适合想把 AI 辅助开发从临时对话变成长期工作系统的人。

## 解决什么问题

- 项目散落在不同目录，路径和上下文容易混乱。
- 外部项目迁移进来时，没有统一放置和命名方式。
- 新建、迁移、归档项目靠临时约定。
- Codex 出错、返工或踩坑后，没有沉淀为下次可复用的规则。
- skills、项目状态和入口信息靠记忆维护。

## 核心思路

- 只保留一个工作区根目录：`<WORKSPACE_ROOT>`。
- 所有正式项目进入 `projects/` 后再处理。
- 正式项目使用统一命名：`Project_三位编号_项目名称`。
- 强执行规则、控制台、命名细则、SOP、项目台账、问题日志和 skills 清单分文件维护。
- 高频变化的信息进入专门台账，不塞进总控文件。

## 推荐工作区结构

```text
<WORKSPACE_ROOT>
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

## 模板

`templates/` 是本项目唯一的可复制源。

| 模板 | 用途 |
|---|---|
| `AGENTS.template.md` | Codex 强执行规则 |
| `codexworkspace-console.template.md` | 工作区总控入口 |
| `workspace-architecture-and-naming.template.md` | 目录架构与项目命名细则 |
| `new-project-sop.template.md` | 新建项目与迁移外部项目流程 |
| `projects-index.template.md` | 正式项目台账 |
| `codex-issue-log.template.md` | 错误、不满意点、返工和踩坑复盘 |
| `codex-skills-inventory.template.md` | Codex skills 清单 |

模板中的 `<WORKSPACE_ROOT>`、`YYYY-MM-DD`、示例项目名和示例编号都需要按自己的工作区替换。

## 文档导览

- [方法论概览](docs/01-methodology.md)
- [文件系统设计](docs/02-file-system.md)
- [Codex 执行规则](docs/03-agent-rules.md)
- [项目生命周期](docs/04-project-lifecycle.md)
- [维护机制](docs/05-maintenance.md)

## 快速开始

1. 选择一个固定工作区目录，用它替换模板里的 `<WORKSPACE_ROOT>`。
2. 将 `templates/` 中的模板复制到工作区根目录，并去掉 `.template` 后缀。
3. 按自己的命名规则、项目类型和 skills 来源调整模板内容。
4. 在全局 Codex 规则中要求外部项目先迁移到该工作区。
5. 新建或迁移项目时，按 `new-project-sop.md` 执行。
6. 项目状态变化、skills 变化或问题复盘后，更新对应文档。

## 适配方式

你可以按自己的工作习惯调整：

- 工作区根目录。
- 项目命名格式。
- 项目类型枚举。
- README 字段。
- skills 来源分组方式。
- 问题复盘字段。

## 贡献

欢迎贡献更清晰的模板、真实使用案例、工作区规则和文档改进。请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。

## License

MIT License. See [LICENSE](LICENSE).
