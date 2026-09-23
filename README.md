# CS5720 Neural Network and Deep Learning - Home Assignment 2

## Student Information

* **Name:** Ruyi Gai
* **Student ID:** 700778329
* **Course:** CS5720 Neural Network and Deep Learning
* **Semester:** Fall 2026
* **University:** University of Central Missouri

---

## Files

```text
Home Assignment 2.docx
Assignment 2.ipynb
README.md
dog.jpg
```

### `Home Assignment 2.docx`

This document contains:S creenshots of the results 代码和结果截图

### `Assignment 2.ipynb`

The Jupyter Notebook contains:

* The code and results for all five programming questions
* Comments explaining the main steps of the code

### `dog.jpg`

The grayscale dog image used for the Sobel edge detection task in Question 4.（彩色的）

---

## Assignment Overview

This assignment focuses on practical implementation of Recurrent Neural Networks (RNNs) and Convolutional Neural Networks (CNNs) using TensorFlow/Keras and other Python libraries.

The assignment covers LSTM-based text generation, sentiment classification, convolution operations, edge detection, pooling operations, and CNN architectures including AlexNet and a ResNet-like model.

---

## Question 1: RNN for Text Generation

An LSTM-based RNN was implemented to generate text character by character.

The Shakespeare Sonnets dataset was loaded and converted into integer character IDs. Training sequences were created using 100-character input sequences and the next character as the target.

The model used:
Embedding
    ↓
LSTM (1024 units)
    ↓
Dense (Character Prediction)

---

## Part II: Programming Tasks

### 1. Tensor Manipulations & Reshaping

A random TensorFlow tensor with shape `(4, 6)` was created, and its rank and shape were examined.

The tensor was then:

* Reshaped from `(4, 6)` to `(2, 3, 4)`
* Transposed from `(2, 3, 4)` to `(3, 2, 4)`
* Combined with a smaller tensor of shape `(1, 4)` using broadcasting

This experiment demonstrates how TensorFlow handles tensor rank, shape, reshaping, transposing, and broadcasting operations.

### 2. Loss Functions

Mean Squared Error (MSE) and Categorical Cross-Entropy (CCE) were implemented and compared using different predictions.

The true label was:

```text
[1, 0, 0]
```

Two predictions were tested:

```text
Original:  [0.7, 0.2, 0.1]
Modified:  [0.8, 0.1, 0.1]
```

When the prediction became closer to the true label, both loss values decreased:

* **MSE:** approximately `0.0467 → 0.0200`
* **Categorical Cross-Entropy:** approximately `0.3567 → 0.2231`

A bar chart was also created using Matplotlib to compare the loss values.

This experiment demonstrates that a lower loss generally indicates that the model prediction is closer to the target values.

### 3. Train a Model with Different Optimizers

The MNIST handwritten digit dataset was used to compare two optimization algorithms:

* **Adam**
* **SGD**

Both models used the same neural network architecture:

```text
Flatten (28 × 28)
        ↓
Dense (128, ReLU)
        ↓
Dense (10, Softmax)
```

The models were trained using the same:

* MNIST dataset
* Network architecture
* Learning rate
* Batch size
* Number of epochs
* Validation split

The main difference was the optimizer.

Training and validation accuracy were plotted to compare the learning behavior of Adam and SGD.

The experiment showed that **Adam generally reached high accuracy faster**, while **SGD improved more gradually**.

### 4. Train a Neural Network and Log to TensorBoard

A neural network was trained on the MNIST dataset using the Adam optimizer, and TensorBoard was used to record and visualize the training process.

The model used the following architecture:

```text
Input (28 × 28)
      ↓
Flatten
      ↓
Dense (128, ReLU)
      ↓
Dense (10, Softmax)
```

TensorBoard was used to monitor:

* Training accuracy
* Validation accuracy
* Training loss
* Validation loss

The TensorBoard log files are stored in the `logs/fit/` directory.

#### 4.1 Five-Epoch Experiment

The first experiment trained the model for **5 epochs**.

The training accuracy increased from approximately **89.42%** in the first epoch to **97.67%** in the fifth epoch.

The validation accuracy increased from approximately **95.53%** to **97.75%**.

Both training and validation accuracy improved, while the training and validation loss decreased. There was **no clear evidence of overfitting after five epochs**.

#### 4.2 Ten-Epoch Experiment

A second experiment was performed by increasing the number of epochs from **5 to 10**.

In this experiment:

* **Training Accuracy:** `89.70% → 99.10%`
* **Training Loss:** `0.3753 → 0.0331`
* **Validation Accuracy:** reached `97.78%`
* **Validation Loss:** `0.1731 → 0.0742`

The validation loss reached its lowest value of approximately **0.0732 at epoch 9** and then increased slightly to **0.0742 at epoch 10**.

At the same time, training accuracy continued to improve. This slight divergence between training and validation performance may indicate the **beginning of overfitting**.

Overall, increasing the number of epochs improved the model's training and validation performance in this experiment. However, training for too many epochs may eventually cause overfitting.

---

## Technologies Used

* **Python**
* **TensorFlow / Keras**
* **Matplotlib**
* **Jupyter Notebook**
* **TensorBoard**
* **MNIST Dataset**

---

## Conclusion

This assignment provided both theoretical and practical experience with neural networks and TensorFlow.

The short-answer section covered fundamental concepts such as neural network architecture, weights and biases, activation functions, perceptrons, the vanishing-gradient problem, and the neural network training cycle.

The programming section provided hands-on experience with tensor operations, broadcasting, loss functions, optimizer comparison, MNIST classification, and TensorBoard visualization.

The experiments also demonstrated the impact of optimizer selection and training duration on neural network performance. In particular, increasing the number of epochs improved the model's training accuracy, while the slight increase in validation loss after epoch 9 suggests that continued training could eventually lead to overfitting.

