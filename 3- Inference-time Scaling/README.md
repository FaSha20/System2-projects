# Inference-Time Scaling for Large Language Models (LLMs)

This repository contains a comprehensive framework for exploring and evaluating inference-time scaling techniques for large language models (LLMs). The project focuses on solving mathematical problems using the **Math500** dataset and implements various advanced reasoning methods, including:

- **Chain-of-Thought (CoT) Reasoning**
- **Best-of-N Sampling**
- **Beam Search**
- **Self-Refinement**
- **Tree of Thoughts (ToT)**
- **A* Search**
- **Monte Carlo Tree Search (MCTS)**

The goal is to evaluate the performance of these methods in generating accurate and concise final answers for challenging mathematical problems.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Implemented Methods](#implemented-methods)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Evaluation](#evaluation)
7. [Results](#results)
8. [Future Work](#future-work)
9. [Contributing](#contributing)
10. [License](#license)

---

## Project Overview

This project explores inference-time scaling techniques for LLMs, focusing on mathematical reasoning tasks. The **Math500** dataset is used as the benchmark, which includes a variety of mathematical problems ranging from basic arithmetic to advanced calculus and algebra.

The implemented methods aim to:
- Improve reasoning accuracy.
- Generate concise final answers in the format `\boxed{...}`.
- Compare the effectiveness of different inference techniques.

---

## Dataset

The **Math500** dataset is a collection of challenging mathematical problems designed to test the reasoning and problem-solving capabilities of LLMs. It includes problems from various domains such as:
- Arithmetic
- Algebra
- Geometry
- Calculus

The dataset is loaded from the Hugging Face Hub:
```python
from datasets import load_dataset
dataset = load_dataset("HuggingFaceH4/MATH-500", split="test")
```

---

## Implemented Methods

### 1. **Chain-of-Thought (CoT) Reasoning**
- Generates intermediate reasoning steps before providing the final answer.
- Encourages step-by-step reasoning to improve accuracy.

### 2. **Best-of-N Sampling**
- Generates multiple candidate answers and selects the best one based on scoring (e.g., log-probabilities or LLM-based verification).

### 3. **Beam Search**
- Explores multiple reasoning paths simultaneously and selects the most promising ones based on probabilities.

### 4. **Self-Refinement**
- Iteratively refines the model's output using feedback loops to improve accuracy and coherence.

### 5. **Tree of Thoughts (ToT)**
- Builds a reasoning tree by generating multiple candidate thoughts at each step.
- Evaluates and prunes weaker paths to focus on the most promising solutions.

### 6. **A* Search**
- Uses a heuristic-based search to explore reasoning paths.
- Balances the cost of reasoning steps (`g(n)`) with an estimated cost to the goal (`h(n)`).

### 7. **Monte Carlo Tree Search (MCTS)**
- Combines random simulations with statistical sampling to explore reasoning paths.
- Balances exploration of new paths with exploitation of promising ones.

---

## Installation

### Prerequisites
- Python 3.8 or higher
- `pip` package manager

### Install Required Libraries
Run the following command to install the required dependencies:
```bash
pip install -U datasets huggingface_hub fsspec requests tqdm
```

---

## Usage

### 1. **Run the Notebook**
Open the `Inference_time_Scaling.ipynb` notebook in Visual Studio Code or Jupyter Notebook and execute the cells step-by-step.

### 2. **Evaluate a Specific Method**
Each method has a dedicated evaluation function. For example:
- To evaluate **Chain-of-Thought (CoT)**:
  ```python
  evaluate_cot()
  ```
- To evaluate **Best-of-N Sampling**:
  ```python
  evaluate_best_of_n(use_logprob=True, N=3)
  ```

### 3. **Run Advanced Search Methods**
- **Tree of Thoughts (ToT):**
  ```python
  evaluate_tot(max_samples=30)
  ```
- **A* Search:**
  ```python
  evaluate_astar_random(max_samples=30)
  ```
- **Monte Carlo Tree Search (MCTS):**
  ```python
  evaluate_mcts(max_samples=30)
  ```

---

## Evaluation

### Metrics
The evaluation framework measures:
- **Accuracy:** Percentage of problems solved correctly.
- **Efficiency:** Time taken to generate and evaluate solutions.
- **Conciseness:** Ensures the final answer is in the format `\boxed{...}`.

### Results Storage
Evaluation results are saved in JSON files under the `results/` directory. For example:
- `evaluation_results_cot.json`
- `evaluation_results_astar_random_test.json`

### Analyze Results
Use the `analyze_results` function to summarize the evaluation:
```python
analyze_results(load_existing_results("results/evaluation_results_cot.json"))
```

---

## Results

The results of each method are summarized in terms of:
- Total problems evaluated.
- Number of correct answers.
- Overall accuracy.

### Example Summary
```
=== Results Summary ===
Total problems: 30
Correct answers: 25
Accuracy: 83.33%
```

---

## Future Work

- **Scaling to Larger Datasets:** Evaluate the methods on larger datasets to test scalability.
- **Improved Heuristics:** Develop more effective heuristics for A* and MCTS.
- **Prompt Engineering:** Experiment with different prompts to improve reasoning accuracy.
- **Hybrid Methods:** Combine multiple techniques (e.g., CoT + Beam Search) for better performance.

---

## Contributing

Contributions are welcome! If you have ideas for improving the framework or implementing new methods, feel free to open an issue or submit a pull request.
