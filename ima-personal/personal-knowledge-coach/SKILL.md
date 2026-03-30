---
name: ima-personal-knowledge-coach
description: |
  个人知识教练。读取个人笔记和知识库内容，生成学习计划、复盘清单、提醒与下一步建议。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '🎯'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - 个人知识教练
    - 帮我做知识复盘
    - 根据我的笔记生成学习计划
    - 我最近该复习什么
    - 帮我做个人知识盘点
---

# Personal Knowledge Coach

把 IMA 中已经沉淀的内容转成持续学习和复盘材料。

## 做什么

- 汇总指定主题下的笔记和知识库资料
- 识别最近新增、长期未复习和重复主题
- 生成学习计划、回顾问题、行动提醒
- 可选输出成一篇新的复盘笔记

## 输入

- 一个主题、项目名或时间范围
- 可选指定知识库或笔记本

## 输出

- 学习清单
- 复盘提纲
- 行动建议
- 可选复盘笔记草稿

## 触发词

- 个人知识教练
- 帮我做知识复盘
- 根据我的笔记生成学习计划
- 我最近该复习什么
- 帮我做个人知识盘点

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 适合已经有一定笔记和知识库沉淀后再使用
- 如果要生成复盘结果并写回 IMA，可搭配 `notes/import_doc`

## 示例 Prompt

- “根据我最近两周关于 AI 产品的笔记，给我一份学习复盘。”
- “看看我的 IMA 里最近积累了什么内容，帮我制定下周学习计划。”
- “围绕‘知识管理’这个主题，帮我列一份回顾问题和下一步建议。”

## 依赖映射

- 列笔记、搜笔记：`notes/list_note_by_folder_id`、`notes/search_note_book`
- 搜知识库、浏览知识库：`knowledge-base/search_knowledge`、`knowledge-base/get_knowledge_list`
- 写回笔记：`notes/import_doc`
