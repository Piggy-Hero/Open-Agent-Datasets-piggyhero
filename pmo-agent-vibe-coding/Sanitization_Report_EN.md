# Sanitization Report — Open Source Demo (EN)

## 1. Scope

This report covers `bug_fix_demo.jsonl`, an 8-record slice of the T020 bug-fix trajectory.

> This demo contains 8 rigorously cleaned multi-step reasoning traces and demonstrates the same level of sanitization validation used for the full release.

## 2. Demo inventory

| Item | Value |
|---|---:|
| Records | 8 |
| Step range | T020-S01 → T020-S08 |
| Category | `3_Bug修复与重构` |
| File size | 44,907 bytes |
| JSON parse | 8 / 8 PASS |
| Empty `agent_thought` | 0 |
| U+FFFD | 0 |
| PII / real username | 0 |
| Known business names | 0 |

## 3. Validation pipeline

The demo is not a hand-written sample. It was taken from the fully processed commercial release after the following gates:

1. **PE / Meta-Prompt audit** — 4 assistant responses, 5 long Meta-Prompt blocks isolated; no code or debugging trace was removed.
2. **PII anonymization** — 6,909 path/username replacements across the full release.
3. **Business-term generalization** — 370 business-name, 927 project-code, 3,938 project-path, 2,482 temp-path, and 431 product-name replacements.
4. **Dirty-data cleanup** — 27 empty `agent_thought` rows removed; 2 encoding-corrupted tool outputs repaired.
5. **Final JSON validation** — 8 demo rows and 1,427 full-release lines parsed with `JSON.parse()`; 0 errors.

## 4. Full-release reference

| Item | Value |
|---|---:|
| Categories | 8 |
| SFT rows | 1,336 |
| Full trajectory rows | 91 |
| Steps | 1,363 |
| Tool calls | 1,277 |

The demo covers only the bug-fix category. It is intentionally small and is not the full training corpus.

## 5. Conclusion

- PASS: the 8 demo rows are valid JSONL and preserve the original multi-step reasoning and tool chain.
- PASS: no PII, known business names, empty reasoning, or encoding replacement characters remain.
- PASS: the demo demonstrates the same sanitization and validation standard as the full commercial release.
