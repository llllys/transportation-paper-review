# 输入示例 / Example Inputs

## 示例 1：标准使用（中文）

```
请用 trc-paper-review skill 严格审稿我上传的论文，目标期刊 Transportation Research Part C。

上传材料：
- 主论文 PDF（信号控制方向，基于强化学习）
- 附录（额外实验）
- 2 篇范例论文（近两年 TR-C 上发表的同方向论文，作为校准标杆）

请特别关注：基线公平性、渗透率敏感性分析、以及摘要中的 claims 是否都被实验支撑。
```

## 示例 2：English, quick triage

```
Review the attached manuscript with the TR-C review skill, target venue TR-C.
Uploaded: main paper LaTeX source + experiment tables.
No exemplar papers provided — use the built-in TR-C calibration profile.
Give me the full review report in English.
```

## 示例 3：复审（re-review）

```
这是修改后的版本（v2）和上一轮的审稿报告。
请用 skill 的复审模式逐条核验：上一轮每位 reviewer 的 Major Issues 是否已被解决？
对比两轮评分变化，判断当前是否达到 Minor Revision 水平。
```

## 上传范例论文的建议

- 选择与被审稿论文**同一子领域**、近 2–3 年发表于 TR-C 的论文 1–3 篇；
- 优先选择你认可的"标杆论文"（方法严谨、实验充分）；
- PDF 需可读取（非纯扫描件）；若某篇无法解析，skill 会声明并将其排除出校准；
- 范例论文用于校准**证据标准**（数据规模、实验深度、基线选择、图表规范），而不是要求你的论文与它们做同样的贡献。
