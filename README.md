# 94-844 Generative AI Lab (Fall 2025) — Assignment #1  
### Prompt Engineering with LLMs  
Prof. Sara Kingsley · Heinz College · Carnegie Mellon University  

**Team Members:** Ansh , Arthur, Jiayi 
**Due Date:** November 2, 2025 · **Weight:** 20% (Part A 10% + Part B 10%)

---

## Overview

Prompt engineering is the process of designing and refining inputs (prompts) to elicit desired outputs from a large language model (LLM).  
This assignment explores how prompt structure, specificity, and reasoning style affect LLM performance and reliability.

Our work is divided into two parts:

| Section | Focus | Description |
|----------|--------|-------------|
| **Part A — Prompt Design Experiments** | Design & Analysis | Created and tested five distinct prompt structures across multiple tasks to observe how prompt framing changes model outputs. |
| **Part B — Zero, Few-Shot & Chain-of-Thought Prompting** | Temperature Sweep & Performance Study | Evaluated LLM accuracy under different prompt styles and sampling temperatures using the HellaSWAG reasoning benchmark. |

---

## 🧩 Part A — Experimenting with Prompt Design (10%)

### 🎯 Objectives
1. Design five diverse prompts for each task that differ in structure and style.  
2. Submit each prompt to the OpenAI API and record model outputs.  
3. Analyze which prompt styles perform best and why.  
4. Derive best practices for prompt crafting based on observed LLM behavior.

### 🧠 Tasks Explored
- **Summarization:** condensing reports into concise insights - analysis done by Jiayi
- **Creative Writing:** open-ended story construction - analysis done by Arthur
- **Question Answering:** fact-based comprehension  - analysis done by Ansh


Each task’s results are analyzed for:
- Accuracy / quality of generation  
- Hallucination rates  
- Sensitivity to instruction phrasing  

### 🧾 Deliverables
- **`part_a_experiments.ipynb`** — Colab notebook with API calls, outputs, and visual examples.  
- **`part_a_report.pdf`** — Includes analysis tables, discussion of patterns, and derived prompt engineering principles.

---

## 🔬 Part B — Zero, Few-Shot & Chain-of-Thought Prompting (10%)

### 🎯 Objective
To measure how different prompting strategies and temperature settings affect LLM reasoning accuracy on a multiple-choice benchmark task.

We experimented with:
1. **Baseline Prompt** — Direct question with no examples.  
2. **1-Shot Prompt** — Includes one example demonstration.  
3. **3-Shot Prompt** — Includes three example demonstrations.  
4. **5-Shot Prompt** — Five example demonstrations (standard few-shot).  
5. **Chain-of-Thought (CoT)** — Explicit reasoning before final answer.  
6. **Custom Variants** — Example order shuffled and mislabeled versions.

### 🧮 Dataset
- **Benchmark:** HellaSWAG (validation split)  
- **Subset:** Randomly sampled instances for speed and reproducibility  
- **Goal:** Evaluate each prompt type on the same set of questions  

### 🧰 Code Overview

#### `run_experiments()`
Runs all prompt types for a given temperature and iteration; records accuracy and model outputs.

#### `run_temperature_variance()`
Sweeps across temperatures ( `[0.0, 0.4, 0.6, 1.0]` ) and aggregates results for visual analysis.



Results are saved and auto-downloaded as:

