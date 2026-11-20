# Windows 上的 Codex 空间迁移

这份指南可以交给 Codex 执行。Windows 上优先迁移项目和 Codex 状态目录，让桌面应用在系统默认位置管理运行组件。已经迁移过的机器也可按此指南逐项修复。

在 Codex 中打开本仓库，给它下面这条指令。

    按 AGENTS.md 检查本机 Codex 的安装渠道和存储占用。先给出迁移表。
    目标盘由我指定。已在目标盘的聊天数据沿用现有目录。执行后从日常入口冷启动，
    核对新旧会话、项目和回退路径；使用代理、Windows 通知、Edge 或手机 Remote 时一并实测。

## 默认迁移范围

| 内容 | 建议位置 |
| --- | --- |
| 普通项目和 Git 工作区 | 可放数据盘。从实体路径打开，核对分支、未提交改动和未跟踪文件。 |
| 配置、会话和数据库 | 可将用户级 `CODEX_HOME` 指向数据盘上已有或已校验的实体目录。从 CLI 和实际桌面入口分别验证。有旧绝对路径依赖时保留 `%USERPROFILE%\.codex` 兼容入口。 |
| 桌面配置和商店包配置 | 保留 `%APPDATA%\Codex` 和 `%LOCALAPPDATA%\Packages\<PackageFamilyName>\LocalCache\Roaming\Codex` 的默认实体位置。包族名从本机安装信息取得。 |
| 桌面日志、本机组件、工具缓存 | 保留 `%LOCALAPPDATA%\Codex`、`%LOCALAPPDATA%\OpenAI\Codex`、`%USERPROFILE%\.cache\codex-runtimes` 的默认实体位置。若以前手工重定向过，按执行规则逐项迁回。 |

这些路径按具体安装版本盘点。应用会管理自己的版本链接和商店依赖包，修复时只处理已确认的手工重定向。[Codex 环境变量](https://learn.chatgpt.com/docs/config-file/environment-variables) · [Windows 商店应用的数据路径](https://learn.microsoft.com/en-us/windows/msix/desktop/desktop-to-uwp-behind-the-scenes)

具体操作见 [迁移、验收与回退步骤](AGENTS.md)，已实测的范围见 [接手记录](HANDOFF.md)。
