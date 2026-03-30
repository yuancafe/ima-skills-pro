---
name: ima-team-team-ops-dashboard
description: |
  团队知识运营台。汇总知识库导入状态、热点内容、待整理内容和异常条目，
  产出文本版运营视图。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '📊'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - 团队知识运营台
    - 生成知识库运营周报
    - 看看知识库最近怎么样
    - 帮我做知识运营摘要
    - 知识库热点和异常
---

# Team Ops Dashboard

把分散的知识库状态汇总为面向团队的运营视图。

## 做什么

- 汇总多个知识库的内容分布和整理状态
- 标出热点主题、异常条目和待整理条目
- 生成适合周会或周报使用的文本版运营摘要

## 输入

- 一个或多个知识库
- 可选时间范围或主题
- 可选导入结果清单

## 输出

- 运营摘要
- 热点主题列表
- 异常与待整理清单
- 下周建议动作

## 触发词

- 团队知识运营台
- 生成知识库运营周报
- 看看知识库最近怎么样
- 帮我做知识运营摘要
- 知识库热点和异常

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 适合团队例会、周报、运营复盘场景
- 本 skill 默认输出文本版运营视图，不依赖未公开统计接口

## 示例 Prompt

- “帮我做一份本周团队知识库运营摘要。”
- “看看这个月产品知识库有哪些热点主题和异常内容。”
- “基于最近导入和搜索情况，给我一个下周整理建议。”

## 依赖映射

- 获取知识库详情：`knowledge-base/get_knowledge_base`
- 浏览知识库：`knowledge-base/get_knowledge_list`
- 搜索知识库：`knowledge-base/search_knowledge`
