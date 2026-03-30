---
name: ima-personal-search-to-action
description: |
  搜索后行动。把 IMA 搜索结果转成可执行输出，例如 FAQ、周报、简报或行动项。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '🔎'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - 搜索后行动
    - 搜完帮我整理
    - 把搜索结果转成 FAQ
    - 把搜索结果做成简报
    - 根据知识库结果生成待办
---

# Search To Action

这个 skill 负责把“搜到了什么”进一步变成“接下来做什么”。

## 做什么

- 在笔记或知识库中搜索主题内容
- 汇总命中结果并生成结构化结论
- 输出 FAQ、简报、周报、待办或下一步行动建议
- 需要时把结果反写成新笔记

## 输入

- 检索关键词
- 搜索范围：笔记、知识库或两者结合
- 期望输出类型：FAQ、briefing、action items、weekly summary

## 输出

- 命中内容摘要
- 结构化回答
- 可选的新笔记草稿

## 触发词

- 搜索后行动
- 搜完帮我整理
- 把搜索结果转成 FAQ
- 把搜索结果做成简报
- 根据知识库结果生成待办
- 搜一下然后给我下一步建议

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 适合在“已有内容较多，但输出仍停留在搜索结果列表”的场景下使用
- 如需把结果沉淀为笔记，可继续复用 `notes/import_doc`

## 示例 Prompt

- “搜索 IMA 里关于入职培训的内容，然后整理成一份 FAQ。”
- “帮我搜一下最近跟 OKR 有关的资料，并输出一份 briefing。”
- “把知识库里关于客户反馈的搜索结果整理成行动项清单。”

## 依赖映射

- 搜索笔记：`notes/search_note_book`
- 搜索知识库：`knowledge-base/search_knowledge`
- 新建结果笔记：`notes/import_doc`
