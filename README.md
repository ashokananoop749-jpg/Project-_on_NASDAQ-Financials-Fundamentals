# Project_on_NASDAQ-Financials-Fundamentals
To analyze the financial performance and fundamentals of NASDAQ-listed companies from 2024 to 2026 using financial statement data,and identify trends,patterns,and key factors affecting company performance.

Data set Information

Source : Kaggle

Total Rows: 22,785

Total Columns: 28

Date Range: January 2024 to August 2026

Abstract:This project presents an exhaustive financial and fundamental analysis of NASDAQ-listed companies covering the period from January 2024 to August 2026. Utilizing a dataset of 22,785 financial statement observations across 28 attributes sourced from Kaggle, the project establishes a rigorous data pipeline encompassing missing value treatment via KNN imputation, exact duplicate removal, outlier handling using the Interquartile Range (IQR) method, and categorization standardization. Exploratory Data Analysis (EDA) and advanced visualizations examine profitability, free cash flow (FCF) efficiency, asset scaling, and financial leverage (long-term debt to assets). Key findings reveal that the top four tech giants—Microsoft, Alphabet, NVIDIA, and Apple—each generated over $100 billion in net income, while cash burn among distressed outliers reached severe magnitudes. Practical recommendations are provided to aid investors and financial analysts in risk screening and capital allocation.

Introduction:The NASDAQ stock exchange is home to many of the world's most innovative and high-growth technology and consumer discretionary companies. Understanding the underlying financial health, capital structure, and cash flow dynamics of these corporations is critical for institutional investors, analysts, and stakeholders. This project explores NASDAQ financial statement data spanning 2024 through 2026, combining Python-based data transformation pipelines with advanced visualizations to uncover structural performance trends.

Problem Statement:Raw corporate financial databases generated from SEC filings exhibit data quality challenges that impede reliable quantitative modeling:

●	High Missingness Rates: Inconsistent field requirements across industry sectors produce elevated missing data rates, exceeding 50% for attributes such as Long-Term Debt and Gross Profit.

●	Categorical Non-Standardization: Entity names, industry tags, and fiscal period definitions lack uniform formatting across reporting entities.

●	Extreme Scale Dispersion: Equity markets contain significant scale variations, where small-cap micro-entities and mega-cap conglomerates inhabit the same feature space. Standard outlier removal risks stripping critical market dynamics.

●	Derived Inconsistencies: Direct computation of financial ratios (e.g., Margins, Returns) fails when underlying primary balances contain nulls, zeroes, or structural zeros.

Analyzing uncleaned financial data leads to biased parametric estimates and faulty corporate valuations. This project implements a standardized preprocessing and analytics framework to yield an model-ready financial database.

Project Objectives:
 Automate data cleaning and imputation pipelines for multi-period financial statements.
 Identify top-performing profitable companies and distressed cash-burning outliers.
 Quantify the statistical relationships between revenues, net income, operating cash flow, and total assets.
 Evaluate financial leverage differences between quarterly and annual reporting filings.
 Provide actionable financial recommendations based on empirical metrics.

 Tools and Technologies Used:	Development Environment: Google Colab
	
  Data Manipulation & Analysis: pandas , numpy
  
  Missing Value Imputation: scikit-learn (KNNImputer, IterativeImputer)

  Data Visualization: matplotlib , seaborn , plotly 





