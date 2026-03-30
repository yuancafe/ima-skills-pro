# ima-skill

`ima copilot` 是腾讯推出的知识库产品，官网地址：

- https://ima.qq.com/

这个仓库收录的是 `IMA` 知识库的官方 skills，来源于：

- https://app-dl.ima.qq.com/skills/ima-skills-1.1.2.zip

如果你需要配置 `IMA` OpenAPI 的 `API Key`，请到这里获取：

- https://ima.qq.com/agent-interface

## 技能包总览

这个仓库现在包含 `1` 个官方基础包和 `3` 个增强包：

| 技能包 | 类型 | 面向用户 | 作用 | 与 `ima-skill` 的关系 |
| --- | --- | --- | --- | --- |
| `ima-skill` | 官方基础包 | 所有用户 | 提供官方 `notes` / `knowledge-base` API 能力、鉴权、约束与调用规范 | 基础包 |
| `ima-personal` | 个人增强包 | 个人用户 | 做知识收藏、笔记沉淀、搜索利用、复盘学习 | 软依赖，推荐先配好 `ima-skill` |
| `ima-team` | 团队增强包 | 团队知识库运营者 | 做批量入库、巡检治理、运营汇总 | 软依赖，推荐先配好 `ima-skill` |
| `ima-agent` | Agent 增强包 | AI Agent / 自动化系统 | 做检索增强、会话沉淀、知识闭环 | 软依赖，推荐先配好 `ima-skill` |

## 安装与使用路径

支持两种使用方式：

1. 全量使用  
   适合想把 IMA 作为完整知识底座来用的场景，组合为：
   `ima-skill + ima-personal + ima-team + ima-agent`
2. 按需使用  
   只选一个增强包也可以，但建议先完成 `ima-skill` 的凭证配置与基础能力理解，再接入某个增强包。

## 目录结构

- `SKILL.md`
  官方基础包入口，统一定义凭证、`ima_api()`、模块路由与安全边界
- `notes/`
  官方笔记能力，负责搜索、读取、新建、追加笔记
- `knowledge-base/`
  官方知识库能力，负责文件上传、网页导入、知识库搜索、知识关联
- `ima-personal/`
  个人增强包，包含以下子 skill：
  - `smart-inbox`：智能收藏箱
  - `note-to-knowledge`：笔记转知识
  - `search-to-action`：搜索后行动
  - `personal-knowledge-coach`：个人知识教练
- `ima-team/`
  团队增强包，包含以下子 skill：
  - `ingestion-pipeline`：资料入库流水线
  - `knowledge-auditor`：知识巡检员
  - `team-ops-dashboard`：团队知识运营台
- `ima-agent/`
  Agent 增强包，包含以下子 skill：
  - `conversation-capture`：会话沉淀助手
  - `retrieval-orchestrator`：Agent 检索增强层

## 使用建议

- 先按 `SKILL.md` 中的说明配置 `IMA_OPENAPI_CLIENTID` 和 `IMA_OPENAPI_APIKEY`
- 具体 API 细节和字段定义请参考各模块目录下的 `references/api.md`
- 官方基础能力优先看根目录 `SKILL.md`、`notes/SKILL.md`、`knowledge-base/SKILL.md`
- 如果你只关心某一类增强能力，直接查看对应增强包和子 skill 的 `SKILL.md`

## 三类增强包

### `ima-personal`

聚焦个人知识沉淀和利用，适合个人知识管理、资料收藏、笔记升级、学习复盘。

- `smart-inbox`
  接收 URL、文件、笔记内容，决定该写入笔记还是知识库，并给出归档建议
- `note-to-knowledge`
  将已有笔记挂入知识库，并补充标题、摘要、标签建议
- `search-to-action`
  将搜索结果转成 FAQ、周报、简报、行动项
- `personal-knowledge-coach`
  读取个人知识后生成复盘、学习计划和提醒建议

### `ima-team`

聚焦团队知识库治理与运营，适合批量导入、规范化治理和运营汇总。

- `ingestion-pipeline`
  管理批量 URL / 文件入库、去重检查、失败重试和结果汇总
- `knowledge-auditor`
  扫描重复内容、弱标题、空描述、待整理知识
- `team-ops-dashboard`
  汇总导入状态、热点内容、待整理与异常内容，形成文本运营视图

### `ima-agent`

聚焦让 Agent 把 IMA 当作长期记忆和检索后端。

- `conversation-capture`
  将 AI 会话、会议纪要、聊天总结转成笔记，并按条件沉淀进知识库
- `retrieval-orchestrator`
  规定 Agent 默认流程：先搜 IMA，再回答；回答后可建议写笔记或沉淀知识库

## 说明

- 本仓库的官方基础能力来自 `ima-skills-1.1.2.zip`
- 三个增强包是基于已开放 API 能力设计的“增强挂件”，不修改官方接口定义
