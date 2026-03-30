# ima-skills-pro

`ima-skills-pro` 不是官方 skills 的搬运版，而是一个面向真实工作流的增强套装。

如果说官方 `ima-skills` 解决的是“我能调用 IMA 的笔记和知识库 API”，那么 `ima-skills-pro` 解决的是：

- 我怎么把资料自动收进知识体系
- 我怎么把零散笔记升级成可检索知识
- 我怎么批量治理团队知识库
- 我怎么让 Agent 先检索、再回答、再沉淀

一句话说，官方包更像“基础能力层”，`ima-skills-pro` 更像“可直接使用的工作流层”。

## PRO 版价值

相比官方 `ima-skills`，`ima-skills-pro` 额外提供了 `3` 个增强包和 `9` 个增强子 skill：

- `ima-personal`
  面向个人知识管理，覆盖收藏、笔记转知识、搜索后行动、个人复盘
- `ima-team`
  面向团队知识运营，覆盖批量入库、巡检治理、运营摘要
- `ima-agent`
  面向 Agent 工作流，覆盖会话沉淀、检索增强、长期记忆闭环

核心增强点：

- 从“调用 API”升级到“完成工作流”
- 从“单次操作”升级到“可复用的场景化 skill”
- 从“基础读写”升级到“个人、团队、Agent 三条产品线”

## 官方包与 PRO 包

`ima-skills-pro` 仍然建立在官方 `ima-skills` 的能力边界之上，是一个“软依赖增强包”套装：

