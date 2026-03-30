---
name: ima-team
description: |
  IMA 团队增强包。基于官方 ima-skill 的知识库与笔记能力，提供批量入库、
  巡检治理和团队知识运营汇总等工作流能力。
homepage: https://ima.qq.com
metadata:
  openclaw:
    emoji: '🏢'
    requires: { env: ['IMA_OPENAPI_CLIENTID', 'IMA_OPENAPI_APIKEY'] }
    primaryEnv: 'IMA_OPENAPI_CLIENTID'
  trigger_keywords:
    - ima-team
    - 团队知识库运营
    - 批量入库
    - 知识巡检
    - 知识运营周报
---

# ima-team

`ima-team` 是面向团队知识库管理和运营的增强包。

> Soft dependency: 推荐先阅读根目录 `../SKILL.md`，再使用本包中的编排型能力。

## 包含的子 skill

| 子 skill | 中文名 | 主要输入 | 主要输出 |
| --- | --- | --- | --- |
| `ingestion-pipeline` | 资料入库流水线 | 批量 URL / 文件 | 导入计划、重试建议、结果汇总 |
| `knowledge-auditor` | 知识巡检员 | 知识库 / 文件夹 / 检索条件 | 重复项、弱标题、异常清单 |
| `team-ops-dashboard` | 团队知识运营台 | 知识库清单、导入记录 | 文本版运营报告 |

## 适用场景

- “把这一批资料分批导入知识库，并汇总哪些失败了”
- “帮我检查某个知识库里哪些内容重复、标题太弱、还没整理”
- “生成本周知识库运营概览，看看哪些内容值得整理”

## 触发词

- ima-team
- 团队知识库运营
- 批量入库
- 知识巡检
- 知识运营周报
- 团队知识治理

## 安装说明

- 推荐先安装并配置基础包 `ima-skill`
- 本包复用基础包中的官方知识库能力和凭证配置
- 如果你面对的是一个团队知识库系统问题，先从本包入口进入
- 如果你已经明确要做“批量入库”或“巡检”，可直接使用对应子 skill

## 示例 Prompt

- “我想把 IMA 用在团队知识运营上，帮我选 `ima-team` 里最合适的 skill。”
- “我们这周要做知识库导入、巡检和周报，优先从 `ima-team` 开始。”
- “帮我判断这个需求应该走 `ima-team` 还是具体某个 team 子 skill。”

## 选择指南

- 当需求是“批量导入、治理、运营汇总”这类团队工作流时，用本包
- 当目标已经明确，例如“跑入库流水线”或“做知识巡检”，直接进入对应子 skill
- 当需求偏个人复盘或 Agent 检索增强时，分别改用 `ima-personal` 或 `ima-agent`

## 设计边界

- 聚焦团队工作流，不承担 Agent 默认回答逻辑
- 复用官方知识库搜索、浏览、导入和挂库能力
- 输出以文本计划、异常列表、运营摘要为主
