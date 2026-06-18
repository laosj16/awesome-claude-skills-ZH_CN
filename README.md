<h1 align="center">Awesome Claude Skills</h1>

<p align="center">
<a href="https://dashboard.composio.dev/login?utm_source=Github&utm_medium=Youtube&utm_campaign=2025-11&utm_content=AwesomeSkills">
  <img width="1280" height="640" alt="Composio banner" src="https://github.com/user-attachments/assets/e91255af-e4ba-4d71-b1a8-bd081e8a234a">
</a>
</p>

<p align="center">
  <a href="https://awesome.re">
    <img src="https://awesome.re/badge.svg" alt="Awesome" />
  </a>
  <a href="https://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="欢迎 PR" />
  </a>
  <a href="https://www.apache.org/licenses/LICENSE-2.0">
    <img src="https://img.shields.io/badge/License-Apache_2.0-blue.svg?style=flat-square" alt="许可证：Apache-2.0" />
  </a>
</p>
<div>
<p align="center">
  <a href="https://twitter.com/composio">
    <img src="https://img.shields.io/badge/关注 X-000000?style=for-the-badge&logo=x&logoColor=white" alt="关注 X" />
  </a>
  <a href="https://www.linkedin.com/company/composiohq/">
    <img src="https://img.shields.io/badge/关注 LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="关注 LinkedIn" />
  </a>
  <a href="https://discord.com/invite/composio">
    <img src="https://img.shields.io/badge/加入 Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="加入 Discord" />
  </a>
  </p>
</div>

<p align="center">
  <a href="./README_us.md">🌐 English</a>
</p>

一份精心整理的 1000+ 个生产可用的实用 Claude Skills 与插件列表，覆盖多种使用场景，不仅适用于 Claude.ai 和 Claude Code，也适用于 Codex、Cursor、Gemini CLI、Antigravity 等各类编程 Agent。

> **想要不止生成文本的技能？** Claude 可以发送邮件、创建 Issue、发布到 Slack，并在 1000+ 个应用中执行真实操作。[了解详情 →](./connect/)

---

## 快速入门：将 Claude 连接到 500+ 个应用

**connect-apps** 插件让 Claude 能够执行真实操作——发送邮件、创建 Issue、发布到 Slack。它通过 Composio 处理身份验证，并连接到 500+ 个应用。

### 1. 安装插件

```bash
claude --plugin-dir ./connect-apps-plugin
```

### 2. 运行配置

```
/connect-apps:setup
```

