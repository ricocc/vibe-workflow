# Vibe Workflow

[English guide](README.en.md)

**Vibe Workflow 是一个按需调用的 Skill，用来整理网站和 Web App 的开发约定，并让每次改动都有迹可循。** 设计规范、开发命令和验收标准可以留在项目里。之后换个会话继续做，AI 也能查到该按什么约定改、怎么验证。

你可以只说这次要做什么，例如整理开发文档、修一个问题，或者审查当前改动。**Agent 只读取当前任务需要的项目资料和模板。** 小改动走简短的实现和检查，涉及一整条用户流程时，再按需补规格或计划。

## 什么时候用

| 场景 | 让 AI 做什么 |
| --- | --- |
| 启动新网站或 Web App | 先定这次要用到的开发约定，再按需用模板建文档。 |
| 接手一个现有网站 | 沿用已有文档，整理散落的开发约定、设计决定和启动命令。 |
| 增加功能或修复问题 | 先明确做到什么算完成，修改后验证受影响的用户路径。 |
| 审查改动或准备发布 | 单独审查当前改动，或检查发布条件是否满足。 |

## 第一次怎么用

```text
按 Vibe Workflow 整理当前网站的开发文档。
```

如果 AI 能读取项目文件，把工作流目录提供给它，并让它从 [SKILL.md](skills/vibe-workflow/SKILL.md) 开始。使用普通聊天助手时，提供相关规则、模板和项目资料。上面的请求会让 AI 检查现有文档、整理相关内容，并按需补齐缺项。同一仓库有多个站点时，写清应用目录。

## 安装

在项目目录运行下面的命令，需要 Node.js 22.20 或更新版本。按提示选择你使用的 AI 工具。如果希望在多个项目中使用，在命令末尾加 `-g`，安装到当前用户的全局目录。

```sh
npx skills add ricocc/vibe-workflow --skill vibe-workflow
```

也可以下载或克隆仓库，把整个 [技能目录](skills/vibe-workflow/) 复制到所用工具的技能目录，保留其中的 `SKILL.md`、`agents/` 和 `references/`。以 Codex 为例，复制到项目或用户主目录下的 `.agents/skills/vibe-workflow/`。

### 调用技能

使用时显式选择 Vibe Workflow。以 Codex 为例，可以输入下面的短指令。

```text
$vibe-workflow
$vibe-workflow design
$vibe-workflow review
```

在 Codex 中，第一条进入 `init`，整理网站开发文档。后两条分别进入设计文档和只读审查阶段。

## 项目文档

### 项目需要哪些文档，就用哪些模板

```text
按 Vibe Workflow 初始化这个新网站的开发文档。
```

**Agent 根据项目现状和这次任务，只读取需要用到的模板。** 比如先做一个落地页，可以用 `AGENTS.md` 写清开发约定，用简短的 `DESIGN.md` 记下已经确认的布局和样式。初始化在文档整理完成后结束。

