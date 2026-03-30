---
name: ima-personal-note-to-knowledge
description: |
  笔记转知识。把已有笔记批量或单条沉淀进知识库，并补充标题、摘要、标签和归档建议。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '📝'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - 笔记转知识
    - 把笔记挂到知识库
    - 把这篇笔记沉淀到知识库
    - 笔记升级成知识条目
    - 把这些笔记归档到知识库
---

# Note To Knowledge

把个人笔记升级为可检索、可归档的知识资产。

## 做什么

- 搜索和定位要转化的笔记
- 读取笔记标题、摘要和正文
- 推荐更适合沉淀到哪个知识库 / 文件夹
- 将笔记作为 `media_type=11` 关联到知识库
- 在挂库前给出标题、摘要、标签建议

## 输入

- 笔记标题、关键词或 `doc_id`
- 目标知识库名称或 `knowledge_base_id`
- 可选目标文件夹

## 输出

- 命中的笔记列表
- 每篇笔记的挂库建议
- 挂库执行计划或实际挂库动作

## 触发词

- 笔记转知识
- 把笔记挂到知识库
- 把这篇笔记沉淀到知识库
- 笔记升级成知识条目
- 把这些笔记归档到知识库

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 本 skill 同时依赖 `notes` 和 `knowledge-base` 两个官方模块
- 使用前最好已经知道目标知识库名称，或允许先搜索知识库再选择

## 示例 Prompt

- “把《产品周会纪要》这篇笔记挂到产品知识库里。”
- “搜索最近关于招聘流程的笔记，并把适合的内容沉淀到团队知识库。”
- “把这几篇笔记批量转成知识资产，顺便给出标题和摘要建议。”

## 依赖映射

- 搜索笔记：`notes/search_note_book`
- 读笔记内容：`notes/get_doc_content`
- 搜知识库：`knowledge-base/search_knowledge_base`
- 挂入知识库：`knowledge-base/add_knowledge` with `note_info.content_id=<doc_id>`
