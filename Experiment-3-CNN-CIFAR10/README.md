# Experiment 3 — Implementation of Convolutional Neural Networks (CNNs) for Image Classification

**CS3807 – Deep Learning Laboratory** · Shiv Nadar University Chennai

Implementation of a CNN for CIFAR-10 image classification, covering the convolution operation, kernel size/stride/padding effects, feature map visualization, pooling comparison, and full model training and evaluation.

## Contents

| File | Description |
|---|---|
| `LAB3_CODE.ipynb` | Full notebook — convolution experiments, feature map visualization, CNN construction, training, and evaluation |
| `Experiment_3_Report.pdf` | Completed lab report with all results, plots, and inferences |

## Dataset

CIFAR-10 — 50,000 training / 10,000 testing images, 10 classes, 32×32×3, perfectly balanced (5,000 images/class).

## Tasks Covered

1. **Dataset preparation** — load CIFAR-10, inspect dimensions, display samples, plot class distribution
2. **Kernel size comparison** — 3×3, 5×5, 7×7 filters, feature map output sizes
3. **Stride & padding study** — effect on output dimensions (valid vs same padding, stride 1 vs 2)
4. **Feature map visualization** — 8 feature maps from the first convolutional layer (16 filters)
5. **Pooling comparison** — Max Pooling vs Average Pooling, output size and accuracy
6. **CNN construction & training** — `Conv → ReLU → MaxPool → Conv → ReLU → MaxPool → Flatten → Dense → Softmax`, Adam optimizer, 20 epochs, batch size 32
7. **Model evaluation** — accuracy, precision, recall, F1-score, confusion matrix, classification report

## Results

| Metric | Value |
|---|---|
| Training Accuracy | 97.20% |
| Testing Accuracy | 69.40% |
| Precision (Macro) | 69.97% |
| Recall (Macro) | 69.40% |
| F1-score (Macro) | 69.23% |
| Test Loss | 2.1924 |
| Trainable Parameters | 545,098 |

**Pooling comparison:** Max Pooling (63.09%) outperformed Average Pooling (61.11%).

**Filter count comparison:** Increasing filters from 16 → 64 improved validation accuracy (68.00% → 70.72%) at the cost of ~4.2× more parameters and ~33% longer training time.

**Key observation:** The gap between rising training accuracy (97.2%) and plateaued/declining validation accuracy (~70%, with a mild downward drift after epoch 14) indicates overfitting, consistent with validation loss bottoming out at epoch 4 (0.86) before climbing steadily to 2.19 by epoch 20. Cat and Bird were the weakest-performing classes, mainly confused with Dog.

## Environment

TensorFlow/Keras, trained on Google Colab.
