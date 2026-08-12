<div align="center">


# 🧬 爱魔豆 iModel

## AI 模型路由调度优化器 · 让每一次调用都物超所值

<br>

**「省心 · 省钱 · 省力」**

> 智能分类路由 · Token 压缩 · 企业级网关 · 实时监控
> 将 API 调用成本直降 40%~70%

</div>

---

<br>

## 一、痛点直击

<br>

### ❌ 你是不是也遇到这些问题？

| 问题                                             | 后果                       |
| :----------------------------------------------- | :------------------------- |
| 所有请求都用最强模型 → 杀鸡用牛刀                | **每月账单高得离谱**       |
| 长对话历史越积越多 → Token 飞涨                  | **一半的钱花在重复计算上** |
| 手动切换模型 → 繁琐又容易出错                    | **开发效率低下**           |
| 没有统一监控 → 成本失控无从优化                  | **月底对账一脸懵**         |
| 多模型 API Key 散落各处 → 无法统一管理           | **安全隐患大**             |
| 团队共用 API → 并发争抢、无审计                  | **资源冲突、合规难**       |
| 想在内网 / NAS / 服务器上部署网关 → 没有现成方案 | **只能手工脚本凑合**       |

> **爱魔豆 iModel 一站式解决以上所有问题。**
> 从个人桌面到企业基础设施，三档产品形态覆盖全场景。

<br>

---

## 二、产品简介

<br>

**爱魔豆 iModel** 是一套面向 AI 开发者与企业 IT 团队的 **智能模型路由与网关管理平台**。它由三大产品形态组成，运行在用户电脑、团队服务器、NAS 与云主机上，统一由 iModel-web 中央平台提供账号、订阅与策略同步。

<br>

**一句话理解爱魔豆：**

> 🎯 你只管用 AI，怎么省钱、怎么管、怎么部署，交给爱魔豆。

<br>

---

## 三、三大产品形态

<br>

爱魔豆从"个人桌面"到"企业基础设施"，提供三个清晰的产品形态：

| 维度           |      🆓 **iModel (Free)**       |        🥇 **iModel-Pro**        |                     🏢 **iModel-Server**                      |
| :------------- | :----------------------------: | :----------------------------: | :----------------------------------------------------------: |
| **产品形态**   |          桌面托盘应用          |          桌面托盘应用          |                       **无界面服务器**                       |
| **运行方式**   |       系统托盘 / 菜单栏        |       系统托盘 / 菜单栏        | **系统服务**（systemd / launchd / Windows Service / Docker） |
| **进程模型**   |     双进程（托盘 + 服务）      |     双进程（托盘 + 服务）      |               **单进程**（FastAPI + uvicorn）                |
| **访问方式**   |         本机 Dashboard         |         本机 Dashboard         |                     **LAN WebUI + CLI**                      |
| **默认监听**   |       `127.0.0.1` 仅本机       |       `127.0.0.1` 仅本机       |           **`0.0.0.0` LAN 可达**（可回 localhost）           |
| **管理入口**   | Dashboard (8799) + 服务 (8788) | Dashboard (8799) + 服务 (8788) |          **单端口 8788**（WebUI + API + 代理合一）           |
| **智能路由**   |               ✅                |               ✅                |                              ✅                               |
| **Token 压缩** |               ❌                |           ✅ Pro 核心           |                              ✅                               |
| **自定义分类** |               ❌                |               ❌                |                              ✅                               |
| **企业级鉴权** |         localhost-only         |         localhost-only         | **HTTPS 默认 + SSO (OIDC/SAML) + 作用域 Admin Key + 审计 + IP 封禁** |
| **CLI**        |    `imodel-cli`（令牌管理）    |    `imodel-cli`（令牌管理）    |           **`imodel-server`**（完整生命周期管理）            |
| **mDNS 发现**  |               ❌                |               ❌                |                    ✅ `imodelserver.local`                    |
| **局域网共享** |               ❌                |       订阅权益（需重启）       |                         **默认能力**                         |
| **目标用户**   |            个人尝鲜            |      个人开发者 / 小团队       |        **10-1000 人团队 / 企业 / NAS 玩家 / 云部署**         |

