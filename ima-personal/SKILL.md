---
name: ima-personal
description: |
  IMA 个人增强包。基于官方 ima-skill 的 notes 和 knowledge-base 能力，
  提供知识收藏、笔记升级、搜索利用、个人复盘等工作流型能力。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '🧠'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - ima-personal
    - 个人知识管理
    - 知识收藏
    - 笔记转知识
    - 个人复盘
---

# ima-personal

`ima-personal` 是 `ima-skill` 的个人效率增强包，聚焦个人知识沉淀与利用。

> Soft dependency: 推荐先阅读根目录 `../SKILL.md`，并完成 `IMA_OPENAPI_CLIENTID` / `IMA_OPENAPI_APIKEY` 配置。

## 包含的子 skill

| 子 skill | 中文名 | 主要输入 | 主要输出 |
| --- | --- | --- | --- |
| `smart-inbox` | 智能收藏箱 | URL / 文件 / 笔记内容 | 归档建议、笔记或知识库动作 |
| `note-to-knowledge` | 笔记转知识 | 笔记标题 / `doc_id` / 目标知识库 | 挂库动作、标题摘要建议 |
| `search-to-action` | 搜索后行动 | 检索关键词 / 检索结果 | FAQ、简报、行动项 |
| `personal-knowledge-coach` | 个人知识教练 | 笔记、知识库内容、复盘主题 | 学习计划、复盘清单、提醒建议 |

## 适用场景

- “把这篇文章收进我的知识体系，并告诉我更适合放在哪里”
- “把最近整理的几篇笔记转成知识库条目”
- “帮我把关于某个主题的搜索结果整理成行动清单”
- “根据我最近的笔记和知识库内容，生成一份个人复盘”

## 触发词

- ima-personal
- 个人知识管理
- 知识收藏
- 笔记转知识
- 个人复盘
- 帮我整理个人知识

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 本包复用基础包中的 `IMA_OPENAPI_CLIENTID` 和 `IMA_OPENAPI_APIKEY`
- 如果你已经知道自己要做的是某个具体动作，优先直接调用对应子 skill
- 如果你只知道目标是“提升个人知识流转效率”，先从本包入口进入最合适

## 示例 Prompt

- “我想把 IMA 用成个人知识系统，帮我看看该用哪个 personal skill。”
- “我在个人知识管理里有收藏、搜索和复盘需求，优先走 `ima-personal`。”
- “帮我在 `ima-personal` 里选最合适的子 skill 来处理这段内容。”

## 选择指南

- 当需求是“收藏、沉淀、搜索利用、复盘”这类个人工作流时，用本包
- 当需求已经明确为某个动作，例如“把笔记挂库”或“把搜索结果转成 FAQ”，直接用对应子 skill
- 当需求涉及团队治理或 Agent 默认回答链路时，分别改用 `ima-team` 或 `ima-agent`

## 设计边界

- 只做工作流编排和建议，不重复解释底层 OpenAPI 参数
- 笔记读写依赖 `notes` 模块
- 知识入库和知识库搜索依赖 `knowledge-base` 模块
- 不引入未公开接口，也不修改官方鉴权与安全规则
