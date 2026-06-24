# Windows Safe Editing

最后更新时间：YYYY-MM-DD

本清单用于减少 Windows、PowerShell、编码和 shim 相关返工。

## 默认编辑策略

- 文本修改优先使用 `apply_patch`。
- 必须使用 PowerShell 写长文本时，优先 here-string，不要把复杂中文、反引号、Windows 路径和 Markdown 代码块塞进单行替换。
- 可执行文件、校验敏感文件和中文 Markdown 默认写成 UTF-8 no BOM。
- CLI 启动优先 `.cmd` 或 `.exe`，不要默认走 `ps1` shim。

## 高风险文件类型

以下文件写回后必须立刻校验：

- `.js`、`.mjs`、shell 脚本
- `SKILL.md`
- JSON、frontmatter 文件
- 中文 Markdown

最少校验动作：

- `node --check`
- `python -X utf8` 或等价 UTF-8 校验
- 搜索字面量 `` `n``、`` `r``、NUL、异常 BOM 或首行损坏

## PowerShell 约束

- 不要用 `Set-Content -Encoding UTF8` 写需要 no BOM 的文件。
- 处理含 Markdown 反引号的文本时，优先单引号 here-string 或占位符替换。
- Windows PowerShell 下不要默认使用 `&&`。
- `-replace` 只适合 pattern + replacement 两段式；固定文本优先 `.Replace()` 或更窄的锚点替换。

## 写后复核

- 检查文件头是否异常。
- 检查 diff 是否只包含预期改动。
- 检查关键词、标题、frontmatter、JSON 解析和脚本入口是否正常。
- 若是公开文档或 README，额外检查是否误删归因、链接或示例引用。