<br>

```
┌────────────────────────────────────────────────────────────────┐
│  iModel-web 中央平台（imodel.work）                               │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │  账号注册 · 订阅管理 · 支付（支付宝/微信/抖音）              │  │
│  │  反馈中心 · 使用统计 · 平台 API                            │  │
│  └──────────────────────────────────────────────────────────┘  │
└──────────────────────────┬─────────────────────────────────────┘
                           │  账号/订阅/策略同步
        ┌──────────────────┼──────────────────┐
        ▼                  ▼                  ▼
┌──────────────┐   ┌──────────────┐   ┌──────────────────────┐
│ iModel Free  │   │ iModel-Pro   │   │  iModel-Server       │
│ 桌面托盘应用  │   │ 桌面托盘应用  │   │  企业级无界面服务器    │
│ 本机自用      │   │ 本机自用      │   │  LAN / Docker / 云    │
└──────────────┘   └──────────────┘   └──────────────────────┘
```

<br>

---

## 四、核心功能

<br>

### 🔀 智能路由 · 好钢用在刀刃上

爱魔豆自动分析每个请求的复杂程度，将简单请求路由到经济型模型，复杂请求路由到高性能模型。

```
┌─────────────────────────────────────────────────────┐
│                                                     │
│  你提问 ──→  爱魔豆分析复杂度 ──→  自动匹配最佳模型    │
│                                                     │
│  ┌─────────────────────────────────────────────┐   │
│  │  "写一个排序函数"  ──→  ✅ Simple  ──→  Flash  │   │
│  │  "设计分布式系统"  ──→  🔬 Complex ──→  Pro    │   │
│  │  "继续" / "好的"   ──→  ✅ Simple  ──→  Flash  │   │
│  │  "帮我重构整个项目" ──→  🔬 Complex ──→  Pro    │   │
│  └─────────────────────────────────────────────┘   │
│                                                     │
│  目标分布：Simple 约 65% / Complex 约 35%           │
│  → 大部分请求走经济模型，成本自然降低                 │
│                                                     │
└─────────────────────────────────────────────────────┘
```

**效果：** 日常使用中，约 **65% 的请求自动走经济模型**，仅复杂任务才调用高性能模型。

**路由能力分层：**

| 能力                | iModel Free | iModel-Pro |   iModel-Server    |
| :------------------ | :---------: | :--------: | :----------------: |
| v4.1 智能分类器     |      ✅      |     ✅      |         ✅          |
| 自定义领域分类      |      ❌      |     ❌      |      ✅ 无上限      |
| 备用模型 + 故障切换 |      ✅      |     ✅      |         ✅          |
| 负载均衡            |    基础     |    完整    | 完整 + 多 Provider |

<br>

### 📦 Token 压缩 · 长对话不怕贵（Pro / Server）

AI 对话中，历史消息越长，Token 消耗越大。爱魔豆的压缩引擎能 **自动压缩长对话历史**，保留核心信息，丢掉冗余内容。

| 对话轮数 |   场景   |    压缩前     |    压缩后     | **节省**  |
| :------: | :------: | :-----------: | :-----------: | :-------: |
|  10 轮   | 代码审查 | 8,200 tokens  | 2,100 tokens  | **⬇ 74%** |
|  20 轮   | 架构设计 | 18,500 tokens | 5,800 tokens  | **⬇ 69%** |
|  30 轮   | 综合讨论 | 32,000 tokens | 11,200 tokens | **⬇ 65%** |
|  50 轮   |  长对话  | 68,000 tokens | 28,000 tokens | **⬇ 59%** |

**额外收益：**

- 🚀 响应速度提升 30%~50%（需要处理的 Token 大幅减少）
- 🎯 响应质量保持 95% 以上（智能压缩，保留关键信息）
- 🔧 压缩策略灵活可调（保护最近 N 轮对话不受压缩）
- 🧠 Pro/Server 支持 headroom-ai 集成、多档位策略、本地向量记忆、图像压缩

<br>

