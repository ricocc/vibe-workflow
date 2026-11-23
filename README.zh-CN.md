# Vibe Workflow

[English guide](README.md)

**Vibe Workflow 是一套面向网站和 Web App 的 Vibe Coding 工作流。** 它帮你把项目的设计规范、开发约定和验收标准整理成 AI 能遵循的文档。之后用 AI 增加功能、修复问题或审查改动时，可以沿用同一套约定，并用可复查的结果确认是否做完。

## 什么时候用

| 场景 | 让 AI 做什么 |
| --- | --- |
| 启动新网站或 Web App | 用模板建立项目文档，在开始写代码前定下开发约定。 |
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

### 启动新项目

```text
按 Vibe Workflow 初始化这个新网站的开发文档。
```

提供网站目标、目标用户、访客要完成的主要动作，以及已经确认的技术或设计决定。工作流用模板生成适用的项目文档，把未确定的选择记为待定。初始化在文档整理完成后结束。对已有项目，工作流优先沿用原有文档位置，只补相关缺项。

| 文档 | 可以用来回答什么 |
| --- | --- |
| `AGENTS.md` | AI 从哪里开始读，项目有哪些开发约定？ |
| `DESIGN.md` | 页面怎么布局，样式、组件和状态如何使用，怎样做视觉验收？ |
| `docs/PROJECT-SPEC.md` | 网站服务谁、当前范围是什么、哪些结果才算达标？ |
| `docs/DEVELOPMENT.md` | 怎样启动和验证，哪些项目命令可以运行？ |
| `docs/TODO.md` | 当前要做什么、哪里受阻、下次从哪里接续？已有任务系统可以继续使用。 |

这些是新项目的默认位置。架构、部署、独立功能规格和实施计划按需补充。 [文档目录和模板](skills/vibe-workflow/references/project-docs.md#template-catalog)

### 后续怎么继续开发

把生成的文档留在项目仓库里，由 `AGENTS.md` 链接到相关的规格、设计规范、开发指南和待办。支持加载项目指令的 AI 可以从 `AGENTS.md` 进入后续任务。使用其他助手时，可以让它先读这个文件，或直接提供相关文档。项目文档负责传递开发规则，想进入 Vibe Workflow 的具体阶段时再主动调用。

### 整理 DESIGN.md

```text
按 Vibe Workflow 整理当前网站的 DESIGN.md。
```

简单落地页用 Markdown 写清视觉方向、配色、布局和关键操作即可。复杂应用可以加 YAML token、主题映射和组件状态。新站的视觉方向还没定时，可以从选定的参考网站带回具体要借鉴的内容，例如页面节奏或图像处理。 [DESIGN.md 模板](skills/vibe-workflow/references/templates/DESIGN.md) · [视觉参考与写作步骤](skills/vibe-workflow/references/project-docs.md#writing-designmd)

### 项目文档语言

优先使用用户为本次交付指定的语言。更新文档时沿用该文件的语言，新建文档时沿用项目的文档语言。没有相关约定时，使用用户本次请求的语言。代码标识和命令保留原写法。

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

- 这是给 AI 的工作指引。强制执行的构建、测试和发布检查由项目的脚本或 CI 执行。
- 文件编辑、浏览器验收和部署取决于所用工具的能力与权限。验收也需要可运行的环境和适用的测试数据。关键路径缺少证据时应保留为待验证。
- 模板能够整理设计证据和约定，设计取舍仍需要项目实现、用户选择或已确认的规范作为依据。
- 发布和其他会改变外部状态的操作按任务授权及项目流程进行。准备度检查可以单独请求。

## 文件入口

- [SKILL.md](skills/vibe-workflow/SKILL.md) 说明何时启动流程，怎样进入相应阶段。
- [项目文档指南](skills/vibe-workflow/references/project-docs.md) 说明如何初始化、复用和维护文档。
- [开发阶段指南](skills/vibe-workflow/references/stages.md) 说明规格、实施、验证、审查、发布和待办的执行方式。
- [设计写作参考](skills/vibe-workflow/references/design-reference.md) 说明如何把设计方向、配色和组件规则写成可执行的约定。

## 开源许可

[MIT](LICENSE)。
