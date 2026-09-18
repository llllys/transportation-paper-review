# transportation-paper-review

**面向 Transportation Research 系列期刊（以 TR-C 为例）的 AI 模拟审稿 Skill — 严格、真实、有校准的投稿前自查。**

**An AI simulated peer-review skill for the Transportation Research journal series (TR-C first) — strict, realistic, calibrated pre-submission assessment.**

[English](#english) | [中文](#中文)

---

## 中文

### 这是什么

一个可直接安装的 Agent Skill（附独立可复制 Prompt），模拟 **Transportation Research Part C: Emerging Technologies** 的真实审稿流程：3 位领域审稿人（方法严谨性 / 数据与实验 / 创新与文献）+ 副主编（AE）meta-review + 编辑决定（Accept / Minor Revision / Major Revision / Reject）。

设计目标不是"鼓励你投稿"，而是帮你在投稿前发现：

- 论文是否通过 TR-C 最核心的**交通系统后果检验**（知识核心在交通侧，而非技术侧）；
- 哪些问题是 **Fatal**（不修必拒）、**Major**（决定大修还是拒稿）、**Minor**；
- 距离 TR-C 真实发表标准的差距（TR-C Readiness Score /100）；
- P0/P1/P2 修改优先级与符合期刊周期（约 3 个月/轮）的修改时间线。

### 特性

- **符合 TR-C 真实难度**：内置期刊档案（范围、desk-reject 模式、姊妹刊定位）、评分校准纪律（仿真-only/toy 网络/无标定论文封顶 6 分；未通过范围检验封顶 4 分）、9 个子领域专项核查清单（交通预测、跟驰模型、信号控制、CAV、共享出行、MFD、数据与传感、综述、写作合规）。
- **范例论文校准**：上传已发表的 TR-C 论文作为参考附件，skill 会先提取其证据深度、实验规模、基线标准作为标杆，再逐项对比审稿——让评分锚定真实发表水准，而不是泛泛而谈。
- **中英文双语**：跟随用户语言输出；内置中文与英文两套完整报告模板。
- **反幻觉证据约束**：所有批评必须定位到具体 section/equation/table/figure；信息不足时强制声明"所提供材料中未充分说明"；无检索时不编造漏引文献标题。
- **两种用法**：安装为 Agent Skill（推荐），或直接复制 `prompts/` 下的独立 prompt 到任意 LLM。

### 快速开始

**用法 A — 复制 Prompt（无需安装）**

1. 打开 `prompts/trc_review_full_zh.md`（中文完整版）或 `prompts/trc_review_full_en.md`（英文版），全文复制；
2. 连同论文 PDF/LaTeX 一起发给你的 LLM（可同时上传 1–3 篇已发表 TR-C 论文作为校准标杆）；
3. 按输出的 P0/P1/P2 清单修改，改完再跑一次对比分数变化。

快速自查可用精简版 `prompts/trc_review_compact_zh.md`。

**用法 B — 安装 Skill**

下载发布页中的 `trc-paper-review.skill`，导入支持 Agent Skills 的环境（如 Kimi / Claude Code 类工具的技能目录）。skill 触发后自动执行完整流程：期刊契合判定 → 范例校准 → 多审稿人模拟 → AE 决定 → 修改计划。

### 仓库结构

```
├── skills/trc-paper-review/          # Agent Skill（SKILL.md + references/）
│   └── references/                   # 期刊档案、评分校准、双语模板、领域核查清单、范例校准
├── prompts/                          # 可直接复制的独立 prompt（中文完整/英文完整/中文精简）
├── examples/                         # 输入示例
└── docs/                             # 使用说明、伦理边界
```

### 免责声明

本项目为**非官方**工具，不隶属于 Elsevier 或 TR-C 编辑部，不构成真实录用概率预测，不能替代领域专家判断。详见 `docs/ethics.md`。

---

## English

### What this is

An installable Agent Skill (plus standalone copy-ready prompts) that simulates a realistic **Transportation Research Part C: Emerging Technologies** review: 3 domain reviewers (Methodological Soundness / Data & Experiments / Novelty & Literature) + an Associate Editor meta-review + an editorial decision (Accept / Minor Revision / Major Revision / Reject).

It is designed to find, before you submit:

- whether the paper passes TR-C's core **transportation-system-consequence test** (intellectual core on the transportation side, not the technology side);
- which issues are **Fatal** / **Major** / **Minor**;
- the gap to TR-C's real publication bar (TR-C Readiness Score /100);
- a P0/P1/P2 revision plan with a timeline realistic to the journal's ~3-month review cycle.

### Features

- **TR-C-grade difficulty**: built-in journal profile (scope, desk-reject patterns, sister-journal positioning), score calibration discipline (simulation-only/toy-network/uncalibrated papers cap ≈ 6; scope failures cap at 4), and a 9-section domain checklist (prediction, car-following, signal control, CAV, shared mobility, MFD, data & sensing, surveys, writing compliance).
- **Exemplar calibration**: upload published TR-C papers as reference attachments; the skill extracts their evidence depth, experiment scale and baseline standards as the calibration bar before scoring.
- **Bilingual**: full report templates in Chinese and English; output follows the user's language.
- **Anti-hallucination evidence rules**: every criticism anchored to a specific location; mandatory "Not sufficiently specified in the provided material" when evidence is missing; no fabricated missing citations without search.
- **Two ways to use**: install as an Agent Skill (recommended), or copy a standalone prompt from `prompts/` into any LLM.

### Quick start

**Option A — copy a prompt (no install)**: copy `prompts/trc_review_full_en.md` (or the Chinese version), paste it with your paper PDF/LaTeX into your LLM, optionally attaching 1–3 published TR-C papers as calibration exemplars. Revise along the P0/P1/P2 plan, then re-run to compare score movement. A compact Chinese prompt is available for quick triage.

**Option B — install the skill**: download `trc-paper-review.skill` from Releases and import it into a skills-capable agent environment.

### Disclaimer

Unofficial tool; not affiliated with Elsevier or the TR-C editorial board; not an acceptance predictor; not a substitute for expert human review. See `docs/ethics.md`.

## License

MIT — see `LICENSE`.