### ⚡ 并发控制 · 多任务不打架

团队共用模型时，多请求并发容易导致资源争抢。爱魔豆为每个模型设置独立的 **并发槽位**，请求自动排队，忙时智能等待。

| 能力             | 说明                                   |
| :--------------- | :------------------------------------- |
| **独立并发控制** | 每个模型可单独设置最大并发数           |
| **自动排队**     | 超量请求自动排队，不丢失               |
| **智能超时**     | 排队超时自动通知，避免死等             |
| **故障转移**     | 模型出错自动切换到备用模型，服务不中断 |
| **冷却保护**     | 失败模型自动冷却，避免连续报错         |

<br>

### 🏢 iModel-Server 企业级能力

iModel-Server 将爱魔豆从"桌面工具"升级为"基础设施"：

- 🔐 **HTTPS 默认启用**：首启自动生成自签证书，可选 Let's Encrypt 正式证书
- 🔑 **SSO 单点登录**：OIDC + SAML 2.0 同时支持，对接 Azure AD / Keycloak / Okta / Google
- 🛡️ **作用域 Admin Key**：每个 Key 带权限子集，最小权限原则，SHA-256 存储
- 🚫 **IP 自动封禁**：登录失败超限自动封禁，可信网络 CIDR 白名单降摩擦
- 📋 **关键操作审计**：登录 / 配置变更 / Key 管理 / 会话撤销全审计，append-only 不可篡改
- 🖥️ **系统服务**：systemd / launchd / Windows Service (NSSM) 一键安装，开机自启
- 🐳 **Docker 多架构镜像**：amd64 + arm64，单卷挂载所有数据
- 📡 **mDNS 局域网发现**：广播 `imodelserver.local`，装完即找到
- 🌐 **WebUI 管理界面**：统一导航栏、oklch 设计系统、Auto/Light/Dark 主题自适应
- 🔌 **CLI `imodel-server`**：30+ 子命令，完整生命周期管理，瘦 HTTP 客户端
- 🔄 **桌面版一键迁移**：`imodel-server migrate` 支持 dry-run / rollback
- 🩺 **健康检查就绪**：`/health` + `/ready`，Kubernetes / systemd 直接对接

<br>

### 🧩 客户端自动配置生态

爱魔豆内置 **Config Script Registry**（配置脚本注册表），一键配置 17+ 主流 AI 客户端：

| 客户端类型         | 支持列表                                                     |
| :----------------- | :----------------------------------------------------------- |
| **AI 编程工具**    | Claude Code、Cursor、Aider、Cline、Continue、Windsurf、Void、GitHub Copilot Chat |
| **桌面对话客户端** | Cherry Studio、BoltAI、LobeChat、Open WebUI、TypingMind      |
| **命令行 LLM CLI** | Codex CLI、Gemini CLI、opencode、llm                         |
| **其他**           | Tabby                                                        |

**工作机制：**

- 静态 YAML 描述文件托管在 GitHub Pages / Cloudflare Pages
- 客户端定期检查 Registry 更新，本地执行配置脚本
- 自动检测 App 安装状态、自动修改配置文件、自动创建 API Key
- 社区可贡献 PR 扩展支持更多客户端

<br>

### 📊 实时监控 · 每一分钱都看得见

内置 Web 监控面板，打开浏览器即可查看：

```
┌─────────────────────────────────────────────────────────┐
│                    📊 实时监控面板                         │
│                                                           │
│     ┌──────────┐   ┌──────────┐   ┌──────────┐          │
│     │  活跃请求  │   │  排队请求  │   │ 今日总调用 │          │
│     │    3      │   │    0      │   │  12,847   │          │
│     └──────────┘   └──────────┘   └──────────┘          │
│                                                           │
│   模型延迟 (P50 / P95 / P99):                              │
│   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━       │
│   claude-flash:  1.2s / 3.8s / 6.1s                      │
│   claude-pro:    3.5s / 9.2s / 15.3s                     │
│                                                           │
│   Token 消耗趋势 (今日):                                   │
│   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━       │
│   压缩前: 3,500,000  |  压缩后: 1,200,000  |  节省 66%    │
│                                                           │
│   故障告警:                                                │
│   ⚠️ claude-pro 故障切换中   ❌ gpt-4o 已冷却              │
│                                                           │
│   审计日志（Server 版）:                                    │
│   ✅ admin login 09:23  🔧 config reload 09:45            │
└─────────────────────────────────────────────────────────┘
```

