# AI Context Pack

## Pack Identity

- Upstream: https://github.com/doobidoo/mcp-memory-service
- Pack type: MCP Memory Service Pack
- Doramagic canonical: https://doramagic.ai/projects/mcp-memory-service/
- Relationship: independent pack; not affiliated or endorsed unless explicitly stated.

## Operating Rules

- Evidence first.
- No official endorsement claim.
- Run evals before claiming success.
- Use pitfall and risk files for recovery.

## Host Files

- `../AGENTS.md`
- `../CLAUDE.md`

## Doramagic Source Extract

# mcp-bridge-tests - Doramagic AI Context Pack

> 定位：安装前体验与判断资产。它帮助宿主 AI 有一个好的开始，但不代表已经安装、执行或验证目标项目。

## 充分原则

- **充分原则，不是压缩原则**：AI Context Pack 应该充分到让宿主 AI 在开工前理解项目价值、能力边界、使用入口、风险和证据来源；它可以分层组织，但不以最短摘要为目标。
- **压缩策略**：只压缩噪声和重复内容，不压缩会影响判断和开工质量的上下文。

## 给宿主 AI 的使用方式

你正在读取 Doramagic 为 mcp-bridge-tests 编译的 AI Context Pack。请把它当作开工前上下文：帮助用户理解适合谁、能做什么、如何开始、哪些必须安装后验证、风险在哪里。不要声称你已经安装、运行或执行了目标项目。

## Claim 消费规则

- **事实来源**：Repo Evidence + Claim/Evidence Graph；Human Wiki 只提供显著性、术语和叙事结构。
- **事实最低状态**：`supported`
- `supported`：可以作为项目事实使用，但回答中必须引用 claim_id 和证据路径。
- `weak`：只能作为低置信度线索，必须要求用户继续核实。
- `inferred`：只能用于风险提示或待确认问题，不能包装成项目事实。
- `unverified`：不得作为事实使用，应明确说证据不足。
- `contradicted`：必须展示冲突来源，不得替用户强行选择一个版本。

## 它最适合谁

- **正在使用 Claude/Codex/Cursor/Gemini 等宿主 AI 的开发者**：README 或插件配置提到多个宿主 AI。 证据：`README.md` Claim：`clm_0004` supported 0.86
- **希望把专业流程带进宿主 AI 的用户**：仓库包含 Skill 文档。 证据：`.claude/skills/gitnexus/debugging/SKILL.md`, `.claude/skills/gitnexus/exploring/SKILL.md`, `.claude/skills/gitnexus/impact-analysis/SKILL.md`, `.claude/skills/gitnexus/refactoring/SKILL.md` Claim：`clm_0005` supported 0.86

## 它能做什么

- **AI Skill / Agent 指令资产库**（可做安装前预览）：项目包含可被宿主 AI 读取的 Skill 或 Agent 指令文件，可用于把专业流程带入 Claude、Codex、Cursor 等宿主。 证据：`.claude/skills/gitnexus/debugging/SKILL.md`, `.claude/skills/gitnexus/exploring/SKILL.md`, `.claude/skills/gitnexus/impact-analysis/SKILL.md`, `.claude/skills/gitnexus/refactoring/SKILL.md` Claim：`clm_0001` supported 0.86
- **多宿主安装与分发**（需要安装后验证）：项目包含插件或 marketplace 配置，说明它面向一个或多个 AI 宿主的安装和分发。 证据：`.claude-plugin/marketplace.json`, `claude-hooks/.claude-plugin/plugin.json` Claim：`clm_0002` supported 0.86
- **命令行启动或安装流程**（需要安装后验证）：项目文档中存在可执行命令，真实使用需要在本地或宿主环境中运行这些命令。 证据：`CLAUDE.md`, `README.md` Claim：`clm_0003` supported 0.86

## 怎么开始

- `pip install mcp-memory-service` 证据：`README.md` Claim：`clm_0006` supported 0.86
- `claude mcp add memory -- memory server` 证据：`README.md` Claim：`clm_0007` supported 0.86
- `git clone https://github.com/doobidoo/mcp-memory-service.git` 证据：`README.md` Claim：`clm_0008` supported 0.86
- `pip install -e .  # Editable install` 证据：`README.md` Claim：`clm_0009` supported 0.86
- `pip install -e .` 证据：`CLAUDE.md` Claim：`clm_0009` supported 0.86, `clm_0010` supported 0.86, `clm_0011` supported 0.86, `clm_0012` supported 0.86 等
- `pip install -e ".[full]"      # All features` 证据：`CLAUDE.md` Claim：`clm_0011` supported 0.86
- `pip install -e ".[sqlite]"    # SQLite with ONNX only` 证据：`CLAUDE.md` Claim：`clm_0012` supported 0.86
- `pip install -e ".[ml]"        # Full ML capabilities` 证据：`CLAUDE.md` Claim：`clm_0013` supported 0.86
- `curl http://127.0.0.1:8000/api/health` 证据：`CLAUDE.md` Claim：`clm_0014` supported 0.86

## 继续前判断卡

- **当前建议**：需要管理员/安全审批
- **为什么**：继续前可能涉及密钥、账号、外部服务或敏感上下文，建议先经过管理员或安全审批。

### 30 秒判断

- **现在怎么做**：需要管理员/安全审批
- **最小安全下一步**：先跑 Prompt Preview；若涉及凭证或企业环境，先审批再试装
- **先别相信**：工具权限边界不能在安装前相信。
- **继续会触碰**：命令执行、宿主 AI 配置、本地环境或项目文件

### 现在可以相信

