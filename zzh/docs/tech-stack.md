# Moltbot 技术栈总结

## 项目概述

**Moltbot** 是一个本地优先的个人AI助手平台，通过WebSocket网关架构提供多通道AI交互能力。

- **版本**: 2026.1.27-beta.1
- **许可证**: MIT
- **运行时**: Node.js 22.12.0+
- **包管理器**: pnpm 10.23.0
- **TypeScript文件**: 1,615个
- **代码规模**: 大型生产级项目

## 核心技术栈

### 编程语言与运行时

| 技术 | 版本 | 用途 |
|------|------|------|
| **TypeScript** | 5.x | 主要开发语言（严格模式） |
| **JavaScript (ESM)** | ES2022 | 编译输出格式 |
| **Node.js** | 22.12.0+ | 服务器运行时 |
| **Bun** | Latest | 开发/测试备选运行时 |

### 构建与开发工具

| 工具 | 版本 | 用途 |
|------|------|------|
| **pnpm** | 10.23.0 | 包管理器（workspace monorepo） |
| **TypeScript** | 5.x | 类型检查和编译 |
| **Vite** | 7.3.1 | UI构建工具 |
| **Rolldown** | 1.0.0-rc.1 | 打包工具 |
| **Oxlint** | 1.41.0 | 代码检查（类型感知） |
| **Oxfmt** | 0.26.0 | 代码格式化 |
| **Vitest** | 4.0.18 | 单元测试框架 |

## AI与智能体

| 库/框架 | 版本 | 用途 |
|---------|------|------|
| **@mariozechner/pi-agent-core** | 0.49.3 | 智能体运行时核心 |
| **@mariozechner/pi-ai** | 0.49.3 | AI能力接口 |
| **@mariozechner/pi-coding-agent** | 0.49.3 | 代码生成能力 |
| **@mariozechner/pi-tui** | 0.49.3 | 终端UI框架 |
| **@agentclientprotocol/sdk** | 0.13.1 | Agent客户端协议 |

**AI能力特性：**
- 工具流式执行
- 上下文管理（消息历史、剪枝、压缩）
- 多提供商支持（OpenAI、Anthropic等）
- 模型故障转移
- 向量记忆集成（LanceDB）

## 网络与通信

### WebSocket与API

| 库 | 版本 | 用途 |
|----|------|------|
| **ws** | 8.19.0 | WebSocket服务器 |
| **Hono** | 4.11.4 | 轻量级Web框架 |
| **Express** | 4.x | HTTP服务器（部分功能） |
| **Undici** | 7.19.0 | HTTP客户端 |

### 协议与验证

| 技术 | 用途 |
|------|------|
| **TypeBox** | 类型定义和JSON Schema生成 |
| **Zod** | 运行时schema验证 |
| **JSON Schema** | 协议验证标准 |

## 消息通道集成

### 主要平台SDK

| 平台 | SDK/库 | 版本 | 用途 |
|------|--------|------|------|
| **WhatsApp** | @whiskeysockets/baileys | 7.0.0-rc.9 | WhatsApp Web API |
| **Telegram** | grammy | Latest | Telegram Bot API |
| **Slack** | @slack/bolt | Latest | Slack事件处理 |
| **Slack Web API** | @slack/web-api | Latest | Slack REST API |
| **Discord** | discord-api-types | Latest | Discord类型定义 |
| **LINE** | @line/bot-sdk | Latest | LINE Messaging API |
| **Google Chat** | Google Hangouts Chat | - | 企业聊天集成 |
| **Signal** | signal-client | - | Signal消息客户端 |

### 支持的通道（扩展插件）

- Matrix
- Microsoft Teams
- Zalo (越南)
- Twitch
- BlueBubbles (iMessage)
- iMessage (macOS本地)
- Signal
- 共计**30+个通道**

## Web与UI技术

### 前端框架

