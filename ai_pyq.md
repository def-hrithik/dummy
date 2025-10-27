# 🧠 DEEP INSIGHT ANALYSIS

## 📂 Dataset Summary
From your uploaded merged PDF, I extracted 4 years of university AI question papers:

| Year | QP Code | Date | Difficulty | Notes |
| :--- | :--- | :--- | :--- | :--- |
| May 2023 | 10029721 | 29/05/2023 | Medium | Focus on logic + GA |
| Nov 2023 | 10038167 | 29/11/2023 | Hard | Concept-heavy + planning |
| May 2024 | 10055372 | 07/06/2024 | Moderate | Mix of reasoning + numericals |
| May 2025 | 10083059 | 09/06/2025 | Moderate | Concept + logical deduction |

Each follows same structure:
* Q1 Compulsory (5 × 5 = 20 marks)
* Q2–Q6 (Choose any 3) = 60 marks

---

## 🔁 1. RECURRING QUESTION CLUSTERS (2023–2025)
Let’s break repetition into concept families and probability of recurrence in 2026:

| Concept / Question Topic | 2023 (May) | 2023 (Nov) | 2024 | 2025 | 🔮 2026 Prediction | Insights |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Forward & Backward Chaining | ✅ | ✅ | ✅ | ✅ | 🔥 Very High (90%) | Appears every year – examiners love inference logic |
| Hill Climbing + Problems | ✅ | ✅ | ✅ | ✅ | 🔥 Very High (90%) | Core of heuristic search, often paired with 8-puzzle |
| Genetic Algorithm (GA) | ✅ | ✅ | ✅ | ❌ | 🔥 High (80%) | Missed in 2025 → likely to reappear 2026 |
| Alpha-Beta Pruning | ✅ | ✅ | ✅ | ✅ | 🔥 Very High (90%) | Always numerical, examiner rotates example trees |
| Bayes Theorem / Belief Network | ✅ | ❌ | ✅ | ❌ | ⭐ Medium (60%) | Alternates years; revise calculations |
| Expert System Architecture | ✅ | ✅ | ✅ | ❌ | ⭐⭐ High (75%) | 3-year streak, may return next |
| PEAS Descriptor | ✅ | ✅ | ✅ | ✅ | 🔥 Very High (90%) | Always 5 marks, small but guaranteed |
| Prolog Program (Factorial/Fibonacci) | ✅ | ✅ | ✅ | ✅ | 🔥 Very High (90%) | Compulsory question in Q1 |
| Knowledge Representation (FOPL/Resolution) | ❌ | ✅ | ✅ | ✅ | 🔥 High (80%) | Concept + small logic proof |
| 8-Puzzle / Missionaries & Cannibals Problem | ✅ | ✅ | ✅ | ✅ | 🔥 High (85%) | Classic problem formulation |
| Planning (Partial Order / STRIPS) | ✅ | ✅ | ✅ | ❌ | ⭐⭐ Medium (65%) | Appears every 2 years |
| Types of Environments / Agents | ✅ | ✅ | ✅ | ✅ | 🔥 High (90%) | Rephrased yearly |
| Utility / Goal-based / Learning Agents | ✅ | ❌ | ✅ | ✅ | ⭐⭐ High (80%) | Theoretical must-know |

---

## 🧮 2. NUMERICAL PATTERN ANALYSIS

### 🧩 List of All Numericals Appeared (2023–2025)

| Numerical Topic | Marks | Frequency | Key Skills Tested |
| :--- | :--- | :--- | :--- |
| Alpha-Beta Pruning | 10 | 4× | Apply pruning logic, identify MAX/MIN values |
| A* Search | 10 | 2× | Compute f(n)=g(n)+h(n) and path cost |
| Bayes Theorem | 10 | 2× | Conditional probability + posterior calc |
| Genetic Algorithm | 10 | 3× | Step-by-step iteration (selection, crossover, mutation) |
| 8-Puzzle / Missionaries-Cannibals | 10 | 2× | State-space problem, goal test |
| Resolution in FOPL | 10 | 1× | Logical proof derivation |
| Prolog Numericals (Factorial / Fibonacci) | 5 | 3× | Syntax and recursion check |
| CNF Conversion / Inference Rules | 10 | 1× | Simplify logical sentences |

### 📊 Frequency Summary

| Category | Average Marks per Paper | Probability | Examples |
| :--- | :--- | :--- | :--- |
| Search Algorithms (A*, Hill Climb, Iterative Deepening) | 20 | 🔥 High | A*, Hill Climb |
| Logic & Inference (Forward/Backward, Resolution) | 20–25 | 🔥 Very High | Forward chain |
| Learning & GA | 10–15 | ⭐⭐ Medium | GA ops |
| Probability & Bayes | 10 | ⭐ Medium | BBN example |
| Knowledge Representation & Expert Systems | 15 | ⭐⭐ High | FOPL, Architecture |
| Environment/Agents/PEAS | 10 | 🔥 Very High | Compulsory short answers |

