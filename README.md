# Handwritten Digit Classification Using Deep Learning (MNIST)

## Project Overview

This project builds a deep learning model to classify handwritten digits from 0 to 9 using the MNIST dataset. The model is developed with TensorFlow and Keras and demonstrates core neural network concepts, including data normalization, batch normalization, dropout regularization, model training, and evaluation.

Training and validation metrics are visualized to help understand the model's learning behavior and identify potential overfitting.

## Dataset

**Dataset:** MNIST Handwritten Digits

**Source:** TensorFlow/Keras (`tensorflow.keras.datasets.mnist`)

The MNIST dataset contains 70,000 grayscale images of handwritten digits, each with a resolution of 28 × 28 pixels.

* Training set: 60,000 images
* Test set: 10,000 images
* Number of classes: 10 (digits 0–9)
* Image format: Grayscale, 28 × 28 pixels

The dataset is loaded directly through TensorFlow/Keras, so no separate manual download is required.

## Project Objectives

* Load the MNIST dataset using TensorFlow/Keras.
* Normalize image pixel values to the range [0, 1].
* Prepare image data for a dense neural network.
* Build a deep neural network with two or three hidden layers.
* Apply batch normalization to improve training stability.
* Use dropout regularization to reduce overfitting.
* Train the model with validation data over multiple epochs.
* Visualize training and validation accuracy and loss.
* Evaluate the trained model on the test dataset.

## Methodology

### 1. Dataset Loading

Load the MNIST dataset using the built-in Keras dataset loader.

```python
from tensorflow.keras.datasets import mnist

(x_train, y_train), (x_test, y_test) = mnist.load_data()
```

### 2. Data Preprocessing

Prepare the images for neural network training.

Steps include:

* Normalize pixel values from the original range of 0–255 to 0–1.
* Flatten each 28 × 28 image into a 784-element vector when using a dense neural network.
* Keep the integer class labels for sparse categorical cross-entropy, or convert them to one-hot encoded labels if using categorical cross-entropy.

### 3. Model Architecture

Build a deep neural network using TensorFlow/Keras with:

* Two or three hidden layers.
* Dense layers with ReLU activation.
* Batch Normalization after one or more hidden layers.
* Dropout layers to reduce overfitting.
* An output layer with 10 units and Softmax activation.

The Softmax output produces a probability distribution across the ten digit classes.

### 4. Model Training

Compile and train the model using an appropriate optimizer and loss function.

Training configuration:

* Optimizer: Adam
* Loss: Sparse Categorical Cross-Entropy or Categorical Cross-Entropy, depending on label encoding
* Validation: Validation split from the training data
* Epochs: Approximately 10–20
* History tracking: Training and validation metrics recorded across epochs

### 5. Training Visualization

Plot training and validation accuracy across epochs to examine learning progress.

Optionally, plot training and validation loss to identify signs of overfitting or underfitting.

### 6. Model Evaluation

Evaluate the final trained model using the held-out test dataset.

Report:

* Test accuracy
* Test loss
* Training and validation accuracy plots
* Training and validation loss plots, if included

The test dataset should be reserved for final evaluation rather than used to tune the model repeatedly.

## Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Matplotlib
* Google Colab / Jupyter Notebook

## Project Structure

```text
mnist-handwritten-digit-classifier/
│
├── MNIST_Digit_Classifier.ipynb
└── README.md
```

The notebook contains the preprocessing steps, model architecture, training process, visualizations, and evaluation results.

## How to Run

1. Open the notebook in Google Colab or Jupyter Notebook.
2. Ensure TensorFlow, NumPy, and Matplotlib are available.
3. Run the cells in order to load and preprocess the dataset.
4. Build, compile, and train the neural network.
5. Review the accuracy and loss plots.
6. Evaluate the model on the test dataset.

## Results and Findings

Complete this section after running the notebook.

Include:

* Final test accuracy and test loss.
* Number of epochs used.
* Training versus validation accuracy.
* Training versus validation loss, if available.
* Observations about overfitting and the impact of batch normalization and dropout.

Avoid reporting performance values until they have been measured from the actual model.

## Conclusion

This project demonstrates how a deep neural network can classify handwritten digits using the MNIST dataset. It provides practical experience with image preprocessing, neural network architecture design, batch normalization, dropout regularization, and model evaluation.

The visualizations help explain how the model learns over time and whether its performance on unseen data is consistent with its training results.

## Author

Nadiya Nowshin
