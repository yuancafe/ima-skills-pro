# ima-skill

`ima copilot` 是腾讯推出的知识库产品，官网地址：

- https://ima.qq.com/

这个仓库收录的是 `IMA` 知识库的官方 skills，来源于：

- https://app-dl.ima.qq.com/skills/ima-skills-1.1.2.zip

如果你需要配置 `IMA` OpenAPI 的 `API Key`，请到这里获取：

- https://ima.qq.com/agent-interface

## 仓库内容

- `SKILL.md`：仓库入口说明，介绍统一的 IMA OpenAPI 技能入口
- `notes/`：IMA 个人笔记相关 skills，包含搜索、浏览、读取、创建和追加内容
- `knowledge-base/`：IMA 知识库相关 skills，包含文件上传、网页收藏、知识库搜索和管理

## 使用建议

- 先按 `SKILL.md` 中的说明配置 `IMA_OPENAPI_CLIENTID` 和 `IMA_OPENAPI_APIKEY`
- 具体 API 细节和字段定义请参考各模块目录下的 `references/api.md`
- 如果你只关心某一类能力，直接查看对应模块下的 `SKILL.md` 即可

## 说明

- 本仓库用于整理和分发官方 IMA skills
- 这里的内容基于官方发布的 `ima-skills-1.1.2.zip`
