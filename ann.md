# 🧠 Artificial Neural Network (ANN) — Explained for Machine Learning & Customer Churn Prediction

## 📘 1. What is ANN?

An **Artificial Neural Network (ANN)** is a **computational model inspired by the human brain**.  
It consists of **interconnected nodes (neurons)** organized in layers to **recognize patterns**, **make predictions**, and **learn from data**.

### 🧩 Structure of ANN
1. **Input Layer** → Takes input features  
2. **Hidden Layers** → Process data using **weights** and **activation functions**  
3. **Output Layer** → Produces the final prediction  

### ⚙️ How ANN Works
1. **Forward Propagation:** Inputs → Weights → Activation → Output  
2. **Activation Function:** Adds non-linearity (e.g., Sigmoid, ReLU, Tanh)  
3. **Loss Calculation:** Measures prediction error  
4. **Backward Propagation:** Adjusts weights using **Gradient Descent**

### 🔁 Learning Process
1. Initialize weights  
2. Forward pass  
3. Calculate loss  
4. Backpropagate to update weights  
5. Repeat until convergence  

### 💡 Applications
- Image recognition  
- Speech recognition  
- NLP (Natural Language Processing)  
- Predictive analytics  
- Autonomous vehicles  

### ✅ Advantages
- Learns complex patterns  
- High accuracy  

### ⚠️ Disadvantages
- Needs large datasets  
- Hard to interpret (black-box)  

---

## ⚙️ 2. Activation Functions

Activation functions decide whether a neuron should activate or not — helping the network learn complex relationships.

### 🔹 **1. Sigmoid Function**
\[
f(x) = \frac{1}{1 + e^{-x}}
\]

| Property | Description |
|-----------|--------------|
| **Range** | (0, 1) |
| **Use Case** | Binary classification output |
| **Advantage** | Smooth and differentiable |
| **Disadvantage** | Causes vanishing gradient |

---

### 🔹 **2. ReLU (Rectified Linear Unit)**
\[
f(x) = \max(0, x)
\]

| Property | Description |
|-----------|--------------|
| **Range** | [0, ∞) |
| **Use Case** | Hidden layers in deep networks |
| **Advantage** | Fast training, avoids vanishing gradient |
| **Disadvantage** | Dying ReLU problem (neurons stuck at 0) |

---

### 🔹 **3. Tanh (Hyperbolic Tangent)**
\[
f(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}
\]

| Property | Description |
|-----------|--------------|
| **Range** | (-1, 1) |
| **Use Case** | Hidden layers |
| **Advantage** | Zero-centered output |
| **Disadvantage** | Still suffers vanishing gradient |

---

### 🧾 Comparison Table

| Function | Formula | Output Range | Pros | Cons | Common Use |
|-----------|----------|---------------|------|------|-------------|
| **Sigmoid** | 1 / (1 + e^-x) | (0, 1) | Smooth, probabilistic | Vanishing gradient | Output layer |
| **Tanh** | (e^x - e^-x)/(e^x + e^-x) | (-1, 1) | Zero-centered | Vanishing gradient | Hidden layers |
| **ReLU** | max(0, x) | [0, ∞) | Fast, simple | Dying ReLU | Hidden layers |

---

## 🧩 3. ANN for Customer Churn Prediction

### 💬 What is Customer Churn?
Customer churn = when a customer **stops using a service** (e.g., cancels a subscription or SIM).  
Goal → **Predict which customers are likely to leave.**

---

### 🔹 Why Use ANN?
- Learns complex behavior patterns  
- Handles large feature sets  
- Provides accurate predictions  

---

### 🧱 Steps to Build ANN for Churn Prediction

#### 1. Data Collection
Gather customer data:  
- Age, Gender, Tenure  
- Monthly Charges  
- Contract Type  
- Payment Method  
- Churn (1 = Yes, 0 = No)

#### 2. Data Preprocessing
- Handle missing values  
- Encode categorical features  
- Normalize numeric features  
- Split into training and testing sets  

#### 3. ANN Design
| Layer | Description | Activation |
|--------|--------------|-------------|
| Input | One neuron per feature | — |
| Hidden | Extracts patterns | ReLU |
| Output | Binary output (churn / not churn) | Sigmoid |

#### 4. Model Training
- **Loss Function:** Binary Cross-Entropy  
- **Optimizer:** Adam or SGD  
- **Metric:** Accuracy, ROC-AUC  

