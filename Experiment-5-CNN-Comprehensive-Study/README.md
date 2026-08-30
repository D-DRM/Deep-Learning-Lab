# Experiment 5 — CNN Training, Regularization, Optimization, Transfer Learning & Cross-Validation

CS3807 Deep Learning Laboratory — comprehensive study of CNN training on the Oxford-IIIT Pet dataset using MobileNetV2, covering weight initialization, regularization, optimizers, hyperparameter tuning, transfer learning/fine-tuning, and 5-fold cross-validation for final model selection.

## Overview

A single MobileNetV2 backbone (ImageNet-pretrained) is used throughout. Each section trains the same architecture under a different design choice, using the resulting training/validation curves to pick the best setting before moving to the next stage. The best configurations from each stage are then carried into a 5-fold cross-validation comparison, and the winning configuration is retrained and evaluated once on a held-out test set.

**Dataset:** [Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) (37 breeds, cats & dogs), loaded via `tensorflow_datasets`, resized to 224×224×3.

## What's covered

- Weight initialization: Zero, Random, Xavier/Glorot, He
- Regularization: none, L2, Dropout, Batch Normalization
- Optimizers: SGD, Momentum, RMSProp, Adam
- Hyperparameter sweeps: learning rate, batch size, dropout rate
- Transfer learning: feature extraction (frozen base) vs. fine-tuning (unfrozen top layers)
- 5-fold cross-validation over the best candidate configurations
- Final model evaluation on an independent test set (accuracy, precision, recall, F1, confusion matrix)
- Additional exercise: two extra hyperparameter combinations benchmarked against the selected configuration

## Results summary

| Stage | Best setting | Result |
|---|---|---|
| Weight initialization | Zero | 91.30% val. accuracy |
| Regularization | Batch Normalization | 91.30% val. accuracy |
| Optimizer | RMSProp / Adam | 90.22% val. accuracy |
| Hyperparameters | LR 0.001, batch size 32, dropout 0.25 | — |
| Transfer learning | Feature Extraction | 89.95% val. accuracy (vs. 82.20% fine-tuning) |
| **Final selected model (5-fold CV)** | **Batch Normalization** | **91.27% ± 0.52% CV accuracy** |
| **Final test evaluation** | — | **89.10% test accuracy** (Precision 89.18%, Recall 89.03%, F1 88.95%) |

Full per-epoch curves, all 15 required plots, per-fold cross-validation tables, and the confusion matrix are generated inline in the notebook.

## Requirements

- Python 3.10+
- TensorFlow / Keras
- `tensorflow_datasets`, `scikit-learn`, `matplotlib`, `seaborn`, `pandas`, `numpy`

```bash
pip install tensorflow tensorflow-datasets scikit-learn matplotlib seaborn pandas numpy
```

A GPU is strongly recommended — the notebook was run on a Kaggle GPU session (Tesla T4).

## How to run

1. Open `LAB5_CODE.ipynb` in Jupyter, Colab, or Kaggle.
2. Run all cells top to bottom in a single pass — later sections (cross-validation, final evaluation) depend on results and variables created earlier in the notebook.
3. The Oxford-IIIT Pet dataset downloads automatically via `tensorflow_datasets` on first run (internet access required).
4. All plots are saved at 300 DPI into a `Figures/` folder and zipped at the end of the notebook for easy download.

## Notes

- The test set is held out and never used during any of the tuning, initialization, regularization, optimizer, or cross-validation stages — it is touched only in the final evaluation section, per standard ML practice.
- Cross-validation reports both mean accuracy and standard deviation across folds, since mean accuracy alone can hide inconsistent configurations (see the notebook's discussion for an example where two configurations tie on mean but differ meaningfully in variance).
