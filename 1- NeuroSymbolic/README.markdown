# NeuroSymbolic

## Overview
This notebook explores **Neurosymbolic AI**, using seq2seq models to generate programs for **Visual Question Answering (VQA)**, combining natural language and visual reasoning for interpretable AI.

## Purpose
Demonstrates generating programs with seq2seq models for VQA, where programs act as symbols and seq2seq models as neural structures, leveraging a compositional program space for generalizable solutions.

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
