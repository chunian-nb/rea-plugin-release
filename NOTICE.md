# 插件声明

## 基本信息

- **插件名称**: REA (Reverse Engineer Anything)
- **插件 ID**: `rea`
- **版本**: 1.0.0
- **作者**: 初念
- **发布日期**: 2026-10-18
- **适用平台**: Operit（Android / Linux 侧 MCP 插件）

## 功能声明

本插件为 Operit 提供完整的逆向工程 MCP 服务，支持：

- 原生二进制分析（伪代码、汇编、字符串、符号、调用与引用）
- JavaScript / Electron 应用分析
- .NET 程序集分析
- 网站结构分析
- Android APK 分析
- SQLite 数据库分析
- WASM / EVM 字节码分析
- Go / Rust 二进制静态分析
- 网络抓包（HAR / SAZ / pcap）分析
- 固件分析等

## 来源与版权声明

- 本插件基于开源项目 **morluto/rea** 封装适配，官方仓库：https://github.com/morluto/rea
- 官方文档：https://rea.tools/
- npm 包：`rea-agents`（https://www.npmjs.com/package/rea-agents）
- 上游项目版权归其原作者所有。
- 本打包仅做 Operit 平台的配置封装与中文说明适配，不修改上游代码逻辑。

## 使用声明

- 本插件仅用于**合法授权**的软件分析、安全研究、逆向学习与调试场景。
- 使用者应遵守所在地法律法规、软件许可协议及目标系统的使用条款。
- 禁止将本插件用于任何非法用途，包括但不限于：破解商业软件、绕过授权验证、攻击他人系统等。
- 因使用本插件产生的任何法律责任由使用者自行承担。

## 依赖声明

- 需要 Node.js 22.x (>=22.19) / 24.x (>=24.11) / 26+ 环境。
- 首次启动需要联网下载 `rea-agents` 包。
- 部分高级分析需要外部工具：Hopper / Ghidra / IDA / JADX / adb 等，请按需自行安装。

## 安装方法

将本发布包解压后，把 `mcp_config.json` 与 `rea/` 目录整体放入 Operit 的 MCP 插件目录：

```
/sdcard/Download/Operit/mcp_plugins/
├── mcp_config.json
└── rea/
    ├── README.md
    ├── DEPLOY.md
    ├── mcp_config.json
    ├── server.json
    └── NOTICE.md
```

然后在 Operit 的 MCP 插件管理界面刷新/重新扫描，或重启 Operit 应用即可生效。

---

作者：初念