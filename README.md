
# 🛍️ Mall Customer Segmentation

### 🔍 Unsupervised Learning • Customer Analytics • Clustering
</p>
<b>Red & White Skill Education — Unsupervised Learning Practical Report 1</b> </p>
<p>
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
  <img src="https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge"/>
</p>

<p>
  <img src="https://img.shields.io/badge/K--Means-Clustering-00A8E8?style=flat-square"/>
  <img src="https://img.shields.io/badge/Hierarchical-Clustering-8E44AD?style=flat-square"/>
  <img src="https://img.shields.io/badge/DBSCAN-Density%20Based-27AE60?style=flat-square"/>
</p>

<p>
  <i>Discovering hidden customer segments through unsupervised learning</i>
</p>

</div>

---

<table>
<tr>

<td width="52%" align="center">

<img src="<img width="684" height="475" alt="image" src="https://github.com/user-attachments/assets/b68c33fb-2f29-4b37-ba94-e7478039fed0" />
" width="100%" alt="Mall Customer Segmentation">

</td>

<td width="48%" valign="middle">

## 🎯 Project in One View

This project uses **unsupervised machine learning** to discover meaningful customer segments from mall customer data.

Customers are analysed mainly using:

**Annual Income × Spending Score**

Three clustering algorithms are applied and compared to understand how different unsupervised learning approaches identify customer groups.

### 🤖 Algorithms

🔵 **K-Means Clustering**
🌳 **Agglomerative Hierarchical Clustering**
🟣 **DBSCAN**

### 📊 Dataset

**200 Customers • 5 Original Features**

### 📈 Evaluation

**Silhouette Score**
**Davies-Bouldin Index**
**Calinski-Harabasz Index**

</td>

</tr>
</table>

---

<div align="center">

### 🔄 Data → EDA → Scaling → Clustering → Evaluation → Business Insights

</div>

---

# 📌 Project Overview

Mall Customer Segmentation is an **unsupervised learning project** designed to identify groups of customers with similar characteristics and spending behaviour.

The project explores three different clustering approaches:

* 🔵 K-Means Clustering
* 🌳 Agglomerative Hierarchical Clustering
* 🟣 DBSCAN

The primary clustering analysis uses **Annual Income** and **Spending Score** because these features provide clear visual separation between customer segments and make the results easier to interpret from a business perspective.

---

# 🎯 Objectives

* Load and explore the Mall Customer Segmentation dataset.
* Perform data preprocessing and exploratory data analysis.
* Encode the categorical Gender feature.
* Apply feature scaling using `StandardScaler`.
* Select Annual Income and Spending Score for primary clustering.
* Determine a suitable number of K-Means clusters using:

  * Elbow Method
  * Silhouette Score
* Perform K-Means clustering.
* Analyse customer cluster profiles.
* Apply Agglomerative Hierarchical Clustering.
* Visualise hierarchical relationships using a dendrogram.
* Tune DBSCAN using a 4-NN distance plot and parameter grid search.
* Compare all three clustering algorithms.
* Evaluate clustering quality using multiple metrics.
* Derive business insights and possible marketing strategies.

---

# 📊 Dataset

### Mall Customer Segmentation Dataset

**Source:** Kaggle

