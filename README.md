# Moltbot 架构与业务流程分析

本目录包含对 [moltbot/moltbot](https://github.com/moltbot/moltbot) 项目的架构分析和业务流程文档。

## 📁 文档列表

### 1. [系统架构图](./docs/architecture.md)
- 整体分层架构（客户端层、网关层、通道层、智能体层、工具层等）
- 核心组件架构（Gateway、Channels、Agents等详细组件）
- 目录结构说明
- 关键组件说明
- 数据流向说明

### 2. [业务流程图](./docs/business-flow.md)
- 消息处理主流程
- 工具执行流程
- 客户端连接与认证流程
- 会话管理流程
- 插件加载与扩展流程
- 技能(Skills)安装与执行流程
- 关键业务场景示例
- 错误处理和恢复机制

### 3. [技术栈总结](./docs/tech-stack.md)
- 项目概述
- 核心技术栈（TypeScript、Node.js、构建工具）
- AI与智能体框架
- 网络与通信技术
- 消息通道集成
- Web与UI技术
- 浏览器自动化
- 数据处理
- 原生应用技术
- 安全与测试
- 性能指标

## 🎯 快速开始

### 前置条件

1. **访问 GitHub**: 确保你有 GitHub 账号
2. **Git 安装**: 本地已安装 Git（你的路径: `D:\Program Files\Git\bin\git.exe`）
3. **Node.js**: 推荐 Node.js 22.12.0+

### 操作步骤

#### 步骤 1: Fork 仓库

1. 访问 [moltbot/moltbot](https://github.com/moltbot/moltbot)
2. 点击右上角的 **Fork** 按钮
3. 选择你的 GitHub 账号作为目标
4. 等待 Fork 完成

#### 步骤 2: 克隆你的 Fork

```bash
# 替换 YOUR_USERNAME 为你的 GitHub 用户名
cd D:\02_source
git clone https://github.com/YOUR_USERNAME/moltbot.git zzh
cd zzh
```

#### 步骤 3: 复制文档文件

如果你已经在我创建的 `zzh` 目录中，文档文件已经在这里了：
- `zzh/docs/architecture.md`
- `zzh/docs/business-flow.md`
- `zzh/docs/tech-stack.md`
- `zzh/README.md`

#### 步骤 4: 提交到你的 Fork

```bash
# 设置 Git 配置（如果还没设置）
"D:\Program Files\Git\bin\git.exe" config user.name "Your Name"
"D:\Program Files\Git\bin\git.exe" config user.email "your.email@example.com"

# 添加所有文件
"D:\Program Files\Git\bin\git.exe" add .

# 提交
"D:\Program Files\Git\bin\git.exe" commit -m "docs: 添加系统架构、业务流程和技术栈文档

- 添加完整的系统分层架构图
- 添加核心组件架构说明
- 添加关键业务流程图（消息处理、工具执行、会话管理等）
- 添加插件和技能系统流程
- 添加技术栈详细说明
- 所有图表使用 Mermaid 格式，支持在 GitHub 和 Markdown 查看器中渲染"

# 推送到你的 Fork
"D:\Program Files\Git\bin\git.exe" push origin main
```

#### 步骤 5: 验证

1. 访问你的 GitHub 仓库: `https://github.com/YOUR_USERNAME/moltbot`
2. 检查 `docs/` 目录是否已上传
3. 点击任意 `.md` 文件，确认 Mermaid 图表正常渲染
4. 查看 README.md 是否显示正确

## 📊 文档预览

### Mermaid 图表支持

本文档使用 [Mermaid](https://mermaid.js.org/) 图表语法，支持在以下环境中查看：

✅ **GitHub**: 直接在 GitHub 上查看（自动渲染）
✅ **VS Code**: 安装 Markdown Preview Mermaid Support 插件
✅ **Typora**: 原生支持 Mermaid
✅ **Obsidian**: 原生支持 Mermaid
✅ **其他**: 支持标准 Markdown + Mermaid 的编辑器

## 🔄 同步更新

如果你以后想同步上游更新：

```bash
# 添加上游仓库
"D:\Program Files\Git\bin\git.exe" remote add upstream https://github.com/moltbot/moltbot.git

# 获取上游更新
"D:\Program Files\Git\bin\git.exe" fetch upstream

# 合并上游更新
"D:\Program Files\Git\bin\git.exe" merge upstream/main

# 推送到你的 Fork
"D:\Program Files\Git\bin\git.exe" push origin main
```

## 📝 贡献

如果你想将这些改进贡献回原始仓库：

1. 在你的 Fork 中创建新分支: `git checkout -b docs-update`
2. 进行修改
3. 提交并推送
4. 在 GitHub 上创建 Pull Request

## 📖 相关资源

- [Moltbot 官方文档](https://docs.molt.bot)
- [Moltbot GitHub 仓库](https://github.com/moltbot/moltbot)
- [Mermaid 文档](https://mermaid.js.org/)
- [TypeScript 文档](https://www.typescriptlang.org/)

## 📄 许可证

本文档遵循原项目的 MIT 许可证。

---

**创建时间**: 2026-01-29
**分析版本**: moltbot 2026.1.27-beta.1
**文档生成者**: Claude Code
