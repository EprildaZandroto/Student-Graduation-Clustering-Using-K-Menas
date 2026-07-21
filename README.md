# 🎓 Student Graduation Clustering Using K-Means
## 📌 Project Description

This project applies the **K-Means Clustering** algorithm to group students based on their academic performance and study characteristics.
Instead of predicting graduation, this project focuses on discovering hidden patterns among students using an unsupervised machine learning approach.

---

## 🎯 Objectives

- Analyze student academic data.
- Determine the optimal number of clusters using the Elbow Method.
- Group students with similar academic characteristics.
- Visualize clustering results for easier interpretation.

---

## 📊 Dataset Information

The dataset consists of **100,000 student records** with the following features:

| Feature | Description |
|---------|-------------|
| IPK | Grade Point Average (GPA) |
| Mata Kuliah Tidak Lulus | Number of failed courses |
| Jumlah Cuti Akademik | Number of academic leave semesters |
| Pekerjaan Sambil Kuliah | Working while studying (Yes/No) |
| Jumlah Semester | Total semesters completed |
| Status Kelulusan | Graduation Status |
| IPS Rata-rata | Average Semester GPA |
| Kehadiran (%) | Attendance Percentage |
| IPS Tren | Semester GPA Trend |
| Kategori Kehadiran | Attendance Category |

---

## 🛠️ Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

---

## 📚 Machine Learning Workflow

```python
Load Dataset
        │
        ▼
Exploratory Data Analysis (EDA)
        │
        ▼
Data Preprocessing
        │
        ▼
Label Encoding
        │
        ▼
Feature Selection
        │
        ▼
Elbow Method
        │
        ▼
K-Means Clustering
        │
        ▼
Cluster Visualization
        │
        ▼
Interpretation of Results
```

---

## 💻 Sample Code

### Import Library

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.cluster import KMeans
from sklearn.preprocessing import LabelEncoder
```

### Load Dataset

```python
data = pd.read_csv("dataset_kelulusan_mahasiswa.csv")
data.head()
```

Loads the dataset into a Pandas DataFrame for further analysis.

---

### Exploratory Data Analysis

```python
sns.pairplot(data)
plt.show()
```

Visualizes relationships between variables and helps identify patterns before clustering.

---

### Data Preprocessing

```python
encoder = LabelEncoder()

data["Pekerjaan Sambil Kuliah"] = encoder.fit_transform(
    data["Pekerjaan Sambil Kuliah"]
)

data["Kategori Kehadiran"] = encoder.fit_transform(
    data["Kategori Kehadiran"]
)
```

Converts categorical features into numerical values suitable for K-Means.

---

### Elbow Method

```python
wcss = []

for i in range(1,11):
    model = KMeans(n_clusters=i, random_state=42)
    model.fit(X)
    wcss.append(model.inertia_)
```

Determines the optimal number of clusters using Within-Cluster Sum of Squares (WCSS).

---

### K-Means Clustering

```python
kmeans = KMeans(
    n_clusters=3,
    random_state=42
)

data["Cluster"] = kmeans.fit_predict(X)
```

Groups students into clusters based on similarities in their academic performance.

---

## 📈 Output

✔ Pairplot Visualization

✔ Elbow Method Graph

✔ Cluster Scatter Plot

✔ Student Cluster Distribution

---

## 📁 Repository Structure

```
Student-Graduation-KMeans
│
├── Kelulusan Mahasiswa.ipynb
├── dataset_kelulusan_mahasiswa.csv
├── README.md
└── images/
```

---

## 👩‍💻 Author

**Eprilda Nonifili Zandroto**

Informatics Engineering Student
Passionate about Machine Learning, Data Analytics, and Data Visualization
