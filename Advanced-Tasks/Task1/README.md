# Task 1: News Topic Classifier Using BERT

## Objective
Fine-tune a transformer model (BERT) to classify news headlines into topic categories.

---

## Dataset
**AG News Dataset** — Available on [Hugging Face Datasets](https://huggingface.co/datasets/fancyzhx/ag_news)

| Label | Category |
|-------|----------|
| 0 | World |
| 1 | Sports |
| 2 | Business |
| 3 | Sci/Tech |

---

## Setup & Installation

```bash
pip install datasets transformers evaluate numpy torch
```

---

## Usage

```bash
python train.py
```

---

## What It Does

- Tokenizes and preprocesses the AG News dataset using `bert-base-uncased` tokenizer
- Fine-tunes the `bert-base-uncased` model for 4-class sequence classification
- Evaluates using **Accuracy** and **F1-score (weighted)**
- Saves the trained model and tokenizer to `./news_classifier`

---

## Training Configuration

| Parameter | Value |
|-----------|-------|
| Model | bert-base-uncased |
| Max Length | 128 tokens |
| Batch Size | 16 |
| Epochs | 3 |
| Learning Rate | 2e-5 |
| Weight Decay | 0.01 |

---

## Project Structure

```
task1/
├── train.py              # BERT fine-tuning script
├── news_classifier/      # Saved model & tokenizer
├── results/              # Training checkpoints
├── logs/                 # Training logs
└── README.md
```

---

## Requirements

```
torch
transformers>=4.0.0
datasets>=5.0.0
evaluate>=0.4.0
numpy
```

---

## Known Issues & Fixes

> **Dataset loading error:** If you see `HfUriError: Invalid HF URI 'hf://datasets/ag_news'`, use the namespaced version:
> ```python
> dataset = load_dataset("fancyzhx/ag_news")  # ✅ Correct
> # dataset = load_dataset("ag_news")          # ❌ Deprecated
> ```

> **Slow training on CPU:** Training the full dataset on CPU takes several hours. It is recommended to use Google Colab with a free T4 GPU (Runtime → Change runtime type → T4 GPU) for ~15–20 min training.

---

## Skills Gained
- NLP using Transformers
- Transfer learning & fine-tuning
- Evaluation metrics for text classification
- Lightweight model deployment (Streamlit / Gradio)
