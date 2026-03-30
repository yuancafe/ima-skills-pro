# Official Usage

这份文档放在基础包目录中，用来保存一份便于查阅的官方使用说明摘要。

官方包页面：

- [`ima-skills`](https://clawhub.ai/iampennyli/ima-skills)

如果你想看官方包的原始安装页、版本页和完整文件内容，请以上面的官方页面为准。

## 官方包定位

官方 `ima-skills` 是 IMA OpenAPI 的基础 skills 套件，核心目标是提供：

- IMA 笔记能力
- IMA 知识库能力
- 官方凭证配置方式
- 官方 API 调用约定与安全边界

在 `ima-skills-pro` 中，这些能力对应：

- 根目录 `SKILL.md`
- `notes/`
- `knowledge-base/`

## 官方包使用前提

根据官方说明，使用前需要准备：

- `IMA_OPENAPI_CLIENTID`
- `IMA_OPENAPI_APIKEY`

获取地址：

- https://ima.qq.com/agent-interface

## 官方基础使用方式

官方包的典型使用流程可以概括为：

1. 获取 `Client ID` 和 `API Key`
2. 配置环境变量或本地凭证
3. 按模块调用官方能力：
   - `notes`：搜索、浏览、读取、新建、追加笔记
   - `knowledge-base`：上传文件、导入链接、搜索知识库、浏览知识库、将笔记挂入知识库

## 官方包核心能力

### `notes`

适合处理：

- 搜索笔记
- 浏览笔记本
- 获取笔记内容
- 新建笔记
- 追加内容到已有笔记

### `knowledge-base`

适合处理：

- 上传文件到知识库
- 添加网页和微信公众号文章
- 搜索知识库内容
- 浏览知识库和文件夹
- 将已有笔记挂接到知识库

## 官方包使用建议

- 如果你的需求只是基础的笔记读写、知识库导入和搜索，优先使用官方包
- 如果你的需求已经上升到个人工作流、团队运营或 Agent 检索增强，再叠加使用 `ima-skills-pro`

## 在本仓库中的关系

`ima-skills-pro` 与官方包的关系是：

- 官方包负责基础 API 能力
- `ima-skills-pro` 负责增强型工作流与产品化编排
- 两者是“基础层 + 增强层”的软依赖关系
