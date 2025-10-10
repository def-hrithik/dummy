# 📘 Data Warehousing and Mining (DWM) — Question Bank Answers
**(Mumbai University | 5 Marks Each)**  

---

### **1. Explain the working of DBSCAN algorithm using appropriate diagrams.**

**DBSCAN (Density-Based Spatial Clustering of Applications with Noise)** is a clustering algorithm that groups together closely packed data points and marks points in low-density regions as outliers.

#### **Key Concepts:**
- **Eps (ε):** Radius of neighborhood.  
- **MinPts:** Minimum number of points required to form a dense region.

#### **Steps:**
1. Select an unvisited point.  
2. If it has ≥ MinPts within distance ε → it’s a **core point** and a cluster starts.  
3. All points within ε become part of the cluster.  
4. Repeat expansion until no more points can be added.  
5. Points not reachable from any cluster → **noise**.

#### **Example:**  
If ε = 2 and MinPts = 3, nearby dense points will form one cluster while sparse ones are marked as noise.

---

### **2. What is web mining? Explain web content mining in detail.**

**Web Mining:**  
Process of discovering useful patterns and information from web data (web content, structure, and usage).

#### **Types of Web Mining:**
1. **Web Content Mining**  
2. **Web Structure Mining**  
3. **Web Usage Mining**

#### **Web Content Mining:**  
Extracts data from web pages — such as text, images, audio, video, or structured data like tables.

**Techniques Used:**  
- Natural Language Processing (NLP)  
- Text Mining  
- HTML Parsing  
- Machine Learning  

**Applications:**  
- News Categorization  
- Sentiment Analysis  
- Product Recommendation  

**Example:** Extracting and classifying product reviews from Amazon pages.

---

### **3. What is clustering? Apply K-means algorithm to `{4, 8, 20, 24, 6, 40, 60, 22, 50}` for K = 2.**

**Clustering:**  
Grouping similar data objects so that objects in the same group are more similar to each other than to those in other groups.

#### **Steps for K-Means (K = 2):**
1. **Initialize Centroids:** C₁ = 4, C₂ = 60  
2. **Assign points to nearest centroid:**  
   - Cluster1 → {4, 8, 6, 20, 24, 22}  
   - Cluster2 → {40, 50, 60}  
3. **Recalculate Means:**  
   - New C₁ = (4 + 8 + 6 + 20 + 24 + 22)/6 = 14  
   - New C₂ = (40 + 50 + 60)/3 = 50  
4. **Reassign Points:**  
   - Cluster1 → {4, 6, 8, 20, 22, 24}  
   - Cluster2 → {40, 50, 60}

✅ **Final Clusters:**  
- C₁ = {4, 6, 8, 20, 22, 24}  
- C₂ = {40, 50, 60}

---

### **4. Plot a Dendrogram using the single linkage approach of Agglomerative algorithm.**

**Agglomerative Hierarchical Clustering:**
- Starts with each object as an individual cluster.  
- Merges the two closest clusters step by step using a linkage method.

**Single Linkage:**  
Distance between clusters = smallest distance between members.

#### **Steps:**
1. Compute the distance matrix.  
2. Merge the two closest clusters.  
3. Recompute distances.  
4. Continue merging until all clusters are combined.

#### **Dendrogram:**  
A tree-like diagram showing the sequence of merges.  
- **Horizontal axis:** Clusters  
- **Vertical axis:** Distance at which clusters are merged.

---

### **5. What is market basket analysis? Explain with example and formulas for Support & Confidence.**

**Market Basket Analysis (MBA):**  
A technique used to find associations between items bought together. Commonly used in retail and recommendation systems.

#### **Example:**  
If 70% of people who buy milk also buy bread, the rule is:  
**Milk → Bread**

#### **Formulas:**
- **Support (A→B)** = (Transactions containing both A & B) / (Total transactions)  
- **Confidence (A→B)** = (Transactions containing both A & B) / (Transactions containing A)

#### **Numerical Example:**  
If 100 total transactions, 30 contain milk, and 15 contain both milk & bread:  
- Support = 15/100 = **0.15**  
- Confidence = 15/30 = **0.5**

---

### **6. Explain web structure mining in detail.**

**Web Structure Mining:**  
Analyzes the structure of hyperlinks within or between websites to discover relationships among web pages.

#### **Input:**  
Link structure data (URLs and hyperlink relationships).

#### **Techniques:**  
- Graph Theory  
- Link Analysis Algorithms (e.g., PageRank)

#### **Applications:**
- Search engine ranking (Google’s PageRank)  
- Website structure optimization  
- Detecting communities or hubs

#### **Example:**  
In a university website, the link structure helps identify main department pages (hubs) and authoritative course pages.

---

### **7. What is clustering? Apply K-means for `{6, 14, 18, 22, 1, 40, 50, 11, 25}` with K = 2.**

#### **Step 1:** Initial Centroids → C₁ = 6, C₂ = 50  
#### **Step 2:** Assign points to nearest centroid.  
- Cluster1 → {6, 14, 18, 22, 1, 11, 25}  
- Cluster2 → {40, 50}

#### **Step 3:** Recalculate Means  
- C₁ = (6 + 14 + 18 + 22 + 1 + 11 + 25)/7 = 13.85 ≈ 14  
- C₂ = (40 + 50)/2 = 45

#### **Step 4:** Reassign Points  
- Cluster1 → {1, 6, 11, 14, 18, 22, 25}  
- Cluster2 → {40, 50}

✅ **Final Clusters:**  
- C₁ = {1, 6, 11, 14, 18, 22, 25}  
- C₂ = {40, 50}

---

### **8. Explain FP-Tree with an example.**

**FP-Tree (Frequent Pattern Tree):**  
A compact data structure that stores key information about frequent itemsets in a transaction database.

#### **Steps:**
1. Scan the database → find frequent items and sort them by frequency.  
2. Build the tree by inserting transactions in order.  
3. Create conditional pattern bases to extract frequent itemsets.

#### **Example:**
Transactions:  
- T1: {A, B, C}  
- T2: {A, C, D}  
- T3: {A, B, D}  

→ FP-Tree groups shared prefixes (A) together, reducing redundancy.

#### **Advantages:**
- Avoids generating candidate itemsets.  
- Efficient for large databases.  
