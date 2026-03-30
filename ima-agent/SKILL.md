---
name: ima-agent
description: |
  IMA Agent 增强包。让 Agent 把 IMA 当作检索前置层和长期记忆后端，
  支持会话沉淀与检索增强式工作流。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '🤖'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - ima-agent
    - 先检索再回答
    - 会话沉淀
    - Agent 长期记忆
    - 用 IMA 增强回答
---

# ima-agent

`ima-agent` 把 IMA 从“知识库工具”提升为“Agent 的长期记忆和检索后端”。

> Soft dependency: 使用本包前，建议先理解根目录 `../SKILL.md` 中的模块路由、鉴权与安全规则。

## 包含的子 skill

| 子 skill | 中文名 | 主要输入 | 主要输出 |
| --- | --- | --- | --- |
| `conversation-capture` | 会话沉淀助手 | AI 对话、会议纪要、聊天总结 | 笔记草稿、挂库建议 |
| `retrieval-orchestrator` | Agent 检索增强层 | 用户问题、检索范围、回答草稿 | 检索增强回答、沉淀建议 |

## 适用场景

- “把刚才这段 AI 对话整理成笔记，并沉淀进项目知识库”
- “让 Agent 先从 IMA 检索已有知识，再给出回答”
- “回答结束后，自动建议是否要写回笔记或挂入知识库”

## 触发词

- ima-agent
- 先检索再回答
- 会话沉淀
- Agent 长期记忆
- 用 IMA 增强回答
- 回答后自动沉淀

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 本包适合接在聊天 Agent、问答流程、总结流程之后
- 如果你已经明确要做“会话沉淀”或“检索编排”，可以直接调用子 skill
- 如果你只知道目标是“让 Agent 更会用 IMA”，先从本包入口进入

## 示例 Prompt

- “我想让 Agent 把 IMA 当作长期记忆来用，先从 `ima-agent` 帮我选流程。”
- “以后回答项目问题前先检索 IMA，再决定要不要沉淀结果。”
- “帮我判断这个 Agent 需求更适合走会话沉淀还是检索增强。”

## 选择指南

- 当需求是“先检索、后回答、再沉淀”的 Agent 工作流时，用本包
- 当需求已经明确，例如“把会话转笔记”或“先搜 IMA 再回答”，直接使用对应子 skill
- 当需求偏个人知识管理或团队运营时，分别改用 `ima-personal` 或 `ima-team`

## 设计边界

- 不重新定义底层 OpenAPI
- 不直接承担团队运营型分析
- 默认工作流是“检索优先、回答其次、沉淀收尾”