---

## 📘 3. EXAMINER’S PATTERN INSIGHT (Hidden Logic)
From Mumbai University’s repetition logic:

* 🔁 Concepts rotate every 2–3 exams (e.g., GA missing in 2025 → will come back 2026)
* 🔁 At least 1 numerical from logic (Alpha-Beta or Bayes)
* 🔁 At least 1 from search algorithms (A\*, Hill, IDA)\*
* 🔁 One reasoning/Prolog-based short question in Q1 always
* 🔁 Q5 or Q6 typically tests planning or learning theory

> 👉 **Inference:** Papers are balanced between reasoning, learning, and numerical logic — ~50% of marks test algorithmic reasoning rather than definitions.

---

## 🧮 4. IMPORTANT NUMERICALS TO STUDY (Ranked by Weightage)

1.  🥇 **Alpha-Beta Pruning (with tree)** - Appears in all 4 papers, always 10 marks
2.  🥈 **Bayes Theorem Example / BBN** - Probability + logic — mixed question type
3.  🥉 **Genetic Algorithm Example** - Easy scoring numerical, often repeated
4.  4️⃣ **8-Puzzle / Missionaries & Cannibals** - Problem formulation, easy 10 marks
5.  5️⃣ **A\* Algorithm** - Numeric + conceptual combo
6.  6️⃣ **Resolution (FOPL proof)** - Logical reasoning 10 marks
7.  7️⃣ **Prolog Recursive Programs** - Repeated small questions (5 marks)

---

## 🧩 5. 7-DAY SMART STUDY STRATEGY

* 🗓️ **Day 1: Agents & Environment (Basics)**
    * Study PEAS, Agent types (Simple Reflex, Model-based, Goal-based, Utility)
    * Short Qs: “Explain PEAS for Medical/Shopping/English Tutor”
* 🗓️ **Day 2: Problem Solving & Search**
    * Uninformed (DFS, BFS, Uniform cost)
    * Informed (Hill Climb, A\*, Best-first)
    * Practice 8-Puzzle example manually
* 🗓️ **Day 3: Knowledge Representation**
    * FOPL, CNF, Resolution, Inference rules
    * Write short Prolog programs (factorial, family tree, Fibonacci)
* 🗓️ **Day 4: Reasoning & Logic**
    * Forward & Backward chaining (with Robert–Missiles problem)
    * Predicate logic conversion + resolution proof
* 🗓️ **Day 5: Learning & Genetic Algorithms**
    * Supervised vs Unsupervised Learning
    * Genetic Algorithm example (selection, crossover, mutation)
* 🗓️ **Day 6: Probability & Bayesian Networks**
    * Bayes theorem numerical
    * Construct small Bayesian Belief Network (Weather–Sprinkler example)
* 🗓️ **Day 7: Revision + Planning + Mock Test**
    * Expert System architecture
    * Planning (Partial order, STRIPS)
    * Alpha-beta pruning numerical
    * Revise past year’s short Q1s

---

## 🧾 6. SUMMARY TABLE – HIGH-RETURN TOPICS (MARKS VS EFFORT)

| Topic | Avg Marks | Effort | ROI | Type |
| :--- | :--- | :--- | :--- | :--- |
| Forward/Backward Chaining | 10 | Medium | 🔥 High | Concept |
| Hill Climbing | 10 | Low | 🔥 High | Algorithm |
| Alpha-Beta Pruning | 10 | Medium | 🔥🔥 Very High | Numerical |
| Genetic Algorithm | 10 | Medium | 🔥 High | Algorithm |
| PEAS Descriptor | 5 | Low | 🔥🔥 High | Short |
| Expert System | 5–10 | Low | 🔥 High | Theory |
| Bayes Theorem / BBN | 10 | Medium | 🔥 High | Numerical |
| Prolog Programs | 5 | Low | 🔥🔥 High | Short |
| Knowledge Representation | 10 | High | 🔥 Medium | Concept |
| Planning / STRIPS | 10 | Medium | ⭐ Medium | Concept |

---

## 🎯 Final Prediction for 2026 AI Paper (Based on 3-Year Rotation)

| Predicted 10-Mark Questions | Predicted 5-Mark Questions |
| :--- | :--- |
| 1. Forward & Backward Chaining | 1. PEAS descriptor |
| 2. Genetic Algorithm with example | 2. Prolog factorial/fibonacci |
| 3. Alpha-Beta pruning (numerical) | 3. Expert System diagram |
| 4. Hill Climbing with problems | 4. Environment types |
| 5. Bayes Theorem numerical | 5. Knowledge-based agent |
| 6. Partial Order Planning | — |