| 技术 | 版本 | 用途 |
|------|------|------|
| **Lit** | 3.3.2 | Web Components框架 |
| **Vite** | 7.3.1 | 开发服务器和构建工具 |
| **Marked** | 17.0.1 | Markdown渲染 |
| **DOMPurify** | 3.3.1 | XSS防护 |

### UI特性
- Web Components（原生组件）
- 响应式设计
- 实时WebSocket连接
- Markdown内容渲染
- 安全的HTML注入

## 浏览器自动化

| 技术 | 版本 | 用途 |
|------|------|------|
| **Playwright** | 1.58.0 | 浏览器自动化 |
| **Chrome DevTools Protocol** | - | CDP控制 |
| **Puppeteer** | - | 备选方案 |

**浏览器能力：**
- 页面导航和交互
- 元素选择和操作
- 截图和PDF生成
- Cookie管理
- 文件上传/下载
- 专用浏览器配置文件

## 数据处理

### 文件处理

| 库 | 版本 | 用途 |
|----|------|------|
| **pdfjs-dist** | 5.4.530 | PDF解析 |
| **Sharp** | 0.34.5 | 图片处理 |
| **ffmpeg** | - | 视频处理（通过插件） |

### 数据库

| 技术 | 用途 |
|------|------|
| **LanceDB** | 向量数据库（记忆系统） |
| **SQLite** | 本地存储（会话、配置） |
| **文件系统** | JSON配置文件 |

## 命令行工具

| 库 | 版本 | 用途 |
|----|------|------|
| **Commander** | 14.0.2 | CLI框架 |
| **Chalk** | 5.6.2 | 终端颜色 |
| **Inquirer** | Latest | 交互式提示 |
| **ora** | Latest | 加载动画 |
| **cli-table3** | Latest | 表格显示 |
| **tslog** | 4.10.2 | 日志记录 |

## 日志与监控

| 技术 | 用途 |
|------|------|
| **tslog** | 结构化日志 |
| **OpenTelemetry** | 诊断追踪（通过插件） |
| **Winston** | 日志传输（部分功能） |

## 安全

| 技术 | 用途 |
|------|------|
| **Zod** | 输入验证 |
| **DOMPurify** | XSS防护 |
| **Helmet** | HTTP安全头 |
| **JWT** | Token认证 |
| **加密存储** | 敏感数据保护 |

## 测试框架

| 技术 | 版本 | 用途 |
|------|------|------|
| **Vitest** | 4.0.18 | 单元测试 |
| **Playwright Test** | 1.58.0 | E2E测试 |
| **MSW** | Latest | API Mock |
| **Testcontainers** | - | Docker集成测试 |

**测试覆盖目标：**
- 行覆盖: 70%+
- 分支覆盖: 70%+
- 函数覆盖: 70%+
- 语句覆盖: 70%+

## 原生应用

### iOS/macOS

| 技术 | 版本 | 用途 |
|------|------|------|
| **Swift** | 5.x | 主要语言 |
| **SwiftUI** | Latest | UI框架 |
| **Xcode** | 15+ | 构建工具 |
| **Bonjour** | - | 网络发现 |

### Android

| 技术 | 版本 | 用途 |
|------|------|------|
| **Kotlin** | 1.9+ | 主要语言 |
| **Jetpack Compose** | Latest | UI框架 |
| **Gradle** | 8.x | 构建工具 |

### 共享框架

- **MoltbotKit**: 共享Swift框架
- 协议代码生成（TypeScript → Swift）

## 容器化与部署

| 技术 | 用途 |
|------|------|
| **Docker** | 容器化部署 |
| **docker-compose** | 本地开发环境 |
| **Dockerfile** | 多阶段构建 |
| **Tailscale** | 远程访问（Serve/Funnel） |

## 配置管理

| 技术 | 用途 |
|------|------|
| **Zod** | 配置Schema验证 |
| **环境变量** | 环境特定配置 |
| **JSON/YAML** | 配置文件格式 |
| **迁移系统** | 配置版本升级 |

