# 🎮 MLBB Hero Meta & Performance Analysis

> An exploratory data analysis project to understand hero performance, popularity, ban priority, and meta trends in Mobile Legends: Bang Bang (MLBB).

---

## 📌 Project Overview

This project analyzes MLBB hero ranking data to understand how different performance metrics relate to each other.

Instead of looking only at hero rankings, the analysis explores questions such as:

- Which heroes have the highest and lowest win rates?
- Which heroes are the most popular?
- Does popularity translate into better performance?
- Which heroes have high win rates but low pick rates?
- Which heroes are popular but underperforming?
- How strongly are Pick Rate, Win Rate, and Ban Rate related?
- Which heroes have the highest overall Meta Score?

The project follows a complete data analytics workflow:

**Data Understanding → Data Cleaning → Exploratory Data Analysis → Performance Analysis → Correlation Analysis → Meta Analysis**

---

## 🎯 Objectives

The main objectives of this project are:

1. Understand the structure and quality of the MLBB hero dataset.
2. Analyze hero performance using Win Rate.
3. Analyze hero popularity using Pick Rate.
4. Analyze draft priority using Ban Rate.
5. Identify relationships between popularity and performance.
6. Identify potential "Hidden Gem" heroes.
7. Identify popular but underperforming heroes.
8. Study correlations between numerical performance metrics.
9. Create a composite Meta Score for comparing heroes.

---

## 📊 Dataset

The dataset contains **133 MLBB heroes** and 7 variables. :contentReference[oaicite:1]{index=1}

| Column | Description |
|---|---|
| `Rank` | Current ranking position of the hero |
| `Hero` | Name of the MLBB hero |
| `Pick Rate (%)` | Percentage representing how frequently the hero is picked |
| `Win Rate (%)` | Percentage representing the hero's win rate |
| `Ban Rate (%)` | Percentage representing how frequently the hero is banned |
| `Scraped_At` | Timestamp when the data was collected |
| `META Score` | Existing meta-performance score in the dataset |

The dataset contains no missing values in these seven columns, and the numerical metrics are stored as numeric data types. :contentReference[oaicite:2]{index=2}

---

## 🛠️ Technologies Used

- **Python**
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical operations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **Scikit-learn** – Min-Max scaling
- **Google Colab / Jupyter Notebook**

---

## 🔍 Analysis Performed

### 1. Dataset Exploration

The first stage focuses on understanding the dataset:

- Dataset dimensions
- Column names
- Data types
- Missing values
- Duplicate records
- Unique values
- Descriptive statistics

The dataset contains 133 records and 7 columns. :contentReference[oaicite:3]{index=3}

---

### 2. Win Rate Analysis

Heroes are ranked based on their Win Rate to identify:

- Top-performing heroes
- Lowest-performing heroes
- Overall Win Rate distribution

A bar chart is used to visualize the Top 10 heroes by Win Rate.

---

### 3. Popularity vs Performance

A scatter plot is used to compare:

**Pick Rate vs Win Rate**

with:

- X-axis → Pick Rate
- Y-axis → Win Rate
- Bubble size → Ban Rate

This helps investigate whether frequently picked heroes are necessarily more successful.

---

### 4. Hero Performance Classification

Heroes are divided into four categories using the median Pick Rate and Win Rate as benchmarks:

| Category | Meaning |
|---|---|
| 🔥 Popular & Strong | High Pick Rate + High Win Rate |
| ⚠️ Popular but Weak | High Pick Rate + Low Win Rate |
| 💎 Hidden Gem | Low Pick Rate + High Win Rate |
| 💤 Low Priority | Low Pick Rate + Low Win Rate |

This classification helps identify heroes that may be overlooked despite having strong performance.

---

### 5. Hidden Gem Analysis 💎

A Hidden Gem is defined as a hero with:

**Below-median Pick Rate + Above/equal-to-median Win Rate**

These heroes are particularly interesting because they perform well despite not being highly popular.

---

### 6. Correlation Analysis

Correlation analysis is used to investigate relationships between numerical variables.

The analysis examines relationships involving:

- Pick Rate
- Win Rate
- Ban Rate
- Rank
- Meta Score

A correlation heatmap is used to visualize these relationships.

> Note: Correlation indicates association between variables and does not necessarily imply causation.

---

### 7. Meta Score

A composite Meta Score is created using normalized:

- Win Rate
- Pick Rate
- Ban Rate

The score gives the highest weight to Win Rate:

```text
Meta Score =
0.50 × Win Score
+ 0.30 × Pick Score
+ 0.20 × Ban Score