**所有数据永久保存**，支持按天/周/月查看历史趋势，SQLite WAL 模式，iModel-Server 支持多 worker + LRU 缓存。

<br>

### 🖥️ 跨平台 · 全桌面覆盖

| 平台           | iModel Free | iModel-Pro |            iModel-Server             |
| :------------- | :---------: | :--------: | :----------------------------------: |
| 🍎 **macOS**    | ✅ 完整支持  | ✅ 完整支持 |         ✅ LaunchAgent + .pkg         |
| 🪟 **Windows**  | ✅ 完整支持  | ✅ 完整支持 | ✅ Windows Service (NSSM) + InnoSetup |
| 🐧 **Linux**    | ✅ 完整支持  | ✅ 完整支持 |         ✅ systemd + .tar.gz          |
| 🐳 **Docker**   |      —      |     —      |      ✅ 多架构（amd64 + arm64）       |
| 🍺 **Homebrew** |      —      |     —      |         ✅ formula（规划中）          |

<br>

### 💻 三协议代理 · 兼容主流生态

| 协议        | 用途                    | 代理端点                    | 适用工具                      |
| ----------- | ----------------------- | --------------------------- | ----------------------------- |
| `anthropic` | Anthropic Messages API  | `POST /v1/messages`         | Claude Code、Claude Desktop   |
| `openai`    | OpenAI Chat Completions | `POST /v1/chat/completions` | Hermes、GMOS、OpenAI 兼容工具 |
| `responses` | OpenAI Responses API    | `POST /v1/responses`        | Codex CLI                     |

> 所有形态的产品都支持三协议代理，开箱即用。

<br>

### 🔑 转发令牌（Entry）体系

统一的 API Key 管理体系：

| 能力           | 说明                                                  |
| :------------- | :---------------------------------------------------- |
| **多协议 Key** | 每个 Entry 可绑定 Anthropic / OpenAI / Responses 协议 |
| **路由策略**   | 每个 Key 可独立路由策略（绑定特定分类、特定模型）     |
| **压缩覆盖**   | 每个 Key 可覆盖全局压缩策略                           |
| **配额管理**   | 配合 iModel-web 订阅，限制 Key 数量与模型数量         |
| **作用域管理** | iModel-Server 的 Admin Key 带权限子集，最小权限原则   |

<br>

---

## 五、谁在用

<br>

### 👨‍💻 独立开发者 · 小明

> *"以前每个月 API 账单 3000+，用了爱魔豆之后降到 800 左右。智能路由自动把大部分简单请求走 Flash 模型，完全不影响日常写代码，但钱省了一大半。"*

### 👥 创业团队 · 某 AI 工具公司

> *"团队 5 个人共用 API Key，并发控制帮了大忙。以前经常有人抢资源导致报错，现在自动排队，谁都不用等太久。Dashboard 还能看到每个人的使用量，月底对账清清楚楚。"*

### 🏢 企业用户 · 某互联网公司

> *"我们给内部 20 多个开发者统一配置了爱魔豆企业版，自定义分类能力让不同团队用不同的模型路由策略。Token 压缩每个月省下 40%+ 的 Token 费，老板非常满意。"*

### 🖥️ 企业 IT · 某科技公司基础设施团队

> *"我们把 iModel-Server 部署在内部 NAS 上，作为全公司的 AI 网关。SSO 接入我们的 Azure AD，员工用企业账号直接登录。审计日志满足合规要求，IP 封禁帮我们挡住了几次异常访问。"*

### 🐳 运维工程师 · 容器化部署

> *"Docker 一行命令启动，单卷挂载不丢数据，/health 直接接 Kubernetes 探针。CLI 的 doctor 命令帮我快速定位配置问题，比手写 nginx 代理方案省太多事了。"*

