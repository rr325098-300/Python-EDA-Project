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

---<img width="1763" height="844" alt="Screenshot_2-5-2026_201949_localhost" src="https://github.com/user-attachments/assets/f64f3d59-9987-4e2a-9cc2-c797900b8d32" />


## 📈 Exploratory Data Analysis

### 📊 Descriptive Statistics

* Used `.describe()` to summarize data
* Observed large variation in population values across countries

---<img width="1763" height="844" alt="Screenshot_2-5-2026_202012_localhost" src="https://github.com/user-attachments/assets/5cd114ef-c9fe-47bb-8ec7-0f90b58b6404" />
<img width="1763" height="844" alt="Screenshot_2-5-2026_202031_localhost" src="https://github.com/user-attachments/assets/fff6b580-6be8-4695-8e4c-c1601b6c45e6" />


### 🌎 Population Trends by Continent

```python
df.groupby('Continent').mean(numeric_only=True)
```
<img width="1763" height="844" alt="Screenshot_2-5-2026_20227_localhost" src="https://github.com/user-attachments/assets/f355cd44-dcbb-4f4f-b559-d12e9f2d07ca" />

📌 **Insights:**

* Asia has the highest population across all years
* Africa shows rapid population growth
* Europe remains relatively stable

---<img width="1763" height="844" alt="Screenshot_2-5-2026_202049_localhost" src="https://github.com/user-attachments/assets/645028bf-7964-4d19-ab82-ff5026f7b691" />


### 📉 Boxplot Analysis
<img width="1763" height="844" alt="Screenshot_2-5-2026_202226_localhost" src="https://github.com/user-attachments/assets/eb1ca236-939c-4baf-b0b9-372cd115e2cd" />

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
<img width="1763" height="844" alt="Screenshot_2-5-2026_20217_localhost" src="https://github.com/user-attachments/assets/a3b0abe5-cc90-47d8-8985-a1789921099a" />

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
<img width="1763" height="844" alt="Screenshot_2-5-2026_202123_localhost" src="https://github.com/user-attachments/assets/741f3def-7438-4835-a478-a5089f06ead4" />

```python
df[df['Continent'].str.contains('Asia')]
```
<img width="1763" height="844" alt="Screenshot_2-5-2026_202150_localhost" src="https://github.com/user-attachments/assets/97e591fe-2efe-48c9-b2a7-06eb7c22c0f7" />

---

## 📌 Key Insights

* 🌏 Asia dominates global population
* 📈 Africa has the fastest growth
* 📉 Europe shows slower growth
* 🔗 Population data across years is highly correlated
* ⚖️ Data is skewed due to very large countries
