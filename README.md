# 📊 Part 1: Neural Network Fundamentals and Training Behavior Analysis

## 📌 Overview

This project focuses on building and analyzing a feed-forward neural network for a customer churn prediction problem. The goal is not only to train a model but also to understand how neural networks learn through preprocessing, forward propagation, loss computation, and evaluation.

---

## 📂 Dataset

* Dataset: `customer_churn_nn.csv`
* Target Variable: `churn`

  * 1 → Customer churned
  * 0 → Customer retained

### Feature Types:

* **Categorical**: region, plan_type, contract_type, payment_method
* **Numerical**: tenure, charges, login activity, support tickets, data usage, satisfaction score, etc.
* **Excluded**: `customer_id` (identifier, not predictive)

---

## 🧩 Task 1: Dataset Understanding

* Loaded and explored dataset structure
* Checked:

  * Number of rows and columns
  * Data types of features
  * Missing values
* Generated statistical summary using `.describe()`
* Analyzed target distribution

### 🔍 Key Insight:

* The dataset is a **binary classification problem**
* The target variable is **imbalanced**, with significantly more non-churn cases

---

## ⚙️ Task 2: Data Preprocessing

Steps performed:

* Removed irrelevant column: `customer_id`
* Handled missing values:

  * Numerical → mean imputation
  * Categorical → "Unknown"
* Applied **One-Hot Encoding** for categorical features
* Split dataset:

  * 80% Training
  * 20% Testing
* Applied **StandardScaler** to normalize features

### ✔ Verification:

* Mean ≈ 0
* Standard deviation ≈ 1

---

## 🤖 Task 3: Neural Network Model

A feed-forward neural network was built using TensorFlow/Keras.

### 🧱 Architecture:

* Input Layer (based on feature size)
* Hidden Layer 1: 16 neurons (ReLU)
* Hidden Layer 2: 8 neurons (ReLU)
* Output Layer: 1 neuron (Sigmoid)

### ⚙️ Configuration:

* Loss Function: Binary Crossentropy
* Optimizer: Adam
* Metric: Accuracy

---

## 📊 Task 4: Training and Evaluation

### 📈 Performance:

* Test Accuracy: ~98%
* Test Loss: Low (~0.07)

### 📉 Confusion Matrix:

* Correctly predicts majority class (non-churn)
* Fails to predict minority class (churn)

### ⚠️ Key Insight:

* High accuracy is misleading due to **class imbalance**
* Model predicts mostly class 0

---

## 🔬 Task 5: Hyperparameter Experimentation

Experiments conducted by varying:

* Number of neurons
* Learning rate
* Number of epochs

### 📊 Observations:

* Increasing neurons slightly improved performance
* Higher learning rate led to unstable results
* More epochs improved loss marginally

### ⚠️ Insight:

* Hyperparameter tuning had limited impact due to class imbalance

---

## 🧠 Task 6: Final Reflection

### 🔹 Weights & Biases:

* Learn feature importance and adjust predictions

### 🔹 Activation Functions:

* Introduce non-linearity to capture complex patterns

### 🔹 Learning Rate:

* Too high → unstable learning
* Too low → slow convergence

### 🔹 Model Behavior:

* No overfitting observed
* Strong bias toward majority class due to imbalance

---

## 🚀 Conclusion

* The neural network successfully learned patterns for the majority class
* However, it failed to generalize for the minority class
* Accuracy alone is not sufficient for evaluation

### 💡 Future Improvements:

* Handle class imbalance using:

  * Class weights
  * Oversampling (SMOTE)
* Use evaluation metrics like:

  * Precision
  * Recall
  * F1-score

---

## 🛠️ Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* TensorFlow / Keras
* Matplotlib, Seaborn

---

## 📎 Note

Dataset source is referenced from the shared project folder.
Dataset files are not included in this repository as per submission guidelines.
