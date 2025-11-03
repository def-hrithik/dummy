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