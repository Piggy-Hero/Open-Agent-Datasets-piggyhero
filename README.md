# Open Agent & SWE Trajectory Datasets

Welcome to the **Open Agent Datasets** repository! 

This repository serves as a centralized hub for high-quality, open-source datasets aimed at advancing the capabilities of Large Language Models (LLMs) and AI Agents. We focus on providing **100% raw, un-truncated human-AI pair programming traces**, multi-step reasoning chains, and complex software engineering (SWE) problem-solving trajectories.

## 📦 Available Datasets

### 1. PMO-Agent-Vibe-Coding-Trajectory (Demo)
* **Status**: [Available on Hugging Face](https://huggingface.co/datasets/your-username/PMO-Agent-Vibe-Coding-Demo) 
* **Description**: A sample dataset extracted from a real-world, 1200+ steps Vibe-Coding session. It captures the collaboration between a human architect and an AI agent building a complex SaaS frontend from scratch.
* **Key Features**: 
  - **Multi-step Reasoning**: Includes how the agent analyzes, writes code, self-corrects, and runs regressions.
  - **Human-in-the-loop**: Real human corrections, debugging commands, and architectural interventions.
  - **Fully Sanitized**: PII, local paths, and proprietary business logic have been safely redacted.

## 🧠 Why These Datasets?

Most synthetic datasets lack the chaotic reality of true engineering. Our datasets are extracted from actual production-ready projects, containing:
1. **Self-Correction Loops**: See how agents detect their own bugs (e.g., syntax errors, memory leaks) and fix them.
2. **Architecture Refactoring**: Traces showing how to break down monoliths into ES Modules and resolve circular dependencies.
3. **UI/UX Iterations**: From basic logic to pixel-perfect dark modes and PWA configurations.

## 📂 Repository Structure

```text
Open-Agent-Datasets/
 ┣ 📂 PMO-Agent-Demo/      # The demo dataset files
 ┃ ┣ 📜 bug_fix_demo.jsonl # 8 raw multi-step reasoning samples
 ┃ ┣ 📜 README.md          # Dataset specific details
 ┃ ┗ 📂 _reports/          # Sanitization & Quality Control reports
 ┗ 📜 README.md            # This main hub file
