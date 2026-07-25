# Experiment 2: Multi Layer Perceptron

## Objective

Implementation of Multi Layer Perceptron models to understand the role of hidden layers, activation functions, and backpropagation in solving classification problems.

## Experiments Implemented

This experiment contains:

1. Multi Layer Perceptron classification model
2. XOR classification using Multi Layer Perceptron

## Description

A Multi Layer Perceptron (MLP) was implemented using neural network concepts. Unlike a Single Layer Perceptron, an MLP contains one or more hidden layers that allow the network to learn non-linear relationships.

The model learns using:

- Forward propagation
- Backpropagation
- Gradient-based optimization

The XOR problem was implemented to demonstrate the advantage of MLPs over Single Layer Perceptrons. Since XOR is not linearly separable, a hidden layer is required to learn the required non-linear decision boundary.

## XOR Experiment

The XOR gate was classified using an MLP with:

- Input layer: 2 neurons
- Hidden layer: 2 neurons
- Output layer: 1 neuron

The model successfully learned the XOR relationship and produced the correct output for all input combinations.

## Results

The experiment demonstrates that:

- Single Layer Perceptrons fail for non-linear problems like XOR.
- Multi Layer Perceptrons can solve XOR by learning hidden feature representations.
- The loss decreases during training as the network updates its weights through backpropagation.

## Files

### Experiment_2_MLP.ipynb

Contains:

- MLP model implementation
- Model training
- XOR classification
- Prediction results
- Visualization of decision boundaries and loss curves


### Experiment_2_Report.pdf

Contains:

- Theory of Multi Layer Perceptrons
- Network architecture
- Training methodology
- Results and analysis


### plots/

Contains generated 300 DPI PNG images:

- XOR_MLP_boundary.png
- MLP_training_loss.png

## Dependencies

Required Python libraries:

- NumPy
- Matplotlib
- Scikit-learn

Install dependencies using:

```bash
pip install numpy matplotlib scikit-learn
```

## How to Run

1. Open `Experiment_2_MLP.ipynb` using Google Colab or Jupyter Notebook.

2. Install the required dependencies.

3. Run all cells sequentially.

4. The notebook will train the MLP model and generate the required plots.

## Conclusion

This experiment demonstrates that Multi Layer Perceptrons overcome the limitations of Single Layer Perceptrons by using hidden layers and non-linear activation functions. The XOR experiment confirms that MLPs can learn complex non-linear relationships that cannot be solved using simple linear classifiers.

## Additional Task

An additional XOR classification experiment was performed using a Multi Layer Perceptron.

The model uses hidden layers and nonlinear activation to solve the XOR problem, which cannot be solved by a Single Layer Perceptron.

Additional files:

- `MLP_XOR.ipynb`
- `Additional_Task_Report.pdf`