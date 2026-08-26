# Experiment 4 — Comparative Study of Deep CNN Architectures Using Transfer Learning

**CS3807 – Deep Learning Laboratory** · Shiv Nadar University Chennai

Comparison of five CNN architectures — **LeNet-5, AlexNet, VGG16, GoogleNet (InceptionV3), and ResNet50** — on the CIFAR-10 dataset, using transfer learning for the ImageNet-pretrained models and training from scratch for LeNet-5/AlexNet (no pretrained weights exist for these).

## Contents

| File | Description |
|---|---|
| `dllab4.ipynb` | Full Kaggle notebook — data loading, model building, training, fine-tuning, and evaluation for all 5 architectures |
| `Experiment_4.tex` | Lab report source (LaTeX), with results and plot inferences filled in |
| `Experiment_4.pdf` | Compiled lab report |
| `plots/` | All result plots (300 DPI), classification report, and comparison tables (CSV) |

## Dataset

CIFAR-10 — 50,000 training / 10,000 testing images, 10 classes, 32×32×3.

## Method

- **VGG16, ResNet50, MobileNetV2** — pretrained ImageNet weights, base frozen → GAP → Dense(256, ReLU) → Softmax(10), trained 15 epochs, then fine-tuned (last block unfrozen) for 8 epochs.
- **GoogleNet (InceptionV3)** — same pipeline, with CIFAR images resized to 75×75 (Inception's minimum input size).
- **LeNet-5, AlexNet** — no pretrained weights available; built and trained from scratch on native 32×32 CIFAR-10 images.
- Optimizer: Adam · Loss: Categorical Cross-Entropy · Batch size: 32.

## Results

| Model | Parameters | Test Accuracy (%) | Training Time (min) |
|---|---|---|---|
| LeNet-5 | 83,126 | 52.69 | 1.83 |
| AlexNet | 5,282,378 | 82.04 | 4.87 |
| VGG16 | 14,848,586 | 79.19 | 6.49 |
| GoogleNet (InceptionV3) | 22,329,898 | 70.04 | 11.15 |
| ResNet50 | 24,114,826 | 65.33 | 6.18 |

**Key observation:** models trained from scratch at CIFAR-10's native scale (AlexNet, LeNet-5) were not handicapped by the resolution mismatch that limits the ImageNet-pretrained backbones (which expect 224×224 input), which is why AlexNet outperforms the deeper pretrained networks here. Full discussion and per-model confusion matrices are in the report.

## Environment

Trained on Kaggle (Tesla T4 GPU), TensorFlow/Keras.
