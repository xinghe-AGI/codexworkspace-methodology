# New Project SOP

最后更新时间：YYYY-MM-DD

维护范围：新建项目、迁移外部项目、初始化项目说明和项目登记流程。

## 01 文件职责

本文件是 `<WORKSPACE_ROOT>` 的新项目与外部项目迁移流程 SOP。

- 本文件负责规定“怎么做”。
- 目录职责、编号分配、中文项目名和归档规则以 [workspace-architecture-and-naming.md](workspace-architecture-and-naming.md) 为准。
- Codex 执行边界和安全规则以 [AGENTS.md](AGENTS.md) 为准。
- 工作区总览以 [codexworkspace-console.md](codexworkspace-console.md) 为准。

## 02 新建项目 SOP

新建正式项目时按以下步骤执行：

1. 确认项目意图
   - 明确项目用途、目标用户、技术方向和预期产物。
   - 判断它是正式项目还是临时实验。
   - 临时实验放入 `temp\`，不分配正式项目编号。

2. 分配项目编号
   - 按 [workspace-architecture-and-naming.md](workspace-architecture-and-naming.md) 的编号规则执行。
   - 新项目编号使用 `projects\` 下现有最大编号 + 1。
   - 如果没有正式项目，从 `001` 开始。

3. 创建项目目录
   - 默认路径格式：`<WORKSPACE_ROOT>\projects\Project_三位编号_项目名称`。
   - 项目名称应清晰表达用途。
   - 不直接在根目录创建正式项目。

4. 初始化项目内容
   - 按用户要求和项目类型初始化代码、文档或配置。
   - 优先使用项目适合的标准工具链。
   - 不引入与项目目标无关的依赖或复杂结构。

5. 初始化项目 README
   - 正式项目应包含项目级 `README.md`。
   - 如果项目已有 README，不要覆盖；应在理解原内容后补充缺失信息。
   - README 内容必须按项目实际类型设计，不强制套用代码项目字段。

6. 完成基础验证
   - 根据项目类型确认关键使用方式可用，例如运行、打开、检索、阅读或维护流程。
   - 如果无法验证，记录原因和后续动作。

## 03 外部项目迁移 SOP

外部项目必须先迁移到 `<WORKSPACE_ROOT>` 后再继续工作。

迁移步骤：

1. 确认外部项目路径
   - 明确外部项目当前所在位置。
   - 说明为什么需要读取或复制该路径。

2. 获得用户明确同意
   - 在用户同意前，不复制、不移动、不修改外部项目。
   - 如果只需要查看外部路径，也应先说明目的。

3. 分配迁移目标编号
   - 按 [workspace-architecture-and-naming.md](workspace-architecture-and-naming.md) 的编号规则分配新编号。
   - 迁移后的目录名必须符合 `Project_三位编号_项目名称`。

4. 复制到工作区
   - 迁移目标路径：`<WORKSPACE_ROOT>\projects\Project_三位编号_项目名称`。
   - 默认复制外部项目，不直接移动原项目。
   - 迁移完成后，只操作工作区内副本。

5. 迁移后检查
   - 先判断项目类型，再检查对应的关键入口、资料结构、依赖配置、运行脚本或 README。
   - 如有必要，按项目实际用途补充项目级 README，不强制补充运行说明。
   - 不回写外部原项目，除非用户明确要求并批准。

## 04 项目 README 初始化模板

正式项目应根据项目类型设计 README。以下是通用模板，字段可以按实际项目增删。

````markdown
# 项目名称

最后更新时间：YYYY-MM-DD

## 项目定位

说明这个项目解决什么问题、面向谁、主要产物是什么。

## 项目类型

例如：代码项目、知识库项目、文档项目、研究项目、自动化项目、素材项目。

## 内容结构

说明主要目录、核心文件、资料分类或内容组织方式。

## 使用方式

说明这个项目应该如何被使用、阅读、运行、检索、维护或交付。

## 关键信息

- 入口文件或入口目录：
- 重要资料：
- 维护方式：

## 可选：代码项目信息

如果这是代码项目，再补充：

- 技术栈：
- 安装命令：
- 运行命令：
- 测试命令：
- 配置文件：

## 可选：知识库/文档项目信息

如果这是知识库或文档项目，再补充：

- 主题范围：
- 分类方式：
- 更新频率：
- 检索方式：

## 注意事项

记录环境变量、账号、外部服务、资料来源、已知限制、维护坑点或协作注意事项。
````

## 05 项目完成后检查

新建或迁移项目完成后，检查以下事项：

- 项目是否位于 `<WORKSPACE_ROOT>\projects\Project_三位编号_项目名称`。
- 项目命名是否符合 [workspace-architecture-and-naming.md](workspace-architecture-and-naming.md)。
- 是否有项目级 `README.md`。
- README 是否符合项目实际类型，而不是机械套用代码项目模板。
- 是否已经验证关键使用方式，或说明无法验证的原因。
- 是否产生错误、返工、不满意点或踩坑；如有，更新 [codex-issue-log.md](codex-issue-log.md)。
- 是否改变了工作区规则；如有，更新 [codexworkspace-console.md](codexworkspace-console.md) 和对应规则文件。

## 06 何时更新其他文档

按以下规则同步文档：

- 工作区规则、目录结构、命名规则变化：更新 [codexworkspace-console.md](codexworkspace-console.md) 和 [workspace-architecture-and-naming.md](workspace-architecture-and-naming.md)。
- 新建或迁移项目流程变化：更新本文件。
- 出现错误、不满意、返工或踩坑并处理完成：更新 [codex-issue-log.md](codex-issue-log.md)。
- 新增、安装、删除或调整 Codex skill：更新 [codex-skills-inventory.md](codex-skills-inventory.md)。
- 新建、迁移、暂停、恢复、归档项目时，必须更新 [projects-index.md](projects-index.md)，登记项目编号、名称、类型、状态、路径、使用方式和最后更新时间。
