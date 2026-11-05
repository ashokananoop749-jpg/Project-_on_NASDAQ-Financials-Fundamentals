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


Data Cleaning and Preprocessing
The dataset underwent rigorous cleaning and validation steps:
	Handling Missing Values: Identified missing values across financial metrics (revenues, long_term_debt, net_income) and applied groupwise median imputation by ticker, followed by KNN imputation (n_neighbors=5) for remaining numeric features.
	Removing Duplicate Records: Checked for exact duplicate rows (df.duplicated().sum()) and dropped redundant entries while maintaining the primary time-series index.
	Correcting Data Types: Standardized date columns to datetime objects and cast financial metrics to float64.
	Outlier Handling (IQR Method): Calculated Interquartile Ranges (IQR=Q3-Q1) and established bounds [Q1-1.5×IQR,Q3+1.5×IQR] to identify and analyze extreme financial outliers (e.g., hyper-growth firms and distressed cash burners).
	Checking Invalid Values: Scanned for negative revenues, zero division anomalies, and infinite values (np.inf), cleaning and replacing them appropriately.
	Categorical Standardization: Stripped whitespace and standardized text and sector names (e.g., unifying "Tech" and "Information Technology").


Exploratory Data Analysis (EDA)
EDA focused on evaluating data distributions, summary statistics, and structural relationships across fundamental metrics. Summary statistics confirmed that median company revenue hovers within predictable operating bands, while net income and operating cash flows exhibit long right-tail distributions driven by megacap technology firms


Data Visualization
Chart 1: comparison of Top &Bottom 10 Companies to identify the most profitable and loss making companies with Horizonal Bar Chart in one window
Interpretation: Microsoft (MSFT) leads the NASDAQ exchange with $133.75 billion in net income, closely followed by Alphabet (GOOGL at $132.17B), NVIDIA (NVDA at $120.07B), and Apple (AAPL at $112.01B). Big tech dominates the top tier, generating over $100 billion each.
Highlights distressed outliers experiencing negative net income, led by heavy capital expenditure or operational losses (such as Hooker Furnishings at extreme negative earnings), emphasizing the dichotomy between growth-stage cash burners and mature market leaders

Free Cash Flow Margin (FCF / Revenue) Ranking(Horizontal Bar Chart
Photronics (PLAB) achieves the highest cash efficiency, converting 41.8% of revenue into free cash flow. A wide spread exists between efficient cash generators and cash-burning retailers/furnishing firms.

Distribution of Free Cash Flow Across Sectors/Filings (Hist Plot)
Interpretation: The distribution is heavily skewed toward zero. The vast majority of companies experiencing negative cash flow cluster tightly between $0$ and $2 billion, indicating that most "burning" firms operate with relatively low cash burn magnitude. A long, thin tail stretches out toward $25billion for heavily capital-intensive or distressed outliers.
 The distribution of profitable companies is similarly front-loaded near zero (peaking around the $0to $3billion. The curve drops off steeply, showing that companies generating massive positive free cash flow (stretching past $10 to $40 billion are rare outliers.

The frequency distribution heavily mirrors reporting cycles. Quarterly filings (10-Q, shown in blue) vastly outnumber annual reports (10-K, shown in orange) by roughly a $4to$1 ratio, which aligns with companies filing three quarters and one annual report per fiscal year.
Across both filing types, the bulk of financial data points compress intensely within the $2 billionto $3billion band, demonstrating that median company-level cash flows in the dataset hover very close to breakeven

Correlation Heatmap of NASDAQ Fundamentals
Interpretation: Operating cash flow and net income exhibit a very strong positive correlation (0.89), demonstrating that earnings reliably translate to operating cash inflows. Total assets and revenues show robust scaling correlation (0.62).

Financial Leverage (Debt-to-Assets) by Form Type with Box Plot
 Interpretation: Median leverage remains conservative (under 25%) across both 10-Q and 10-K filings. 10-Q quarterly reports exhibit slightly broader interquartile spreads and higher upper whiskers prior to year-end audit adjustments.

 Key Findings and Insights
	Megacap Profit Concentration: The top 4 tech companies account for an outsized share of total net income on the NASDAQ exchange.
	Cash Flow Alignment: Net income correlates strongly with operating cash flow (0.89) and free cash flow (0.79).
	 Sector Divergence: While asset-heavy industrial firms rely more heavily on long-term debt financing, asset-light tech firms maintain high FCF conversion efficiency.

Recommendations
●	For Investors: Prioritize companies with robust Free Cash Flow margins (such as PLAB and LULU) over top-line revenue growth alone.
●	 For Risk Managers: Monitor companies exhibiting extreme negative cash flow margins and elevated debt-to-asset ratios during quarterly 10-Q filings.


Conclusion
This project executed a data cleaning, imputation, and exploratory analysis pipeline across 22,785 NASDAQ corporate records spanning 2024 to 2026. By addressing data quality challenges—including missingness rates reaching 58.5% across balance sheet fields—through structured accounting rules, domain-based medians, and K-Nearest Neighbors imputation, a complete dataset was established without synthetic skewing. The resulting analysis highlights structural market dynamics on the NASDAQ exchange, contrasting the operating efficiency of established large-cap leaders with the cash deployment patterns of early-stage growth firms


Limitations and Future Scope
●	Constrained Time Horizon: The analyzed dataset spans a 32-month period (January 2024 – August 2026), limiting long-term historical cyclical evaluation across broader market environments.
●	Exogenous Macro Factors: Macroeconomic indicators—such as Federal Reserve benchmark interest rates, prevailing inflation metrics, and foreign exchange currency fluctuations—were not included in this dataset.
●	Future Scope: Future work can incorporate macroeconomic interest rate indicators, daily stock price volatility, and machine learning models to predict financial distress ahead of quarterly earnings releases.



References
●	NASDAQ Financials & Fundamentals (2024–2026) Dataset by Abdurrahman Hakan Acar on Kaggle
●	Pandas Software Library Documentation: https://pandas.pydata.org/docs/
●	NumPy Mathematical Library Reference: https://numpy.org/doc/
●	Scikit-Learn Machine Learning Architecture Guides: https://scikit-learn.org/stable/documentation.html



