---
name: ima-agent-retrieval-orchestrator
description: |
  Agent 检索增强层。规定 Agent 默认先搜 IMA，再回答；
  回答后可建议写回笔记或沉淀知识库。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '🧭'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - Agent 检索增强层
    - 回答前先搜 IMA
    - 用知识库增强这个回答
    - 先检索再回答
    - 把 IMA 当作长期记忆
---

# Retrieval Orchestrator

这是一个给 Agent 用的 IMA 检索编排层。

## 做什么

- 在回答前优先查询 IMA 中已有知识
- 决定是查笔记、查知识库还是两者组合
- 根据检索结果输出更稳妥的回答
- 在回答结束后建议是否应该沉淀成笔记或知识条目

## 输入

- 用户问题
- 可选检索范围：笔记、知识库或两者
- 可选输出模式：直接回答、briefing、FAQ、行动建议

## 输出

- 检索增强回答
- 命中知识摘要
- 后续沉淀建议

## 触发词

- Agent 检索增强层
- 回答前先搜 IMA
- 用知识库增强这个回答
- 先检索再回答
- 把 IMA 当作长期记忆

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 适合需要“先检索、后回答、再沉淀”的 Agent 工作流
- 本 skill 只编排官方已开放的搜索和沉淀能力，不依赖未公开接口

## 示例 Prompt

- “以后回答这个项目的问题时，先从 IMA 里检索再输出结论。”
- “帮我基于 IMA 里的内容回答这个问题，并在最后给出是否需要沉淀的建议。”
- “用笔记和知识库双检索模式来回答，然后生成一个简短摘要。”

## 依赖映射

- 搜索笔记：`notes/search_note_book`
- 搜索知识库：`knowledge-base/search_knowledge`
- 需要写回时可调用：`notes/import_doc` 或 `knowledge-base/add_knowledge`
