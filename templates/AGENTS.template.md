# <WORKSPACE_ROOT> 的 Codex 执行规则

本文件是 `<WORKSPACE_ROOT>` 的 Codex 执行规则文件。Codex 进入本工作区后，必须优先遵守本文件；`codexworkspace-console.md` 是总控索引和说明书。

## 规则来源

- `codexworkspace-console.md`：工作区总控入口，记录工作区定位、目录地图、项目生命周期和长期规则。
- `codex-skills-inventory.md`：当前 Codex 可用 skills 清单，记录目录名、Skill 名称、中文作用简介、来源分组和添加时间。
- `codex-issue-log.md`：记录 Codex 使用过程中的错误、不满意点、返工点和踩坑复盘。
- `projects-index.md`：正式项目台账，记录项目编号、名称、类型、状态、路径、使用入口和最后更新时间。
- `automation-index.md`：自动化台账，记录定时自动化、提醒、巡检、报告生成和外部投递任务。
- `governance\playbooks\`：治理执行模板目录，记录任务分型、外部投递、Windows 写入、sandbox 分流、多副本同步和 canonical artifact 检查等 checklist/runbook。
- `governance\reviews-index.md`：治理复盘包索引，记录完整复盘、整改行为和证据材料的归档状态。
- 本文件只记录强执行规则，不复制其他文件全文。

## 工作区边界

- 所有 Codex 工作默认只在 `<WORKSPACE_ROOT>` 内完成。
- 全局 Codex 规则建议：无论以后打开哪个 Codex 项目，都必须先迁移到 `<WORKSPACE_ROOT>` 再继续工作。
- 不得在 `<WORKSPACE_ROOT>` 之外直接创建、编辑、运行或整理项目文件。
- 如任务涉及外部项目，必须先说明外部路径、迁移目的和影响，并获得用户明确同意。
- 外部项目获得同意后，先迁移或复制到 `<WORKSPACE_ROOT>\projects\Project_编号_项目名称`，后续只操作工作区内副本。
- 除非用户明确批准，不维护或修改 `<WORKSPACE_ROOT>` 之外的清单、日志或项目文件。

## 项目命名与放置

- 正式项目统一放在 `projects\` 下。
- 新建项目和迁移外部项目必须遵守 `new-project-sop.md`。
- 新项目目录命名必须遵守 `workspace-architecture-and-naming.md`。
- 命名格式摘要：`Project_三位编号_项目名称`。
- 目录职责、编号分配、中文项目名和归档规则以 `workspace-architecture-and-naming.md` 为准。

## 工作流程

- 修改前先阅读相关项目结构、配置文件、说明文件和当前任务上下文。
- 优先使用项目已有脚本、工具链和代码风格。
- 不擅自修改与当前任务无关的文件。
- 不擅自删除、移动、重命名用户已有内容。
- 不做无关重构，不引入与任务无关的新抽象或依赖。
- 完成修改后，根据任务风险运行必要验证；若无法验证，需要在回复中说明原因。
- 对用户展示结果时，说明关键改动、验证结果和未完成风险。

## 自动化与外部投递

- 创建定时自动化、提醒、巡检、报告发送或外部通知前，必须确认任务目标、读取范围、运行时间、接收方和失败处理方式。
- 推荐定期整理 `codex-issue-log.md`：识别相似错误、复发模式、已有规则覆盖情况和防复发待办，并生成报告供用户审查；定时复盘必须先读取 issue log 顶部“已归档重复问题索引”和 `governance\reviews-index.md`。
- 自动化读取本地文件并发送到飞书、邮件、GitHub、Slack、网页或其他外部系统前，必须说明外部披露风险并获得用户明确批准。
- 外部通道不能只看本地配置或 masked secret，必须先用最小内容做真实发送或真实调用验证。
- API 返回成功不等于用户可读；长报告必须验证目标客户端展示效果。
- 聊天工具中完整报告优先使用“短摘要 + 附件”模式，不要把长报告塞进单条消息。
- 自动化不应默认修改治理文件；除非用户明确授权，否则只输出报告、建议或待办。
- 如果工作区维护 `automation-index.md`，创建、更新、暂停、恢复或删除自动化后，必须同步更新自动化台账。
- 当自动化发现重复复盘、长期未关闭整改或需要证据留存的问题时，应建议创建或更新 `governance\reviews\` 下的复盘包，而不是把长报告塞进 `codex-issue-log.md`。

## 治理档案馆

- `codex-issue-log.md` 只记录短复盘、入口索引、复发标注和指向复盘包的链接；旧日期章节是原始发生记录，不承担完整长复盘职责。
- `governance\playbooks\` 保存可重复执行的 checklist 和 runbook；具体操作模板放这里，不把细节回填到 `AGENTS.md`。
- 重复问题、重要返工、跨项目规则变化、自动化整改和需要证据留存的问题，应升级为 `governance\reviews\YYYY\YYYY-MM-DD_slug\` 复盘包。
- 复盘包固定包含 `review.md`、`actions.md` 和 `evidence\`。
- 创建或更新复盘包后，必须同步更新 `governance\reviews-index.md`；如果问题簇只是候选，也可先在 reviews-index 和 issue log 顶部索引登记为 `候选`。
- 复盘包不得记录密钥、token、App Secret、完整飞书群 ID、GitHub 个人访问令牌或其他完整凭据。

## 执行模板入口

- 任务分型预检和收尾检查：`governance\playbooks\task-intake-and-closeout-checklist.md`
- 外部投递前检查：`governance\playbooks\external-delivery-checklist.md`
- Windows 安全写入：`governance\playbooks\windows-safe-editing.md`
- sandbox 与提权分流：`governance\playbooks\sandbox-and-escalation-decision-tree.md`
- 多副本同步矩阵：`governance\playbooks\multi-surface-sync-matrix.md`
- canonical artifact 检查：`governance\playbooks\canonical-artifact-check.md`
- 本文件只保留强规则和治理触发器；执行细节优先查对应 playbook。


## 最终回复前检查

- 最终回复前必须回看本轮是否触发了工作区治理动作：新建/迁移/归档项目，安装/删除/重命名/调整 skill，修改工作区规则，或出现错误/返工/遗漏。
- 如果触发 skill 变更，必须确认 `codex-skills-inventory.md` 已同步更新；如果未更新，不得先发送完成回复。
- 如果触发规则变更，必须确认 `codexworkspace-console.md` 已同步更新最后更新时间或相关索引说明。
- 如果触发自动化变更，必须确认 `automation-index.md` 已同步更新；如果未更新，不得先发送完成回复。
- 如果创建或更新治理复盘包，必须确认 `governance\reviews-index.md` 已同步更新。
- 如果出现错误、不满意结果、返工、规则理解偏差或遗漏清单维护，必须确认 `codex-issue-log.md` 已记录处理完成后的复盘。
- 最终回复中要明确说明这些治理文件是否已更新，不能只说明业务文件或安装动作完成。
## 文档维护

- 用户改变工作区规则、命名规则、目录结构或长期工作方式时，必须同步更新 `codexworkspace-console.md`，并更新其中的 `最后更新时间`。
- 出现错误、不满意结果、返工、踩坑或规则理解偏差，并且处理完成后，必须更新 `codex-issue-log.md`。
- 自动化或外部投递出现链路失败、权限问题、披露风险拦截或客户端展示异常时，处理完成后必须更新 `codex-issue-log.md`。
- 创建、更新、暂停、恢复或删除自动化时，如工作区存在 `automation-index.md`，必须同步更新该台账。
- 创建或更新治理复盘包时，必须同步更新 `governance\reviews-index.md`；如果新增了长期治理目录或规则，也要更新 `codexworkspace-console.md` 和 `workspace-architecture-and-naming.md`。
- 新建或迁移项目时，如项目管理规则发生变化，需要同步更新控制台或对应 SOP 文件。
- 新建、迁移、暂停、恢复或归档正式项目时，必须更新 `projects-index.md`。
- 文档更新应保持简洁，优先沉淀可复用规则和复盘，不记录无意义流水账。

## Skills 清单维护

- 每次添加、安装、删除、重命名或调整 Codex skill 后，必须更新 `codex-skills-inventory.md`。
- skills 清单按相同来源分组。
- GitHub 安装来源保留仓库 URL。
- 本地、自带和插件来源使用简短来源标签，不写冗长缓存路径。
- `作用简洁` 必须使用中文概括，不直接复制英文 frontmatter。
- 新增 skill 的 `添加时间` 使用实际添加日期。
- 如果用户补充 skill 的真实来源，应按真实来源重新分组；本地目录只代表安装位置，不等于来源。

## Codex Skills 全局配置变更

- 安装、删除、重命名、调整或个性化修改 Codex skill，属于全局 Codex 配置变更。
- 执行前必须说明 skill 来源、目标安装路径、是否位于 `<WORKSPACE_ROOT>` 之外、影响范围，以及是否需要重启 Codex 生效。
- 如果操作路径在 `<WORKSPACE_ROOT>` 之外，必须先获得用户明确同意。
- 执行后必须同步更新 `codex-skills-inventory.md`，记录目录名、Skill 名称、中文作用、真实来源、添加或调整时间和备注。
- 如果安装、删除或修改过程中出现返工、不满意、规则理解偏差或遗漏清单维护，处理完成后必须更新 `codex-issue-log.md`。
- 除非用户明确要求，不得把工作区外的 skill 目录当作项目目录进行整理、迁移或批量修改。

## 安全规则

- 不执行破坏性操作，除非用户明确要求并确认影响。
- 不使用 `git reset --hard`、强制删除、批量移动等高风险操作，除非用户明确要求。
- 发现用户已有改动时，不要回退；必须在现有状态上继续工作。
- 需要访问或修改工作区外路径时，先说明原因并等待用户同意。
- 若规则冲突，优先遵守用户最新明确要求和工作区边界。