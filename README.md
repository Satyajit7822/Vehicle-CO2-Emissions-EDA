# 🚗 Vehicle CO₂ Emissions — Exploratory Data Analysis

## 📌 Project Overview

This project performs a complete **Exploratory Data Analysis (EDA)** on vehicle specifications, fuel consumption, fuel types, and CO₂ emissions using Python.

The objective is to explore patterns, relationships, distributions, and outliers in vehicle data and identify important factors associated with CO₂ emissions.

The analysis covers dataset exploration, data quality checks, categorical analysis, numerical distributions, correlation analysis, fuel economy analysis, manufacturer comparisons, and vehicle-level emission analysis.

---

## 🎯 Objectives

The main objectives of this project are:

- Understand the structure of the vehicle dataset
- Analyze the number of rows and columns
- Examine column names and data types
- Perform data quality checks
- Identify missing values and duplicate records
- Analyze categorical variables
- Study numerical variable distributions
- Detect potential outliers using box plots and IQR
- Analyze relationships between vehicle specifications and CO₂ emissions
- Compare CO₂ emissions across fuel types
- Compare CO₂ emissions across vehicle classes
- Analyze manufacturer-level emission patterns
- Study fuel consumption and fuel economy
- Analyze the relationship between engine size, cylinders, MPG, and CO₂ emissions
- Examine model-year emission trends
- Generate meaningful data-driven insights

---

## 🛠️ Tools & Technologies

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook**

---

## 📂 Dataset

The project uses a vehicle fuel-consumption dataset containing information about vehicle specifications, fuel consumption, and CO₂ emissions.

### Major Features

| Feature | Description |
|---|---|
| `MAKE` | Vehicle manufacturer |
| `MODEL` | Vehicle model |
| `VEHICLECLASS` | Vehicle class/category |
| `ENGINESIZE` | Engine size in litres |
| `CYLINDERS` | Number of engine cylinders |
| `TRANSMISSION` | Transmission type |
| `FUELTYPE` | Fuel type |
| `FUELCONSUMPTION_CITY` | City fuel consumption |
| `FUELCONSUMPTION_HWY` | Highway fuel consumption |
| `FUELCONSUMPTION_COMB` | Combined fuel consumption |
| `FUELCONSUMPTION_COMB_MPG` | Combined fuel economy in MPG |
| `CO2EMISSIONS` | CO₂ emissions in g/km |
| `MODELYEAR` | Vehicle model year |

---

## 🔍 EDA Workflow

The project follows a structured Exploratory Data Analysis workflow.

### 1. Dataset Overview

The dataset is initially examined using:

- Number of rows
- Number of columns
- Column names
- Data types
- Descriptive statistics

Functions used include:

```python
df.shape
df.columns
df.info()
df.describe()
```

---

### 2. Data Quality Check

The dataset is checked for:

- Missing values
- Duplicate records
- Data consistency

Functions used include:

```python
df.isnull().sum()
df.duplicated().sum()
```

---

### 3. Categorical Analysis

Categorical variables are analyzed to understand their frequency and distribution.

The analysis includes:

- Manufacturer
- Fuel type
- Vehicle class
- Transmission type

---

### 4. Manufacturer Analysis

The project analyzes the most frequently represented vehicle manufacturers.

A bar chart is used to visualize the top manufacturers by number of vehicles.

**Insight:**

- The dataset contains many manufacturers with uneven representation.
- Manufacturers with fewer observations should be interpreted cautiously.

---

### 5. Fuel Type Analysis

The distribution of vehicles across different fuel types is analyzed.

**Insight:**

- Fuel types are not equally represented.
- Less common fuel types have smaller sample sizes.
- Comparisons between fuel types should consider the number of observations.

---

### 6. Vehicle Class Analysis

Vehicle classes are analyzed to understand their representation within the dataset.

**Insight:**

- Mid-size, compact, and small SUV categories are strongly represented.
- Vehicle classes have different numbers of observations.
- Vehicle class provides useful context when analyzing fuel consumption and emissions.

---

### 7. Transmission Analysis

Transmission types are analyzed using a frequency-based visualization.

**Insight:**

- Automatic and manual transmission categories make up most observations.
- Other transmission types are less common.
- Transmission can be compared with fuel consumption and CO₂ emissions.

---

### 8. Engine Size Distribution

