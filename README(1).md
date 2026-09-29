# Lesson 6 - Task 1: Build and Train a Simple ANN Model

## 📌 Project Description

This project builds and trains a simple **Artificial Neural Network
(ANN)** using TensorFlow/Keras to classify mobile phones into two price
ranges:

-   `0` → Low Price
-   `1` → High Price

The model learns the relationship between mobile phone specifications
such as RAM, internal memory, battery power, camera features, etc. and
the corresponding price range.

The dataset used in this task is:

`Mobile_Price_Classification.csv`

------------------------------------------------------------------------

## 🎯 Objectives

The main objectives of this task are:

1.  Read the mobile phone dataset from a CSV file.
2.  Split the dataset into training and testing data.
3.  Build a simple ANN model.
4.  Compile the ANN model.
5.  Train the model for 100 epochs with a batch size of 32.
6.  Evaluate the trained model.
7.  Save the trained model weights for future predictions.

------------------------------------------------------------------------

## 🛠️ Technologies and Libraries

-   Python
-   Google Colab
-   Pandas
-   NumPy
-   TensorFlow
-   Keras
-   Scikit-learn

------------------------------------------------------------------------

## 🧠 ANN Architecture

The ANN architecture used in this task is:

``` text
Input Features (20)
        ↓
Dense Layer - 8 Neurons
Activation: ReLU
        ↓
Dense Layer - 4 Neurons
Activation: ReLU
        ↓
Output Layer - 1 Neuron
Activation: Sigmoid
        ↓
Price Range
0 = Low
1 = High
```

### Architecture Summary

  Layer                  Neurons Activation
  ---------------- ------------- ------------
  Input              20 features \-
  Hidden Layer 1               8 ReLU
  Hidden Layer 2               4 ReLU
  Output Layer                 1 Sigmoid

------------------------------------------------------------------------

## 📊 Dataset Split

The dataset is divided into:

-   **75% Training Data**
-   **25% Testing Data**

The split is performed using `train_test_split()`.

``` python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.25,
    random_state=42
)
```

------------------------------------------------------------------------

## ⚙️ Model Configuration

The model is compiled using:

-   **Optimizer:** SGD
-   **Loss Function:** Binary Crossentropy
-   **Metric:** Accuracy

``` python
model.compile(
    loss='binary_crossentropy',
    optimizer='sgd',
    metrics='accuracy'
)
```

Since this is a binary classification problem with two classes (`0` and
`1`), binary crossentropy and a sigmoid output are used.

------------------------------------------------------------------------

## 🏋️ Model Training

The ANN is trained using:

-   **Epochs:** 100
-   **Batch Size:** 32

``` python
model.fit(
    X_train,
    y_train,
    validation_data=(X_test, y_test),
    epochs=100,
    batch_size=32
)
```

------------------------------------------------------------------------

## 💾 Saving the Trained Weights

The trained model weights can be saved using:

``` python
model.save_weights('mobile_price_ann.weights.h5')
```

The saved weights can later be loaded into the same ANN architecture for
future predictions.

------------------------------------------------------------------------

## 📁 Project Structure

``` text
Lesson-6-Task-1/
│
├── Mobile_Price_Classification.csv
├── ANN_Model.ipynb
├── mobile_price_ann.weights.h5
└── README.md
```

> File names may be different depending on the files uploaded to the
> GitHub repository.

------------------------------------------------------------------------

## 🚀 How to Run the Project

### Step 1 - Open Google Colab

Open the notebook in Google Colab.

### Step 2 - Upload the Dataset

The notebook can upload the CSV file using:

``` python
from google.colab import files

uploaded = files.upload()
```

### Step 3 - Run the Code

Run the cells in order:

1.  Import libraries
2.  Upload/read CSV
3.  Separate features and target
4.  Split training/testing data
5.  Scale the features
6.  Build ANN
7.  Compile ANN
8.  Train ANN
9.  Evaluate the model
10. Save the weights

------------------------------------------------------------------------

## 📈 Expected Result

After training, the model displays the training/validation performance
and the final test accuracy.

Example:

``` text
Test Loss: ...
Test Accuracy: ...
```

The exact accuracy may vary depending on the model configuration and
training process.

------------------------------------------------------------------------

## 📚 Key Concepts Learned

This task demonstrates the following machine learning concepts:

-   Binary Classification
-   Artificial Neural Networks
-   Dense Layers
-   ReLU Activation
-   Sigmoid Activation
-   Training and Testing Data
-   Data Scaling
-   Epochs
-   Batch Size
-   Model Compilation
-   Model Evaluation
-   Saving Model Weights

------------------------------------------------------------------------

## 👨‍💻 Author

**F.M.F Ziyadha**

Bachelor of Software Engineering Honours

------------------------------------------------------------------------

## 📌 Note

This project was completed as part of **Lesson 6 - Task 1: Build and
Train a Simple ANN Model**.