🔗 [View Dataset on Kaggle](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

### Dataset Statistics

| Property            |   Value |
| ------------------- | ------: |
| 👥 Rows             | **200** |
| 📊 Original Columns |   **5** |
| ❌ Missing Values    |   **0** |
| 🔁 Duplicate Rows   |   **0** |

### Original Features

| Feature                  | Description                |
| ------------------------ | -------------------------- |
| `CustomerID`             | Unique customer identifier |
| `Gender`                 | Customer gender            |
| `Age`                    | Customer age               |
| `Annual Income (k$)`     | Annual income              |
| `Spending Score (1-100)` | Customer spending score    |

---

# ⚙️ Data Preprocessing

The following preprocessing steps were performed:

### Column Renaming

```text
Annual Income (k$)       → Annual_Income
Spending Score (1-100)   → Spending_Score
```

### Identifier Removal

`CustomerID` was removed because it is an identifier and does not provide useful information for clustering.

### Gender Encoding

`Gender` was converted into numerical values using `LabelEncoder`.

### Feature Scaling

`StandardScaler` was applied to:

* `Age`
* `Annual_Income`
* `Spending_Score`

The primary clustering analysis uses:

```text
Annual_Income
Spending_Score
```

Scaling is important because K-Means and DBSCAN use distance calculations and are sensitive to feature magnitude.

---

# 🔍 Exploratory Data Analysis

The project includes:

* Dataset preview
* Dataset information
* Statistical summary
* Histograms with KDE
* Pairplot
* Correlation heatmap

The EDA helps understand the distributions and relationships between the customer features.

### Primary Segmentation Features

```text
        Annual Income
              ×
       Spending Score
```

These two features provide useful visual separation for customer segmentation.

---

# 🤖 Machine Learning Approach

<table>
<tr>

<td width="33%" align="center">

## 🔵 K-Means

**Centroid-Based**

Groups customers around cluster centroids.

**Used for:**

* Elbow Method
* Silhouette Score
* Cluster profiling
* Centroid visualisation

</td>

<td width="33%" align="center">

## 🌳 Hierarchical

**Agglomerative**

Progressively merges similar customers.

**Used for:**

* Ward linkage
* Dendrogram
* Cluster comparison

</td>

<td width="33%" align="center">

## 🟣 DBSCAN

**Density-Based**

Groups dense regions and detects noise.

**Used for:**

* 4-NN analysis
* Parameter tuning
* Noise detection

</td>

</tr>
</table>

---

# 🔵 K-Means Clustering

## Elbow Method

The Elbow Method evaluates the **inertia** for different values of `k`.

The elbow point represents a balance between reducing within-cluster variation and avoiding unnecessary clusters.

![Elbow Method](screenshots/elbow_method.png)

---

## Silhouette Score

The Silhouette Score was evaluated for:

```text
k = 2 → 10
```

A higher Silhouette Score generally indicates better-separated and more compact clusters.

The Elbow Method and Silhouette Score were considered together when selecting the final K-Means cluster count.

---

## Customer Segmentation

The final K-Means model visualises customers using:

* Annual Income
* Spending Score
* Cluster labels
* Cluster centroids

The resulting clusters are profiled using average:

* Age
* Annual Income
* Spending Score

---

# 🌳 Agglomerative Hierarchical Clustering

Hierarchical clustering was performed using:

```text
Linkage = Ward
```

Ward linkage merges clusters while minimising the increase in within-cluster variance.

## Dendrogram

![Dendrogram](screenshots/dendrogram.png)

The dendrogram helps understand how customers are progressively merged into larger groups and supports the selection of an appropriate clustering level.

---

# 🟣 DBSCAN Clustering

DBSCAN is a density-based clustering algorithm.

It uses two important parameters:

| Parameter     | Meaning                                        |
| ------------- | ---------------------------------------------- |
| `eps`         | Maximum neighbourhood distance                 |
| `min_samples` | Minimum number of neighbouring points required |

DBSCAN also provides the ability to identify low-density observations as **noise (`-1`)**.

---

## 4-NN Distance Plot

A 4-nearest-neighbour distance plot was used to estimate a suitable `eps` value.

![DBSCAN k-Distance Plot](screenshots/dbscan_k_distance.png)

A parameter grid search was then performed using different combinations of:

```text
eps
min_samples
```

The selected parameters were evaluated based on cluster quality and noise points.

---

# 📊 Algorithm Comparison

All three algorithms were compared using the same primary feature space:

```text
Annual Income × Spending Score
```

![Algorithm Comparison](screenshots/algorithm_comparison.png)

---

## Comparison Table

| Algorithm       | Approach               | Requires `k`? | Noise Detection | Cluster Shape           |
| --------------- | ---------------------- | :-----------: | :-------------: | ----------------------- |
| 🔵 K-Means      | Centroid-based         |       ✅       |        ❌        | Approximately spherical |
| 🌳 Hierarchical | Connectivity / merging |       ✅       |        ❌        | Depends on linkage      |
| 🟣 DBSCAN       | Density-based          |       ❌       |        ✅        | Arbitrary shapes        |

### Key Differences

**K-Means**

* Requires the number of clusters.
* Assigns every customer to a cluster.
* Uses cluster centroids.
* Easy to interpret for customer segmentation.

**Hierarchical Clustering**

* Builds a hierarchy of customer groups.
* Provides a dendrogram.
* Useful for understanding how clusters merge.
* Customer assignments can differ near cluster boundaries.

**DBSCAN**

* Does not require the number of clusters beforehand.
* Groups customers according to density.
* Can identify noise.
* Sensitive to `eps` and `min_samples`.

---

# 📏 Clustering Evaluation

The project evaluates all three algorithms using multiple internal clustering metrics.

### Silhouette Score

Higher values generally indicate better-separated and more compact clusters.

### Davies-Bouldin Index

Lower values generally indicate better cluster separation and compactness.

### Calinski-Harabasz Index

Higher values generally indicate better-defined clustering based on between-cluster and within-cluster dispersion.

### DBSCAN Metric Handling

For DBSCAN, observations labelled as noise (`-1`) are excluded from the metric calculations.

---

# 💼 Business Insights

The customer segments are interpreted using:

* Age
* Annual Income
* Spending Score

The exact interpretation is based on the actual cluster averages produced by the notebook.

---

## 💎 High Income + High Spending

Customers with strong purchasing power and high spending behaviour.

**Possible strategies:**

* Premium products
* Loyalty rewards
* Personalised offers

---

## 💰 High Income + Low Spending

Customers with high purchasing power but relatively low spending behaviour.

**Possible strategies:**

* Personalised recommendations
* Premium promotions
* Targeted campaigns

---

## 🛍️ Low Income + High Spending

Customers showing relatively high spending despite lower income.

**Possible strategies:**

* Discounts
* Budget-friendly offers
* Promotional campaigns

---

## 🏷️ Low Income + Low Spending

Customers with lower income and lower spending behaviour.

**Possible strategies:**

* Value products
* Budget-focused promotions
* Entry-level offers

---

## ⚖️ Medium Income + Medium Spending

Customers with balanced income and spending behaviour.

**Possible strategies:**

* Loyalty programmes
* Regular promotions
* Personalised recommendations

> **Note:** Cluster numbers are not assumed to represent a fixed customer category. Segment names are interpreted from the actual cluster averages.

---

# 📈 Project Workflow

```text
                    📂 Dataset
                        │
                        ▼
                  🔍 Data Analysis
                        │
                        ▼
                 ⚙️ Preprocessing
                        │
                        ▼
                  📏 Feature Scaling
                        │
              ┌─────────┼─────────┐
              ▼         ▼         ▼
          🔵 K-Means   🌳 Hier.   🟣 DBSCAN
              │         │         │
              └─────────┼─────────┘
                        ▼
                 📊 Comparison
                        │
                        ▼
                  📏 Evaluation
                        │
                        ▼
                  💼 Business
                    Insights
```

---

# 📊 Project Highlights

| Category            | Implementation                        |
| ------------------- | ------------------------------------- |
| 📂 Dataset          | Mall Customer Segmentation            |
| 👥 Customers        | 200                                   |
| 🔍 EDA              | Histograms, KDE, Pairplot, Heatmap    |
| ⚙️ Preprocessing    | Encoding + Scaling                    |
| 🔵 Clustering       | K-Means                               |
| 🌳 Clustering       | Hierarchical                          |
| 🟣 Clustering       | DBSCAN                                |
| 📉 Parameter Tuning | Elbow + Silhouette + 4-NN             |
| 📏 Evaluation       | 3 Clustering Metrics                  |
| 💼 Output           | Customer Segments + Business Insights |

---

# 🛠️ Tech Stack

<p align="center">

<img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=for-the-badge&logo=numpy&logoColor=white"/>
<img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
<img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge"/>
<img src="https://img.shields.io/badge/SciPy-Scientific%20Computing-8CAAE6?style=for-the-badge"/>

</p>

### Development Environment

* Jupyter Notebook
* VS Code
* Git & GitHub

---

# 📁 Project Structure

```text
Unsupervised-Learning-PR1/
│
├── 📄 Mall_Customers.csv
├── 📓 UL_PR1.ipynb
├── 🌐 UL_PR1.html
├── 📦 requirements.txt
│
└── 📁 screenshots/
    ├── 🖼️ elbow_method.png
    ├── 🖼️ dendrogram.png
    ├── 🖼️ dbscan_k_distance.png
    └── 🖼️ algorithm_comparison.png
```

---

# ▶️ How to Run

### 1️⃣ Clone the repository

```bash
git clone https://github.com/dhorajiyamisri/Unsupervised-Learning-PR1.git
```

### 2️⃣ Open the project

```bash
cd Unsupervised-Learning-PR1
```

### 3️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 4️⃣ Open the notebook

```bash
jupyter notebook UL_PR1.ipynb
```

### 5️⃣ Run All Cells

Run the notebook from beginning to end to reproduce the complete analysis.

---

# 📸 Visual Gallery

### 🔵 K-Means — Elbow Method

![Elbow Method](screenshots/elbow_method.png)

### 🌳 Hierarchical — Dendrogram

![Dendrogram](screenshots/dendrogram.png)

### 🟣 DBSCAN — 4-NN Distance

![DBSCAN k-Distance](screenshots/dbscan_k_distance.png)

### 📊 Algorithm Comparison

![Algorithm Comparison](screenshots/algorithm_comparison.png)

---

# 🎥 Project Demonstration

<div align="center">

## ▶️ Complete Project Walkthrough

**EDA → Preprocessing → K-Means → Hierarchical → DBSCAN → Evaluation → Business Insights**

</div>

### 🎬 Video

**Video link:** `Coming soon`

---

# 📋 Practical Report Coverage

* ✅ Data Loading
* ✅ Data Cleaning
* ✅ Exploratory Data Analysis
* ✅ Gender Encoding
* ✅ Feature Scaling
* ✅ Feature Selection
* ✅ Elbow Method
* ✅ Silhouette Score
* ✅ K-Means Clustering
* ✅ Cluster Centroids
* ✅ Cluster Profiling
* ✅ Ward-Linkage Dendrogram
* ✅ Agglomerative Hierarchical Clustering
* ✅ 4-NN Distance Plot
* ✅ DBSCAN Parameter Tuning
* ✅ DBSCAN Clustering
* ✅ Noise Detection
* ✅ Three-Algorithm Comparison
* ✅ Silhouette Score
* ✅ Davies-Bouldin Index
* ✅ Calinski-Harabasz Index
* ✅ Business Insights

---

# 🎓 Practical Report

**Red & White Skill Education**

### Unsupervised Learning — Practical Report 1

**Topic:** Mall Customer Segmentation

---

# 👩‍💻 Author

<div align="center">

## Misari Dhorajiyiya

**Data Science / AI-ML Learner**

📊 Data Analysis • 🤖 Machine Learning • 📈 Data Visualization

[![GitHub](https://img.shields.io/badge/GitHub-dhorajiyamisri-181717?style=for-the-badge\&logo=github)](https://github.com/dhorajiyamisri)

</div>

---

<div align="center">

### ⭐ If you found this project useful, consider giving it a star!

**Built with Python • Scikit-learn • Pandas • Seaborn • SciPy**

</div>
