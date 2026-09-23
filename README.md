# CS5720 Neural Network and Deep Learning - Home Assignment 2

## Student Information

* **Name:** Ruyi Gai
* **Student ID:** 700778329
* **Course:** CS5720 Neural Network and Deep Learning
* **Semester:** Fall 2026
* **University:** University of Central Missouri


## Files

```text
Home Assignment 2.docx
Assignment 2.ipynb
README.md
dog.jpg
```

### `Home Assignment 2.docx`

This document contains: Code and results screenshots

### `Assignment 2.ipynb`

The Jupyter Notebook contains:

* The code and results for all five programming questions
* Comments explaining the main steps of the code

### `dog.jpg`

The grayscale dog image used for the Sobel edge detection task in Question 4.（彩色的）


## Assignment Overview

This assignment focuses on practical implementation of Recurrent Neural Networks (RNNs) and Convolutional Neural Networks (CNNs) using TensorFlow/Keras and other Python libraries.

The assignment covers LSTM-based text generation, sentiment classification, convolution operations, edge detection, pooling operations, and CNN architectures including AlexNet and a ResNet-like model.


## Question 1: RNN for Text Generation

An LSTM-based RNN was implemented to generate text character by character.

The Shakespeare Sonnets dataset was loaded and converted into integer character IDs. Training sequences were created using 100-character input sequences and the next character as the target.

The model used:

```text
Embedding
    ↓
LSTM (1024 units)
    ↓
Dense (Character Prediction)
```
The model was trained for 10 epochs using the Adam optimizer.

New text was generated one character at a time. Temperature scaling was also explained to demonstrate how temperature affects the randomness and diversity of generated text.


## Question 2: Sentiment Classification Using RNN

The IMDB movie review dataset was used to build an LSTM-based sentiment classifier.

The reviews were represented as integer sequences and padded to a maximum length of 200.

The model used:

```text
Embedding
    ↓
LSTM (128 units)
    ↓
Dense (1, Sigmoid)
```

The model was trained for 5 epochs using the Adam optimizer.

A confusion matrix and classification report were generated to evaluate:

* Accuracy
* Precision
* Recall
* F1-score

The model achieved approximately 83%–84% test accuracy.

The precision-recall tradeoff was also discussed to explain why both metrics are important for sentiment classification.


## Question 3: Convolution Operations with Different Parameters

A 5×5 input matrix and a 3×3 kernel were used to demonstrate convolution operations with different stride and padding settings.

The following four cases were implemented:

* Stride = 1, Padding = VALID
* Stride = 1, Padding = SAME
* Stride = 2, Padding = VALID
* Stride = 2, Padding = SAME

The output feature maps for each case were printed using TensorFlow.

This experiment demonstrates how stride and padding affect the size and values of convolution outputs.


## Question 4: CNN Feature Extraction with Filters and Pooling

### Task 1: Sobel Edge Detection

A grayscale dog image was processed using Sobel filters for edge detection.

Both Sobel-X and Sobel-Y filters were applied, and the following images were displayed:

* Original Image
* Sobel-X Edge Detection
* Sobel-Y Edge Detection

### Task 2: Max Pooling and Average Pooling

A random 4×4 matrix was created and processed using:

* 2×2 Max Pooling
* 2×2 Average Pooling

The original matrix and both pooled matrices were printed.

This experiment demonstrates the effects of different pooling operations on feature maps.


## Question 5: CNN Architectures

### Task 1: AlexNet

A simplified AlexNet architecture was implemented using TensorFlow/Keras.

The model includes:

```text
Conv2D
MaxPooling
Conv2D
MaxPooling
Conv2D
Conv2D
Conv2D
MaxPooling
Flatten
Dense
Dropout
Dense
Dropout
Dense (10, Softmax)
```

The model summary was printed after defining the architecture.

### Task 2: ResNet-like Model

A Residual Block was implemented using two Conv2D layers and a skip connection.

Two residual blocks were then used to build a simple ResNet-like model:

```text
Input
   ↓
Conv2D
   ↓
Residual Block
   ↓
Residual Block
   ↓
Flatten
   ↓
Dense (128)
   ↓
Dense (10, Softmax)
```

The model summary was printed to show the complete architecture.


## Technologies Used

* **Python**
* **TensorFlow / Keras**
* **NumPy**
* **OpenCV**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **Jupyter Notebook**


## Conclusion

This assignment provided practical experience with both RNNs and CNNs.

The RNN tasks demonstrated LSTM-based text generation and sentiment classification, including temperature scaling, confusion matrices, and precision-recall evaluation.

The CNN tasks demonstrated convolution with different strides and padding, Sobel edge detection, pooling operations, and the implementation of simplified AlexNet and ResNet-like architectures.

Overall, the assignment provided hands-on experience with fundamental deep learning models and their practical applications.

