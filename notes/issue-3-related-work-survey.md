# Issue #3：Survey recent research and open-source projects for requirements insights

- **Issue**：https://github.com/Ghostflamez/ScriptMyself/issues/3
- **分支**：`spike/3-related-work-survey`
- **PR**：（待创建）
- **状态**：进行中

## 背景 / 目标

维护者要求：根据项目 scope，调研近几年相关论文与开源项目，提炼对需求工程的启发；允许并行子线程；完成后整理报告写入 Wiki 的合适结构。

## 讨论与上下文

- 2026-10-21：拆为 4 条并行调研线：
  1. 行为/临床研究（ADHD/拖延的数字干预、任务启动、implementation intentions、JITAI、习惯形成）
  2. HCI 与设计（神经多样性用户设计、参与式设计、可及性、自我追踪的伦理与陷阱）
  3. 开源项目（习惯追踪、例程/视觉日程、纯文本任务系统、ADHD 向应用）
  4. DSL 与终端用户编程（trigger-action programming、纯文本格式、个人自动化、LLM 生成脚本）
- 报告在 Wiki 中归入 Requirements Engineering → Elicitation。
- 2026-10-21：四条线完成（B1–B41、H1–H30、O1–O25/C1–C5/S1–S3、D1–D45）。综合页 Related-Work 产出：
  - 36 条需求候选 RC-01–RC-36、12 条风险 RK-01–RK-12、14 个待定问题 OQ-01–OQ-14、8 个建议后续 issue。
  - 关键结论：implementation intentions 是最强理论依据（README 未提）；决策疲劳 / 蔡格尼克 / 助推证据薄弱；开源空白存在但窄；避免默认 streak；AI 起草必须复述确认。
- 维护者曾质疑 issue 是否为英文；核对后 #3 标题与正文均为英文，note 按 D-012 用中文。

## 决策（候选，PR merge 前并入 AGENTS.md §4）

- Related-Work 中的条目均为"需求候选"，不是已决定的需求；决策在后续 issue 中做出。
- 引用键前缀按调研线区分（B/H/O·C·S/D），跨 Wiki 页面唯一。

## 待定问题

- 8 个建议后续 issue（Related-Work §8）待维护者确认后创建。
- 标注为未核实的引用待专门 spike 核对（Related-Work §9）。

## Wiki 改动

| Wiki commit | 页面 | 说明 |
| --- | --- | --- |
| `555527f` | Related-Work、4 个 Related-Work-* 子页、Requirements-Engineering、_Sidebar | 新增调研综合页与四条线报告，挂到 Elicitation 下 |

## 归并清单（PR merge 前完成）

- [ ] 长期有效的决策已并入 AGENTS.md §4
- [ ] 未解决的问题已并入 AGENTS.md §5 或转为新 issue
- [ ] 需求/项目管理结论已同步到 Wiki
- [ ] 删除本 note
