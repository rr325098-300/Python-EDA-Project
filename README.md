# Python-EDA-Project

Exploratory Data Analysis (EDA) project using Python and pandas to analyze global population data. Includes data cleaning, grouping, correlation analysis, and visualizations across continents and years.
# 🌍 World Population EDA (Python Project)

## 📊 Dataset Description

The dataset contains **234 countries/territories** with the following features:

### 🌐 Country Information

* Country/Territory
* Capital
* Continent
* CCA3 (Country Code)

### 📈 Population Data

* 1970 Population
* 1980 Population
* 1990 Population
* 2000 Population
* 2010 Population
* 2015 Population
* 2020 Population
* 2022 Population

### 📌 Additional Features

* Area (km²)
* Density (per km²)
* Growth Rate
* World Population Percentage
* Rank

---

## ⚙️ Tech Stack

* Python 🐍
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## 🧹 Data Cleaning & Preparation

* ✔️ No missing values found
* ✔️ Checked uniqueness of data
* ✔️ Verified data types using `.info()`

---<img width="1763" height="844" alt="Screenshot_2-5-2026_04321_localhost" src="https://github.com/user-attachments/assets/1a6fd635-5edb-4f86-9c1e-2c2337c72fb6" />

## 📈 Exploratory Data Analysis

### 📊 Descriptive Statistics

* Used `.describe()` to summarize data
* Observed large variation in population values across countries

---

### 🌎 Population Trends by Continent

```python
df.groupby('Continent').mean(numeric_only=True)
```

📌 **Insights:**

* Asia has the highest population across all years
* Africa shows rapid population growth
* Europe remains relatively stable

---

### 📉 Boxplot Analysis

```python
df.boxplot()
```

📌 **Insights:**

* Strong presence of outliers in population columns
* Smaller spread in growth rate and density

---

### 🔥 Correlation Heatmap

```python
sns.heatmap(df.corr(numeric_only=True), annot=True)
```

📌 **Insights:**

* Very high correlation between population across years (~0.97–1.00)
* Area moderately correlates with population
* Growth rate and density have weak correlation

---

### 🏆 Top 5 Most Populated Countries (2022)

```python
df.sort_values(by="2022 Population", ascending=False).head(5)
```

1. China 🇨🇳
2. India 🇮🇳
3. United States 🇺🇸
4. Indonesia 🇮🇩
5. Pakistan 🇵🇰

---

### 🔍 Filtering Example

```python
df[df['Continent'].str.contains('Asia')]
```

---

## 📌 Key Insights

* 🌏 Asia dominates global population
* 📈 Africa has the fastest growth
* 📉 Europe shows slower growth
* 🔗 Population data across years is highly correlated
* ⚖️ Data is skewed due to very large countries