按提示粘贴你的 API Key。（免费获取：[dashboard.composio.dev](https://dashboard.composio.dev/login?utm_source=Github&utm_content=AwesomeSkills)）

### 3. 重启并试用

```bash
exit
claude
```

> **想要不止生成文本的技能？** Claude 可以发送邮件、创建 Issue、发布到 Slack，并在 1000+ 个应用中执行真实操作。[了解详情 →](./connect/)

如果你收到了邮件，说明 Claude 已成功连接到 500+ 个应用。

**[查看所有支持的应用 →](https://composio.dev/toolkits)**

---

## 目录

- [什么是 Claude Skills？](#什么是-claude-skills)
- [技能列表](#技能列表)
  - [文档处理](#文档处理)
  - [开发与代码工具](#开发与代码工具)
  - [数据与分析](#数据与分析)
  - [商业与营销](#商业与营销)
  - [通信与写作](#通信与写作)
  - [创意与媒体](#创意与媒体)
  - [生产力与组织](#生产力与组织)
  - [协作与项目管理](#协作与项目管理)
  - [安全与系统](#安全与系统)
  - [通过 Composio 实现应用自动化](#通过-composio-实现应用自动化)
- [快速上手](#快速上手)
- [创建技能](#创建技能)
- [参与贡献](#参与贡献)
- [资源](#资源)
- [许可证](#许可证)

## 什么是 Claude Skills？

Claude Skills 是可复用的指令包，教会 AI Agent 如何处理特定类型的任务。每个技能是一个文件夹，包含带有 YAML frontmatter（名称、描述）和 Markdown 指令的 `SKILL.md` 文件，还可以捆绑脚本、参考资料和资产文件。Anthropic 于 2025 年 10 月引入该格式，并于 2025 年 12 月以[开放标准](https://github.com/anthropics/skills)发布；现已被 Claude Code、Claude.ai、Claude API、OpenAI Codex、Cursor、Gemini CLI、Antigravity 和 Windsurf 支持。

技能采用渐进式加载。在会话开始时，Agent 只能看到每个技能的名称和描述——每个技能大约 100 个 token。完整的 `SKILL.md` 正文（通常不超过 5000 个 token）只在 Agent 判断该技能与当前任务相关时才会加载。`scripts/` 和 `references/` 中的辅助文件按需加载。这就是单个 Agent 能托管数百个技能而不撑爆上下文窗口的原因。

技能不是 MCP 服务器，也不是工具。MCP 定义 Agent 如何连接外部系统——身份验证、传输、工具发现。工具是 Agent 调用的具体函数。技能定义工作流——在 Agent 具备所需连接和工具的情况下，做什么、按什么顺序、遵循什么规范。在生产环境中，三层通常一起运行：MCP 负责访问，工具负责执行，技能负责行为。

## 技能列表

### 文档处理

- [docx](https://github.com/anthropics/skills/tree/main/skills/docx) - 创建、编辑、分析 Word 文档，支持修订追踪、注释和格式化。
- [pdf](https://github.com/anthropics/skills/tree/main/skills/pdf) - 提取文本、表格、元数据，合并和标注 PDF。
- [pptx](https://github.com/anthropics/skills/tree/main/skills/pptx) - 读取、生成和调整幻灯片、布局和模板。
- [xlsx](https://github.com/anthropics/skills/tree/main/skills/xlsx) - 电子表格操作：公式、图表、数据转换。
- [Markdown to EPUB Converter](https://github.com/smerchek/claude-epub-skill) - 将 Markdown 文档和聊天摘要转换为专业的 EPUB 电子书文件。*作者 [@smerchek](https://github.com/smerchek)*
- [Master Claude for Legal](https://github.com/sboghossian/master-claude-for-legal) - 法律团队技能包。包含 NDA 审查、多方版本对比、引用验证、会议简报和周五通讯状态综合模式。包含 10 份参考文档和 3 个公司模板。*作者 [@sboghossian](https://github.com/sboghossian)*

### 开发与代码工具

- [artifacts-builder](https://github.com/anthropics/skills/tree/main/skills/web-artifacts-builder) - 使用现代前端技术（React、Tailwind CSS、shadcn/ui）创建复杂多组件 claude.ai HTML Artifact 的工具套件。
- [aws-skills](https://github.com/zxkane/aws-skills) - 使用 CDK 最佳实践进行 AWS 开发，包含成本优化 MCP 服务器和无服务器/事件驱动架构模式。
- [building-blog](https://github.com/BuildShipGrowRepeat/nextjs-sanity-blog-skill) - 通过 40 个问题的引导、一页计划和 20 节规格说明，为 Next.js + Sanity 站点添加支持 SEO 和国际化的博客。*作者 [@BuildShipGrowRepeat](https://github.com/BuildShipGrowRepeat)*
- [Changelog Generator](./changelog-generator/) - 通过分析 git 历史，将技术性提交信息转化为用户友好的发布说明，自动生成面向用户的变更日志。
- [Chrome Relay](https://chrome-relay.kushalsm.com/) - 通过本地 CLI 桥接驱动用户已打开的 Chrome 会话（含 Cookie、SSO、扩展、localhost）。Playwright 浏览器自动化的真实 Chrome 替代方案。
- [Claude Code Terminal Title](https://github.com/bluzername/claude-code-terminal-title) - 为每个 Claude Code 终端窗口提供描述当前工作的动态标题，方便追踪。
- [Connect](./connect/) - 将 Claude 连接到任意应用。发送邮件、创建 Issue、发布消息、更新数据库——跨 Gmail、Slack、GitHub、Notion 和 1000+ 服务执行真实操作。
- [D3.js Visualization](https://github.com/chrisvoncsefalvay/claude-d3js-skill) - 教会 Claude 生成 D3 图表和交互式数据可视化。*作者 [@chrisvoncsefalvay](https://github.com/chrisvoncsefalvay)*
- [FFUF Web Fuzzing](https://github.com/jthack/ffuf_claude_skill) - 集成 ffuf Web 模糊测试工具，让 Claude 可以运行模糊测试任务并分析漏洞结果。*作者 [@jthack](https://github.com/jthack)*
- [finishing-a-development-branch](https://github.com/obra/superpowers/tree/main/skills/finishing-a-development-branch) - 通过呈现清晰选项和处理所选工作流来引导完成开发工作。
- [Full-Page Screenshot](https://github.com/LewisLiu007/full-page-screenshot) - 通过 Chrome DevTools Protocol 零依赖捕获网页全页截图。*作者 [@LewisLiu007](https://github.com/LewisLiu007)*
- [great_cto](https://github.com/avelikiy/great_cto) - Claude Code 插件：7 个专业子 Agent（技术负责人、高级开发、QA 工程师、安全官员、DevOps、L3 支持、项目审计员）编排完整 SDLC 流水线。支持 13 个合规框架（GDPR/PCI-DSS/HIPAA/SOC2/ISO 27001）。*作者 [@avelikiy](https://github.com/avelikiy)*
- [iOS Simulator](https://github.com/conorluddy/ios-simulator-skill) - 让 Claude 与 iOS 模拟器交互，用于测试和调试 iOS 应用。*作者 [@conorluddy](https://github.com/conorluddy)*
- [jules](https://github.com/sanjay3290/ai-skills/tree/main/skills/jules) - 将编码任务委托给 Google Jules AI Agent，在 GitHub 仓库上异步修复 bug、编写文档、测试和实现功能。*作者 [@sanjay3290](https://github.com/sanjay3290)*
- [LangSmith Fetch](./langsmith-fetch/) - 通过自动获取和分析 LangSmith Studio 的执行追踪来调试 LangChain 和 LangGraph Agent。Claude Code 首个 AI 可观测性技能。*作者 [@OthmanAdi](https://github.com/OthmanAdi)*
- [lean-ctx](https://github.com/yvgude/lean-ctx) - AI 编程 Agent 的 MCP 服务器和上下文运行时：会话缓存、AST 感知压缩和 90+ Shell 模式，降低 token 使用量。*作者 [@yvgude](https://github.com/yvgude)*
- [MCP Builder](./mcp-builder/) - 指导使用 Python 或 TypeScript 创建高质量的 MCP（模型上下文协议）服务器，将外部 API 和服务与 LLM 集成。
- [move-code-quality-skill](https://github.com/1NickPappas/move-code-quality-skill) - 根据 Move 2024 Edition 官方代码质量检查清单分析 Move 语言包，检查合规性和最佳实践。
- [OpenWeb](https://github.com/openweb-org/openweb) - Agent 原生的网站访问方式。调用网站自身的 API（JSON 输入/输出），自动解析认证（Cookie、JWT、CSRF、签名）。内置 90+ 个站点。*作者 [@openweb-org](https://github.com/openweb-org)*
- [overkill](https://github.com/santiago-vargas-de-kruijf/claude-overkill) - 为当前讨论的解决方案提供高级、最大化的替代方案——高级数据结构、分布式系统算法、冷门框架、设计模式和前沿工具——每项都带有复杂度评分和适用场景。*作者 [@santiago-vargas-de-kruijf](https://github.com/santiago-vargas-de-kruijf)*
- [Playwright Browser Automation](https://github.com/lackeyjb/playwright-skill) - 模型调用的 Playwright 自动化，用于测试和验证 Web 应用。*作者 [@lackeyjb](https://github.com/lackeyjb)*
- [prompt-engineering](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins/customaize-agent/skills/prompt-engineering) - 教授知名提示词工程技术和模式，包括 Anthropic 最佳实践和 Agent 说服原则。
- [pypict-claude-skill](https://github.com/omkamal/pypict-claude-skill) - 使用 PICT（成对独立组合测试）为需求或代码设计全面的测试用例，生成具有成对覆盖的优化测试套件。
- [reddit-fetch](https://github.com/ykdojo/claude-code-tips/tree/main/skills/reddit-fetch) - 在 WebFetch 被封锁或返回 403 错误时，通过 Gemini CLI 获取 Reddit 内容。
- [Septim Agents Pack](https://septimlabs.com/tools/agents?utm_source=awesome-claude-skills&utm_medium=awesome-list&utm_campaign=oss-backlink) - 10 个命名的 Claude Code 子 Agent，覆盖规划、架构、品牌、营销、财务、设计、法律、客户、研究和协调。*作者 [@septimlabs-code](https://github.com/septimlabs-code)*
- [Skill Creator](./skill-creator/) - 提供创建有效 Claude Skills 的指导，使用专业知识、工作流和工具集成扩展能力。
- [Skill Seekers](https://github.com/yusufkaraaslan/Skill_Seekers) - 几分钟内自动将任意文档网站转换为 Claude AI 技能。*作者 [@yusufkaraaslan](https://github.com/yusufkaraaslan)*
- [software-architecture](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins/ddd/skills/software-architecture) - 实现设计模式，包括整洁架构、SOLID 原则和全面的软件设计最佳实践。
- [subagent-driven-development](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins/sadd/skills/subagent-driven-development) - 为各个任务分派独立子 Agent，在迭代之间进行代码审查检查点，实现快速、受控的开发。
- [test-driven-development](https://github.com/obra/superpowers/tree/main/skills/test-driven-development) - 实现任何功能或修复 bug 前，在编写实现代码之前使用。
- [using-git-worktrees](https://github.com/obra/superpowers/blob/main/skills/using-git-worktrees/) - 创建带有智能目录选择和安全验证的隔离 git worktree。
- [Webapp Testing](./webapp-testing/) - 使用 Playwright 测试本地 Web 应用，验证前端功能、调试 UI 行为和捕获截图。

### 数据与分析

- [CSV Data Summarizer](https://github.com/coffeefuelbump/csv-data-summarizer-claude-skill) - 自动分析 CSV 文件并生成全面的洞察和可视化，无需用户提示。*作者 [@coffeefuelbump](https://github.com/coffeefuelbump)*
- [deep-research](https://github.com/sanjay3290/ai-skills/tree/main/skills/deep-research) - 使用 Gemini Deep Research Agent 执行自主多步研究，用于市场分析、竞争格局和文献综述。*作者 [@sanjay3290](https://github.com/sanjay3290)*
- [postgres](https://github.com/sanjay3290/ai-skills/tree/main/skills/postgres) - 安全地执行只读 SQL 查询，支持多连接和纵深防御。*作者 [@sanjay3290](https://github.com/sanjay3290)*
- [recursive-research](https://github.com/Anjos2/recursive-research) - 在任意领域（科学、技术、商业、艺术、人文）进行博士级递归研究，支持来源分级、WDM + Munger 反向思维和磁盘检查点。*作者 [@Anjos2](https://github.com/Anjos2)*
- [root-cause-tracing](https://github.com/obra/superpowers/tree/main/skills/root-cause-tracing) - 当错误发生在执行深处，需要追溯到原始触发器时使用。

### 商业与营销

- [Brand Build Skills](https://github.com/rampstackco/claude-skills) - 包含 59 个技能的库，覆盖完整的网站生命周期：品牌、设计、内容、SEO、开发、运维、增长和研究。技术栈无关，包含 Ahrefs MCP 驱动的 SEO 审计套件。*作者 [@rampstackco](https://github.com/rampstackco)*
- [Brand Guidelines](./brand-guidelines/) - 将 Anthropic 官方品牌色和字体应用到 Artifact，保持视觉识别一致和专业的设计标准。
- [Competitive Ads Extractor](./competitive-ads-extractor/) - 从广告库中提取和分析竞品广告，理解能引起共鸣的信息和创意方法。
- [Domain Name Brainstormer](./domain-name-brainstormer/) - 生成有创意的域名想法并检查多个 TLD（包括 .com、.io、.dev 和 .ai）的可用性。
- [Internal Comms](./internal-comms/) - 帮助撰写内部通讯，包括 3P 更新、公司通讯、FAQ、状态报告和项目更新，使用公司专有格式。
- [Lead Research Assistant](./lead-research-assistant/) - 通过分析你的产品、搜索目标公司并提供可执行的外联策略，识别和筛选高质量的潜在客户。

### 通信与写作

- [article-extractor](https://github.com/michalparkola/tapestry-skills-for-claude-code/tree/main/article-extractor) - 从网页中提取完整的文章文本和元数据。
- [brainstorming](https://github.com/obra/superpowers/tree/main/skills/brainstorming) - 通过结构化提问和方案探索，将粗略的想法转化为完整的设计。
- [Content Research Writer](./content-research-writer/) - 通过研究、添加引用、改进开头、提供分节反馈来辅助撰写高质量内容。
- [family-history-research](https://github.com/emaynard/claude-family-history-research-skill) - 提供规划家族史和族谱研究项目的帮助。
- [Meeting Insights Analyzer](./meeting-insights-analyzer/) - 分析会议转录文本，揭示行为模式，包括冲突回避、发言比例、口头禅和领导风格。
- [NotebookLM Integration](https://github.com/PleasePrompto/notebooklm-skill) - 让 Claude Code 直接与 NotebookLM 对话，基于上传的文档获得有源依据的答案。*作者 [@PleasePrompto](https://github.com/PleasePrompto)*
- [Twitter Algorithm Optimizer](./twitter-algorithm-optimizer/) - 利用 Twitter 开源算法洞察分析和优化推文以获得最大触达。重写和编辑推文以提高互动和可见度。

### 创意与媒体

- [anydesign](https://github.com/uxKero/anydesign) - 分析任意图片、URL 或 Figma 文件，生成结构化的 `design.md`，包含完整的设计系统、组件清单和重建说明。可移植到 v0、Lovable、Cursor 或任何 AI 构建器。*作者 [@uxKero](https://github.com/uxKero)*
- [Canvas Design](./canvas-design/) - 使用设计哲学和美学原则在 PNG 和 PDF 文档中创作精美的视觉艺术作品，适用于海报、设计和静态作品。
- [imagen](https://github.com/sanjay3290/ai-skills/tree/main/skills/imagen) - 使用 Google Gemini 的图像生成 API 生成 UI 原型、图标、插画和视觉资产。*作者 [@sanjay3290](https://github.com/sanjay3290)*
- [Image Enhancer](./image-enhancer/) - 通过提升分辨率、清晰度和锐度，改善专业演示和文档的图像和截图质量。
- [Slack GIF Creator](./slack-gif-creator/) - 创建针对 Slack 优化的动图，附带尺寸验证器和可组合的动画原语。
- [Theme Factory](./theme-factory/) - 为 Artifact（包括幻灯片、文档、报告和 HTML 落地页）应用专业字体和配色方案，提供 10 个预设主题。
- [Video Downloader](./video-downloader/) - 从 YouTube 和其他平台下载视频用于离线观看、编辑或归档，支持多种格式和质量选项。
- [youtube-transcript](https://github.com/michalparkola/tapestry-skills-for-claude-code/tree/main/youtube-transcript) - 获取 YouTube 视频的转录文本并准备摘要。
- [swiftui-design-skill](https://github.com/wholiver/swiftui-design-skill) - SwiftUI 前端设计 skill — 反 AI Slop 六条铁律、设计方向顾问、品牌资产协议、五维评审。支持 Claude Code / Cursor / Codex / OpenCode 等全部 AI agent 平台。*作者 [@wholiver](https://github.com/wholiver)*
- [Pixelbin-Media-Generation](https://github.com/anandpareek-hub/pixelbin-claude-skill) - 使用 85+ API 组合生成和编辑图片与视频，构建视觉吸引力的网站页面。

### 生产力与组织

- [File Organizer](./file-organizer/) - 通过理解上下文、查找重复文件并建议更好的组织结构，智能整理文件和文件夹。
- [Invoice Organizer](./invoice-organizer/) - 通过读取文件、提取信息和一致重命名，自动整理发票和收据以备税务申报。
- [kaizen](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins/kaizen/skills/kaizen) - 应用持续改进方法论，结合多种分析方法，基于日本 Kaizen 哲学和精益方法论。
- [n8n-skills](https://github.com/haunchen/n8n-skills) - 让 AI 助手直接理解和操作 n8n 工作流。
- [Raffle Winner Picker](./raffle-winner-picker/) - 从列表、电子表格或 Google Sheets 中随机选取抽奖和比赛获奖者，使用密码学安全的随机数。
- [solo-skills](https://github.com/rockscy/solo-skills) - 7 个面向独立创业者和独立开发者的中英双语技能：发布推文、客户邮件、决策框架、复盘。每个技能都包含明确的"何时不使用"章节。
- [Tailored Resume Generator](./tailored-resume-generator/) - 分析职位描述并生成定制化简历，突出相关经验、技能和成就，最大化面试机会。
- [ship-learn-next](https://github.com/michalparkola/tapestry-skills-for-claude-code/tree/main/ship-learn-next) - 帮助基于反馈循环迭代下一步该做什么或学什么。
- [tapestry](https://github.com/michalparkola/tapestry-skills-for-claude-code/tree/main/tapestry) - 将相关文档互联并总结为知识网络。

### 协作与项目管理

- [git-pushing](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/engineering-workflow-plugin/skills/git-pushing) - 自动化 git 操作和仓库交互。
- [google-workspace-skills](https://github.com/sanjay3290/ai-skills/tree/main/skills) - Google Workspace 集成套件：Gmail、日历、Chat、文档、表格、幻灯片和 Drive，支持跨平台 OAuth。*作者 [@sanjay3290](https://github.com/sanjay3290)*
- [mercury-mcp](https://www.teamoffsite.ai/proton/docs/skill) - Mercury（Proton）MCP 工具速查表。在协调的 Agent 团队之间发送 Agent 队友消息、管理线程、创建任务和安排自动化。*作者 [Mercury](https://mercury.build)*
- [outline](https://github.com/sanjay3290/ai-skills/tree/main/skills/outline) - 在 Outline wiki 实例（云端或自托管）中搜索、读取、创建和管理文档。*作者 [@sanjay3290](https://github.com/sanjay3290)*
- [review-implementing](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/engineering-workflow-plugin/skills/review-implementing) - 评估代码实现计划并与规格保持一致。
- [test-fixing](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/engineering-workflow-plugin/skills/test-fixing) - 检测失败的测试并提出补丁或修复方案。

### 安全与系统

- [computer-forensics](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/computer-forensics-skills/skills/computer-forensics) - 数字取证分析和调查技术。
- [file-deletion](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/computer-forensics-skills/skills/file-deletion) - 安全的文件删除和数据清理方法。
- [metadata-extraction](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/computer-forensics-skills/skills/metadata-extraction) - 提取和分析文件元数据用于取证目的。
- [threat-hunting-with-sigma-rules](https://github.com/jthack/threat-hunting-with-sigma-rules-skill) - 使用 Sigma 检测规则狩猎威胁并分析安全事件。

### 辅助技术

- [ASD-AuDHD-PAI-Skills](https://github.com/emory/ASD-AuDHD-PAI-Skills) - 新合集，首个技能 [pda-reframing](https://github.com/emory/ASD-AuDHD-PAI-Skills/blob/main/Skills/pda-reframing/SKILL.md) 可重构请求或决定，帮助克服自闭症谱系障碍中的持续需求回避（PDA），或帮助有 ADHD 难以开始任务的人对齐任务。

### 通过 Composio 实现应用自动化

通过 [Rube MCP（Composio）](https://composio.dev) 为 78 个 SaaS 应用提供预构建的工作流技能。每个技能包含工具序列、参数指南、已知陷阱和快速参考表——全部使用从 Composio API 发现的真实工具标识符。

**CRM 与销售**
- [Close Automation](./close-automation/) - 自动化 Close CRM：线索、联系人、商机、活动和销售管线。
- [HubSpot Automation](./hubspot-automation/) - 自动化 HubSpot CRM：联系人、交易、公司、工单和邮件互动。
- [Pipedrive Automation](./pipedrive-automation/) - 自动化 Pipedrive：交易、联系人、组织、活动和销售管线。
- [Salesforce Automation](./salesforce-automation/) - 自动化 Salesforce：对象、记录、SOQL 查询和批量操作。
- [Zoho CRM Automation](./zoho-crm-automation/) - 自动化 Zoho CRM：线索、联系人、交易、账户和模块。

**项目管理**
- [Asana Automation](./asana-automation/) - 自动化 Asana：任务、项目、章节、分配和工作区。
- [Basecamp Automation](./basecamp-automation/) - 自动化 Basecamp：待办列表、消息、人员、群组和项目。
- [ClickUp Automation](./clickup-automation/) - 自动化 ClickUp：任务、列表、空间、目标和时间追踪。
- [Jira Automation](./jira-automation/) - 自动化 Jira：Issue、项目、看板、Sprint 和 JQL 查询。
- [Linear Automation](./linear-automation/) - 自动化 Linear：Issue、项目、周期、团队和工作流。
- [Monday Automation](./monday-automation/) - 自动化 Monday.com：看板、项目、列、组和工作区。
- [Notion Automation](./notion-automation/) - 自动化 Notion：页面、数据库、块、评论和搜索。
- [Todoist Automation](./todoist-automation/) - 自动化 Todoist：任务、项目、章节、标签和过滤器。
- [Trello Automation](./trello-automation/) - 自动化 Trello：看板、卡片、列表、成员和清单。
- [Wrike Automation](./wrike-automation/) - 自动化 Wrike：任务、文件夹、项目、评论和工作流。

**通信**
- [Discord Automation](./discord-automation/) - 自动化 Discord：消息、频道、服务器、角色和反应。
- [Intercom Automation](./intercom-automation/) - 自动化 Intercom：会话、联系人、公司、工单和文章。
- [Microsoft Teams Automation](./microsoft-teams-automation/) - 自动化 Teams：消息、频道、团队、聊天和会议。
- [Slack Automation](./slack-automation/) - 自动化 Slack：消息、频道、搜索、反应、线程和定时发送。
- [Telegram Automation](./telegram-automation/) - 自动化 Telegram：消息、聊天、媒体、群组和机器人。
- [WhatsApp Automation](./whatsapp-automation/) - 自动化 WhatsApp：消息、媒体、模板、群组和商业资料。

**邮件**
- [Gmail Automation](./gmail-automation/) - 自动化 Gmail：发送/回复、搜索、标签、草稿和附件。
- [Outlook Automation](./outlook-automation/) - 自动化 Outlook：邮件、文件夹、联系人和日历集成。
- [Postmark Automation](./postmark-automation/) - 自动化 Postmark：交易邮件、模板、服务器和投递统计。
- [SendGrid Automation](./sendgrid-automation/) - 自动化 SendGrid：邮件、模板、联系人、列表和活动统计。

**代码与 DevOps**
- [Bitbucket Automation](./bitbucket-automation/) - 自动化 Bitbucket：仓库、PR、分支、Issue 和工作区。
- [CircleCI Automation](./circleci-automation/) - 自动化 CircleCI：流水线、工作流、任务和项目配置。
- [Datadog Automation](./datadog-automation/) - 自动化 Datadog：监控、仪表板、指标、事件和告警。
- [GitHub Automation](./github-automation/) - 自动化 GitHub：Issue、PR、仓库、分支、Action 和代码搜索。
- [GitLab Automation](./gitlab-automation/) - 自动化 GitLab：Issue、MR、项目、流水线和分支。
- [PagerDuty Automation](./pagerduty-automation/) - 自动化 PagerDuty：事件、服务、排班、升级策略和值班。
- [Render Automation](./render-automation/) - 自动化 Render：服务、部署和项目管理。
- [Sentry Automation](./sentry-automation/) - 自动化 Sentry：Issue、事件、项目、版本和告警。
- [Supabase Automation](./supabase-automation/) - 自动化 Supabase：SQL 查询、表结构、Edge Function 和存储。
- [Vercel Automation](./vercel-automation/) - 自动化 Vercel：部署、项目、域名、环境变量和日志。

**存储与文件**
- [Box Automation](./box-automation/) - 自动化 Box：文件、文件夹、搜索、共享、协作和签名请求。
- [Dropbox Automation](./dropbox-automation/) - 自动化 Dropbox：文件、文件夹、搜索、共享和批量操作。
- [Google Drive Automation](./google-drive-automation/) - 自动化 Google Drive：上传、下载、搜索、共享和组织文件。
- [OneDrive Automation](./one-drive-automation/) - 自动化 OneDrive：文件、文件夹、搜索、共享、权限和版本管理。

**电子表格与数据库**
- [Airtable Automation](./airtable-automation/) - 自动化 Airtable：记录、表格、Base、视图和字段管理。
- [Coda Automation](./coda-automation/) - 自动化 Coda：文档、表格、行、公式和自动化。
- [Google Sheets Automation](./googlesheets-automation/) - 自动化 Google Sheets：读写单元格、格式化、公式和批量操作。

**日历与排期**
- [Cal.com Automation](./cal-com-automation/) - 自动化 Cal.com：事件类型、预订、可用性和排期。
- [Calendly Automation](./calendly-automation/) - 自动化 Calendly：事件、被邀请人、事件类型、排期链接和可用性。
- [Google Calendar Automation](./google-calendar-automation/) - 自动化 Google 日历：事件、参与者、忙闲和重复日程。
- [Outlook Calendar Automation](./outlook-calendar-automation/) - 自动化 Outlook 日历：事件、参与者、提醒和重复日程。

**社交媒体**
- [Instagram Automation](./instagram-automation/) - 自动化 Instagram：帖子、Story、评论、媒体和商业洞察。
- [LinkedIn Automation](./linkedin-automation/) - 自动化 LinkedIn：帖子、个人资料、公司、图片和评论。
- [Reddit Automation](./reddit-automation/) - 自动化 Reddit：帖子、评论、Subreddit、投票和管理。
- [TikTok Automation](./tiktok-automation/) - 自动化 TikTok：视频上传、查询和创作者管理。
- [Twitter Automation](./twitter-automation/) - 自动化 Twitter/X：推文、搜索、用户、列表和互动。
- [YouTube Automation](./youtube-automation/) - 自动化 YouTube：视频、频道、播放列表、评论和订阅。

**营销与邮件营销**
- [ActiveCampaign Automation](./activecampaign-automation/) - 自动化 ActiveCampaign：联系人、交易、活动、列表和自动化。
- [Brevo Automation](./brevo-automation/) - 自动化 Brevo：联系人、邮件营销、交易邮件和列表。
- [ConvertKit Automation](./convertkit-automation/) - 自动化 ConvertKit (Kit)：订阅者、标签、序列、广播和表单。
- [Klaviyo Automation](./klaviyo-automation/) - 自动化 Klaviyo：用户档案、列表、分群、活动和事件。
- [Mailchimp Automation](./mailchimp-automation/) - 自动化 Mailchimp：受众、活动、模板、分群和报告。

**支持与工单**
- [Freshdesk Automation](./freshdesk-automation/) - 自动化 Freshdesk：工单、联系人、客服、群组和预设回复。
- [Freshservice Automation](./freshservice-automation/) - 自动化 Freshservice：工单、资产、变更、问题和服务目录。
- [Help Scout Automation](./helpdesk-automation/) - 自动化 Help Scout：会话、客户、邮箱和标签。
- [Zendesk Automation](./zendesk-automation/) - 自动化 Zendesk：工单、用户、组织、搜索和宏。

**电商与支付**
- [Shopify Automation](./shopify-automation/) - 自动化 Shopify：商品、订单、客户、库存和 GraphQL 查询。
- [Square Automation](./square-automation/) - 自动化 Square：支付、客户、目录、订单和门店。
- [Stripe Automation](./stripe-automation/) - 自动化 Stripe：支付、客户、商品、订阅和退款。

**设计与协作**
- [Canva Automation](./canva-automation/) - 自动化 Canva：设计、模板、资产、文件夹和品牌套件。
- [Confluence Automation](./confluence-automation/) - 自动化 Confluence：页面、空间、搜索、CQL、标签和版本。
- [DocuSign Automation](./docusign-automation/) - 自动化 DocuSign：信封、模板、签署和文档管理。
- [Figma Automation](./figma-automation/) - 自动化 Figma：文件、组件、评论、项目和团队管理。
- [Miro Automation](./miro-automation/) - 自动化 Miro：看板、便签、形状、连接器和项目。
- [Webflow Automation](./webflow-automation/) - 自动化 Webflow：CMS 集合、项目、站点、发布和资产。

**分析与数据**
- [Amplitude Automation](./amplitude-automation/) - 自动化 Amplitude：事件、分群、用户属性和分析查询。
- [Google Analytics Automation](./google-analytics-automation/) - 自动化 Google Analytics：报告、维度、指标和资源管理。
- [Mixpanel Automation](./mixpanel-automation/) - 自动化 Mixpanel：事件、漏斗、分群、注解和 JQL 查询。
- [PostHog Automation](./posthog-automation/) - 自动化 PostHog：事件、用户、特性开关、洞察和注解。
- [Segment Automation](./segment-automation/) - 自动化 Segment：源、目标、追踪和数据仓库连接。

**人力资源**
- [BambooHR Automation](./bamboohr-automation/) - 自动化 BambooHR：员工、休假、报告和通讯录管理。

**自动化平台**
- [Make Automation](./make-automation/) - 自动化 Make (Integromat)：场景、连接和执行管理。

**Zoom 与会议**
- [Zoom Automation](./zoom-automation/) - 自动化 Zoom：会议、录制、参与者、Webinar 和报告。

## 快速上手

### 在 Claude.ai 中使用技能

1. 在聊天界面点击技能图标（🧩）。
2. 从市场添加技能或上传自定义技能。
3. Claude 会基于你的任务自动激活相关技能。

### 在 Claude Code 中使用技能

1. 将技能放到 `~/.config/claude-code/skills/`：
   ```bash
   mkdir -p ~/.config/claude-code/skills/
   cp -r skill-name ~/.config/claude-code/skills/
   ```

2. 验证技能元数据：
   ```bash
   head ~/.config/claude-code/skills/skill-name/SKILL.md
   ```

3. 启动 Claude Code：
   ```bash
   claude
   ```

4. 技能会自动加载并在相关时激活。

### 通过 API 使用技能

使用 Claude Skills API 以编程方式加载和管理技能：

```python
import anthropic

client = anthropic.Anthropic(api_key="your-api-key")

response = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    skills=["skill-id-here"],
    messages=[{"role": "user", "content": "Your prompt"}]
)
```

详见 [Skills API 文档](https://docs.claude.com/en/api/skills-guide)。

## 创建技能

### 技能结构

每个技能是一个文件夹，包含带 YAML frontmatter 的 `SKILL.md` 文件：

```
skill-name/
├── SKILL.md          # 必需：技能说明和元数据
├── scripts/          # 可选：辅助脚本
├── templates/        # 可选：文档模板
└── resources/        # 可选：参考文件
```

### 基础技能模板

```markdown
---
name: my-skill-name
description: 清晰描述这个技能的功能和使用场景。
---

# 我的技能名称

详细描述技能的目的和能力。

## 何时使用此技能

- 使用场景 1
- 使用场景 2
- 使用场景 3

## 指令

[给 Claude 的详细执行指令]

## 示例

[展示技能实际效果的真实示例]
```

### 技能最佳实践

- 聚焦于具体、可重复的任务
- 包含清晰的示例和边界情况
- 为 Claude 编写指令，而不是为最终用户
- 在 Claude.ai、Claude Code 和 API 三个平台上测试
- 记录前置条件和依赖
- 包含错误处理指引

## 参与贡献

我们欢迎贡献！请阅读[贡献指南](CONTRIBUTING.md)了解：

- 如何提交新技能
- 技能质量标准
- Pull Request 流程
- 行为准则

### 快速贡献步骤

1. 确保你的技能基于真实使用场景
2. 检查现有技能中是否有重复
3. 遵循技能结构模板
4. 在多个平台上测试你的技能
5. 提交带有清晰文档的 Pull Request

## 资源

### 官方文档

- [Claude Skills 概览](https://www.anthropic.com/news/skills) - 官方公告与特性
- [Skills 用户指南](https://support.claude.com/en/articles/12512180-using-skills-in-claude) - 如何在 Claude 中使用技能
- [创建自定义技能](https://support.claude.com/en/articles/12512198-creating-custom-skills) - 技能开发指南
- [Skills API 文档](https://docs.claude.com/en/api/skills-guide) - API 集成指南
- [Agent Skills 博客文章](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) - 工程深度解析

### 社区资源

- [Anthropic Skills 仓库](https://github.com/anthropics/skills) - 官方示例技能
- [Claude 社区](https://community.anthropic.com) - 与其他用户讨论技能
- [Skills Marketplace](https://claude.ai/marketplace) - 发现和分享技能

### 灵感与用例

- [Lenny's Newsletter](https://www.lennysnewsletter.com/p/everyone-should-be-using-claude-code) - 50 种使用 Claude Code 的方式
- [Notion Skills](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0) - Notion 集成技能
- [Top Claude Skills](https://composio.dev/content/top-claude-skills)


## 加入社区

- [加入我们的 Discord](https://discord.com/invite/composio) - 与其他构建 Claude Skills 的开发者交流
- [在 Twitter/X 上关注](https://x.com/composio) - 获取新技能和功能更新
- 有问题？[support@composio.dev](mailto:support@composio.dev)

---

<p align="center">
  <b>加入 20,000+ 名构建可交付 Agent 的开发者</b>
</p>

<p align="center">
  <a href="https://platform.composio.dev/?utm_source=Github&utm_content=AwesomeSkills">
    <img src="https://img.shields.io/badge/免费开始使用-4F46E5?style=for-the-badge" alt="开始使用"/>
  </a>
</p>

## 许可证

本仓库采用 Apache License 2.0 许可证。

各个技能可能使用不同的许可证——请检查每个技能文件夹中的具体许可证信息。

---

**注意**：Claude Skills 在 Claude.ai、Claude Code 和 Claude API 中通用。一旦创建了技能，它就可以跨所有平台移植，让你的工作流在任何使用 Claude 的地方保持一致。

- [AgentsKB](https://agentskb.com) - 通过研究过的答案升级你的 AI。我们替你做了研究，让你的 AI 第一次就答对。
