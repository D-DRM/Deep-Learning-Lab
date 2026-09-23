# Experiment 6 — RNN, LSTM and GRU for Sequence Learning and Video Understanding

CS3807 Deep Learning Laboratory | Shiv Nadar University Chennai

## Overview

End-to-end comparison of Vanilla RNN, LSTM and GRU on the [UCI HAR
dataset](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones)
(6-class activity recognition from raw 128×9 inertial signals), extended to
video action recognition with a CNN (MobileNetV2) + LSTM/GRU pipeline on a
UCF101 subset, and a synthetic sequence-reversal task for the
encoder–decoder framework.

## Contents

| File | Description |
|---|---|
| `Experiment_6.ipynb` | Full implementation — preprocessing, RNN/LSTM/GRU training and evaluation, sequence-length sweep, CNN–RNN video pipeline, seq2seq reversal task |
| `Experiment_6_Report.pdf` | Lab report with architecture diagrams, plots, and inferences |

## Results Summary

| Model | Accuracy (%) | Macro F1 (%) | Parameters | Training Time (s) |
|---|---|---|---|---|
| RNN  | 75.56 | 73.96 | 1,974 | 24.69 |
| LSTM | 93.33 | 93.63 | 6,006 | 22.01 |
| GRU  | 94.72 | 95.02 | 4,758 | 19.08 |

GRU gives the best accuracy, fewest parameters among the gated models, and
shortest training time. The Vanilla RNN shows visible gradient instability
around epoch 20 and confuses all three WALKING-type activities; LSTM and
GRU resolve that but still confuse SITTING/STANDING.

**Video task (CNN–LSTM/GRU, Punch vs. TennisSwing):** 100% test accuracy
for both recurrent variants.

**Seq2seq reversal task:** token accuracy and sequence accuracy both 1.0000
on an 8,000-sequence synthetic dataset.

## How to Run

1. Download the UCI HAR raw inertial signals and a small UCF101 subset (see
   report for details and recommended subset sizes).
2. Open `Experiment_6.ipynb` and run all cells top to bottom.
3. Outputs (plots, metrics) are used to fill in `Experiment_6_Report.pdf`.

## Requirements

TensorFlow/Keras, NumPy, scikit-learn, Matplotlib, OpenCV (for video frame
extraction).