The distribution of engine sizes is analyzed using a histogram.

**Insight:**

- Most vehicles have engine sizes concentrated around approximately **2L–4L**.
- Very large engines are relatively uncommon.
- The distribution has a tail toward larger engine sizes.

---

### 9. Cylinder Count Distribution

The number of vehicles is analyzed by cylinder count.

**Insight:**

- **4-cylinder vehicles** are the most common.
- **6-cylinder vehicles** are the second most common.
- 8-cylinder vehicles are also significantly represented.
- 3, 5, 10, and 12-cylinder vehicles are comparatively uncommon.

**Important Point:** The dataset is mainly concentrated around **4, 6, and 8-cylinder vehicles**.

---

### 10. City Fuel Consumption Distribution

City fuel consumption is analyzed using a histogram.

**Insight:**

- Most vehicles have city fuel consumption around **8–15 L/100 km**.
- The highest concentration is around **10–13 L/100 km**.
- Very high city fuel consumption is less common.
- The distribution is right-skewed.

---

### 11. Highway Fuel Consumption Distribution

Highway fuel consumption is analyzed using a histogram.

**Insight:**

- Most vehicles have highway fuel consumption around **6–12 L/100 km**.
- The highest concentration is approximately **7–10 L/100 km**.
- Values above 15 L/100 km are relatively uncommon.
- The distribution is right-skewed.

**Important Point:** Highway fuel consumption is generally lower than city fuel consumption.

---

### 12. Combined Fuel Consumption Distribution

Combined fuel consumption is analyzed using a histogram.

**Insight:**

- Most vehicles have combined fuel consumption between approximately **7 and 13 L/100 km**.
- The highest concentration is around **9–11 L/100 km**.
- Very high combined consumption is relatively uncommon.
- The distribution is right-skewed.

---

### 13. Combined Fuel Consumption — Box Plot

A box plot is used to examine the central distribution and potential outliers.

**Insight:**

- The median combined fuel consumption is around **11 L/100 km**.
- Most observations fall within the central interquartile range.
- Several high-value observations appear beyond the upper whisker.
- These observations represent vehicles with unusually high fuel consumption.

---

### 14. Combined MPG — Box Plot

Combined MPG is analyzed using a box plot.

**Insight:**

- MPG provides an inverse view of fuel consumption.
- Higher MPG generally indicates better fuel economy.
- The box plot helps identify the central range and extreme fuel-economy observations.

**Important Point:** Higher MPG generally represents better fuel efficiency.

---

### 15. CO₂ Emissions Distribution

The distribution of CO₂ emissions is analyzed using a histogram.

The project also calculates:

- Mean CO₂ emissions
- Median CO₂ emissions

**Insight:**

- CO₂ emissions vary substantially across vehicles.
- Mean and median describe the typical emission level.
- Higher-emission vehicles occupy the upper end of the distribution.

---

### 16. CO₂ Emissions — Box Plot and Outliers

A box plot and IQR method are used to identify potential CO₂ emission outliers.

The IQR method calculates:

