# 📘 Statistics Notes – 5 Marks Answers (Mumbai University)

---

## 1️⃣ Single Linear Regression

### 🔹 Definition  
It is a method used to study the relationship between **one independent variable (X)** and **one dependent variable (Y)**.

\[
Y = a + bX
\]

Where:  
- **Y** = Dependent variable  
- **X** = Independent variable  
- **a** = Intercept  
- **b** = Slope of regression line  

### 🔹 Example  
Predict **marks (Y)** based on **hours studied (X)**.

| Hours (X) | Marks (Y) |
|------------|------------|
| 1 | 30 |
| 2 | 40 |
| 3 | 50 |
| 4 | 60 |

Regression line:  
\[
Y = 20 + 10X
\]

➡ Shows a linear upward trend.

---

## 2️⃣ Multiple Linear Regression

### 🔹 Definition  
Used when there are **two or more independent variables** affecting one dependent variable.

\[
Y = a + b_1X_1 + b_2X_2 + \ldots + b_nX_n
\]

### 🔹 Example  
Predict **sales (Y)** based on **advertising (X₁)** and **price (X₂)**:
\[
Y = 50 + 5X_1 - 3X_2
\]

Meaning:  
- Each unit increase in advertising increases sales by 5.  
- Each unit increase in price decreases sales by 3.

---

## 3️⃣ Friedman Test (Non-Parametric Test)

### 🔹 Theory  
Used to **compare three or more related samples** (like repeated measures) when data is **not normally distributed**.

### 🔹 Steps  
1. Rank data within each group.  
2. Compute the sum of ranks for each treatment.  
3. Calculate Friedman test statistic \( \chi^2_F \).  
4. Compare with chi-square critical value.

### 🔹 Example  
Testing 3 teaching methods on same students’ scores.

| Student | Method A | Method B | Method C |
|----------|-----------|-----------|-----------|
| 1 | 70 | 80 | 75 |
| 2 | 60 | 65 | 70 |
| 3 | 80 | 75 | 85 |

---

## 4️⃣ Type I and Type II Errors

| Type | Definition | Example |
|------|-------------|----------|
| **Type I Error (α)** | Rejecting a true null hypothesis | Concluding a medicine works when it doesn’t |
| **Type II Error (β)** | Accepting a false null hypothesis | Concluding a medicine doesn’t work when it actually does |

### 🔹 Difference
| Feature | Type I | Type II |
|----------|---------|---------|
| Meaning | False Positive | False Negative |
| Symbol | α | β |
| Minimized By | Increasing confidence level | Increasing sample size |

---

## 5️⃣ Stratified vs Cluster Sampling

| Basis | Stratified Sampling | Cluster Sampling |
|--------|---------------------|------------------|
| Definition | Population divided into **homogeneous strata** | Population divided into **heterogeneous clusters** |
| Sampling | Sample taken from **each stratum** | **Few clusters** chosen randomly |
| Example | Divide by age group and take samples | Choose a few cities randomly |
| Accuracy | More accurate | Less accurate but cheaper |

---

## 6️⃣ Fisher’s F-Test

### 🔹 Purpose  
Used to **compare the variances** of two populations or test significance in **ANOVA**.

### 🔹 Formula  
\[
F = \frac{S_1^2}{S_2^2}
\]
(Where \( S_1^2 \) > \( S_2^2 \))

### 🔹 Example  
If variance of two teaching methods is 25 and 10,  
\[
F = 25 / 10 = 2.5
\]  
Compare with F-critical value to conclude if variances differ.

---

## 7️⃣ Linear Regression and Its Applications

### 🔹 Definition  
A method to model relationship between dependent and independent variables using a straight line.

### 🔹 Applications  
- Predicting sales, prices, or scores  
- Risk assessment in finance  
- Forecasting trends  
- Business decision-making  

---

## 8️⃣ Kruskal–Wallis Test

### 🔹 Definition  
Non-parametric test used to compare **three or more independent samples** when data is not normally distributed.

### 🔹 Example  
Compare customer satisfaction for 3 different products.

| Group | Scores |
|--------|--------|
| A | 7, 8, 9 |
| B | 5, 6, 7 |
| C | 8, 9, 10 |

Rank data and apply Kruskal–Wallis formula to test if medians differ.

---

## 9️⃣ Test Statistic

### 🔹 Definition  
A **numerical value** calculated from sample data to make a decision about the hypothesis.

\[
\text{Test Statistic} = \frac{\text{Sample Estimate} - \text{Hypothesized Value}}{\text{Standard Error}}
\]

### 🔹 Example  
Z-test, t-test, chi-square, F-test all use different test statistics.

---

## 🔟 Confidence Level

### 🔹 Definition  
The probability that the true population parameter lies within the confidence interval.

### 🔹 Example  
A **95% confidence level** means:  
“If we take 100 samples, the true mean will lie within the interval 95 times.”

---

## 1️⃣1️⃣ Correlation and Regression

| Concept | Meaning | Example |
|----------|----------|----------|
| **Correlation** | Measures strength & direction of relationship between variables | Height & Weight (r = +0.9) |
| **Regression** | Predicts value of dependent variable using independent variable(s) | Predict salary from experience |

\[
r = \frac{\text{Cov(X,Y)}}{\sigma_X \sigma_Y}
\]

---

## 1️⃣2️⃣ Analysis of Variance (ANOVA)

### 🔹 Definition  
Used to check if **three or more group means** are significantly different.

### 🔹 Example  
Comparing average marks of students from 3 different classes.

### 🔹 Usage  
- Test effect of multiple treatments  
- Check variance across groups  
- Used in experimental design

---

## 1️⃣3️⃣ Empirical Cumulative Distribution Function (ECDF)

### 🔹 Definition  
A function that gives the **proportion of observations less than or equal to a particular value**.

\[
F(x) = \frac{\text{Number of observations ≤ x}}{n}
\]

### 🔹 Example  
For data [10, 20, 30, 40],  
\[
F(30) = 3/4 = 0.75
\]

---

## 1️⃣4️⃣ Linear Least Squares Regression

### 🔹 Definition  
A method to find the **best-fitting line** by minimizing the **sum of squared residuals**.

\[
\text{Minimize } \sum (Y_i - (a + bX_i))^2
\]

### 🔹 Advantages  
- Simple and interpretable  
- Works well for linear data  
- Good for prediction and trend analysis  

### 🔹 Disadvantages  
- Sensitive to outliers  
- Assumes linearity and homoscedasticity  
- Poor performance on non-linear data  

---

## ✅ Summary Table

| Topic | Type | Marks |
|--------|------|--------|
| Single & Multiple Linear Regression | Descriptive + Plot | 5 |
| Friedman Test | Non-parametric | 5 |
| Type I & II Error | Conceptual | 5 |
| Stratified vs Cluster | Comparison | 5 |
| Fisher Test | Parametric | 5 |
| Linear Regression & Application | Applied | 5 |
| Kruskal Wallis | Non-parametric | 5 |
| Test Statistic | Conceptual | 5 |
| Confidence Level | Conceptual | 5 |
| Correlation & Regression | Analytical | 5 |
| ANOVA | Parametric | 5 |
| Empirical CDF | Conceptual | 5 |
| Linear Least Squares | Analytical | 5 |

---

📘 **Prepared for:** Statistics (Mumbai University)   
✍️ **Author:** Hrithik Singh  


### 🔹 Suitable Plot
