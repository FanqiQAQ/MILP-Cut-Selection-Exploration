# Exploratory Study on Learning-Based Cut Selection for MILP
---
## 📖 Overview
This repository contains the code and report for an exploratory task reproducing the mechanisms of **HEM**. The project investigates how data-driven cut selection policies can replace traditional heuristics in Mixed-Integer Linear Programming (MILP).

**Objective:** Transform the cut selection strategy from "Passive Filtering" to "Active Guiding" to optimize the Maximum Independent Set (MIS) problem.

## 🌏 Key Findings
By implementing a geometric heuristic ($Score = 0.8 \cdot Efficacy + 0.2 \cdot Orthogonality$) and overcoming dual degeneracy using proxy rewards, the following results were achieved on a 150-node dense MIS instance:

| Metric | Default SCIP (Exact) | Heuristic Policy (Approximation) | Improvement |
| :--- | :--- | :--- | :--- |
| **Search Nodes** | 92,837 | **1** | ⬇ 100% (Drastic Reduction) |
| **Solving Time** | 254.66s | **0.24s** | ⬇ >1000x Speedup |
| **Optimality** | 27.0 | 24.0 | 11% Gap (Sacrificed for Speed) |

**Observation:** The learned policy acts as an aggressive **"Diving Heuristic,"** efficiently pruning the search space by fixing variables at the root node.

## 📂 Repository Structure
* `src/`: Contains the executable code.
    * `Exploratory_Task.ipynb`: All-in-one Jupyter Notebook containing the data collection pipeline, heuristic implementation, and comparison experiments.
* `report/`: Contains the detailed PDF report explaining the methodology and process.

## 🚀 How to Run
### Prerequisites
* Python 3.8+
* SCIP Solver (System Installation)
* PySCIPOpt

### Installation
```bash
pip install -r requirements.txt
