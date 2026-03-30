---
name: ima-personal-smart-inbox
description: |
  智能收藏箱。接收 URL、文件、笔记内容或临时资料，判断应写入笔记还是知识库，
  并输出目标知识库、文件夹、标题和归档动作建议。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '📥'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - 智能收藏箱
    - 收进知识库
    - 帮我归档这个链接
    - 帮我收纳这份资料
    - 这个该放笔记还是知识库
---

# Smart Inbox

基于 `ima-skill` 的 `notes` 和 `knowledge-base` 能力实现的个人收藏入口。

## 做什么

- 接收零散输入：URL、文件、笔记内容、已有笔记
- 判断更适合进入“笔记”还是“知识库”
- 给出目标知识库 / 文件夹 / 标题建议
- 在用户确认后执行 `import_doc`、`import_urls`、文件上传或 `add_knowledge`

## 输入

- 一个或多个 URL
- 一个或多个本地文件
- 一段待保存内容
- 一篇已有笔记的 `doc_id` 或可搜索标题

## 输出

- 归档决策：写笔记 or 入知识库
- 目标位置建议：知识库、文件夹或笔记本
- 标题、摘要、标签建议
- 可执行的下一步动作

## 触发词

- 智能收藏箱
- 收进知识库
- 帮我归档这个链接
- 帮我收纳这份资料
- 这个该放笔记还是知识库
- 给这篇内容找个合适的位置

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 复用基础包中的 `IMA_OPENAPI_CLIENTID` 和 `IMA_OPENAPI_APIKEY`
- 首次使用前，建议先确认默认使用的知识库或笔记本范围

## 示例 Prompt

- “把这篇网页收进我的 IMA，顺便判断更适合写成笔记还是进知识库。”
- “我有一份本地 PDF 和一段总结，帮我决定怎么归档最合适。”
- “把这条已有笔记也纳入我的知识体系，并建议放到哪个知识库里。”

## 依赖映射

- 写入笔记：`notes/import_doc`
- 追加笔记：`notes/append_doc`
- 导入网页：`knowledge-base/import_urls`
- 上传文件：`knowledge-base/create_media` → COS → `add_knowledge`
- 将已有笔记挂库：`knowledge-base/add_knowledge` with `media_type=11`