- **适合人群线索：正在使用 Claude/Codex/Cursor/Gemini 等宿主 AI 的开发者**（supported）：有 supported claim 或项目证据支撑，但仍不等于真实安装效果。 证据：`README.md` Claim：`clm_0004` supported 0.86
- **适合人群线索：希望把专业流程带进宿主 AI 的用户**（supported）：有 supported claim 或项目证据支撑，但仍不等于真实安装效果。 证据：`.claude/skills/gitnexus/debugging/SKILL.md`, `.claude/skills/gitnexus/exploring/SKILL.md`, `.claude/skills/gitnexus/impact-analysis/SKILL.md`, `.claude/skills/gitnexus/refactoring/SKILL.md` Claim：`clm_0005` supported 0.86
- **能力存在：AI Skill / Agent 指令资产库**（supported）：可以相信项目包含这类能力线索；是否适合你的具体任务仍要试用或安装后验证。 证据：`.claude/skills/gitnexus/debugging/SKILL.md`, `.claude/skills/gitnexus/exploring/SKILL.md`, `.claude/skills/gitnexus/impact-analysis/SKILL.md`, `.claude/skills/gitnexus/refactoring/SKILL.md` Claim：`clm_0001` supported 0.86
- **能力存在：多宿主安装与分发**（supported）：可以相信项目包含这类能力线索；是否适合你的具体任务仍要试用或安装后验证。 证据：`.claude-plugin/marketplace.json`, `claude-hooks/.claude-plugin/plugin.json` Claim：`clm_0002` supported 0.86
- **能力存在：命令行启动或安装流程**（supported）：可以相信项目包含这类能力线索；是否适合你的具体任务仍要试用或安装后验证。 证据：`CLAUDE.md`, `README.md` Claim：`clm_0003` supported 0.86
- **存在 Quick Start / 安装命令线索**（supported）：可以相信项目文档出现过启动或安装入口；不要因此直接在主力环境运行。 证据：`README.md` Claim：`clm_0006` supported 0.86

### 现在还不能相信

- **工具权限边界不能在安装前相信。**（unverified）：MCP/tool 类项目通常会触碰文件、网络、浏览器或外部 API，必须真实检查权限和日志。
- **真实输出质量不能在安装前相信。**（unverified）：Prompt Preview 只能展示引导方式，不能证明真实项目中的结果质量。
- **宿主 AI 版本兼容性不能在安装前相信。**（unverified）：Claude、Cursor、Codex、Gemini 等宿主加载规则和版本差异必须在真实环境验证。
- **不会污染现有宿主 AI 行为，不能直接相信。**（inferred）：Skill、plugin、AGENTS/CLAUDE/GEMINI 指令可能改变宿主 AI 的默认行为。 证据：`.claude-plugin/marketplace.json`, `.claude/skills/gitnexus/debugging/SKILL.md`, `.claude/skills/gitnexus/exploring/SKILL.md`, `.claude/skills/gitnexus/impact-analysis/SKILL.md` 等
- **可安全回滚不能默认相信。**（unverified）：除非项目明确提供卸载和恢复说明，否则必须先在隔离环境验证。
- **真实安装后是否与用户当前宿主 AI 版本兼容？**（unverified）：兼容性只能通过实际宿主环境验证。 证据：`.claude-plugin/marketplace.json`, `claude-hooks/.claude-plugin/plugin.json`
- **项目输出质量是否满足用户具体任务？**（unverified）：安装前预览只能展示流程和边界，不能替代真实评测。
- **安装命令是否需要网络、权限或全局写入？**（unverified）：这影响企业环境和个人环境的安装风险。 证据：`README.md`

### 继续会触碰什么

- **命令执行**：包管理器、网络下载、本地插件目录、项目配置或用户主目录。 原因：运行第一条命令就可能产生环境改动；必须先判断是否值得跑。 证据：`CLAUDE.md`, `README.md`
- **宿主 AI 配置**：Claude/Codex/Cursor/Gemini/OpenCode 等宿主的 plugin、Skill 或规则加载配置。 原因：宿主配置会改变 AI 后续工作方式，可能和用户已有规则冲突。 证据：`.claude-plugin/marketplace.json`, `.claude/skills/gitnexus/debugging/SKILL.md`, `.claude/skills/gitnexus/exploring/SKILL.md`, `.claude/skills/gitnexus/impact-analysis/SKILL.md` 等
- **本地环境或项目文件**：安装结果、插件缓存、项目配置或本地依赖目录。 原因：安装前无法证明写入范围和回滚方式，需要隔离验证。 证据：`.claude-plugin/marketplace.json`, `CLAUDE.md`, `README.md`, `claude-hooks/.claude-plugin/plugin.json`
- **环境变量 / API Key**：项目入口文档明确出现 API key、token、secret 或账号凭证配置。 原因：如果真实安装需要凭证，应先使用测试凭证并经过权限/合规判断。 证据：`.claude/directives/storage-backends.md`, `CLAUDE.md`, `archive/docs-root-cleanup-2025-08-23/CLOUDFLARE_IMPLEMENTATION.md`, `archive/docs-root-cleanup-2025-08-23/README-ORIGINAL-BACKUP.md` 等
- **宿主 AI 上下文**：AI Context Pack、Prompt Preview、Skill 路由、风险规则和项目事实。 原因：导入上下文会影响宿主 AI 后续判断，必须避免把未验证项包装成事实。

### 最小安全下一步

