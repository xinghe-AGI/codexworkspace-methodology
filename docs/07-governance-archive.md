# 治理档案馆

`governance\` 用于保存完整复盘包、整改记录和证据材料。它不是项目目录，也不是临时目录，而是工作区级治理资产。

## 与 codex-issue-log 的关系

- `codex-issue-log.md` 保留短记录、问题索引和复盘包链接。
- 完整长复盘、整改行为和证据材料进入 `governance\reviews\...`。
- 普通小错误不必创建复盘包，仍可只写短 issue log。

## 推荐结构

```text
<WORKSPACE_ROOT>
└── governance\
    ├── README.md
    ├── reviews-index.md
    └── reviews\
        └── YYYY\
            └── YYYY-MM-DD_slug\
                ├── review.md
                ├── actions.md
                └── evidence\
```

## 适合归档的场景

- 同类问题重复出现，需要合并复盘。
- 一次返工影响多个规则、自动化或模板。
- 需要长期追踪整改行为、验证状态或证据。
- 涉及跨项目、跨工作区或全局 Codex 规则调整。
- 自动化报告发现某个问题需要长期观察或归档。

## 维护规则

- 创建或更新复盘包后，同步更新 `governance\reviews-index.md`。
- 如果复盘包来自某条 issue log，应在 `codex-issue-log.md` 中保留复盘包链接。
- 证据材料放入 `evidence\`，正文只保留摘要和引用。
- 不在复盘包中记录密钥、token、App Secret、完整飞书群 ID 或 GitHub 个人访问令牌。
