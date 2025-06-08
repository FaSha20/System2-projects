# Symbolic_Regression

## Overview
Implementing **symbolic regression** using two approaches: **Equation Learner (EQL)** and **Seq2Seq with Transformers**, to discover mathematical expressions from data, emphasizing neurosymbolic AI for interpretable models.

## Purpose
The notebook demonstrates symbolic regression to uncover mathematical relationships in datasets:
- **EQL-Based Approach**: Uses neural networks with specialized activation functions to learn symbolic expressions differentiably.
- **Seq2Seq with Transformers**: Frames symbolic regression as a sequence-to-sequence translation task, leveraging Transformers to generate expressions from numerical data.

## Datasets
- **Dataset 1**: Known formula `2 * x + np.sin(x) + x * np.sin(x)` for benchmarking.
- **Dataset 2**: Unknown formula, with the task to recover it (e.g., `((C)*(x1))*((x2)**2)`).

## Prerequisites
- **Environment**: Python 3.6+, Jupyter Notebook/Lab, GPU recommended (Colab T4 GPU).
- **Dependencies**:
  ```bash
  pip install torch sympy numpy pandas matplotlib sklearn tqdm
  ```
- **Storage/Internet**: For dataset/model downloads via Google Drive.

## How to Run
1. Clone/download `Symbolic_Regression.ipynb`.
2. Set up environment:
   ```bash
   python -m venv symbolic_env
   source symbolic_env/bin/activate
   pip install torch sympy numpy pandas matplotlib sklearn tqdm
   ```
3. Run: `jupyter notebook Symbolic_Regression.ipynb`.
4. Execute cells sequentially, ensuring Google Drive is mounted if needed.
5. Review plots and expression outputs.

## Notes
- The notebook uses Colab with GPU support (`T4`).
- The second dataset’s formula is predicted but requires completion of TODOs for full implementation.
- Ensure compatibility with libraries and sufficient storage for datasets.

## Author
- Fatemeh Shahhosseini
- Course: System 2, Spring 2025
