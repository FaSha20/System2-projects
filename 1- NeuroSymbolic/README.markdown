# NeuroSymbolic.ipynb - README

## Overview
`NeuroSymbolic.ipynb` is a Jupyter notebook for a System 2 course (Spring 2025) homework by Fatemeh Shahhosseini (403206519). It explores **Neurosymbolic AI**, using seq2seq models to generate programs for **Visual Question Answering (VQA)**, combining natural language and visual reasoning for interpretable AI.

## Purpose
Demonstrates generating programs with seq2seq models for VQA, where programs act as symbols and seq2seq models as neural structures, leveraging a compositional program space for generalizable solutions.

## Structure
- **Markdown Cells**: Introduce the assignment, student info, and neurosymbolic VQA concepts, with a base64-encoded image.
- **Code Cells**: Likely include Python code for:
  - Loading VQA datasets (e.g., CLEVR) and models (e.g., 6.43GB weights).
  - Implementing and training a seq2seq model for program generation.
  - Evaluating VQA performance.
- **Widgets**: Show download progress for datasets/models using Jupyter widgets.

## Key Components
- **Neurosymbolic Framework**: Programs as symbols, seq2seq models (e.g., Transformer/RNN) as neural components.
- **VQA Task**: Process image-question pairs to generate answers or programs.
- **Dependencies**: Likely uses `torch`, `transformers`, `numpy`, `pandas`, `pillow`, `matplotlib`.
- **Downloads**: Large files (e.g., 6.43GB) for datasets or model weights.

## Prerequisites
- Python 3.6+, Jupyter Notebook/Lab.
- Install: `pip install torch transformers numpy pandas pillow matplotlib seaborn jupyter`.
- GPU recommended; 7GB+ storage; internet for downloads.

## How to Run
1. Download `NeuroSymbolic.ipynb`.
2. Set up environment:
   ```bash
   python -m venv neurosymbolic_env
   source neurosymbolic_env/bin/activate
   pip install -r requirements.txt
   ```
3. Run: `jupyter notebook NeuroSymbolic.ipynb`.
4. Execute cells, monitor downloads, review outputs.

## Notes
- Truncated document limits full details; assumes typical VQA/neurosymbolic setup.
- Ensure widget compatibility (`@jupyter-widgets/controls` v1.5.0).
- Contact instructor for dataset access (e.g., CLEVR).

## Author
- Fatemeh Shahhosseini (403206519)
- Course: System 2, Spring 2025

## License
Academic work; contact author/instructor for usage permissions.