```text
Q1 = First Quartile
Q3 = Third Quartile
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

**Insight:**

- The box plot identifies the central emission range and extreme observations.
- IQR-based analysis provides a systematic method for identifying unusually low or high CO₂ values.
- Outliers should be investigated rather than automatically removed.

**Important Point:** An outlier may represent a genuine unusual vehicle rather than a data error.

---

## 📈 Bivariate Analysis

### 17. Combined MPG vs CO₂ Emissions

The relationship between combined MPG and CO₂ emissions is analyzed using a scatter plot.

**Insight:**

- CO₂ emissions generally **decrease as combined MPG increases**.
- Vehicles with lower fuel economy tend to have higher CO₂ emissions.
- The relationship is strongly negative.

**Important Point:** Better fuel economy is generally associated with lower CO₂ emissions.

---

### 18. Engine Size vs CO₂ Emissions

The relationship between engine size and CO₂ emissions is analyzed.

**Insight:**

- CO₂ emissions generally increase as engine size increases.
- Smaller engines tend to have lower emission values.
- Larger engines generally show higher emission levels.

**Important Point:** Engine size has a strong positive association with CO₂ emissions.

---

### 19. Cylinders vs CO₂ Emissions

The relationship between cylinder count and CO₂ emissions is analyzed.

**Insight:**

- CO₂ emissions generally increase with the number of cylinders.
- 4- and 6-cylinder vehicles are common and cover a wide emission range.
- Vehicles with 8 or more cylinders generally show higher emission levels.

**Important Point:** Cylinder count has a positive association with CO₂ emissions.

---

### 20. City vs Highway Fuel Consumption

The relationship between city and highway fuel consumption is analyzed.

**Insight:**

- Vehicles with high city fuel consumption generally also have high highway fuel consumption.
- The two fuel-consumption measures have a strong positive relationship.
- Highway consumption is generally lower than city consumption.

**Important Point:** City and highway fuel consumption are strongly related.

---

## ⛽ Category-Based CO₂ Analysis

### 21. Fuel Type vs CO₂ Emissions

CO₂ emissions are compared across different fuel types using:

- Count
- Mean
- Median
- Box plots

**Insight:**

- Average CO₂ emissions differ across fuel types.
- The number of observations is unequal across fuel categories.
- The box plot shows variation within each fuel type.

**Important Point:** Fuel type is associated with different emission patterns, but sample size should be considered.

---

### 22. Vehicle Class vs CO₂ Emissions

Average CO₂ emissions are compared across vehicle classes.

**Insight:**

- CO₂ emissions vary considerably between vehicle classes.
- Larger/heavier vehicle categories can show higher average emissions.
- Smaller passenger-oriented categories generally show lower average emissions.

**Important Point:** Vehicle class captures differences in vehicle size and use that can help explain emission differences.

---

### 23. Transmission vs CO₂ Emissions

Average CO₂ emissions are compared across transmission categories.

**Insight:**

- Average emissions differ across transmission categories.
- Transmission should be interpreted together with engine size, cylinders, vehicle class, and fuel type.
- Some transmission categories have fewer observations.

**Important Point:** Transmission may be associated with emissions, but it should not be interpreted in isolation.

---

### 24. Manufacturer vs Average CO₂ Emissions

Average CO₂ emissions are analyzed by manufacturer.

The analysis includes:

- Number of observations
- Mean CO₂ emissions
- Median CO₂ emissions

**Insight:**

- Average CO₂ emissions vary across manufacturers.
- Manufacturer differences can reflect differences in vehicle classes, engine sizes, and powertrains.
- Manufacturers with very few observations should be interpreted cautiously.

**Important Point:** Manufacturer-level comparisons should be considered alongside vehicle characteristics.

---

## 🔗 Correlation Analysis

### 25. Correlation Analysis

A correlation matrix is generated for numerical variables to understand relationships between features.

The analysis focuses particularly on:

- Engine size
- Cylinders
- City fuel consumption
- Highway fuel consumption
- Combined fuel consumption
- Combined MPG
- CO₂ emissions

**Key Findings:**

- Engine size, cylinder count, and fuel-consumption measures show strong positive relationships with CO₂ emissions.
- Combined MPG has a strong negative relationship with CO₂ emissions.
- Fuel-consumption variables are strongly related to one another.

**Important Point:** Fuel consumption, engine size, cylinders, and MPG are key numerical variables for understanding CO₂ emissions.

---

## 📦 Outlier Analysis

### 26. IQR Outlier Analysis for Numerical Variables

The Interquartile Range (IQR) method is applied to numerical variables.

For each numerical variable, the analysis calculates:

- Q1
- Q3
- IQR
- Lower Bound
- Upper Bound
- Outlier Count

**Insight:**

- Outlier counts vary across numerical variables.
- Fuel-consumption and emissions variables can contain high-end observations.
- Outliers should be investigated before deciding whether they represent errors.

**Important Point:** Outlier detection is part of EDA; removal should always have a clear justification.

---

## 🚘 Vehicle-Level Analysis

### 27. Highest and Lowest Emitting Vehicles

The project identifies the highest and lowest CO₂-emitting vehicles.

The analysis considers:

- Manufacturer
- Model
- Vehicle class
- Engine size
- Cylinders
- Fuel type
- Combined fuel consumption
- Combined MPG
- CO₂ emissions

**Insight:**

- High-emission vehicles can be examined for characteristics such as larger engines, more cylinders, and higher fuel consumption.
- Low-emission vehicles can be examined for smaller engines and better fuel economy.

**Important Point:** Extreme individual records help explain the upper and lower ends of CO₂ emissions.

---

## 📅 Model Year Analysis

### 28. Model Year vs CO₂ Emissions

Average and median CO₂ emissions are analyzed across model years.

**Insight:**

- Model year allows examination of how average emissions vary across the years represented in the dataset.
- Year-to-year differences should be interpreted alongside changes in vehicle mix and technology.
- This is a descriptive trend and does not prove that model year alone causes changes.

**Important Point:** Model year can reveal emission trends, but vehicle composition also matters.

---

## ⛽ Fuel Consumption by Fuel Type

### 29. Average Combined Fuel Consumption by Fuel Type

Average combined fuel consumption is compared across fuel types using:

- Count
- Mean
- Median
- Bar chart

**Insight:**

- Combined fuel consumption varies between fuel types.
- Mean and median help identify typical consumption and the influence of extreme values.
- Unequal sample sizes should be considered.

**Important Point:** Fuel type is useful for segmenting fuel-consumption behavior.

---

## 🔬 Engine Size Group Analysis

### 30. Engine Size Groups vs CO₂ Emissions

Engine size is grouped into the following categories:

```text
<=2L
2-3L
3-4L
4-5L
>5L
```

Average CO₂ emissions are then compared between these groups.

**Insight:**

- Average CO₂ emissions generally rise as engine-size groups increase.
- Grouping a continuous variable makes the pattern easier to communicate.

**Important Point:** Engine-size grouping provides a business-friendly view of the engine/emission relationship.

---

# 📊 Final EDA Findings

The main findings from the analysis are:

1. The dataset contains many manufacturers and vehicle classes with uneven representation.
2. Most vehicles have engine sizes around **2L–4L**.
3. **4- and 6-cylinder vehicles** are the most common groups.
4. City fuel consumption is generally higher than highway fuel consumption.
5. Most combined fuel consumption values fall around **7–13 L/100 km**.
6. Higher combined MPG is strongly associated with lower CO₂ emissions.
7. Larger engines generally correspond to higher CO₂ emissions.
8. Vehicles with more cylinders generally show higher CO₂ emissions.
9. CO₂ emissions differ across vehicle classes and fuel types.
10. Several high-consumption and high-emission observations can be identified as potential outliers.
11. Fuel consumption, engine size, cylinders, and MPG show strong relationships with CO₂ emissions.

### ⭐ Important Overall Insight

> **Higher fuel consumption and larger engine-related specifications are associated with higher CO₂ emissions, while higher MPG is associated with lower emissions.**

---

## 📁 Project Structure

```text
Vehicle-CO2-Emissions-EDA/
│
├── Vehicle_CO2_Emissions_EDA.ipynb
├── FuelConsumption.csv
├── README.md
└── requirements.txt
```

---

## 🚀 How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Vehicle-CO2-Emissions-EDA.git
```

