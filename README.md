# limuxuan-update

李慕玄取色宏的版本发布与安装包分发仓库。

本仓库不存放主程序源码，主要通过 [GitHub Releases](https://github.com/restoflife/limuxuan-update/releases) 发布经过版本标记的 `BnsMacro.exe`，供用户手动下载，也供主程序更新流程使用。

## 下载

前往 [Releases](https://github.com/restoflife/limuxuan-update/releases) 选择需要的版本。正式版本的附件名为：

```text
BnsMacro.exe
```

通常应选择最新的正式版本。回退到旧版本前，请先确认配置格式和功能是否兼容。

## 与主项目的关系

| 仓库 | 用途 |
| --- | --- |
| [`restoflife/BnsMacro`](https://github.com/restoflife/BnsMacro) | 主程序、独立更新器、构建与发布脚本 |
| [`restoflife/limuxuan-update`](https://github.com/restoflife/limuxuan-update) | 正式版本标签和可下载的程序附件 |
| [`restoflife/BnsMacroThemes`](https://github.com/restoflife/BnsMacroThemes) | 在线过图主题、目录与完整性清单 |

主项目的发布脚本会生成带版本号的本地发布目录、上传用的 `BnsMacro.exe`、更新清单和更新说明。选择上传后，脚本在本仓库创建或更新对应的 `v<版本号>` Release。

更新清单由主程序从独立地址读取；本仓库负责承载清单所指向的 GitHub Release 附件，不把本地生成的 `update.json` 作为仓库文件提交。

## 完整性与更新规则

- 每个版本使用独立的 `v<版本号>` 标签，例如 `v1.6.1`。
- 主程序只接受高于当前版本的更新，不自动降级。
- 下载完成后，主程序会按更新清单中的 SHA-256 校验附件；校验失败的文件不会安装。
- Release 附件可下载并不代表在线更新清单已经切换到该版本，两者由维护者分别确认。

## 维护说明

版本发布应从 `BnsMacro` 主仓库的发布脚本执行，避免手工上传与项目版本、更新说明或 SHA-256 不一致。覆盖已有版本前，应先确认附件和 Release 说明都属于同一构建结果。

此仓库仅用于版本分发；功能说明、运行条件、构建步骤和问题排查请以主项目 README 为准。
