# REA - Reverse Engineer Anything（Operit 插件发布包）

本目录是 **Rea** 插件在 Operit 插件市场的发布包，由初念制作。

## 发布包内容

```
rea-plugin-release/
├── README.md          # 本说明文件
├── PUBLISH.md         # 发布页填写草稿（对照表单逐项填写）
├── NOTICE.md          # 插件声明（来源/版权/使用/依赖）
├── mcp_config.json    # Operit MCP 注册配置（含插件元数据）
└── rea/               # 插件主体（导入到 Operit 的源目录）
    ├── README.md
    ├── DEPLOY.md
    ├── NOTICE.md
    ├── mcp_config.json
    └── server.json
```

## 快速发布

1. 打开 Operit → 插件市场 →「发布 MCP 插件」。
2. 按 `PUBLISH.md` 中的字段填写：插件名称、描述、分类、GitHub 仓库地址、版本、安装配置 JSON。
3. 点击「发布到市场」。

## 用户安装方式

将 `rea/` 目录整体放入 Operit 的 MCP 插件目录：

```
/sdcard/Download/Operit/mcp_plugins/
└── rea/
    ├── README.md
    ├── DEPLOY.md
    ├── NOTICE.md
    ├── mcp_config.json
    └── server.json
```

然后在 Operit MCP 插件管理界面刷新/重新扫描，或重启 Operit 应用即可生效。

## 核心信息

| 项目 | 值 |
|---|---|
| 插件名称 | Rea |
| 插件 ID | `rea` |
| 版本 | 6.7.0 |
| 作者 | 初念 |
| 发布仓库 | [chunian-nb/rea-plugin-release](https://github.com/chunian-nb/rea-plugin-release) |
| 上游项目 | [morluto/rea](https://github.com/morluto/rea) |
| npm 包 | `rea-agents` |
| 启动命令 | `npx rea-agents mcp` |
| 传输方式 | stdio |

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

- Node.js 22.x (>=22.19) / 24.x (>=24.11) / 26+
- npm / pnpm（Operit 运行 npx 类 MCP 时内部转换为 pnpm dlx）
- 首次启动需联网下载 `rea-agents` 包
- 部分高级分析需要外部工具：Hopper / Ghidra / IDA / JADX / adb 等

## 声明

本插件基于开源项目 morluto/rea 封装适配，仅做 Operit 平台配置封装与中文说明适配，不修改上游代码逻辑。上游版权归其原作者所有。请仅用于合法授权的软件分析、安全研究与逆向学习场景。

---

作者：初念