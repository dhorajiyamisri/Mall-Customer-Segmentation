<div align="center">

🛍️ Mall Customer Segmentation
🚀 Unsupervised Learning • Customer Analytics • Clustering

<p> <b>K-Means</b> &nbsp;•&nbsp; <b>Hierarchical Clustering</b> &nbsp;•&nbsp; <b>DBSCAN</b> </p>

<p> <i>Discovering hidden customer segments through unsupervised learning</i> </p>

</div>

<p align="center">
  <b>Red & White Skill Education — Unsupervised Learning Practical Report 1</b>
</p>

---

## 📌 Project Overview

This project performs **Mall Customer Segmentation** using three unsupervised learning algorithms:

* 🔵 **K-Means Clustering**
* 🌳 **Agglomerative Hierarchical Clustering**
* 🟣 **DBSCAN**

The objective is to identify meaningful customer groups based on their **Age, Annual Income, and Spending Score**, and compare different clustering techniques using visualisations and clustering evaluation metrics.

The primary clustering analysis uses:

* `Annual_Income`
* `Spending_Score`

These two features provide clear visual separation between customer segments and make the resulting clusters easier to interpret from a business perspective.

---

## 🎯 Objectives

* Load and explore the Mall Customer Segmentation dataset.
* Perform data preprocessing and exploratory data analysis.
* Encode the categorical Gender feature.
* Apply feature scaling using `StandardScaler`.
* Select Annual Income and Spending Score for primary clustering.
* Determine a suitable number of K-Means clusters using:

  * Elbow Method
  * Silhouette Score
* Perform K-Means clustering and analyse customer segments.
* Apply Agglomerative Hierarchical Clustering using Ward linkage.
* Use a dendrogram to understand hierarchical grouping.
* Tune DBSCAN using a 4-NN distance plot and parameter grid search.
* Compare K-Means, Hierarchical Clustering, and DBSCAN.
* Evaluate clustering quality using multiple metrics.
* Derive business insights and possible marketing strategies.

---

## 📊 Dataset

**Dataset:** Mall Customer Segmentation Dataset

**Source:** Kaggle

