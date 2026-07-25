# Experiment 1: Single Layer Perceptron

## Objective

This experiment implements the Perceptron Learning Algorithm for basic logical gates and analyzes the limitations of a single layer perceptron.

## Contents of the Experiment

The notebook implements:

1. AND Gate using Perceptron
2. OR Gate using Perceptron
3. NOT Gate using Perceptron
4. XOR Gate analysis using Perceptron

## Implementation Details

A Single Layer Perceptron was implemented using Python from scratch.

The model updates weights and bias values using the perceptron learning rule. The final decision boundaries are plotted for each logical gate.

The experiment demonstrates that:

- AND and OR gates can be solved because they are linearly separable.
- NOT gate can be learned using a single input feature.
- XOR cannot be solved because it is not linearly separable.

## Files in this Folder

### Experiment_1_Perceptron.ipynb

This is the Google Colab notebook containing:

- Perceptron implementation
- Training process
- Weight updates
- Gate predictions
- Decision boundary plots

### Experiment_1_Report.pdf

Contains the detailed experiment report including:

- Theory
- Algorithm
- Results
- Inferences
- Conclusion

### plots/

Contains the generated 300 DPI PNG images:

- AND_boundary.png
- OR_boundary.png
- NOT_boundary.png
- XOR_boundary.png


## Dependencies

The notebook requires the following Python libraries:

- NumPy
- Matplotlib

Install them using:

```bash
pip install numpy matplotlib
```

## How to Run

1. Open `Experiment_1_Perceptron.ipynb` using Google Colab or Jupyter Notebook.

2. Install the required dependencies.

3. Run all cells in the notebook.

4. The notebook will generate the perceptron outputs and decision boundary plots.

## Conclusion

This experiment shows that a Single Layer Perceptron can solve linearly separable problems such as AND and OR gates. However, it fails for non-linear problems such as XOR, motivating the need for Multi Layer Perceptrons.