<br>

---

## 六、方案与定价

<br>

| 方案             |       月费        | API Key 数 | 模型总数 | 自定义分类 | Token 压缩 | 局域网访问 | 适合谁             |
| :--------------- | :---------------: | :--------: | :------: | :--------: | :--------: | :--------: | :----------------- |
| 🆓 **Free**       |      **¥0**       |    1 个    |   3 个   |     ❌      |     ❌      |     ❌      | 先试试看           |
| 🥉 **Trial**      | **¥0**（7天试用） |   10 个    |  10 个   |     ❌      |     ✅      |     ❌      | 体验个人版全部功能 |
| 🥈 **Pro** 🔥      |     **¥9.99**     |   10 个    |  10 个   |     ❌      |     ✅      |     ❌      | **开发者首选**     |
| 🥇 **Enterprise** |    **¥99.99**     |   无上限   |  无上限  |  ✅ 无上限  |     ✅      |     ✅      | 团队/企业          |

> 💳 支持 **支付宝 / 微信 / 抖音** 支付，一键订阅，随时升级。

<br>

**iModel-Server 定价：**

iModel-Server 为企业定制版，基于 **Enterprise 订阅**，一次订阅即可在团队内通过局域网分发，支持无上限的 API Key、模型与自定义分类。如需私有化部署、SSO 接入或定制开发，请联系企业合作咨询：[cooperate@imodel.work](mailto:cooperate@imodel.work)。

<br>

**为什么选订阅制而不是按量付费？**

- ✅ **成本可预测** — 每月固定支出，不怕突发调用量
- ✅ **用得越多越划算** — 高频用户相当于 Token 成本节约大半
- ✅ **随时升级降级** — 需求变化灵活调整

<br>

---

## 七、和竞品比好在哪？

<br>

| 对比维度                   |       🧬 爱魔豆 iModel        | OpenRouter | LiteLLM  | One API  |
| :------------------------- | :--------------------------: | :--------: | :------: | :------: |
| **智能路由（按复杂度）**   |          ✅ **独家**          |     ❌      |    ❌     |    ❌     |
| **Token 压缩**             |          ✅ **独家**          |     ❌      |    ❌     |    ❌     |
| **桌面应用 + 系统托盘**    |          ✅ **独家**          |     ❌      |    ❌     |    ❌     |
| **企业级无界面服务器**     |       ✅ iModel-Server        |     ❌      | ⚠️ 自托管 | ⚠️ 自托管 |
| **SSO (OIDC + SAML)**      |          ✅ v1 标配           |     ❌      |  企业版  |    ❌     |
| **关键操作审计**           |          ✅ v1 标配           |     ❌      |  企业版  |  ⚠️ 基础  |
| **mDNS 局域网发现**        |          ✅ **独家**          |     ❌      |    ❌     |    ❌     |
| **订阅制（成本可控）**     |              ✅               | ❌ 按量付费 |    ❌     |    ❌     |
| **中国本土化**             |       ✅ 中文+国内支付        | ❌ 可能被墙 |    ❌     |    ✅     |
| **数据本地化**             |         ✅ 数据在本地         |   ❌ SaaS   | ✅ 自托管 | ✅ 自托管 |
| **客户端一键配置**         |         ✅ 17+ 客户端         |     ❌      |    ❌     |    ❌     |
| **Docker 多架构**          |       ✅ amd64 + arm64        |     —      |    ✅     |    ✅     |
| **自动故障转移**           |              ✅               |     ✅      |  ⚠️ 有限  |    ❌     |
| **三协议支持**             | ✅ OpenAI+Anthropic+Responses |     ✅      |    ✅     |    ✅     |
| **远程访问中继（规划中）** |     ✅ QuickConnect 模式      |     —      |    —     |    —     |

**爱魔豆的四大独家优势：**

