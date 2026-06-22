# Governance Archive

最后更新时间：YYYY-MM-DD

`governance\` 是 `<WORKSPACE_ROOT>` 的治理档案馆，用于保存较完整的复盘包、整改记录和证据材料。

## 职责边界

- `codex-issue-log.md`：记录短复盘、问题索引和指向复盘包的链接。
- `governance\reviews-index.md`：记录所有治理复盘包的总览、状态和最后验证时间。
- `governance\reviews\`：按年份保存完整复盘包。
- `evidence\`：保存截图、报告、命令输出、附件等证据材料，不把大段证据塞进正文。

## 何时进入治理档案馆

- 同类问题重复出现，需要合并复盘。
- 一次返工影响多个规则、自动化或模板。
- 需要长期追踪整改行为、验证状态或证据。
- 涉及跨项目、跨工作区或全局 Codex 规则调整。
- 自动化报告发现某个问题需要长期观察或归档。

普通小错误仍可只写入 `codex-issue-log.md`，不必创建复盘包。

## 复盘包结构

```text
governance\reviews\YYYY\YYYY-MM-DD_slug\
├── review.md
├── actions.md
└── evidence\
```

## 命名规则

- 年份目录：`YYYY`。
- 复盘包目录：`YYYY-MM-DD_slug`。
- `slug` 使用小写英文、数字和短横线，表达问题主题。
- 不在路径中写入密钥、账号、飞书群 ID、客户名或其他敏感信息。
