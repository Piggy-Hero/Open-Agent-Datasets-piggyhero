---
license: mit
language:
- en
- zh
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

**English** | [中文](README_ZH.md)

> 8 real T020 bug-fix trajectories showing the tool use, error localization, and regression verification density of the full human-AI pair-programming corpus.

## What is in this demo

- `bug_fix_demo.jsonl`: **8 records** from `3_Bug修复与重构` (T020-S01 → T020-S08).
- Each row preserves `human_input`, `agent_thought`, `action_taken`, `test_result`, and `human_feedback`.
- The data passed PII anonymization, business-term generalization, and path cleanup; code, diffs, stack traces, and tool results are preserved.
- `LICENSE`: MIT.
- Audit report: [`Sanitization_Report_EN.md`](_reports/Sanitization_Report_EN.md).

## Full dataset

This demo contains only the bug-fix category. The full release contains 87 turns, 1,363 steps, 1,277 tool calls, 8 categories, and a full trajectory file:

| Category | Rows |
|---|---:|
| `1_架构设计与拆分` | 350 |
| `2_功能开发与调试` | 135 |
| `3_Bug修复与重构` | 97 |
| `4_UI与交互体验优化` | 234 |
| `5_商业化与权限控制` | 116 |
| `6_工程化与PWA配置` | 112 |
| `7_人类纠偏与反思` | 268 |
| `8_Meta_Cognition_and_Dataset_Pipeline` | 24 |
| **Total** | **1,336** |

`full_trajectory.jsonl` contains **91** strictly time-ordered segments with complete reasoning, tool chains, code changes, and error stacks.

> **For the full commercial-grade dataset with 1,300+ steps of end-to-end construction, AI debugging, ambiguous-boundary handling, and human correction traces, email gaoyi_sec@outlook.com for a commercial quote.**

## Use cases

- Agent tool-use and action SFT
- Bug reproduction, localization, minimal repair, and regression verification
- Multi-step reasoning and error recovery in real codebases
- Human correction signals and preference data
- Long-context engineering planning and agent benchmarks

## Schema

| Field | Type | Description |
|---|---|---|
| `step_id` | string | e.g. `T020-S01` |
| `category` | enum | one of 8 categories |
| `human_input` | string | original human request or correction |
| `agent_thought` | string | reasoning for the step |
| `action_taken` | array | `{tool, call_id, arguments}` |
| `test_result` | array | `{call_id, is_error, content, error?}` |
| `human_feedback` | string | mid-turn feedback; empty if none |

## Data boundary

This demo is for showcase and evaluation only. It does not contain the full commercial training corpus.

## License

MIT. See [`LICENSE`](LICENSE).