🔗 [Mall Customer Segmentation Dataset](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

### Dataset Information

* **Rows:** 200
* **Columns:** 5
* **Missing Values:** 0
* **Duplicate Rows:** 0

### Original Features

| Feature                | Description                |
| ---------------------- | -------------------------- |
| CustomerID             | Unique customer identifier |
| Gender                 | Customer gender            |
| Age                    | Customer age               |
| Annual Income (k$)     | Annual income              |
| Spending Score (1-100) | Customer spending score    |

### Preprocessing

The following changes were performed:

* `Annual Income (k$)` → `Annual_Income`
* `Spending Score (1-100)` → `Spending_Score`
* `CustomerID` was removed because it is only an identifier.
* `Gender` was encoded using `LabelEncoder`.
* `Age`, `Annual_Income`, and `Spending_Score` were scaled using `StandardScaler`.

---

## 🤖 Algorithms Used

### 1. K-Means Clustering

K-Means is a centroid-based clustering algorithm that divides customers into a predefined number of clusters.

The optimal cluster count was investigated using:

* Elbow Method
* Silhouette Score

The final model uses the selected number of clusters based on the clustering analysis.

---

### 2. Agglomerative Hierarchical Clustering

Agglomerative Hierarchical Clustering starts with individual observations and progressively merges similar observations into larger groups.

**Linkage method:** Ward

A dendrogram was used to visualise the hierarchical merging process and determine an appropriate clustering level.

---

### 3. DBSCAN

DBSCAN is a density-based clustering algorithm.

It uses:

* `eps` — neighbourhood distance
* `min_samples` — minimum number of neighbouring points

Unlike K-Means, DBSCAN does not require the number of clusters to be specified beforehand and can identify low-density observations as **noise (`-1`)**.

A 4-NN distance plot and parameter grid search were used for parameter selection.

---

## 📈 Exploratory Data Analysis

The project includes:

* Dataset preview
* Dataset information
* Statistical summary
* Histograms with KDE
* Pairplot
* Correlation heatmap

The EDA indicates that **Annual Income and Spending Score** provide useful separation for customer segmentation and are therefore used as the primary two-dimensional clustering space.

---

## 📉 K-Means Analysis

### Elbow Method

The Elbow Method evaluates the inertia for different values of `k`.

![Elbow Method](screenshots/elbow_method.png)

### Silhouette Score

The Silhouette Score was evaluated for `k = 2` to `k = 10`.

The final K-Means cluster count was selected using the clustering analysis and interpretability of the resulting customer segments.

### K-Means Customer Segmentation

The final K-Means model was visualised using:

* Annual Income
* Spending Score
* Cluster labels
* Cluster centroids

---

## 🌳 Hierarchical Clustering

### Dendrogram

Ward-linkage hierarchical clustering was visualised using a dendrogram.

![Dendrogram](screenshots/dendrogram.png)

The dendrogram helps understand how customers are progressively merged into larger groups.

---

## 🟣 DBSCAN Analysis

### 4-NN Distance Plot

A 4-nearest-neighbour distance plot was used to estimate a suitable `eps` value.

![DBSCAN k-Distance Plot](screenshots/dbscan_k_distance.png)

A grid search was then performed over multiple combinations of:

* `eps`
* `min_samples`

The final DBSCAN model identifies dense customer groups and can classify low-density observations as noise.

---

## 📊 Algorithm Comparison

The three clustering algorithms were compared using the same feature space:

* Annual Income
* Spending Score

![Algorithm Comparison](screenshots/algorithm_comparison.png)

### Comparison

| Algorithm    | Main Approach                       | Requires Number of Clusters? | Handles Noise? |
| ------------ | ----------------------------------- | ---------------------------: | -------------: |
| K-Means      | Centroid-based                      |                          Yes |             No |
| Hierarchical | Connectivity / hierarchical merging |                          Yes |             No |
| DBSCAN       | Density-based                       |                           No |            Yes |

---

## 📏 Evaluation Metrics

The clustering models were evaluated using:

### Silhouette Score

Higher values generally indicate better-separated and more compact clusters.

### Davies-Bouldin Index

Lower values generally indicate better cluster separation and compactness.

### Calinski-Harabasz Index

Higher values generally indicate better-defined clustering based on between-cluster and within-cluster dispersion.

For DBSCAN, noise points labelled `-1` are excluded from the metric calculations.

---

## 💼 Business Insights

The K-Means customer segments are interpreted using the average:

* Age
* Annual Income
* Spending Score

Possible customer segment categories include:

### 💎 High Income + High Spending

Customers with strong purchasing power and high spending behaviour.

**Possible strategy:**

* Premium products
* Loyalty rewards
* Personalised offers

### 💰 High Income + Low Spending

Customers with high purchasing power but relatively low spending.

**Possible strategy:**

* Personalised recommendations
* Premium promotions
* Targeted campaigns

### 🛍️ Low Income + High Spending

Customers showing relatively high spending despite lower income.

**Possible strategy:**

* Discounts
* Budget-friendly offers
* Promotional campaigns

### 🏷️ Low Income + Low Spending

Customers with lower income and lower spending behaviour.

**Possible strategy:**

* Value products
* Budget-focused offers
* Entry-level promotions

### ⚖️ Medium Income + Medium Spending

Customers with balanced income and spending behaviour.

**Possible strategy:**

* Loyalty programmes
* Regular promotions
* Personalised recommendations

> Segment interpretation is based on the actual cluster averages produced by the notebook rather than assuming that cluster numbers have a fixed business meaning.

---

## 🛠️ Technologies & Libraries

### Programming Language

* Python

### Data Analysis

* Pandas
* NumPy

### Data Visualisation

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn

### Hierarchical Clustering

* SciPy

### Development Environment

* Jupyter Notebook
* VS Code

---

## 📁 Project Structure

```text
Unsupervised-Learning-PR1/
│
├── Mall_Customers.csv
├── UL_PR1.ipynb
├── UL_PR1.html
├── requirements.txt
│
└── screenshots/
    ├── elbow_method.png
    ├── dendrogram.png
    ├── dbscan_k_distance.png
    └── algorithm_comparison.png
```

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/dhorajiyamisri/Unsupervised-Learning-PR1.git
```

### 2. Open the project

```bash
cd Unsupervised-Learning-PR1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Open the notebook

```bash
jupyter notebook UL_PR1.ipynb
```

Run all notebook cells from beginning to end.

---

## 📋 Practical Report Coverage

This project covers the complete PR workflow:

* ✅ Data Loading
* ✅ Data Cleaning
* ✅ Exploratory Data Analysis
* ✅ Feature Encoding
* ✅ Feature Scaling
* ✅ Feature Selection
* ✅ Elbow Method
* ✅ Silhouette Score
* ✅ K-Means Clustering
* ✅ Cluster Centroids
* ✅ Cluster Profiling
* ✅ Dendrogram
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

## 🎥 Project Video

**Video demonstration:**
`Video link will be added here.`

The demonstration covers the notebook workflow, clustering concepts, visualisations, evaluation metrics, and business insights.

---

## 👩‍💻 Author

**Misari Dhorajiya**

GitHub: [@dhorajiyamisri](https://github.com/dhorajiyamisri)

---

## ⭐ Project Summary

This project demonstrates how unsupervised learning can be used for **customer segmentation**.

By comparing K-Means, Agglomerative Hierarchical Clustering, and DBSCAN, the project shows how different clustering approaches can reveal customer groups from the same dataset and how those groups can be translated into practical business insights.