## 文档

| 技术 | 用途 |
|------|------|
| **Mintlify** | 文档站点 |
| **Markdown** | 文档格式 |
| **Mermaid** | 图表渲染 |
| **TypeDoc** | API文档 |

## 性能优化

| 技术 | 用途 |
|------|------|
| **Node Compile Cache** | 启动加速 |
| **Vite HMR** | 热模块替换 |
| **代码分割** | 按需加载 |
| **流式处理** | 大数据传输 |

## 开发工作流

### 构建流程

```bash
# 1. 类型检查
tsc -p tsconfig.json

# 2. UI构建
cd ui && vite build

# 3. 协议生成
scripts/generate-protocol.ts

# 4. 插件打包
pnpm --filter ./extensions/* build
```

### 开发命令

```bash
pnpm dev          # 开发模式
pnpm build        # 完整构建
pnpm test         # 运行测试
pnpm lint         # 代码检查
pnpm ui:dev       # UI开发服务器
pnpm gateway:watch # 网关热重载
```

## 依赖管理

### 主要依赖分类

1. **核心依赖** (dependencies)
   - AI框架
   - 通道SDK
   - Web框架

2. **开发依赖** (devDependencies)
   - TypeScript
   - 测试框架
   - 构建工具

3. **扩展依赖** (workspace)
   - 通道插件
   - 技能包

### pnpm Workspace结构

```yaml
packages:
  - 'extensions/*'
  - 'packages/*'
  - 'ui'
```

## 代码质量

### 静态分析

- **Oxlint**: 快速类型感知linting
- **TypeScript**: 严格模式检查
- **Prettier/Oxfmt**: 代码格式化

### 测试策略

- **单元测试**: 源码同级 `*.test.ts`
- **E2E测试**: `*.e2e.test.ts`
- **Live测试**: 真实API测试
- **Docker测试**: 容器化测试

### CI/CD

- GitHub Actions
- 多Node.js版本测试
- Docker镜像构建
- 自动发布

## 平台支持

### 服务器端

- **Linux**: 主要部署平台
- **macOS**: 开发和部署
- **Windows**: 开发支持

### 客户端

- **Web浏览器**: 现代浏览器（Chrome、Firefox、Safari、Edge）
- **macOS**: 10.15+
- **iOS**: 15+
- **Android**: 10+

## 性能指标

- **启动时间**: < 2秒（Node compile cache）
- **内存占用**: 基础 ~200MB，取决于通道和会话数
- **并发连接**: WebSocket支持数百并发
- **消息延迟**: 通常 < 500ms（取决于LLM）

## 扩展性设计

### 插件系统

- **清单驱动**: JSON配置
- **钩子系统**: 生命周期事件
- **依赖注入**: 自动解析
- **热加载**: 开发时自动重载

### API设计

- **WebSocket协议**: TypeBox Schema
- **REST API**: Hono框架
- **事件驱动**: 发布/订阅模式

## 安全考虑

- **输入验证**: Zod schema验证
- **输出编码**: DOMPurify净化
- **认证**: 多种认证方式
- **授权**: 配对和允许列表
- **加密**: 本地数据加密
- **沙箱**: 工具执行隔离

## 监控与诊断

- **结构化日志**: tslog
- **健康检查**: `/health` 端点
- **指标**: OpenTelemetry插件
- **错误追踪**: 集成错误报告

## 总结

Moltbot采用现代化的技术栈，具有以下特点：

✅ **类型安全**: 全面的TypeScript严格模式
✅ **模块化**: 插件和技能系统
✅ **可扩展**: 清晰的架构和接口
✅ **高性能**: 优化构建和运行时
✅ **跨平台**: 支持所有主流平台
✅ **开发者友好**: 完善的工具链
✅ **生产就绪**: 全面的测试和文档
✅ **本地优先**: 隐私和自主控制