### 2. Open the Project Folder

```bash
cd Vehicle-CO2-Emissions-EDA
```

### 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

Or install all dependencies using:

```bash
pip install -r requirements.txt
```

### 4. Open Jupyter Notebook

```bash
jupyter notebook
```

Then open:

```text
Vehicle_CO2_Emissions_EDA.ipynb
```

Run the notebook cells sequentially to reproduce the analysis.

---

## 📦 Requirements

```text
pandas
numpy
matplotlib
seaborn
jupyter
```

---

## 📌 Project Purpose

This project was created as a practical **Data Analytics and Python EDA project** to develop hands-on experience in:

- Data exploration
- Data cleaning
- Statistical analysis
- Data visualization
- Correlation analysis
- Outlier detection
- Feature analysis
- Insight generation

The project demonstrates how Python can be used to transform a raw dataset into meaningful analytical insights.

---

## ⚠️ Disclaimer

This project is intended for **educational and data-analysis purposes only**.

The relationships identified in this exploratory analysis are descriptive and should not automatically be interpreted as causal relationships.

---

## 👨‍💻 Author

**Satyajit Pradhan**

**Aspiring Data Analyst**

### Skills

`SQL` • `Excel` • `Power BI` • `Python` • `Pandas` • `NumPy` • `Matplotlib` • `Seaborn` • `Data Visualization`

---

## 🔗 Connect With Me

- **GitHub:** https://github.com/YOUR_USERNAME
- **LinkedIn:** Add your LinkedIn profile URL

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.
