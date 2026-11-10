# Open Agent Engineering Datasets

Welcome to the **Open Agent Engineering Datasets** repository! 

This is a curated hub dedicated to advancing the capabilities of Large Language Models (LLMs) and AI Agents in complex software engineering (SWE) tasks. We provide **100% raw, un-truncated human-AI pair programming traces**, focusing on long-context reasoning, self-correction loops, and multi-step tool usage.

## 📦 Featured Dataset: PMO-Agent-Vibe-Coding

Our debut dataset captures a real-world, 1,200+ step Vibe-Coding session where a human architect and an AI agent collaborated from scratch to build a production-ready SaaS frontend (The "Intelligent PMO Hub"). 

### Why is this dataset unique?
Most synthetic datasets lack the chaotic reality of true engineering. Our traces are extracted from actual, painful, and ultimately successful debugging sessions:
*   **Self-Correction Loops**: Watch the agent detect its own memory leaks (e.g., ECharts lifecycle management, SortableJS ghost nodes) and fix them.
*   **Architecture Refactoring**: Traces showing how to break down a 6,800-line monolith into 14 ES Modules, including resolving circular dependencies via Dependency Injection.
*   **Human-in-the-loop (HITL)**: Real human interventions, strict architectural red lines, and "tough love" feedback provided during the process.

## 🧠 Repository Structure

```text
Open-Agent-Engineering-Datasets/
 ┣ 📂 datasets/
 ┃ ┣ 📂 PMO-Agent-Demo/         # Open-source demo (CC BY-NC 4.0)
 ┃ ┃ ┣ 📜 bug_fix_demo.jsonl   # 8 high-quality multi-step reasoning traces
 ┃ ┃ ┣ 📜 README.md            # Dataset details & YAML Front Matter
 ┃ ┃ ┣ 📜 LICENSE              # CC BY-NC 4.0
 ┃ ┃ ┗ 📂 _reports/            # Bilingual Sanitization & QC reports
 ┗ 📜 README.md
```

⚖️ Licensing & Commercial Use
We believe in open research but also respect the value of high-quality engineering data.

Open-Source Demo: The sample data provided in this repository is licensed under CC BY-NC 4.0 (Attribution-NonCommercial 4.0 International). You are free to use it for academic research and personal learning. Commercial use or training commercial models is strictly prohibited.

Premium Commercial Version: The full dataset (1,435+ steps, including deep debugging logs, long-context trajectories, and failure cases) is available for commercial licensing.

📧 For commercial inquiries, bulk licensing, or custom dataset generation, please contact: gaoyi_sec@outlook.com

Stay tuned for more datasets related to Agentic workflows, frontend engineering, and automated software testing.
