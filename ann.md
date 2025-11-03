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

# 🧠 Artificial Neural Networks (ANN) for Customer Churn Prediction

This document explains how an Artificial Neural Network (ANN) is used to predict **Customer Churn**.

---

## 🎯 What is Customer Churn Prediction?

**Customer Churn** occurs when a customer stops using a company’s product or service.

The primary **goal** of churn prediction is to **identify customers who are likely to leave** so the company can implement targeted retention strategies.

> **Example:** In a telecom context, if a customer terminates their subscription or stops using their SIM card, that is considered churn.

---

## 🔹 Why Use ANN for Churn Prediction?

ANNs are exceptionally powerful for this task because they can:

* **Learn Complex Patterns:** They automatically discover deep, non-linear relationships within customer behavioral data that simpler models might miss.
* **Feature Combination:** They effectively combine and weigh multiple diverse features (e.g., usage, payment history, complaints) to form a unified prediction.
* **Scalability:** They provide **accurate predictions** even when dealing with the large, high-dimensional datasets typical of customer behavior.

---

## ⚙️ Steps to Build an ANN for Churn Prediction

### 1. Data Collection
The foundation of the model relies on historical customer data:
* **Demographics:** Age, gender, location.
* **Usage/Behavior:** Monthly charges, tenure (time as a customer), service usage.
* **Contract:** Contract type, payment method.
* **Target Variable:** Whether the customer **churned (1)** or **did not churn (0)**.

### 2. Data Preprocessing
Preparing the data is crucial for model performance:
* **Cleaning:** Handling missing values (imputation).
* **Encoding:** Converting categorical variables (e.g., contract type, payment method) into numerical format.
* **Scaling:** Normalizing or scaling numerical data (e.g., using `MinMaxScaler` or `StandardScaler`) to ensure all features contribute equally.
* **Splitting:** Dividing the dataset into **training** and **testing** sets.

### 3. Designing the ANN Model
The network architecture is defined based on the problem:

| Layer | Structure | Activation Function | Purpose |
| :--- | :--- | :--- | :--- |
| **Input Layer** | One neuron per feature (e.g., 10 features $\rightarrow$ 10 neurons) | N/A | Receives the processed customer data. |
| **Hidden Layers** | Typically 1–2 dense layers (e.g., 16 and 8 neurons) | **ReLU** (`Rectified Linear Unit`) | Learns complex mappings and non-linearities. |
| **Output Layer** | **1 neuron** | **Sigmoid** | Produces the final probability of churn (a value between 0 and 1). |

### 4. Training the Model
The ANN learns by minimizing prediction errors:
* **Forward Propagation:** Input data moves through the network to generate a prediction.
* **Loss Calculation:** The prediction is compared to the actual churn outcome using the **Binary Cross-Entropy** loss function.
* **Backpropagation:** The error is sent backward through the network, and an **optimizer** (like **Adam** or **SGD**) adjusts the weights to reduce the loss.

### 5. Testing and Evaluation
Model performance is assessed on the unseen test set using key metrics:
* **Accuracy:** Overall correct predictions.
* **Precision/Recall:** Important for classifying the minority class (churned customers).
* **Confusion Matrix:** Shows true positives, true negatives, false positives, and false negatives.
* **ROC-AUC Curve:** Measures the model's ability to distinguish between churners and non-churners.

---

## 💻 Example: Python Code (Keras)

A basic implementation using the Keras framework:

