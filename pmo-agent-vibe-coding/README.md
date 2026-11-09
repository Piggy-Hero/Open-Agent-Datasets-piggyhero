---
license: cc-by-nc-4.0
language:
- zh
- en
task_categories:
- text-generation
tags:
- agent
- tool-use
- bug-fixing
- software-engineering
- demo
pretty_name: PMO Agent Data Pro - Bug Fix Demo
size_categories:
- n<1K
configs:
- config_name: bug_fix_demo
  data_files:
  - split: train
    path: bug_fix_demo.jsonl
---

# PMO Agent Data Pro · Bug Fix Demo

**中文** | [English](README_EN.md)

> 8 条真实 T020 Bug 修复轨迹，用于展示这套人机结对编程数据集的工具调用、错误定位和回归验证密度。

## 这个 Demo 里有什么

- `bug_fix_demo.jsonl`：**8 条** `3_Bug修复与重构` 轨迹（T020-S01 → T020-S08）。
- 每行保留原始 `human_input`、`agent_thought`、`action_taken`、`test_result` 和 `human_feedback`。
- 数据已经过 PII、商业名词与路径脱敏；代码、Diff、报错栈和工具结果保留。
- `LICENSE`：CC BY-NC 4.0。
- 审计报告：[`Sanitization_Report_ZH.md`](_reports/Sanitization_Report_ZH.md)。

## 完整数据集

当前 Demo 只包含 Bug 修复类的 8 条样例。完整版覆盖 87 个 turn、1,363 个 step、1,277 次工具调用，并包含 8 大分类与 full trajectory：

| 分类 | 行数 |
|---|---:|
| `1_架构设计与拆分` | 350 |
| `2_功能开发与调试` | 135 |
| `3_Bug修复与重构` | 97 |
| `4_UI与交互体验优化` | 234 |
| `5_商业化与权限控制` | 116 |
| `6_工程化与PWA配置` | 112 |
| `7_人类纠偏与反思` | 268 |
| `8_Meta_Cognition_and_Dataset_Pipeline` | 24 |
| **合计** | **1,336** |

此外，`full_trajectory.jsonl` 提供 **91 条**严格时间序轨迹，保留完整 reasoning、工具调用链、代码修改与报错栈。

> **如需包含 1300 多步完整的搭建过程、AI排错、模糊边界处理与人类极致纠偏等全量商业级数据集，请发送邮件至 gaoyi_sec@outlook.com 获取商业报价。**

## 适合什么

- Agent 工具调用与动作 SFT
- Bug 复现、定位、最小修复、回归验证
- 真实代码库中的多步推理与错误恢复
- 人类纠偏信号与偏好数据
- 长上下文工程规划与 Agent benchmark

## Schema

| 字段 | 类型 | 说明 |
|---|---|---|
| `step_id` | string | 形如 `T020-S01` |
| `category` | enum | 8 类之一 |
| `human_input` | string | 人类原始需求或纠偏 |
| `agent_thought` | string | 该 step 的 reasoning |
| `action_taken` | array | `{tool, call_id, arguments}` |
| `test_result` | array | `{call_id, is_error, content, error?}` |
| `human_feedback` | string | 中途反馈；无则为空 |

## 数据边界

本 Demo 仅用于展示与评测，不包含完整商业训练集。完整版包含更多架构设计、UI/UX、商业化权限、工程化/PWA、人类纠偏与元认知数据管道轨迹。

## License

CC BY-NC 4.0，详见 [`LICENSE`](LICENSE)。

> **授权声明**：本 Demo 数据集采用 CC BY-NC 4.0 协议，严禁用于商业用途及训练商业模型。如需获取全量商业授权，请联系：gaoyi_sec@outlook.com。