**已有项目优先沿用现有文档和任务记录。** 启动和测试命令可以继续放在现有 README 里，待办可以继续由 GitHub Issues 跟踪。需要新增文档时，按下面的用途选模板。 [文档默认路径](skills/vibe-workflow/references/project-docs.md#template-catalog)

| 模板 | 什么时候用 |
| --- | --- |
| [`AGENTS.md`](skills/vibe-workflow/references/templates/AGENTS.md) | 文档总览和指引 |
| [`DESIGN.md`](skills/vibe-workflow/references/templates/DESIGN.md) | 设计规范与视觉验收 |
| [`PROJECT-SPEC.md`](skills/vibe-workflow/references/templates/PROJECT-SPEC.md) | 服务对象、范围与完成标准 |
| [`DEVELOPMENT.md`](skills/vibe-workflow/references/templates/DEVELOPMENT.md) | 启动方式、命令与验证步骤 |
| [`TODO.md`](skills/vibe-workflow/references/templates/TODO.md) | 工作留痕与进度 |
| [`ARCHITECTURE.md`](skills/vibe-workflow/references/templates/ARCHITECTURE.md) | 系统结构与模块关系 |
| [`DEPLOYMENT.md`](skills/vibe-workflow/references/templates/DEPLOYMENT.md) | 部署流程与步骤 |
| [`FEATURE-SPEC.md`](skills/vibe-workflow/references/templates/FEATURE-SPEC.md) | 单个功能的流程与验收 |
| [`PLAN.md`](skills/vibe-workflow/references/templates/PLAN.md) | 规划、实施步骤 |

### 后续怎么继续开发

把相关文档留在项目仓库里，可以用 `AGENTS.md` 或已有的文档索引指向规格、设计规范、开发指南和待办。支持加载项目指令的 AI 可以从 `AGENTS.md` 进入后续任务。使用其他助手时，可以让它先读这个文件，或直接提供相关文档。项目文档负责传递开发规则，想进入 Vibe Workflow 的具体阶段时再主动调用。

### 整理 DESIGN.md

```text
按 Vibe Workflow 整理当前网站的 DESIGN.md。
```

简单落地页用 Markdown 写清视觉方向、配色、布局和关键操作即可。复杂应用可以加 YAML token、主题映射和组件状态。新站的视觉方向还没定时，可以从选定的参考网站带回具体要借鉴的内容，例如页面节奏或图像处理。 [DESIGN.md 模板](skills/vibe-workflow/references/templates/DESIGN.md) · [视觉参考与写作步骤](skills/vibe-workflow/references/project-docs.md#writing-designmd)

### 项目文档语言

优先使用用户为本次交付指定的语言。更新文档时沿用该文件的语言，新建文档时沿用项目的文档语言。没有相关约定时，使用用户本次请求的语言。代码标识和命令保留原写法。

## 和其他 Skill 搭配

做界面时，可以用你习惯的设计或动效 Skill 处理布局和交互。需要整理项目约定、验证改动或审查 diff 时，再调用 Vibe Workflow。具体怎么实现、怎么组织输出，Agent 可以按当前任务和项目判断。

## 教程：从改代码到浏览器验收

```text
按 Vibe Workflow 修复移动端菜单关闭后焦点丢失的问题。
```

说清要改什么即可。AI 会定位相关页面和组件，能复现时先记录修复前的表现，再用同一条浏览器路径复测。这里的验收会确认菜单收起后焦点实际落在哪个元素。复制、下载或表单等操作会核对内容、文件或提交结果。

检查结果应写明实际操作和观察到的结果。构建、类型检查和浏览器验收分别记录。浏览器、测试数据或服务不可用时，标出受影响的验收项。 [浏览器验收指南](skills/vibe-workflow/references/stages.md#browser-acceptance)

## 命令参考

下表使用 Codex 的短指令。在其他工具里，可以直接用自然语言描述要做的事。已有规格、计划或改动时，可以从对应阶段开始。

| 短调用 | 作用 |
| --- | --- |
| `$vibe-workflow init` | 整理站点开发文档。 |
| `$vibe-workflow design` | 整理设计文档。 |
| `$vibe-workflow spec 搜索筛选` | 写功能规格，停在编码前。 |
| `$vibe-workflow plan` | 按现有规格拆任务，停在实现前。 |
| `$vibe-workflow build 修复导航` | 实现指定改动，完成必要检查。 |
| `$vibe-workflow test` | 验证当前改动，报告结果和缺口。 |
| `$vibe-workflow review` | 只读审查当前 diff。 |
| `$vibe-workflow ship` | 检查发布就绪度。 |
| `$vibe-workflow todo` | 查看当前任务和阻塞项。 |

[各阶段的完整规则](skills/vibe-workflow/references/stages.md)

## 局限

- **检查靠项目自己的脚本和 CI。** Skill 会让 AI 按项目约定跑检查。要在测试失败时拦住合并或上线，需要在 CI 里设好规则。
- **能验到哪一步取决于工具和环境。** 改文件、用浏览器和部署都需要相应的工具和权限。如果网站跑不起来，或者缺测试账号、测试数据，AI 会写明还有哪一步待验证。
- **设计方向由你定。** 模板可以整理已有页面、参考和确认过的设计要求。还没决定的地方可以留作待定。
- **上线前检查可以单独做。** `ship` 可以先检查还有哪些发布条件没满足。实际部署需要你明确指定目标环境，并按项目已有的步骤走。

## 文件入口

- [SKILL.md](skills/vibe-workflow/SKILL.md) 说明何时启动流程，怎样进入相应阶段。
- [项目文档指南](skills/vibe-workflow/references/project-docs.md) 说明如何初始化、复用和维护文档。
- [开发阶段指南](skills/vibe-workflow/references/stages.md) 说明规格、实施、验证、审查、发布和待办的执行方式。
- [设计写作参考](skills/vibe-workflow/references/design-reference.md) 说明如何把设计方向、配色和组件规则写成可执行的约定。

## 开源许可

[MIT](LICENSE)。