```python
from keras.models import Sequential
from keras.layers import Dense

# Assume X_train, y_train, X_test, y_test are preprocessed data
input_features = 10 # Example: if you have 10 input features

# Create ANN model
model = Sequential([
    Dense(16, input_dim=input_features, activation='relu'),  # Input + 1st Hidden Layer
    Dense(8, activation='relu'),                             # 2nd Hidden Layer
    Dense(1, activation='sigmoid')                           # Output Layer (Churn Probability)
])

# Compile the model
model.compile(optimizer='adam', 
              loss='binary_crossentropy', 
              metrics=['accuracy'])

# Train the model
model.fit(X_train, y_train, 
          epochs=50, 
          batch_size=10, 
          validation_data=(X_test, y_test))

# Evaluate
loss, accuracy = model.evaluate(X_test, y_test)
print(f"\nModel Accuracy on Test Set: {accuracy*100:.2f}%")







# 📉 Loss Function, Binary Cross-Entropy, and Optimizers

This document provides a clear explanation of how **Loss Functions** and **Optimizers** work in the context of Artificial Neural Network (ANN) training, specifically focusing on binary classification tasks like Customer Churn Prediction.

---

## 🧠 1. Loss Function (Error Function)

### 🔹 Definition
A Loss Function (or Cost Function) is a metric that **measures the disparity** between the model's **predicted output ($\hat{y}$)** and the **actual output ($y$)**.

The function tells the model **how wrong its predictions are**. The fundamental goal of training an ANN is to **minimize the loss** by iteratively adjusting the network's weights.

> **Goal:** Smaller Loss $\implies$ Better Model Performance.

### 🔹 Example
* **Actual $y = 1$** (customer churned) and **Predicted $\hat{y} = 0.9$** (high probability of churn). **Loss is small** $\rightarrow$ Good prediction.
* **Actual $y = 1$** and **Predicted $\hat{y} = 0.1$** (low probability of churn). **Loss is large** $\rightarrow$ Bad prediction.

---

## ⚙️ 2. Binary Cross-Entropy Loss (BCE)

BCE is the standard loss function used when the output layer has **two classes (0 or 1)**, making it ideal for tasks like churn prediction.

### 📘 Formula
The Binary Cross-Entropy loss calculated over $N$ samples is:

$$L = -\frac{1}{N} \sum_{i=1}^{N} [y_i \log(\hat{y}_i) + (1 - y_i)\log(1 - \hat{y}_i)]$$

Where:
* $y_i$ = The **actual output** (ground truth: 0 or 1).
* $\hat{y}_i$ = The **predicted probability** (output of the Sigmoid function: $0 < \hat{y}_i < 1$).
* $N$ = The number of samples.

### 🔹 Intuition
BCE strongly penalizes confident wrong answers:
* If the **actual $y=1$**, the term $(1 - y_i)\log(1 - \hat{y}_i)$ becomes zero. The model is penalized if it predicts a low $\hat{y}$ (since $\log(\text{small number}) \approx -\infty$, making the overall loss large).
* If the **actual $y=0$**, the term $y_i \log(\hat{y}_i)$ becomes zero. The model is penalized if it predicts a high $\hat{y}$ (since $\log(1 - \text{high number}) \approx -\infty$, making the overall loss large).

| Actual ($y$) | Predicted ($\hat{y}$) | Loss | Outcome |
| :---: | :---: | :--- | :--- |
| **1** | **0.9** | Low loss | Correct & confident |
| **1** | **0.1** | **High loss** | Incorrect & confident |
| **0** | **0.1** | Low loss | Correct & confident |
| **0** | **0.9** | **High loss** | Incorrect & confident |

---

## ⚙️ 3. Optimizers

An Optimizer is an algorithm used to **update the weights** in the neural network to **minimize the Loss Function** during the training process.

### 🔹 (a) SGD — Stochastic Gradient Descent

#### 🔸 How it works
SGD is the most fundamental optimizer. For each training step, it:
1.  Calculates the **gradient** (the slope of the loss function with respect to the weights).
2.  Updates the weights in the direction **opposite** to the gradient (the direction of steepest descent).

$$\mathbf{w_{new}} = \mathbf{w_{old}} - \eta \frac{\partial L}{\partial \mathbf{w}}$$

* $\eta$ (eta) is the **learning rate**, which controls the size of the step taken.

#### ✅ Pros & ⚠️ Cons
| Pros (✅) | Cons (⚠️) |
| :--- | :--- |
| Simple to implement and widely understood. | **Slow convergence** for complex landscapes. |
| Works well for very large datasets. | Can **oscillate** around the minimum or get stuck in a local minimum. |
| | Highly sensitive to the choice of learning rate ($\eta$). |

### 🔹 (b) Adam — Adaptive Moment Estimation

#### 🔸 How it works
Adam is currently the most popular choice for deep learning because it combines the best features of other optimizers:
* **Momentum:** It tracks a running average of past gradients (like a ball rolling downhill).
* **Adaptive Learning Rate:** It calculates a unique, dynamic learning rate for **each parameter** based on the past squared gradients.

#### ✅ Pros & ⚠️ Cons
| Pros (✅) | Cons (⚠️) |
| :--- | :--- |
| **Faster convergence** due to adaptive step sizes. | Slightly more complex and memory-intensive. |
| Requires less tuning; less sensitive to $\eta$. | Can sometimes **overshoot** the optimal point due to its momentum term. |
| The **default choice** for most complex, deep neural networks. | |

---

## 🔸 Comparison Table

| Optimizer | Learning Type | Speed | Key Feature | Common Use |
| :--- | :--- | :--- | :--- | :--- |
| **SGD** | Fixed global learning rate ($\eta$) | Slower | Simple gradient descent mechanism. | Small or very simple models; baseline comparisons. |
| **Adam** | **Adaptive** learning rate for each weight | **Faster** | Uses **Momentum** + **Adaptive Step Size**. | **Deep Neural Networks** and complex problems (often the default choice). |

---

Would you like me to provide a simple diagram showing how the loss decreases over epochs with Adam versus SGD to help visualize their difference nicely?


# 🧠 Forward and Backward Propagation in ANN (Customer Churn Prediction)

## 🔹 1. Forward Propagation (Prediction Step)
- In this step, the input data (like **customer age, tenure, monthly charges**, etc.) is passed through the network.
- Each layer has **weights** and **biases** that transform the input and apply an **activation function** (such as ReLU or Sigmoid).
- The output layer gives the **final prediction**, e.g.:
  - `0.9` → Customer likely to **churn (leave)**
  - `0.1` → Customer likely to **stay**

> 🧩 Think of forward propagation as the **"prediction" phase** of the model.

---

## 🔹 2. Backward Propagation (Learning Step)
- After getting the prediction, the model compares it with the **actual result** using a **loss function** (like *Binary Cross-Entropy*).
- Then, it calculates how much **each weight contributed to the error** using the **chain rule** (mathematics).
- Using an **optimizer** (like *Adam* or *SGD*), the model updates its weights to **reduce the error** in the next iteration.

> 🔁 Think of backward propagation as the **"learning from mistakes"** phase.

---

## 🔹 Example
- Model predicts churn = **0.8 (80%)**, but actual label = **1 (customer left)**.
- The loss function calculates the **error**.
- Backpropagation updates weights to make the next prediction **closer to 1**.

---

## ⚙️ In Short

| Step | Name | What Happens | Example |
|------|------|---------------|----------|
| 1 | Forward Propagation | Model makes a prediction | “Customer will churn with 80% probability” |
| 2 | Backward Propagation | Model learns from the error and updates weights | Adjusts weights to improve next prediction |

---

✨ **Summary:**
> Forward Propagation = Prediction  
> Backward Propagation = Learning

These two steps work together to help the ANN become more accurate at predicting **customer churn** over time.