1. 🧠 **智能路由** — 只有爱魔豆能按请求复杂度自动分配模型
2. 📦 **Token 压缩** — 独家技术，长对话成本直降 60%+
3. 🖥️ **桌面 + 服务器双形态** — 个人到企业无缝升级路径
4. 🏢 **企业级安全 v1 标配** — SSO / 审计 / IP 封禁 / 可信网络 / 作用域 Key

<br>

---

## 八、下载与安装

<br>

### 一键安装 — 免费版 (v2.0.62)

| 平台          | 架构                | 下载链接                                                     |  大小  | 系统要求                  |
| :------------ | :------------------ | :----------------------------------------------------------- | :----: | :------------------------ |
| 🍎 **macOS**   | Apple Silicon (ARM) | [下载 iModel-2.0.62-macOS-arm64.pkg](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-2.0.62-macOS-arm64.pkg) | ~33 MB | macOS 13.x 或更高版本     |
| 🍎 **macOS**   | Intel (X64)         | [下载 iModel-2.0.62-macOS-x64.pkg](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-2.0.62-macOS-x64.pkg) | ~36 MB | macOS 13.x 或更高版本     |
| 🪟 **Windows** | X64                 | [下载 iModel-2.0.62-windows-x64-setup.exe](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-2.0.62-windows-x64-setup.exe) | ~22 MB | Windows 10/11             |
| 🪟 **Windows** | ARM                 | [下载 iModel-2.0.62-windows-arm64-setup.exe](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-2.0.62-windows-arm64-setup.exe) | ~18 MB | Windows 10/11             |
| 🐧 **Linux**   | X64                 | [下载 iModel-2.0.62-linux-x64.tar.gz](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-2.0.62-linux-x64.tar.gz) | ~37 MB | Ubuntu 20.04+ / CentOS 7+ |
| 🐧 **Linux**   | ARM64               | [下载 iModel-2.0.62-linux-arm64.tar.gz](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-2.0.62-linux-arm64.tar.gz) | ~36 MB | Ubuntu 24.04 或更高版本   |

### 一键安装 — Pro 版 (v2.0.62)

