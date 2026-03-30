---
name: ima-agent-conversation-capture
description: |
  会话沉淀助手。把 AI 会话、会议纪要和聊天总结转成笔记，
  并根据主题建议是否沉淀到知识库。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '💬'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - 会话沉淀助手
    - 把这段对话记下来
    - 把会议纪要沉淀到 IMA
    - 把聊天总结成笔记
    - 回答完后帮我归档
---

# Conversation Capture

为 Agent 提供“会话结束后如何沉淀”的默认能力。

## 做什么

- 把对话整理成结构化内容
- 生成一篇新笔记或追加到明确指定的已有笔记
- 识别是否适合挂入知识库
- 输出沉淀建议与执行动作

## 输入

- AI 对话、会议纪要、聊天总结
- 可选目标笔记本或目标知识库

## 输出

- 笔记草稿或写入动作
- 可选挂库建议
- 会话摘要和关键行动项

## 触发词

- 会话沉淀助手
- 把这段对话记下来
- 把会议纪要沉淀到 IMA
- 把聊天总结成笔记
- 回答完后帮我归档

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 适合与聊天 Agent、会议纪要工具、总结型流程一起使用
- 如果目标是追加到已有笔记，必须遵守 `notes/append_doc` 的敏感操作确认规则

## 示例 Prompt

- “把我们刚才这段 AI 对话整理成笔记，并判断要不要挂到项目知识库。”
- “把这份会议纪要沉淀到 IMA，顺便提炼关键行动项。”
- “帮我把今天的聊天记录变成一篇笔记草稿。”

## 依赖映射

- 新建笔记：`notes/import_doc`
- 追加笔记：`notes/append_doc`
- 搜索目标笔记：`notes/search_note_book`
- 挂入知识库：`knowledge-base/add_knowledge` with `media_type=11`