- **先跑 Prompt Preview**：用安装前交互式试用判断工作方式是否匹配，不需要授权或改环境。（适用：任何项目都适用，尤其是输出质量未知时。）
- **只在隔离目录或测试账号试装**：避免安装命令污染主力宿主 AI、真实项目或用户主目录。（适用：存在命令执行、插件配置或本地写入线索时。）
- **先备份宿主 AI 配置**：Skill、plugin、规则文件可能改变 Claude/Cursor/Codex 的默认行为。（适用：存在插件 manifest、Skill 或宿主规则入口时。）
- **不要使用真实生产凭证**：环境变量/API key 一旦进入宿主或工具链，可能产生账号和合规风险。（适用：出现 API、TOKEN、KEY、SECRET 等环境线索时。）
- **安装后只验证一个最小任务**：先验证加载、兼容、输出质量和回滚，再决定是否深用。（适用：准备从试用进入真实工作流时。）

### 退出方式

- **保留安装前状态**：记录原始宿主配置和项目状态，后续才能判断是否可恢复。
- **准备移除宿主 plugin / Skill / 规则入口**：如果试装后行为异常，可以把宿主 AI 恢复到试装前状态。
- **记录安装命令和写入路径**：没有明确卸载说明时，至少要知道哪些目录或配置需要手动清理。
- **准备撤销测试 API key 或 token**：测试凭证泄露或误用时，可以快速止损。
- **如果没有回滚路径，不进入主力环境**：不可回滚是继续前阻断项，不应靠信任或运气继续。

## 哪些只能预览

- 解释项目适合谁和能做什么
- 基于项目文档演示典型对话流程
- 帮助用户判断是否值得安装或继续研究

## 哪些必须安装后验证

- 真实安装 Skill、插件或 CLI
- 执行脚本、修改本地文件或访问外部服务
- 验证真实输出质量、性能和兼容性

## 边界与风险判断卡

- **把安装前预览误认为真实运行**：用户可能高估项目已经完成的配置、权限和兼容性验证。 处理方式：明确区分 prompt_preview_can_do 与 runtime_required。 Claim：`clm_0015` inferred 0.45
- **宿主 AI 插件或 Skill 规则冲突**：新规则可能改变用户现有宿主 AI 的工作方式。 处理方式：安装前先检查插件 manifest 和 Skill 文件，必要时隔离测试。 证据：`.claude-plugin/marketplace.json`, `claude-hooks/.claude-plugin/plugin.json` Claim：`clm_0016` supported 0.86
- **命令执行会修改本地环境**：安装命令可能写入用户主目录、宿主插件目录或项目配置。 处理方式：先在隔离环境或测试账号中运行。 证据：`CLAUDE.md`, `README.md` Claim：`clm_0017` supported 0.86
- **待确认**：真实安装后是否与用户当前宿主 AI 版本兼容？。原因：兼容性只能通过实际宿主环境验证。
- **待确认**：项目输出质量是否满足用户具体任务？。原因：安装前预览只能展示流程和边界，不能替代真实评测。
- **待确认**：安装命令是否需要网络、权限或全局写入？。原因：这影响企业环境和个人环境的安装风险。

## 开工前工作上下文

### 加载顺序

- 先读取 how_to_use.host_ai_instruction，建立安装前判断资产的边界。
- 读取 claim_graph_summary，确认事实来自 Claim/Evidence Graph，而不是 Human Wiki 叙事。
- 再读取 intended_users、capabilities 和 quick_start_candidates，判断用户是否匹配。
- 需要执行具体任务时，优先查 role_skill_index，再查 evidence_index。
- 遇到真实安装、文件修改、网络访问、性能或兼容性问题时，转入 risk_card 和 boundaries.runtime_required。

### 任务路由

- **AI Skill / Agent 指令资产库**：先基于 role_skill_index / evidence_index 帮用户挑选可用角色、Skill 或工作流。 边界：可做安装前 Prompt 体验。 证据：`.claude/skills/gitnexus/debugging/SKILL.md`, `.claude/skills/gitnexus/exploring/SKILL.md`, `.claude/skills/gitnexus/impact-analysis/SKILL.md`, `.claude/skills/gitnexus/refactoring/SKILL.md` Claim：`clm_0001` supported 0.86
- **多宿主安装与分发**：先说明这是安装后验证能力，再给出安装前检查清单。 边界：必须真实安装或运行后验证。 证据：`.claude-plugin/marketplace.json`, `claude-hooks/.claude-plugin/plugin.json` Claim：`clm_0002` supported 0.86
- **命令行启动或安装流程**：先说明这是安装后验证能力，再给出安装前检查清单。 边界：必须真实安装或运行后验证。 证据：`CLAUDE.md`, `README.md` Claim：`clm_0003` supported 0.86

### 上下文规模

- 文件总数：1112
- 重要文件覆盖：40/1112
- 证据索引条目：80
- 角色 / Skill 条目：4

### 证据不足时的处理

- **missing_evidence**：说明证据不足，要求用户提供目标文件、README 段落或安装后验证记录；不要补全事实。
- **out_of_scope_request**：说明该任务超出当前 AI Context Pack 证据范围，并建议用户先查看 Human Manual 或真实安装后验证。
- **runtime_request**：给出安装前检查清单和命令来源，但不要替用户执行命令或声称已执行。
- **source_conflict**：同时展示冲突来源，标记为待核实，不要强行选择一个版本。

## Prompt Recipes

### 适配判断

- 目标：判断这个项目是否适合用户当前任务。
- 预期输出：适配结论、关键理由、证据引用、安装前可预览内容、必须安装后验证内容、下一步建议。

