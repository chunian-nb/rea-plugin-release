# REA - Reverse Engineer Anything (Operit MCP Plugin)

One MCP for reverse engineering across binaries, applications, and runtime behavior.

- 上游官方仓库: https://github.com/morluto/rea
- 本发布包仓库: https://github.com/chunian-nb/rea-plugin-release
- npm 包: `rea-agents`
- 启动命令: `npx rea-agents mcp`

## 功能

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

## 依赖

- Node.js 22.x (>=22.19), 24.x (>=24.11) 或 26+
- npm / pnpm（Operit 运行 npx 类 MCP 时内部会转换为 pnpm dlx）
- 部分高级分析需要外部工具：Hopper / Ghidra / IDA / JADX / adb 等

## Operit 注册

见同目录 `mcp_config.json`。