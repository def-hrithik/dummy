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

```python
from keras.models import Sequential
from keras.layers import Dense

# Build ANN model
model = Sequential([
    Dense(16, input_dim=10, activation='relu'),
    Dense(8, activation='relu'),
    Dense(1, activation='sigmoid')
])

# Compile model
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])

# Train model
model.fit(X_train, y_train, epochs=50, batch_size=10, validation_data=(X_test, y_test))

# 💡 Common Activation Functions in Neural Networks

This document provides a clear and simple overview of the three most common activation functions used in Artificial Neural Networks: **Sigmoid**, **ReLU**, and **Tanh**.

---

## 🔹 1. Sigmoid Function

### 📘 Definition
The Sigmoid activation function maps input values into a range between **0 and 1**.

$$f(x) = \frac{1}{1 + e^{-x}}$$

### 📊 Example Values
| $x$ | $f(x)$ |
| :---: | :---: |
| -2 | 0.12 |
| 0 | 0.5 |
| 2 | 0.88 |

### ⚙️ Key Points
* **Output Range:** $(0, 1)$
* **Use Case:** Good for **binary classification** (outputting a probability).
* **Feature:** It is a smooth and fully **differentiable** function.

### ⚠️ Drawbacks
* **Vanishing Gradient Problem:** For very high or very low input values ($x$), the gradient becomes extremely close to zero, which slows down or halts learning in deep networks.
* **Slow Learning:** Generally slower for training deep networks.

---

## 🔹 2. ReLU (Rectified Linear Unit)

### 📘 Definition
ReLU outputs the input directly if it's positive, and outputs **0** otherwise.

$$f(x) = \max(0, x)$$

### 📊 Example Values
| $x$ | $f(x)$ |
| :---: | :---: |
| -3 | 0 |
| 0 | 0 |
| 2 | 2 |

### ⚙️ Key Points
* **Output Range:** $[0, \infty)$
* **Use Case:** **Fast** and **simple**, making it the most commonly used function in **hidden layers** of deep networks.
* **Advantage:** Helps mitigate the **vanishing gradient problem** for positive inputs.

### ⚠️ Drawbacks
* **Dying ReLU Problem:** If a large gradient flows through a ReLU neuron, it can cause the neuron to output 0 permanently. Once the output is 0, the gradient is 0, and the neuron can never activate again, effectively "dying."

---

## 🔹 3. Tanh (Hyperbolic Tangent)

### 📘 Definition
Tanh is similar to Sigmoid but outputs values in a range between **-1 and 1**.

$$f(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}$$

### 📊 Example Values
| $x$ | $f(x)$ |
| :---: | :---: |
| -2 | -0.96 |
| 0 | 0 |
| 2 | 0.96 |

### ⚙️ Key Points
* **Output Range:** $(-1, 1)$
* **Advantage:** The output is **zero-centered**, meaning the mean activation is closer to zero. This is often better for optimizing weights during backpropagation.
* **Performance:** Often performs **better than Sigmoid** in hidden layers.

### ⚠️ Drawbacks
* **Vanishing Gradient:** Still suffers from the vanishing gradient problem for large absolute values of $x$ (i.e., $|x|$).

---

## 🔸 Quick Comparison Table

| Function | Formula | Output Range | Pros | Cons | Common Use |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Sigmoid** | $\frac{1}{1 + e^{-x}}$ | $(0, 1)$ | Smooth, probabilistic. | Vanishing gradient, not zero-centered. | Output layer (binary classification). |
| **Tanh** | $\frac{e^x - e^{-x}}{e^x + e^{-x}}$ | $(-1, 1)$ | Zero-centered output. | Vanishing gradient for large inputs. | Hidden layers. |
| **ReLU** | $\max(0, x)$ | $[0, \infty)$ | Fast, no vanishing gradient (for $x>0$). | Dying ReLU problem. | Hidden layers (**most common**). |

---

Would you like me to include the labeled diagram comparing their shapes (Sigmoid vs ReLU vs Tanh) to help visualize the difference clearly?
