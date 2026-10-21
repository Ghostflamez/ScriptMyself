# AGENTS.md

> 本文件是本项目 AI 协作的**顶层上下文**。任何 AI agent 在开始工作前必须先读本文件。
> 只记录**长期有效**的信息：项目关键信息、重要决策、当前阶段。过程性讨论写进 `notes/`，需求与项目管理写进 `wiki/`。

## 1. 项目概览

- **名称**：script myself
- **目标**：为受拖延与 ADHD 困扰的人提供一种**最小可执行语法**，把日常例程抽象为"决策脚本"，降低启动行动的认知负荷。
- **示例**：`wake_up -> brush_teeth -> make_coffee -> open_laptop`
- **仓库**：https://github.com/Ghostflamez/ScriptMyself
- **许可**：MIT
- 详细背景与理论依据见 [README.md](README.md)。

## 2. 当前阶段

- **方法论**：Agile
- **当前 Sprint**：**Sprint 0（无限期）**——需求工程分析阶段。
- **本阶段边界**：以需求获取、分析、规格化和项目管理基础建设为主；**不进入实现**，除非某个 issue 明确要求做原型/技术验证（spike）。
- 进度与 backlog 见 Wiki 的 [Project-Management](https://github.com/Ghostflamez/ScriptMyself/wiki/Project-Management) 页面。

## 3. 上下文体系

| 层级 | 位置 | 内容 | 生命周期 |
| --- | --- | --- | --- |
| 顶层 | `AGENTS.md` | 项目关键信息、重要决策、当前阶段 | 长期，只增改不随意删 |
| 知识库 | [GitHub Wiki](https://github.com/Ghostflamez/ScriptMyself/wiki)（本地克隆于 `wiki/`） | 需求工程产物、项目管理基础（backlog、sprint、术语表等） | 长期，随需求演进 |
| 过程 | `notes/` | 对话中产生的上下文，**一个 issue 一份** | 随 issue 关闭而压缩归并 |

### 3.0 Wiki 本地工作方式

- Wiki 是独立仓库 `https://github.com/Ghostflamez/ScriptMyself.wiki.git`，本地克隆到主仓库的 `wiki/` 目录，该目录已在主仓库 `.gitignore` 中忽略。
- 页面为扁平结构（`Home.md`、`_Sidebar.md`、`<Page-Name>.md`），页面间链接用 `[[显示文字|Page-Name]]`。
- Wiki 改动在 `wiki/` 内单独 commit / push，不经过主仓库 PR；在对应 note 中记录改了哪些页面。

### 3.1 notes 生命周期

1. 开始处理某个 issue 时，创建 `notes/issue-<编号>-<简短slug>.md`（模板：[notes/_template.md](notes/_template.md)）。
2. 处理过程中，对话里产生的关键上下文（讨论、取舍、待定问题、结论）持续追加到该 note。
3. 当该 issue 对应的 PR 被 merge、issue 被标记为 closed 后：
   - 将 note **压缩总结**，把长期有效的内容并入本文件（通常是 §4 决策记录，必要时更新 §1/§2）；
   - 需求/项目管理相关的结论同步到 `wiki/`；
   - 删除该 note 文件（原文保留在 git 历史中）。

### 3.2 AI agent 工作约定

- 开始工作前：读 `AGENTS.md` → 确认当前关联的 issue → 读对应 `notes/issue-*.md`（如有）→ 按需读 `wiki/`。
- 没有关联 issue 的工作，先与维护者确认是否需要建 issue。
- 不在 `AGENTS.md` 中写过程性内容；不确定放哪里时，先放 note。
- 与维护者的对话使用中文；**所有 issue 与 PR（标题、描述、评论）必须使用英文**；代码、标识符与 commit message 使用英文。

## 4. 决策记录

> 格式：`D-编号 | 日期 | 决策 | 理由 | 来源（issue/PR）`。被推翻的决策保留并标注 `已废弃 → D-xxx`。

| ID | 日期 | 决策 | 理由 | 来源 |
| --- | --- | --- | --- | --- |
| D-001 | 2026-10-21 | 建立三层 AI 上下文体系：`AGENTS.md`（顶层）/ `wiki/`（需求与项目管理）/ `notes/`（按 issue 的过程上下文） | 分离长期知识与过程信息，控制顶层上下文体积 | 维护者指示 |
| D-002 | 2026-10-21 | 采用 Agile；当前处于无限期 Sprint 0，专注需求工程 | 先厘清需求再进入实现 | 维护者指示 |
| D-003 | 2026-10-21 | 使用 GitHub Wiki 承载需求工程与项目管理；本地克隆到被忽略的 `wiki/` 目录供 AI 读写 | 维护者偏好 GitHub Wiki；本地克隆保证 AI 可直接访问 | 维护者指示 |
| D-004 | 2026-10-21 | issue 关闭后 note 压缩并入 `AGENTS.md`，随后直接删除 note（不另设归档） | 保持 `notes/` 只含进行中的上下文；原文可从 git 历史找回 | 维护者指示 |
| D-005 | 2026-10-21 | 对话使用中文；issue、PR、代码、标识符、commit message 一律使用英文 | 维护者指示 | 维护者指示 |
| D-006 | 2026-10-21 | 项目初始化 PR（#1，建立上下文规范）不关联 issue；此后所有工作以 issue 为单位 | 初始化先于 issue 流程存在 | PR #1 |