```text
请基于 mcp-bridge-tests 的 AI Context Pack，先问我 3 个必要问题，然后判断它是否适合我的任务。回答必须包含：适合谁、能做什么、不能做什么、是否值得安装、证据来自哪里。所有项目事实必须引用 evidence_refs、source_paths 或 claim_id。
```

### 安装前体验

- 目标：让用户在安装前感受核心工作流，同时避免把预览包装成真实能力或营销承诺。
- 预期输出：一段带边界标签的体验剧本、安装后验证清单和谨慎建议；不含真实运行承诺或强营销表述。

```text
请把 mcp-bridge-tests 当作安装前体验资产，而不是已安装工具或真实运行环境。

请严格输出四段：
1. 先问我 3 个必要问题。
2. 给出一段“体验剧本”：用 [安装前可预览]、[必须安装后验证]、[证据不足] 三种标签展示它可能如何引导工作流。
3. 给出安装后验证清单：列出哪些能力只有真实安装、真实宿主加载、真实项目运行后才能确认。
4. 给出谨慎建议：只能说“值得继续研究/试装”“先补充信息后再判断”或“不建议继续”，不得替项目背书。

硬性边界：
- 不要声称已经安装、运行、执行测试、修改文件或产生真实结果。
- 不要写“自动适配”“确保通过”“完美适配”“强烈建议安装”等承诺性表达。
- 如果描述安装后的工作方式，必须使用“如果安装成功且宿主正确加载 Skill，它可能会……”这种条件句。
- 体验剧本只能写成“示例台词/假设流程”：使用“可能会询问/可能会建议/可能会展示”，不要写“已写入、已生成、已通过、正在运行、正在生成”。
- Prompt Preview 不负责给安装命令；如用户准备试装，只能提示先阅读 Quick Start 和 Risk Card，并在隔离环境验证。
- 所有项目事实必须来自 supported claim、evidence_refs 或 source_paths；inferred/unverified 只能作风险或待确认项。

```

### 角色 / Skill 选择

- 目标：从项目里的角色或 Skill 中挑选最匹配的资产。
- 预期输出：候选角色或 Skill 列表，每项包含适用场景、证据路径、风险边界和是否需要安装后验证。

```text
请读取 role_skill_index，根据我的目标任务推荐 3-5 个最相关的角色或 Skill。每个推荐都要说明适用场景、可能输出、风险边界和 evidence_refs。
```

### 风险预检

- 目标：安装或引入前识别环境、权限、规则冲突和质量风险。
- 预期输出：环境、权限、依赖、许可、宿主冲突、质量风险和未知项的检查清单。

```text
请基于 risk_card、boundaries 和 quick_start_candidates，给我一份安装前风险预检清单。不要替我执行命令，只说明我应该检查什么、为什么检查、失败会有什么影响。
```

### 宿主 AI 开工指令

- 目标：把项目上下文转成一次对话开始前的宿主 AI 指令。
- 预期输出：一段边界明确、证据引用明确、适合复制给宿主 AI 的开工前指令。

```text
请基于 mcp-bridge-tests 的 AI Context Pack，生成一段我可以粘贴给宿主 AI 的开工前指令。这段指令必须遵守 not_runtime=true，不能声称项目已经安装、运行或产生真实结果。
```


## 角色 / Skill 索引

- 共索引 4 个角色 / Skill / 项目文档条目。

- **gitnexus-debugging**（skill）：Trace bugs through call chains using knowledge graph 激活提示：当用户任务与“gitnexus-debugging”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.claude/skills/gitnexus/debugging/SKILL.md`
- **gitnexus-exploring**（skill）：Navigate unfamiliar code using GitNexus knowledge graph 激活提示：当用户任务与“gitnexus-exploring”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.claude/skills/gitnexus/exploring/SKILL.md`
- **gitnexus-impact-analysis**（skill）：Analyze blast radius before making code changes 激活提示：当用户任务与“gitnexus-impact-analysis”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.claude/skills/gitnexus/impact-analysis/SKILL.md`
- **gitnexus-refactoring**（skill）：Plan safe refactors using blast radius and dependency mapping 激活提示：当用户任务与“gitnexus-refactoring”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.claude/skills/gitnexus/refactoring/SKILL.md`

## 证据索引

- 共索引 80 条证据。