#### 5. Evaluation
Check **accuracy**, **precision**, **recall**, and **confusion matrix**.

---

### 🧮 Example (Python / Keras)

# 🧠 Artificial Neural Networks (ANN) – Complete Concept Guide

This repository provides a **clear, beginner-friendly explanation** of key concepts in Artificial Neural Networks (ANN), including activation functions, customer churn prediction, loss functions, optimizers, and forward/backward propagation.

---

## 💡 Common Activation Functions in Neural Networks

This section explains the three most commonly used activation functions in ANN:

- **Sigmoid**
- **ReLU**
- **Tanh**

---

### 🔹 1. Sigmoid Function

#### 📘 Definition
The Sigmoid activation function maps input values into a range between **0 and 1**.

\[
f(x) = \frac{1}{1 + e^{-x}}
\]

#### 📊 Example Values

| x | f(x) |
|---|------|
| -2 | 0.12 |
| 0 | 0.5 |
| 2 | 0.88 |

#### ⚙️ Key Points
- **Output Range:** (0, 1)
- **Use Case:** Binary classification (probability output)
- **Feature:** Smooth and fully differentiable

#### ⚠️ Drawbacks
- **Vanishing Gradient Problem**
- Slow learning in deep networks

---

### 🔹 2. ReLU (Rectified Linear Unit)

#### 📘 Definition
ReLU outputs the input directly if it is positive, otherwise outputs **0**.

\[
f(x) = \max(0, x)
\]

#### 📊 Example Values

| x | f(x) |
|---|------|
| -3 | 0 |
| 0 | 0 |
| 2 | 2 |

#### ⚙️ Key Points
- **Output Range:** [0, ∞)
- **Use Case:** Most common activation function for **hidden layers**
- **Advantage:** Reduces vanishing gradient problem

#### ⚠️ Drawbacks
- **Dying ReLU Problem**

---

### 🔹 3. Tanh (Hyperbolic Tangent)

#### 📘 Definition
Tanh maps inputs to values between **-1 and 1**.

\[
f(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}
\]

#### 📊 Example Values

| x | f(x) |
|---|------|
| -2 | -0.96 |
| 0 | 0 |
| 2 | 0.96 |

#### ⚙️ Key Points
- **Output Range:** (-1, 1)
- Zero-centered output
- Performs better than Sigmoid in hidden layers

#### ⚠️ Drawbacks
- Suffers from vanishing gradient problem

---

### 🔸 Activation Function Comparison

| Function | Formula | Output Range | Pros | Cons | Common Use |
|--------|--------|--------------|------|------|------------|
| Sigmoid | 1 / (1 + e⁻ˣ) | (0,1) | Smooth, probabilistic | Vanishing gradient | Output layer |
| Tanh | (eˣ - e⁻ˣ) / (eˣ + e⁻ˣ) | (-1,1) | Zero-centered | Vanishing gradient | Hidden layers |
| ReLU | max(0, x) | [0,∞) | Fast, simple | Dying ReLU | Hidden layers |

---

## 🧠 ANN for Customer Churn Prediction

### 🎯 What is Customer Churn?
Customer churn occurs when a customer stops using a product or service.

**Goal:** Predict customers likely to leave so businesses can take preventive action.

---

### 🔹 Why Use ANN?

- Learns complex non-linear patterns
- Combines multiple customer features
- Works well with large datasets

---

### ⚙️ Steps to Build an ANN Model

#### 1. Data Collection
- Demographics
- Usage behavior
- Contract details
- Target variable (Churn: 0 or 1)

#### 2. Data Preprocessing
- Handle missing values
- Encode categorical features
- Scale numerical features
- Train-test split

#### 3. ANN Architecture

| Layer | Structure | Activation | Purpose |
|------|----------|------------|---------|
| Input | One neuron per feature | — | Input data |
| Hidden | Dense layers (e.g., 16, 8) | ReLU | Feature learning |
| Output | 1 neuron | Sigmoid | Churn probability |

---

### 💻 Example: Keras Implementation

```python
from keras.models import Sequential
from keras.layers import Dense

model = Sequential([
    Dense(16, input_dim=10, activation='relu'),
    Dense(8, activation='relu'),
    Dense(1, activation='sigmoid')
])

model.compile(optimizer='adam',
              loss='binary_crossentropy',
              metrics=['accuracy'])

model.fit(X_train, y_train,
          epochs=50,
          batch_size=10,
          validation_data=(X_test, y_test))