- 官方基础包：[`ima-skills`](https://clawhub.ai/iampennyli/ima-skills)
- 官方使用说明：如果你要看官方包的安装、配置和基础能力说明，请先看这里：
  [`https://clawhub.ai/iampennyli/ima-skills`](https://clawhub.ai/iampennyli/ima-skills)
- 当前增强基线：基于官方 `1.2` 版能力边界进行增强设计

这意味着：

- 你仍然可以继续使用官方包作为基础层
- `ima-skills-pro` 不重写官方 OpenAPI
- `ima-skills-pro` 不引入未公开接口
- `ima-skills-pro` 重点补足官方包没有覆盖的工作流和产品化体验

## 官方来源

`ima copilot` 是腾讯推出的知识库产品，官网地址：

- https://ima.qq.com/

如果你需要配置 IMA OpenAPI 的 `API Key`，请到这里获取：

- https://ima.qq.com/agent-interface

## 套装结构

这个仓库包含 `1` 个基础包视图和 `3` 个增强包：

| 包名 | 类型 | 角色 | 是否依赖官方包 |
| --- | --- | --- | --- |
| `ima-skill` | 基础包 | 官方兼容基础层，负责 `notes` / `knowledge-base` 能力、鉴权与规则 | 官方基础能力本身 |
| `ima-personal` | 增强包 | 面向个人知识管理、收藏、复盘、搜索利用 | 软依赖 |
| `ima-team` | 增强包 | 面向团队知识运营、批量入库、巡检治理 | 软依赖 |
| `ima-agent` | 增强包 | 面向 Agent 检索增强、会话沉淀、长期记忆 | 软依赖 |

## 和官方包的关系

`ima-skills-pro` 的定位是：

- 不重写官方 OpenAPI
- 不引入未公开接口
- 不替代官方基础包的安装说明
- 只在官方能力之上补“工作流编排层”和“产品化增强层”

也就是说：

- 如果你只需要官方笔记与知识库 API 能力，用官方包就够了
- 如果你想要更完整的个人、团队、Agent 工作流，再安装本仓库里的增强包

## 如何安装

### 整体安装全部

如果你想完整使用这套增强方案，推荐安装顺序是：

1. 先安装官方基础包 `ima-skills`
2. 完成官方包要求的 `IMA_OPENAPI_CLIENTID` / `IMA_OPENAPI_APIKEY` 配置
3. 再安装本仓库中的三个增强包：
   `ima-personal`、`ima-team`、`ima-agent`

整体安装后的能力组合是：

`ima-skill + ima-personal + ima-team + ima-agent`

如果你的 agent 运行时支持本地 skills 目录，常见做法是：

- 官方基础包使用官方发布版本
- 本仓库只额外挂载增强包目录

例如你可以从本仓库中单独取出这些目录进行安装：

- `ima-personal/`
- `ima-team/`
- `ima-agent/`

### 单独安装增强包

如果你只需要某一类增强能力，也可以只安装一个增强包，但前提仍然是：

- 已经安装官方基础包 `ima-skills`
- 已经完成官方基础包要求的凭证配置

然后按需选择：

- 只做个人知识管理：安装 `ima-personal`
- 只做团队知识库治理：安装 `ima-team`
- 只做 Agent 检索与沉淀：安装 `ima-agent`

## 仓库目录

- `SKILL.md`
  官方兼容基础包入口
- `OFFICIAL-USAGE.md`
  基础包目录中的官方使用说明整理版，方便和增强包一起查看
- `notes/`
  官方笔记能力
- `knowledge-base/`
  官方知识库能力
- `ima-personal/`
  个人增强包
- `ima-team/`
  团队增强包
- `ima-agent/`
  Agent 增强包
- `CHANGELOG.md`
  本套装的版本更新记录

## 增强包详解

### `ima-personal`

面向个人知识管理，强调“收进来、转起来、用起来、复盘起来”。

包含的子 skill：

- `smart-inbox`
  智能收藏箱。接收 URL、文件、笔记内容，判断更适合写笔记还是进知识库，并给出归档建议。
- `note-to-knowledge`
  笔记转知识。把已有笔记挂到知识库，补标题、摘要和归档建议。
- `search-to-action`
  搜索后行动。把搜索结果转成 FAQ、briefing、行动项或总结。
- `personal-knowledge-coach`
  个人知识教练。基于已有沉淀内容生成复盘、学习清单和提醒建议。

特色：

- 更适合个人用户的日常知识流转
- 强调“搜索结果之后要有动作”
- 适合把 IMA 从存储工具升级成个人知识系统

使用说明：

- 当你的需求是收藏、沉淀、复盘、个人学习时，优先从 `ima-personal` 开始
- 当目标动作已经很明确时，可以直接调用具体子 skill

示例：

- “把这篇内容收进我的知识体系，并告诉我更适合放笔记还是知识库。”
- “把最近关于 OKR 的搜索结果整理成一份行动建议。”
- “根据我最近两周的笔记，帮我做一次个人复盘。”

### `ima-team`

面向团队知识库运营，强调“批量入库、质量治理、运营汇总”。

包含的子 skill：

- `ingestion-pipeline`
  资料入库流水线。管理批量 URL / 文件导入、冲突检查、失败重试和结果汇总。
- `knowledge-auditor`
  知识巡检员。扫描重复内容、弱标题、空描述、待整理条目。
- `team-ops-dashboard`
  团队知识运营台。输出热点主题、异常清单、整理建议和文本版运营摘要。

特色：

- 更适合团队知识库管理员和运营者
- 不依赖未公开统计接口，也能形成轻量运营视图
- 把“散装导入”和“散装巡检”变成稳定工作流

使用说明：

- 当你的需求是批量导入、巡检、周报、治理时，优先从 `ima-team` 开始
- 如果已经明确是“跑入库流水线”或“做健康检查”，直接进入对应子 skill

示例：

- “帮我把这一批资料分批导入知识库，并列出失败项。”
- “巡检一下产品知识库，找出重复内容和弱标题。”
- “做一份本周团队知识库运营摘要。”

### `ima-agent`

面向 Agent 工作流，强调“先检索，再回答，再沉淀”。

包含的子 skill：

- `conversation-capture`
  会话沉淀助手。把 AI 对话、会议纪要、聊天总结转成笔记，并建议是否挂入知识库。
- `retrieval-orchestrator`
  Agent 检索增强层。规定 Agent 默认先搜 IMA，再回答，并在回答后建议沉淀动作。

特色：

- 把 IMA 从知识库工具提升为 Agent 的长期记忆后端
- 适合问答、总结、会议纪要和知识回写场景
- 明确强调“检索优先”的 Agent 回答路径

使用说明：

- 当你想让 Agent 更会使用 IMA 时，先从 `ima-agent` 开始
- 当目标已经明确为“会话沉淀”或“检索增强”，直接进入子 skill

示例：

- “以后回答这个项目的问题前先检索 IMA。”
- “把这段 AI 对话整理成笔记，并判断要不要沉淀进知识库。”
- “用 IMA 中已有内容增强这个回答，并给出后续沉淀建议。”

## 基础包说明

仓库根目录中的 `SKILL.md`、`notes/`、`knowledge-base/` 保持官方兼容结构，主要作用是：

- 作为增强包的基础依赖说明
- 统一凭证、模块路由和安全边界
- 提供本仓库联调时所需的基础文档视图
- 补充一份便于查阅的官方使用说明整理版：`OFFICIAL-USAGE.md`

如果你要看官方基础包的原始使用说明，请直接查看：
[`ima-skills`](https://clawhub.ai/iampennyli/ima-skills)

## 版本记录

版本更新记录见：

- [CHANGELOG.md](./CHANGELOG.md)
