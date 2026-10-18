# REA 插件发布草稿（Operit 插件市场）

> 此文档为 Operit「发布 MCP 插件」表单的填写内容，请对照发布页逐项填写。

---

## 表单字段

### 插件名称
```
Rea
```

### 插件描述
```
REA - Reverse Engineer Anything：一站式逆向分析 MCP 插件。

基于开源项目 morluto/rea（npm: rea-agents）封装，为 Operit 提供完整的逆向工程能力，覆盖二进制、应用、运行时行为三个维度：

- 原生二进制分析：伪代码、汇编、字符串、符号、调用与引用
- JavaScript / Electron 应用分析
- .NET 程序集分析
- 网站结构分析
- Android APK 分析
- SQLite 数据库分析
- WASM / EVM 字节码分析
- Go / Rust 二进制静态分析
- 网络抓包分析（HAR / SAZ / pcap）
- 固件分析

一键部署，启动命令 npx rea-agents mcp（Operit 自动转换为 pnpm dlx）。
```

### 分类
```
逆向工程 / 开发工具
```
（如发布页分类下拉无该选项，请选择最接近的「开发工具」或「安全研究」。）

### GitHub 仓库地址
```
https://github.com/chunian-nb/rea-plugin-release
```

### 版本
```
1.0.0
```

### 允许所有人更新该插件
```
关闭（推荐仅自己维护）
```

### 安装配置 JSON
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

---

## 填写提示

- 插件名称*、插件描述*、GitHub 仓库地址* 为必填。
- 安装配置 JSON 为选填，但建议填入，用户可直接导入。
- 表单会自动保存为草稿，直到成功发布后才会清空。
- 发布后插件信息会作为 GitHub Issue 发布到市场仓库。

---

作者：初念