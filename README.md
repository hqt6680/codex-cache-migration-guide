# Windows 上的 Codex 空间迁移

这份指南可以交给 Codex 执行。目标是把工作区或选定的可重建数据放到目标盘，通过路径、哈希和启动检查保留回退能力。

在 Codex 中打开本仓库，给它下面这条指令。

    按 AGENTS.md 检查本机 Codex 的安装渠道和存储占用。先给出迁移表。
    目标盘由我指定。执行完要核对原有会话、项目、新建会话和回退路径。

## 默认迁移范围

- 普通 Git 工作区可以放在数据盘。复制后先核对当前分支、提交、未提交改动和项目入口，再用真实目标路径打开项目。
- 日志和可重建缓存按实际客户端支持的路径处理。项目源码、聊天存储、认证状态和包管理器目录分别核对。
- Codex CLI 的配置根和 Windows Store 版应用的包目录分别处理。检查 `CODEX_HOME` 是否已设置，按[配置文档](https://learn.chatgpt.com/docs/config-file/config-basic)确认当前 CLI 生效范围。
- Windows Store/MSIX 版的 Roaming 和 LocalCache 目录保留实体路径。若已有重解析点且出现异常内存或远程会话故障，优先核对包目录和链接目标；先备份再按执行规则回退。

[Windows 应用文档](https://learn.chatgpt.com/docs/windows/windows-app)
