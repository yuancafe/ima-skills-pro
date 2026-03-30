---
name: ima-team-ingestion-pipeline
description: |
  资料入库流水线。面向批量文件和 URL 入库，负责去重检查、导入顺序、
  失败重试建议和结果汇总。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '🚚'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - 资料入库流水线
    - 批量导入知识库
    - 批量上传资料到 IMA
    - 帮我跑一轮入库
    - 导入失败重试
---

# Ingestion Pipeline

把零散的团队资料导入变成一个可管理的流水线。

## 做什么

- 批量接收文件和 URL
- 对文件做类型、大小、重名检查
- 给出分批导入顺序和失败重试建议
- 在执行后汇总成功、失败和待人工处理项

## 输入

- 批量 URL
- 批量本地文件
- 目标知识库和可选目标文件夹

## 输出

- 导入计划
- 重复项与冲突清单
- 失败重试建议
- 导入结果汇总

## 触发词

- 资料入库流水线
- 批量导入知识库
- 批量上传资料到 IMA
- 帮我跑一轮入库
- 导入失败重试
- 批量收录这一批文件和链接

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 本 skill 强依赖 `knowledge-base` 模块中的文件检查、URL 导入和上传流程
- 使用前最好已经确认目标知识库，必要时先用基础包搜索知识库

## 示例 Prompt

- “把这个文件夹里的资料分批导入团队知识库，并告诉我哪些会重名。”
- “这 10 个 URL 和 3 个 PDF 帮我规划一轮入库流水线。”
- “把失败的导入项单独列出来，并给我重试建议。”

## 依赖映射

- 文件前置检查：`knowledge-base/scripts/preflight-check.cjs`
- 文件重名检查：`knowledge-base/check_repeated_names`
- 文件上传：`knowledge-base/create_media` → COS → `add_knowledge`
- URL 导入：`knowledge-base/import_urls`