| 平台          | 架构                | 下载链接                                                     |  大小   | 系统要求                  |
| :------------ | :------------------ | :----------------------------------------------------------- | :-----: | :------------------------ |
| 🍎 **macOS**   | Apple Silicon (ARM) | [下载 iModel-Pro-2.0.62-macOS-arm64.pkg](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-Pro-2.0.62-macOS-arm64.pkg) | ~276 MB | macOS 13.x 或更高版本     |
| 🍎 **macOS**   | Intel (X64)         | [下载 iModel-Pro-2.0.62-macOS-x64.pkg](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-Pro-2.0.62-macOS-x64.pkg) | ~164 MB | macOS 13.x 或更高版本     |
| 🪟 **Windows** | X64                 | [下载 iModel-Pro-2.0.62-windows-x64-setup.exe](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-Pro-2.0.62-windows-x64-setup.exe) | ~216 MB | Windows 10/11             |
| 🐧 **Linux**   | X64                 | [下载 iModel-Pro-2.0.62-linux-x64.tar.gz](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-Pro-2.0.62-linux-x64.tar.gz) | ~373 MB | Ubuntu 20.04+ / CentOS 7+ |
| 🐧 **Linux**   | ARM64               | [下载 iModel-Pro-2.0.62-linux-arm64.tar.gz](https://github.com/sztechnexus/iModel/releases/download/v2.0/iModel-Pro-2.0.62-linux-arm64.tar.gz) | ~330 MB | Ubuntu 24.04 或更高版本   |

### iModel-Server（企业定制版）

iModel-Server 是面向企业客户的无界面服务器形态，基于 Enterprise 订阅，提供私有化部署、SSO 接入、审计合规等企业级能力。

> **📧 企业合作咨询：** [cooperate@imodel.work](mailto:cooperate@imodel.work)

| 平台       | 安装方式                                             |   状态   |
| :--------- | :--------------------------------------------------- | :------: |
| 🍎 macOS    | `.pkg` + LaunchAgent                                 | ✅ 已发布 |
| 🐧 Linux    | `.tar.gz` + `install.sh`（自动写入 systemd unit）    | ✅ 已发布 |
| 🪟 Windows  | InnoSetup `.exe` + NSSM 包装为 Windows Service       | ✅ 已发布 |
| 🐳 Docker   | 官方镜像 `imodel-server:latest`（amd64 + arm64）     | 🚧 开发中 |
| 🍺 Homebrew | `brew install imodel-server` + `brew services start` | 📋 规划中 |

### 3 步上手（桌面版）

```
1️⃣ 下载安装 →  2️⃣ 手机号登录 →  3️⃣ 启动服务 → 开始使用

总耗时：不超过 1 分钟
```

**然后就可以在你的 AI 工具中使用了：**

- 🛠️ Claude Code / Claude Desktop → 指向 `http://127.0.0.1:8788/v1`
- 🛠️ OpenAI API → 指向 `http://127.0.0.1:8788/v1`
- 🛠️ LangChain / LlamaIndex → 配置代理地址即可
- 🛠️ 任何兼容 OpenAI / Anthropic / Responses SDK 的工具 → 开箱即用

<br>

---

## 九、常见问题

<br>

**Q：爱魔豆会收集我的数据吗？**
A：不会。所有请求数据都存储在你的本地电脑上（或你自己部署的 iModel-Server 上），爱魔豆只做智能路由和压缩，不收集、不上传你的对话内容。

**Q：支持哪些模型供应商？**
A：支持 OpenAI Chat Completions、Anthropic Messages 和 OpenAI Responses 三种主流协议。兼容 Claude Code、Claude Desktop、OpenAI API 客户端，以及任何支持这三种协议的 AI 工具。未来将通过 provider 扩展支持 Ollama / vLLM 等本地 LLM 后端。

**Q：安装后对现有工具有影响吗？**
A：完全没有。只需将 API 地址改为 `http://127.0.0.1:8788/v1`，现有代码和工具无需任何改动。桌面版使用 `imodel-cli config setup` 可以一键自动配置。

**Q：免费版和付费版有什么区别？**
A：免费版可体验核心路由功能，有 1 个 API Key 额度、3 个模型上限。Pro 版（¥9.99/月）解锁 Token 压缩、最多 10 个 API Key 和 10 个模型等高级功能。企业版（¥99.99/月）提供无上限的转发 API Key、模型和自定义分类路由，支持局域网分发，也是 iModel-Server 的订阅基础。

**Q：可以按月订阅吗？可以随时取消吗？**
A：可以。按月订阅，随时取消，不扣违约金。

**Q：iModel-Server 和桌面版有什么区别？能同时用吗？**
A：iModel-Server 是无界面的企业级服务器形态，默认 LAN 可达，支持 SSO、审计、系统服务等企业级能力。默认不允许与桌面版同机并存（端口冲突），但可以通过不同端口和数据目录配置并存。提供 `imodel-server migrate` 命令一键从桌面版迁移。

**Q：iModel-Server 需要联网吗？**
A：代理 LLM API 需要互联网；iModel-web 账号同步也需要网络。但如果 iModel-web 不可达，本地管理员密码可作为兜底继续管理。完全离线（air-gapped）场景需要接入本地 LLM 后端（Ollama / vLLM），这是未来规划中的扩展方向。

**Q：如何从桌面版迁移到 iModel-Server？**
A：运行 `imodel-server migrate <旧数据目录>`，自动备份旧目录、迁移配置与统计数据、转换兼容字段。支持 `--dry-run` 预览和 `--rollback` 回滚。旧数据保留 30 天。

<br>

---

<div align="center">


<br>

# 🧬 爱魔豆 iModel

**让每一次 AI 调用都物超所值**

<br>

[🌐 官方网站](https://imodel.work)
[📖 使用文档](https://docs.imodel.work)
[💬 用户反馈](https://imodel.work/feedback)
[⬇️ 立即下载](https://imodel.work/download)

<br>

*版本 2.0.62 · 支持 macOS / Windows / Linux*
*iModel-Server 企业定制版 · 合作咨询 cooperate@imodel.work*
*如有任何问题，请发送邮件至 support@imodel.work*

<br>

</div>
