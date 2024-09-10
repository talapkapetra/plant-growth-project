# Agricultural Data Science Project I

## Table of Contents

- [Data Source](#data-source)
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Tools](#tools)
- [Data Preparation](#data-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Statistical Analysis](#statistical-analysis)
- [Results](#results)
- [Data Visualisation in Tableau](#data-visualisation-in-tableau)

## Data Source

I used "Plant Growth Data Classification" dataset for this project which is available on Kaggle.com

[plant_growth_data.csv]( https://talapkapetra.github.io/plant-growth-project/plant_growth_data.csv)

## Project Overview

The dataset contain factors of different conditions having effects on the growth of different plant tpyes (Plant types are not available in the data in case of this open data source). 

Each entity (row) corresponds to one plant kept in different condition, supplemented with numeric values (0 or 1), indicate whether its achieved the growth milestone in the investigation period or not.

## Objectives

My aim was to compare the different conditions, environment and management factors, in order to predict which are the most ideal to achieve growth milestone.
## Tools

Python, PyCharm: data cleaning, data preparation, exploratory data analysis, statistics
Tableau, Tableau Public: data visualisation

## Data Preparation

[plant_growth_project.ipynb](https://talapkapetra.github.io/plant-growth-project/plant_growth_project.ipynb)

 - I used the following methods to explore the dataset: head(), size, shape, info(), value_counts()
 - Remove duplicated values
 - I inserted two new columns for representing 'Water Frequency' and 'Fertilizer Type' categories in numeric values: Water_Frequency_Num, Fertilizer_Type_Num

## Exploratory Data Analysis

 **Descriptive statistics** 

![descr_stat](https://github.com/user-attachments/assets/8ed73df2-fd05-4ae0-aa85-6786e1a7297a)

**Identify Outliers**

I used Z-score method to discover outliers in the datasets. No outliers could be identified in Soil_Type, Sunlight_Hours, Water_Frequency, Fertilizer_Type, Temperature, Humidity, Growth_Milestone.

**Boxplots**

![Sunlgiht](https://github.com/user-attachments/assets/8b9d8a47-46f6-4858-ab68-da5418077758)

![Temperature](https://github.com/user-attachments/assets/52afd58b-04a6-41d3-8cfb-0cb0bf7de8cc)

![Humidity](https://github.com/user-attachments/assets/d9945c95-0440-4e78-92e6-83b389893f3b)

**Histograms**

![Histograms](https://github.com/user-attachments/assets/e6fb31fe-80c0-4a16-9d02-ce45f73a9431)

**Normality test**

Shapiro-Wilk normality test was used to investigate if the datasets are fit to the Gaussian distribution.

![stat_analysis02](https://github.com/user-attachments/assets/9c3ba6cc-b59a-40f3-9da4-59923a18c866)

1. value: t-stat of the test, 2. value: p-value

All of the datasets were non-normally distributed (p < 0.05)

## Statistical Analysis

### Correlations between the conditions in case of different soil types

 - At first I grouped the dataset according to the different soil types (loam, sandy, clay).
 - I made heatmaps for presenting the data.
 - I performed point-biserial correlations between the continuous attributes and the binary target variable (Growth Milestone)

**LOAM**

![LOAM](https://github.com/user-attachments/assets/d24ffbe2-a129-4f5b-b4ed-4d6ab1c05fbe)

```
Sunlight_Hours: correlation = -0.03, p-value = 0.79303
Temperature: correlation = -0.21, p-value = 0.10947
Humidity: correlation = -0.09, p-value = 0.49645
Water_Frequency_Num: correlation = 0.07, p-value = 0.58097
Fertilizer_Type_Num: correlation = 0.16, p-value = 0.21526
```

**SANDY**

![SANDY](https://github.com/user-attachments/assets/41996396-28f8-48d2-b3d3-c766b5aed2e2)

```
Sunlight_Hours: correlation = -0.04, p-value = 0.73610
Temperature: correlation = 0.09, p-value = 0.46363
Humidity: correlation = -0.16, p-value = 0.21601
Water_Frequency_Num: correlation = -0.03, p-value = 0.83842
Fertilizer_Type_Num: correlation = 0.30, p-value = 0.01513
```

**CLAY**

![CLAY](https://github.com/user-attachments/assets/f4a57cbb-0efe-4100-a2c4-fe0396ce016b)

```
Sunlight_Hours: correlation = -0.25, p-value = 0.03793
Temperature: correlation = -0.07, p-value = 0.58516
Humidity: correlation = -0.13, p-value = 0.30975
Water_Frequency_Num: correlation = -0.00, p-value = 0.98290
Fertilizer_Type_Num: correlation = 0.23, p-value = 0.06115
```

**Representative heatmap visulatisation to summarize the different conditions grouped by the soil types.**

![SUMMARY](https://github.com/user-attachments/assets/64e5fc67-18b0-4608-87ba-46aba703b9b8)

## Results

*Loam* soil type seems to be the most productive, since the less sunlight hours (6) and humidity level (57) needed to reach the growth milestone for plants cultivated in this type.

## Data Visualisation in Tableau

I created an interactive visualisation of the data in Tableau with three dashboards summarized in a story (plant_growth_project)

### Dashboard Snapshot I:  Introduction

![plant_growth_project_introduction](https://github.com/user-attachments/assets/890a6dfe-b3c2-4499-badc-49ca29113710)

### Dashboard Snapshot II: Descriptive Statistics

![descriptive_statistics_tableau](https://github.com/user-attachments/assets/b544fd5f-3a78-4929-ae85-f62cd7d599c1)

### Dashboard Snapshot III: Statistical Analysis

![statistical_analysis_tableau](https://github.com/user-attachments/assets/09146994-e7a0-480e-b45f-8775339f8be6)

[Tableau public reference](https://talapkapetra.github.io/plant-growth-project/plant_growth_project_tableau_public.html)












