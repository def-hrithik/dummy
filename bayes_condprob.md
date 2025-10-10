# Bayes’ Theorem & Conditional Probability
**Subject:** Artificial Intelligence (AI)
**Semester:** 5, Mumbai University

---

## 1️⃣ Recap of Concepts

**Conditional Probability:**
$$P(A|B) = \frac{P(A \cap B)}{P(B)}, \quad P(B) \neq 0$$

**Bayes’ Theorem:**
$$P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}$$
> Used to **reverse conditional probability** from $P(B|A)$ to $P(A|B)$.

---

## 2️⃣ Example Scenario: Mumbai University AI Exam

**Given:**

* 40% of students study **Machine Learning (ML)**: $P(ML) = 0.4$
* 30% of students study **Natural Language Processing (NLP)**: $P(NLP) = 0.3$
* 20% of students study **both ML and NLP**: $P(ML \cap NLP) = 0.2$

**Questions:**

1.  Probability that a student studies **NLP** given that they study **ML**?
2.  Probability that a student studies **ML** given that they study **NLP**?

---

## 3️⃣ Step A: Conditional Probability Formulas

**(i) NLP given ML)**
$$P(NLP|ML) = \frac{P(ML \cap NLP)}{P(ML)}$$

**(ii) ML given NLP)**
$$P(ML|NLP) = \frac{P(ML \cap NLP)}{P(NLP)}$$

---

## 4️⃣ Step B: Solve

**Given values:**
$$P(ML) = 0.4, \quad P(NLP) = 0.3, \quad P(ML \cap NLP) = 0.2$$

**(i) Probability that a student studies NLP given ML:**
$$P(NLP|ML) = \frac{0.2}{0.4} = 0.5$$

**(ii) Probability that a student studies ML given NLP:**
$$P(ML|NLP) = \frac{0.2}{0.3} \approx 0.667$$

---

## 5️⃣ Step C: Using Bayes’ Theorem

Here we can verify the result from Step B(ii) using the result from Step B(i).
$$P(ML|NLP) = \frac{P(NLP|ML) \cdot P(ML)}{P(NLP)}$$

$$P(ML|NLP) = \frac{0.5 \cdot 0.4}{0.3} = \frac{0.2}{0.3} \approx 0.667$$
> The result matches the one calculated using the direct conditional probability formula. ✅

---

## 6️⃣ Step D: Visual Representation (Venn Diagram)

The Venn diagram below illustrates the probabilities. The overlapping section represents students studying both subjects, helping to visualize the relationships.



* **ML Only:** $P(ML) - P(ML \cap NLP) = 0.4 - 0.2 = 0.2$
* **NLP Only:** $P(NLP) - P(ML \cap NLP) = 0.3 - 0.2 = 0.1$
* **Both ML and NLP:** $P(ML \cap NLP) = 0.2$
* **Neither:** $1 - (0.2 + 0.1 + 0.2) = 0.5$
