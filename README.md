# 🔍 Big Data Mining with PySpark 🚀

A hands-on **big data mining** project built with **Apache Spark (PySpark)**, covering the three classic mining tasks end to end: **Classification**, **Clustering**, and **Association Rule Mining**. Each task runs on a separate real-world dataset and uses Spark MLlib pipelines. ⚡📊

---

## 📌 About the Project

This project demonstrates how to apply distributed data mining techniques on tabular datasets using Spark's DataFrame API and the MLlib machine learning library. It walks through a full workflow for each task: loading the data, engineering features, building a model, and evaluating or visualizing the results. 🧠

---

## 🛠️ Tech Stack

| Component | Detail |
|---|---|
| Engine | Apache Spark (PySpark) |
| ML library | Spark MLlib (`pyspark.ml`) |
| Models | `DecisionTreeClassifier`, `KMeans` / `StandardScaler`, `FPGrowth` |
| Feature tools | `StringIndexer`, `VectorAssembler` |
| Visualization | Matplotlib, Pandas |

---

## 🧩 Tasks

### 1️⃣ Classification — Decision Tree 🌳

Predicts the "deal quality" of used cars from the **CarDekho** dataset.

- Categorical columns (`Car_Name`, `Fuel_Type`, `Seller_Type`, `Transmission`) are encoded with `StringIndexer`.
- A multi-class label is engineered from business rules over selling price, manufacturing year, and kilometres driven:
  - **2** → great deal (above-average price, recent year, low mileage)
  - **1** → good deal (above-average price, recent year)
  - **0** → above-average price only
  - **3** → not recommended
- Features are combined with `VectorAssembler`, the data is split 80/20, and a `DecisionTreeClassifier` is trained.
- The model is evaluated with `MulticlassClassificationEvaluator` (accuracy). ✅

### 2️⃣ Clustering — Customer Segmentation 👥

Segments customers from a **credit card customer** dataset.

- Features (credit limit, number of cards, bank/online visits, calls) are assembled and scaled with `StandardScaler`.
- Customers are grouped into **Low / Medium / High** tiers based on their average credit limit.
- The distribution is visualized as a bar chart with Matplotlib. 📈

### 3️⃣ Association Rule Mining — FP-Growth 🛒

Discovers buying patterns in a **bakery transactions** dataset.

- Transactions are grouped into baskets per `TransactionNo`.
- `FPGrowth` mines frequent itemsets and generates association rules (with support, confidence, and lift).
- Frequent itemsets, rules, and predictions are exported to CSV files for further analysis. 💾

---

## 📂 Project Structure

```
.
├── big_data_mining.ipynb     # Main notebook (all three tasks)
└── data/                      # Input datasets (see below)
```

---

## 📑 Datasets

| Task | File |
|---|---|
| Classification | `cardekho_data_classification.csv` |
| Clustering | `credit_card_customer_data_clustering.csv` |
| Association Rule Mining | `bakery_arm.csv` |

> 💡 Update the file paths at the top of each section to point to your local dataset locations before running.

---

## ⚙️ Setup

```bash
pip install pyspark matplotlib pandas
```

Then open the notebook and run the cells:

```bash
jupyter notebook big_data_mining.ipynb
```

> ⚡ A `SparkSession` is created at the start of the notebook; each task can be run independently after it.

---

## 📝 License

This project was developed for educational purposes. Feel free to use and build on it. 🚀
