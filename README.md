# 🧠 MNIST Handwritten Digit Recognition

A deep learning project that uses **Artificial Neural Networks (ANN)** to recognize handwritten digits from the **MNIST dataset**. The project experiments with different neural-network architectures, activation functions, batch sizes, and epochs to understand their impact on model performance.

---

## 📌 Project Overview

Handwritten digit recognition is a classic machine learning and deep learning problem where the objective is to classify an image of a handwritten digit into one of the ten classes:

**0, 1, 2, 3, 4, 5, 6, 7, 8, 9**

In this project, the **MNIST handwritten digit dataset** is used to train and evaluate multiple neural-network models.

The notebook focuses on understanding how different model configurations affect training and validation performance.

---

## 🎯 Objective

The main objectives of this project are:

* To understand the MNIST dataset.
* To preprocess handwritten digit images.
* To normalize image pixel values.
* To convert images into suitable input features for a neural network.
* To build Artificial Neural Network models using TensorFlow/Keras.
* To experiment with different neural-network architectures.
* To compare different activation functions.
* To study the effect of batch size and number of epochs.
* To analyze training and validation accuracy.
* To identify the best-performing model.
* To understand overfitting and model complexity.

---

## 📊 Dataset

The project uses the **MNIST handwritten digit dataset**.

### Dataset Details

| Feature           | Details        |
| ----------------- | -------------- |
| Dataset           | MNIST          |
| Total Images      | 70,000         |
| Training Images   | 60,000         |
| Testing Images    | 10,000         |
| Image Size        | 28 × 28 pixels |
| Image Type        | Grayscale      |
| Number of Classes | 10             |
| Classes           | 0–9            |
| Pixel Value Range | 0–255          |

Each image represents a handwritten digit between **0 and 9**.

---
## 🔍 Data Preprocessing

### 1. Loading the Dataset

The MNIST dataset is loaded using Keras:

```python
from tensorflow import keras

(X_train, y_train), (X_test, y_test) = keras.datasets.mnist.load_data()
```

The dataset contains handwritten digit images along with their corresponding labels.

---

### 2. Normalization

The original pixel values range from **0 to 255**.

They are normalized to a range between **0 and 1**:

```python
X_train = X_train / 255.0
X_test = X_test / 255.0
```

Normalization helps the neural network train more efficiently.

---

### 3. Reshaping

Each image has a size of:

```text
28 × 28
```

For a fully connected neural network, the image is converted into a one-dimensional vector:

```text
28 × 28 = 784
```

Therefore, every image is represented using **784 input features**.

```text
28 × 28 Image
      ↓
784 Features
```

---

### 4. One-Hot Encoding

The digit labels are converted into one-hot encoded vectors.

For example:

```text
Digit 3
↓
[0, 0, 0, 1, 0, 0, 0, 0, 0, 0]
```

This is useful because the problem is a **10-class classification problem**.

---

## 🛠️ Technologies Used

### Programming Language

* Python

### Libraries

* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* TensorFlow
* Keras

---

## 🧠 Neural Network

The project uses **Artificial Neural Networks** implemented using TensorFlow/Keras.

The basic architecture can be represented as:

```text
MNIST Image
    ↓
28 × 28 Pixels
    ↓
784 Input Features
    ↓
Hidden Layer(s)
    ↓
10 Output Neurons
    ↓
Digit Prediction
```

The output layer contains **10 neurons**, one for each digit from 0 to 9.

---

## ⚙️ Model Compilation

The neural-network models are compiled using:

### Loss Function

```text
categorical_crossentropy
```

This is used because the project performs multi-class classification with one-hot encoded labels.

### Optimizer

```text
SGD
```

SGD stands for **Stochastic Gradient Descent**.

### Evaluation Metric

```text
accuracy
```

Accuracy measures the percentage of predictions correctly classified by the model.

---

## 🔥 Activation Functions

Different activation functions were explored during the experiments.

### Sigmoid

Sigmoid produces values between 0 and 1.

```text
Sigmoid
```

It was experimented with in the hidden layers.

### Tanh

Tanh produces values between -1 and 1.

```text
Tanh
```

### ReLU

ReLU stands for **Rectified Linear Unit**.

```text
ReLU
```

ReLU was found to perform well in the hidden layers.

### Softmax

Softmax is used in the final output layer.

It converts the output values into probabilities for the ten digit classes.

```text
0 → Probability
1 → Probability
2 → Probability
...
9 → Probability
```

The digit with the highest probability becomes the predicted digit.

---

# 🧪 Model Experiments

Multiple models were created by changing different hyperparameters.

The experiments focused on:

* Number of hidden layers
* Number of neurons
* Activation functions
* Batch size
* Number of epochs

---

## 📈 Model Comparison

| Model    | Hidden Layers | Activation                   | Batch Size | Epochs | Validation Accuracy |
| -------- | ------------: | ---------------------------- | ---------: | -----: | ------------------: |
| Model 9  |             1 | 128 ReLU                     |         32 |     50 |              97.18% |
| Model 10 |             2 | 128 ReLU + 64 Tanh           |         32 |     50 |          **97.54%** |
| Model 11 |             2 | 128 Tanh + 64 ReLU           |         32 |     50 |              97.48% |
| Model 12 |             3 | 128 ReLU + 64 ReLU + 32 ReLU |         32 |     50 |              97.44% |
| Model 13 |             3 | 128 ReLU + 64 ReLU + 32 ReLU |         32 |    100 |              97.45% |

---

# 📌 Conclusion

This project demonstrates the use of **Artificial Neural Networks for handwritten digit recognition using the MNIST dataset**.

Different neural-network architectures and training configurations were tested to understand their impact on model performance.

The experiments showed that **batch size, activation function, hidden-layer architecture, and number of epochs** have an important effect on model performance.

The best-performing experiment achieved approximately:

## 🏆 97.54% Validation Accuracy

The project also demonstrates an important deep-learning concept: **increasing model complexity or training time does not always lead to better validation performance**, as excessive training can result in overfitting.
ST Handwritten Digit Recognition using Neural Networks**

---