- **MCP Memory Service Documentation**（documentation）：Welcome to the comprehensive documentation for MCP Memory Service - a Model Context Protocol server that provides semantic memory and persistent storage capabilities for Claude Desktop and other MCP clients. 证据：`docs/README.md`
- **Agent Integration Guides**（documentation）：mcp-memory-service provides persistent shared memory for multi-agent systems via a framework-agnostic REST API . No MCP client library required — any HTTP client works. 证据：`docs/agents/README.md`
- **Obsolete Workflows Archive**（documentation）：This directory contains historical documentation of workflows that have been superseded by better, automated solutions. 证据：`docs/archive/obsolete-workflows/README.md`
- **MCP Memory Service Screenshots**（documentation）：This directory contains screenshots and visual assets for the MCP Memory Service documentation. 证据：`docs/assets/images/README.md`
- **MCP Memory Service - Agent Guidelines**（documentation）：MCP Memory Service - Agent Guidelines 证据：`docs/guides/AGENTS.md`
- **Gemini Context: MCP Memory Service**（documentation）：This project is a sophisticated and feature-rich MCP Memory Component Protocol server designed to provide a persistent, semantic memory layer for AI assistants, particularly "Claude Desktop". It's built with Python and leverages a variety of technologies to deliver a robust and performant memory service. 证据：`docs/integrations/gemini.md`
- **GitNexus MCP**（documentation）：This project is indexed by GitNexus as mcp-memory-service 6259 symbols, 18031 relationships, 300 execution flows . 证据：`AGENTS.md`
- **CLAUDE.md**（documentation）：This file provides guidance to Claude Code claude.ai/code when working with this MCP Memory Service repository. 证据：`CLAUDE.md`
- **mcp-memory-service**（documentation）：Persistent Shared Memory for AI Agent Pipelines 证据：`README.md`
- **Claude Code Memory Awareness Hooks**（documentation）：Automatic memory awareness and intelligent context injection for Claude Code using the MCP Memory Service. 证据：`claude-hooks/README.md`
- **Claude Code Commands for MCP Memory Service**（documentation）：Claude Code Commands for MCP Memory Service 证据：`claude_commands/README.md`
- **MCP Memory Service Examples**（documentation）：This directory contains example configurations, scripts, and setup utilities for deploying MCP Memory Service in various scenarios. 证据：`examples/README.md`
- **OpenCode Memory Awareness Plugin**（documentation）：Automatic memory retrieval and context injection for OpenCode using the mcp-memory-service HTTP API. 证据：`opencode/README.md`
- **MCP Memory Service Scripts**（documentation）：This directory contains organized utility scripts for maintaining, managing, and operating the MCP Memory Service. Scripts are categorized by function for easy navigation and maintenance. 证据：`scripts/README.md`
- **MCP-MEMORY-SERVICE Tests**（documentation）：This directory contains tests for the MCP-MEMORY-SERVICE project. 证据：`tests/README.md`
- **Development Tools and Utilities**（documentation）：This directory contains development tools, build utilities, and deployment configurations for MCP Memory Service. 证据：`tools/README.md`
- **MCP Memory Service - Technical Showcase Video**（documentation）：MCP Memory Service - Technical Showcase Video 证据：`video/README.md`
- **Claude Code Commands**（documentation）：Custom slash commands for mcp-memory-service development. 证据：`.claude/commands/README.md`
- **Claude Code Directives**（documentation）：This directory contains modular directive files that supplement CLAUDE.md with specific behavioral rules and conventions. 证据：`.claude/directives/README.md`
- **Agent Integrations - Detailed Usage**（documentation）：Agent Integrations - Detailed Usage 证据：`.claude/directives/agents.md`
- **Tool Optimization - Execution Guide**（documentation）：Tool Optimization - Execution Guide 证据：`archive/docs-root-cleanup-2026-04-02/tasks-tool-optimization/CLAUDE.md`
- **MCP Memory Service - Tool Optimization Plan**（documentation）：MCP Memory Service - Tool Optimization Plan 证据：`archive/docs-root-cleanup-2026-04-02/tasks-tool-optimization/README.md`
- **Development Files Archive**（documentation）：This directory contains files used during the development and setup process: 证据：`archive/setup-development/README.md`
- **Audit Log Plugin — Example**（documentation）：Demonstrates all 4 lifecycle hooks by writing events to a JSON Lines file. 证据：`examples/plugin-audit-log/README.md`
- **Maintenance Scripts**（documentation）：This directory contains maintenance and diagnostic scripts for the MCP Memory Service database. 证据：`scripts/maintenance/README.md`
- **Database Synchronization Scripts**（documentation）：This directory contains scripts for synchronizing SQLite-vec databases across multiple machines using JSON export/import and Litestream replication. 证据：`scripts/sync/README.md`
- **Litestream Sync - Local Network HTTP API Synchronization**（documentation）：Litestream Sync - Local Network HTTP API Synchronization 证据：`scripts/sync/litestream/README.md`
- **MCP Memory Service Interactive Dashboard**（documentation）：MCP Memory Service Interactive Dashboard 证据：`src/mcp_memory_service/web/static/README.md`
- **Docker Setup for MCP Memory Service**（documentation）：Docker Setup for MCP Memory Service 证据：`tools/docker/README.md`
- **PyPI Defensive Name Placeholders**（documentation）：Tracking issue: 809 https://github.com/doobidoo/mcp-memory-service/issues/809 证据：`tools/pypi-placeholders/README.md`
- **agent-memory-service placeholder**（documentation）：This is a placeholder package . The actual implementation lives at: 证据：`tools/pypi-placeholders/agent-memory-service/README.md`
- **ai-memory-service placeholder**（documentation）：This is a placeholder package . The actual implementation lives at: 证据：`tools/pypi-placeholders/ai-memory-service/README.md`
- **memory-for-agents placeholder**（documentation）：This is a placeholder package . The actual implementation lives at: 证据：`tools/pypi-placeholders/memory-for-agents/README.md`
- **Package**（package_manifest）：{ "name": "mcp-memory-video", "version": "1.0.0", "description": "Technical Showcase video for MCP Memory Service", "scripts": { "extract-data": "tsx scripts/extract-project-data.ts", "dev": "remotion studio", "build": "remotion render MCPMemoryShowcase out/showcase.mp4", "build:short": "remotion render MCPMemoryShowcase-Short out/showcase-short.mp4", "build:walkthrough": "remotion render MCPMemoryWalkthrough out/walkthrough.mp4", "build:gif": "remotion render MCPMemoryShowcase out/preview.gif --codec=gif --scale=0.5", "preview": "remotion preview out/showcase.mp4", "upgrade": "remotion upgrade" }, "dependencies": { "@react-three/drei": "^9.96.0", "@react-three/fiber": "^8.15.16", "@react-t… 证据：`video/package.json`
- **Contributing to MCP Memory Service**（documentation）：Thank you for your interest in contributing to MCP Memory Service! 🎉 证据：`CONTRIBUTING.md`
- **Package**（package_manifest）：{ "name": "mcp-bridge-tests", "version": "1.0.0", "description": "Unit tests for HTTP-MCP bridge", "main": "test http mcp bridge.js", "scripts": { "test": "mocha test http mcp bridge.js --reporter spec", "test:watch": "mocha test http mcp bridge.js --reporter spec --watch" }, "dependencies": { "mocha": "^10.0.0", "sinon": "^17.0.0" }, "devDependencies": {}, "overrides": { "minimatch": "^10.2.3", "serialize-javascript": "^7.0.3" }, "keywords": "mcp", "bridge", "testing" , "author": "", "license": "Apache-2.0" } 证据：`tests/bridge/package.json`
- **Package**（package_manifest）：{ "name": "mcp-integration-tests", "version": "1.0.0", "description": "Integration tests for HTTP-MCP bridge", "main": "test bridge integration.js", "scripts": { "test": "mocha test bridge integration.js --reporter spec --timeout 10000", "test:watch": "mocha test bridge integration.js --reporter spec --timeout 10000 --watch" }, "dependencies": { "mocha": "^10.0.0", "sinon": "^17.0.0" }, "devDependencies": {}, "overrides": { "minimatch": "^10.2.3", "serialize-javascript": "^7.0.3" }, "keywords": "mcp", "bridge", "integration", "testing" , "author": "", "license": "Apache-2.0" } 证据：`tests/integration/package.json`
- **Debugging with GitNexus**（skill_instruction）：When to Use - "Why is this function failing?" - "Trace where this error comes from" - "Who calls this method?" - "This endpoint returns 500" - Investigating bugs, errors, or unexpected behavior 证据：`.claude/skills/gitnexus/debugging/SKILL.md`
- **Exploring Codebases with GitNexus**（skill_instruction）：When to Use - "How does authentication work?" - "What's the project structure?" - "Show me the main components" - "Where is the database logic?" - Understanding code you haven't seen before 证据：`.claude/skills/gitnexus/exploring/SKILL.md`
- **Impact Analysis with GitNexus**（skill_instruction）：When to Use - "Is it safe to change this function?" - "What will break if I modify X?" - "Show me the blast radius" - "Who uses this code?" - Before making non-trivial code changes - Before committing — to understand what your changes affect 证据：`.claude/skills/gitnexus/impact-analysis/SKILL.md`
- **Refactoring with GitNexus**（skill_instruction）：When to Use - "Rename this function safely" - "Extract this into a module" - "Split this service" - "Move this to a new file" - Any task involving renaming, extracting, splitting, or restructuring code 证据：`.claude/skills/gitnexus/refactoring/SKILL.md`
- **Marketplace**（structured_config）：{ "name": "mcp-memory-service", "owner": { "name": "doobidoo", "url": "https://github.com/doobidoo" }, "plugins": { "name": "mcp-memory-service", "source": "./claude-hooks", "description": "Semantic memory for Claude Code sessions" } } 证据：`.claude-plugin/marketplace.json`
- **Test Environment Scripts**（documentation）：CRITICAL: These scripts protect production data during manual testing. 证据：`scripts/test/README.md`
- **Manual Testing Scripts**（documentation）：This directory contains manual test scripts that are NOT run by pytest. 证据：`scripts/testing/README.md`
- **Plugin**（structured_config）：{ "name": "mcp-memory-service", "version": "1.0.0", "description": "Automatic memory capture and injection for Claude Code via MCP Memory Service", "author": { "name": "doobidoo" }, "homepage": "https://github.com/doobidoo/mcp-memory-service", "mcpServers": "./.mcp.json", "hooks": "./.claude-plugin/hooks.json" } 证据：`claude-hooks/.claude-plugin/plugin.json`
- **License**（source_file）：Apache License Version 2.0, January 2004 http://www.apache.org/licenses/ 证据：`LICENSE`
- **MCP Memory Service — Benchmark Results**（documentation）：MCP Memory Service — Benchmark Results 证据：`docs/BENCHMARKS.md`
- **Claude Code Quick Reference for MCP Memory Service**（documentation）：Claude Code Quick Reference for MCP Memory Service 证据：`docs/CLAUDE_CODE_QUICK_REFERENCE.md`
- **Claude Code Session Hook Improvements**（documentation）：Claude Code Session Hook Improvements 证据：`docs/HOOK_IMPROVEMENTS.md`
- **Docker Image Retention Policy**（documentation）：This document describes the automated image retention and cleanup policies for the MCP Memory Service Docker images across Docker Hub and GitHub Container Registry GHCR . 证据：`docs/IMAGE_RETENTION_POLICY.md`
- **MCP Memory Service - Portable Multi-Machine Setup**（documentation）：MCP Memory Service - Portable Multi-Machine Setup 证据：`docs/LIGHTWEIGHT_ONNX_SETUP.md`
- **LM Studio Compatibility Guide**（documentation）：When using MCP Memory Service with LM Studio or Claude Desktop, you may encounter errors when operations are cancelled or timeout: 证据：`docs/LM_STUDIO_COMPATIBILITY.md`
- **Tool Migration Guide**（documentation）：MCP Memory Service v2.0 consolidates 34 tools into 12 unified tools for better usability and MCP best practices compliance. 证据：`docs/MIGRATION.md`
- **Development Roadmap**（documentation）：The official roadmap has moved to the Wiki for easier maintenance and community collaboration. 证据：`docs/ROADMAP.md`
- **Amp CLI Bridge Semi-Automated Workflow**（documentation）：Amp CLI Bridge Semi-Automated Workflow 证据：`docs/amp-cli-bridge.md`
- **MCP Memory Service Architecture**（documentation）：MCP Memory Service is a Model Context Protocol server that provides semantic memory and persistent storage capabilities for AI assistants. It enables long-term memory storage with semantic search, time-based recall, and tag-based organization across conversations. 证据：`docs/architecture.md`
- **Cloudflare Backend Setup Guide**（documentation）：The MCP Memory Service supports native Cloudflare integration using Vectorize for vector storage, D1 for metadata, and optional R2 for large content. This provides: 证据：`docs/cloudflare-setup.md`
- **Docker Optimized Build Guide**（documentation）：The MCP Memory Service Docker images have been optimized to use sqlite vec as the default storage backend with lightweight ONNX embeddings , removing heavy ML dependencies PyTorch, sentence-transformers from the default build. This results in: 证据：`docs/docker-optimized-build.md`
- **Document Ingestion v7.6.0+**（documentation）：Enhanced document parsing with optional semtools integration for superior quality extraction. 证据：`docs/document-ingestion.md`
- **Memory Awareness Enhancement Roadmap - Issue 14**（documentation）：Memory Awareness Enhancement Roadmap - Issue 14 证据：`docs/enhancement-roadmap-issue-14.md`
- 其余 20 条证据见 `AI_CONTEXT_PACK.json` 或 `EVIDENCE_INDEX.json`。

## 宿主 AI 必须遵守的规则

- **把本资产当作开工前上下文，而不是运行环境。**：AI Context Pack 只包含证据化项目理解，不包含目标项目的可执行状态。 证据：`docs/README.md`, `docs/agents/README.md`, `docs/archive/obsolete-workflows/README.md`
- **回答用户时区分可预览内容与必须安装后才能验证的内容。**：安装前体验的消费者价值来自降低误装和误判，而不是伪装成真实运行。 证据：`docs/README.md`, `docs/agents/README.md`, `docs/archive/obsolete-workflows/README.md`

## 用户开工前应该回答的问题

- 你准备在哪个宿主 AI 或本地环境中使用它？
- 你只是想先体验工作流，还是准备真实安装？
- 你最在意的是安装成本、输出质量、还是和现有规则的冲突？

## 验收标准

- 所有能力声明都能回指到 evidence_refs 中的文件路径。
- AI_CONTEXT_PACK.md 没有把预览包装成真实运行。
- 用户能在 3 分钟内看懂适合谁、能做什么、如何开始和风险边界。

---

## Doramagic Context Augmentation

下面内容用于强化 Repomix/AI Context Pack 主体。Human Manual 只提供阅读骨架；踩坑日志会被转成宿主 AI 必须遵守的工作约束。

## Human Manual 骨架

使用规则：这里只是项目阅读路线和显著性信号，不是事实权威。具体事实仍必须回到 repo evidence / Claim Graph。

宿主 AI 硬性规则：
- 不得把页标题、章节顺序、摘要或 importance 当作项目事实证据。
- 解释 Human Manual 骨架时，必须明确说它只是阅读路线/显著性信号。
- 能力、安装、兼容性、运行状态和风险判断必须引用 repo evidence、source path 或 Claim Graph。

- **项目介绍**：importance `high`
  - source_paths: README.md, src/mcp_memory_service/__init__.py, docs/architecture.md
- **快速开始**：importance `high`
  - source_paths: docs/setup-guide.md, docs/first-time-setup.md, install.py, examples/claude_desktop_config_template.json
- **系统架构**：importance `high`
  - source_paths: src/mcp_memory_service/mcp_server.py, src/mcp_memory_service/server/__main__.py, src/mcp_memory_service/services/memory_service.py, src/mcp_memory_service/services/graph_service.py, docs/architecture.md
- **存储后端**：importance `high`
  - source_paths: src/mcp_memory_service/storage/__init__.py, src/mcp_memory_service/storage/factory.py, src/mcp_memory_service/storage/sqlite_vec.py, src/mcp_memory_service/storage/cloudflare.py, src/mcp_memory_service/storage/hybrid.py
- **知识图谱**：importance `high`
  - source_paths: src/mcp_memory_service/storage/graph.py, src/mcp_memory_service/models/association.py, src/mcp_memory_service/reasoning/entities.py, src/mcp_memory_service/reasoning/inference.py, src/mcp_memory_service/consolidation/relationship_inference.py
- **记忆整合系统**：importance `high`
  - source_paths: src/mcp_memory_service/consolidation/consolidator.py, src/mcp_memory_service/consolidation/scheduler.py, src/mcp_memory_service/consolidation/compression.py, src/mcp_memory_service/consolidation/decay.py, src/mcp_memory_service/consolidation/forgetting.py
- **质量评分系统**：importance `medium`
  - source_paths: src/mcp_memory_service/quality/scorer.py, src/mcp_memory_service/quality/onnx_ranker.py, src/mcp_memory_service/quality/ai_evaluator.py, src/mcp_memory_service/quality/async_scorer.py, src/mcp_memory_service/quality/config.py
- **MCP 协议集成**：importance `high`
  - source_paths: src/mcp_memory_service/mcp_server.py, src/mcp_memory_service/server/handlers/__init__.py, src/mcp_memory_service/server/handlers/memory.py, src/mcp_memory_service/server/handlers/utility.py, src/mcp_memory_service/discovery/mdns_service.py

## Repo Inspection Evidence / 源码检查证据

- repo_clone_verified: true
- repo_inspection_verified: true
- repo_commit: `90fd7b531b48b62c409e2a0cae1fe78479f5dbe7`
- inspected_files: `pyproject.toml`, `README.md`, `uv.lock`, `docs/integrations.md`, `docs/architecture.md`, `docs/HOOK_IMPROVEMENTS.md`, `docs/enhancement-roadmap-issue-14.md`, `docs/sqlite-vec-backend.md`, `docs/CLAUDE_CODE_QUICK_REFERENCE.md`, `docs/setup-guide.md`, `docs/pr-graphql-integration.md`, `docs/oauth-storage-backends.md`, `docs/remote-configuration-wiki-section.md`, `docs/memory-ontology.md`, `docs/BENCHMARKS.md`, `docs/LM_STUDIO_COMPATIBILITY.md`, `docs/wiki-Graph-Database-Architecture.md`, `docs/docker-optimized-build.md`, `docs/remote-mcp-setup.md`, `docs/first-time-setup.md`

宿主 AI 硬性规则：
- 没有 repo_clone_verified=true 时，不得声称已经读过源码。
- 没有 repo_inspection_verified=true 时，不得把 README/docs/package 文件判断写成事实。
- 没有 quick_start_verified=true 时，不得声称 Quick Start 已跑通。

## Doramagic Pitfall Constraints / 踩坑约束

这些规则来自 Doramagic 发现、验证或编译过程中的项目专属坑点。宿主 AI 必须把它们当作工作约束，而不是普通说明文字。

### Constraint 1: 来源证据：chore(milvus): track optional BaseStorage overrides + test coverage gaps

- Trigger: GitHub 社区证据显示该项目存在一个安装相关的待验证问题：chore(milvus): track optional BaseStorage overrides + test coverage gaps
- Host AI rule: 来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- Why it matters: 可能阻塞安装或首次运行。
- Evidence: community_evidence:github | cevd_520e5021db184be199bf78f1b662b13c | https://github.com/doobidoo/mcp-memory-service/issues/888 | 来源讨论提到 docker 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 2: 来源证据：v10.51.0 — Plugin hooks live, dynamic /api/types, audit-log example

- Trigger: GitHub 社区证据显示该项目存在一个安装相关的待验证问题：v10.51.0 — Plugin hooks live, dynamic /api/types, audit-log example
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_fdb895dcb5694a15937c208c89c79c98 | https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.0 | 来源类型 github_release 暴露的待验证使用条件。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 3: 来源证据：v10.51.1 — Milvus consolidation fix

- Trigger: GitHub 社区证据显示该项目存在一个安装相关的待验证问题：v10.51.1 — Milvus consolidation fix
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_c344fbad309a43aa81482c5e4b429a53 | https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.1 | 来源类型 github_release 暴露的待验证使用条件。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 4: 来源证据：v10.51.3 — Versioned memory update flag + transitive graph inference

- Trigger: GitHub 社区证据显示该项目存在一个安装相关的待验证问题：v10.51.3 — Versioned memory update flag + transitive graph inference
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能影响升级、迁移或版本选择。
- Evidence: community_evidence:github | cevd_e282c4b45ed04c8eb58759d1b32722bc | https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.51.3 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 5: 来源证据：v10.54.0 — AND/OR tag filtering for memory_search

- Trigger: GitHub 社区证据显示该项目存在一个安装相关的待验证问题：v10.54.0 — AND/OR tag filtering for memory_search
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能影响升级、迁移或版本选择。
- Evidence: community_evidence:github | cevd_5aa57485baf04502a8291b6694828c38 | https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.54.0 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 6: 来源证据：v10.55.0 — Entity Extraction, Insight Cards, urllib3 bump

- Trigger: GitHub 社区证据显示该项目存在一个安装相关的待验证问题：v10.55.0 — Entity Extraction, Insight Cards, urllib3 bump
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_c50e5d07aa964a89a80ade8ee3055612 | https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.55.0 | 来源类型 github_release 暴露的待验证使用条件。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 7: 可能修改宿主 AI 配置

- Trigger: 项目面向 Claude/Cursor/Codex/Gemini/OpenCode 等宿主，或安装命令涉及用户配置目录。
- Host AI rule: 列出会写入的配置文件、目录和卸载/回滚步骤。
- Why it matters: 安装可能改变本机 AI 工具行为，用户需要知道写入位置和回滚方法。
- Evidence: capability.host_targets | github_repo:908539519 | https://github.com/doobidoo/mcp-memory-service | host_targets=mcp_host, claude
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 8: 能力判断依赖假设

- Trigger: README/documentation is current enough for a first validation pass.
- Host AI rule: 将假设转成下游验证清单。
- Why it matters: 假设不成立时，用户拿不到承诺的能力。
- Evidence: capability.assumptions | github_repo:908539519 | https://github.com/doobidoo/mcp-memory-service | README/documentation is current enough for a first validation pass.
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 9: 来源证据：v10.55.1 — Entity Link Storage Fix

- Trigger: GitHub 社区证据显示该项目存在一个维护/版本相关的待验证问题：v10.55.1 — Entity Link Storage Fix
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_0d033317867f482985c4e395b8825cfe | https://github.com/doobidoo/mcp-memory-service/releases/tag/v10.55.1 | 来源类型 github_release 暴露的待验证使用条件。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 10: 维护活跃度未知

- Trigger: 未记录 last_activity_observed。
- Host AI rule: 补 GitHub 最近 commit、release、issue/PR 响应信号。
- Why it matters: 新项目、停更项目和活跃项目会被混在一起，推荐信任度下降。
- Evidence: evidence.maintainer_signals | github_repo:908539519 | https://github.com/doobidoo/mcp-memory-service | last_activity_observed missing
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

