# Task Intake And Closeout Checklist

最后更新时间：YYYY-MM-DD

本清单用于把“先分型再动手、先收尾再回复”变成默认动作。

## 开工前

先用 1 行判断本轮任务类型：

```text
工作区内/外 + 是否全局 skill + 是否外部投递 + 是否多副本同步 + 是否编码敏感
```

逐项确认：

- 工作区边界：是否只在 `<WORKSPACE_ROOT>` 内操作；如涉及工作区外路径，是否已说明来源、影响和范围。
- 全局 skill：是否触发安装、删除、重命名、同步或个性化修改；如是，先写来源、目标路径、影响范围和是否需要重启。
- 外部投递：是否要把本地内容发到飞书、邮件、GitHub、网页或其他外部系统；如是，先走 [external-delivery-checklist.md](external-delivery-checklist.md)。
- 多副本同步：是否同时涉及运行副本、发布副本、全局副本、README、reference、examples、QA 或治理文件；如是，先走 [multi-surface-sync-matrix.md](multi-surface-sync-matrix.md)。
- 编码敏感：是否要写入 `.js`、`.mjs`、shell、`SKILL.md`、JSON、frontmatter 文件或中文 Markdown；如是，先走 [windows-safe-editing.md](windows-safe-editing.md)。
- canonical artifact：在开始修改前，先确认权威字段、权威文件、对外入口和真正运行中的副本；如不清楚，先走 [canonical-artifact-check.md](canonical-artifact-check.md)。

## 完成前

逐项确认：

- 主动作：用户要的核心改动已经完成，不是只做了一半分析或只改了部分表面。
- 必要校验：按任务风险完成至少一轮有效验证；如果没法验证，要明确说明原因。
- 治理文件：检查是否触发 `codexworkspace-console.md`、`codex-issue-log.md`、`codex-skills-inventory.md`、`automation-index.md`、`projects-index.md`、`governance\reviews-index.md`。
- 外部展示：如果有对外发送或用户可见展示，确认客户端真实可读，不只看 API 成功。
- 最终回复：明确写出哪些治理文件已更新，哪些未触发，不要只说业务文件改完了。

## 常见触发器

- 规则变更：同步更新 `codexworkspace-console.md`。
- 错误、返工、理解偏差：补 `codex-issue-log.md`。
- skill 变更：补 `codex-skills-inventory.md`。
- 自动化变更：补 `automation-index.md`。
- 项目状态变更：补 `projects-index.md`。
- 复盘包创建或更新：补 `governance\reviews-index.md`。