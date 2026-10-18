# REA (Operit 插件) — 部署说明

本目录是 REA MCP 插件在 Operit 中的导入/源目录。

## 插件信息

| 项目 | 值 |
|---|---|
| 插件 ID | `rea` |
| 发布仓库 | [chunian-nb/rea-plugin-release](https://github.com/chunian-nb/rea-plugin-release) |
| 上游项目 | [morluto/rea](https://github.com/morluto/rea) |
| npm 包 | `rea-agents` |
| 版本 | 6.7.0 |
| 启动命令 | `npx rea-agents mcp`（Operit 运行时自动转为 `pnpm dlx rea-agents mcp`） |
| 传输方式 | stdio |

## 目录结构

```
/sdcard/Download/Operit/mcp_plugins/rea/
├── README.md        # 插件说明（识别标志）
├── mcp_config.json  # Operit MCP 注册配置
└── server.json      # 官方 MCP server 元数据
```

## mcp_config.json

```json
{
  "mcpServers": {
    "rea": {
      "command": "npx",
      "args": ["rea-agents", "mcp"],
      "env": {},
      "autoApprove": [],
      "disabled": false
    }
  }
}
```

## 运行原理

- Operit 会把 Android 侧 `/sdcard/Download/Operit/mcp_plugins/rea/` 复制到 Linux 侧 `~/mcp_plugins/rea/`
- 启动时 cwd = `~/mcp_plugins/rea/`，执行 `npx rea-agents mcp`（内部改写为 `pnpm dlx rea-agents mcp`）
- 已实测：`pnpm dlx rea-agents@latest mcp` 可正常完成 MCP initialize 握手，返回 `rea 6.7.0`

## 环境要求（已满足）

- Node.js 22.x (>=22.19) / 24.x (>=24.11) / 26+  → 当前 v24.21.0 ✅
- pnpm（Operit 运行 npx 类 MCP 的实际依赖）       → 当前 v12.10.1 ✅
- 首次启动需联网下载 `rea-agents` 包（约 5.6MB + 依赖）

## 使用提示

- 在 Operit 的 MCP 插件管理界面**刷新/重新扫描**，或重启 Operit 应用，让系统识别并部署本插件
- 若插件列表未出现，检查：
  1. 本目录是否在 `/sdcard/Download/Operit/mcp_plugins/rea/`
  2. 是否包含标志文件（README.md / mcp_config.json）
  3. mcp_config.json 是否合法 JSON
  4. Linux 侧 `~/mcp_plugins/rea/` 是否已生成
- 高级分析（原生二进制、APK、抓包等）需要按需安装 Hopper/Ghidra/IDA/JADX/adb 等外部工具

## 参考

- 上游官方仓库: https://github.com/morluto/rea
- 本发布包仓库: https://github.com/chunian-nb/rea-plugin-release
- 官方文档: https://rea.tools/
- npm: https://www.npmjs.com/package/rea-agents