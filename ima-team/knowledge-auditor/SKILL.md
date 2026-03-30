---
name: ima-team-knowledge-auditor
description: |
  知识巡检员。基于知识库和笔记元信息扫描重复项、弱标题、空描述、
  待整理条目和可疑脏数据。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '🧹'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - 知识巡检员
    - 帮我巡检知识库
    - 查重复内容
    - 找弱标题
    - 给知识库做健康检查
---

# Knowledge Auditor

这个 skill 用于做知识库的轻量治理和健康检查。

## 做什么

- 浏览知识库和指定文件夹内容
- 搜索重复主题和可能重复条目
- 识别弱标题、空描述、待整理内容
- 输出整理建议和优先处理清单

## 输入

- 一个或多个知识库
- 可选文件夹范围
- 巡检主题或关键词

## 输出

- 重复项候选
- 命名质量问题
- 待整理清单
- 整理优先级建议

## 触发词

- 知识巡检员
- 帮我巡检知识库
- 查重复内容
- 找弱标题
- 看看哪些内容还没整理
- 给知识库做健康检查

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 适合面向知识库管理员或团队维护者使用
- 本 skill 主要做扫描和建议，不直接删除或修改知识内容

## 示例 Prompt

- “帮我巡检一下产品知识库，看看有哪些重复或命名不规范的内容。”
- “检查招聘知识库里哪些条目标题太弱，应该优先整理。”
- “给我一份待整理知识清单，按优先级排一下。”

## 依赖映射

- 浏览知识库：`knowledge-base/get_knowledge_list`
- 搜索知识库：`knowledge-base/search_knowledge`
- 搜索知识库列表：`knowledge-base/search_knowledge_base`
- 补充读取笔记信息时可使用 `notes/search_note_book`
