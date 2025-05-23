# 561_FinalProject

This project aims to predict whether a flight will be delayed using historical flight and weather data. We use machine learning techniques to classify flights as on-time or delayed (if arrival delay is ≥ 15 minutes), incorporating temporal, operational, and weather-related features.

Datasets Used
--------------------
Flight Data (BTS)
Source: Bureau of Transportation Statistics (1987–present)
Filtered: April data from 1998 to 2002
Records: 2.2+ million
Features: Scheduled and actual times, airport codes, delays, cancellation status, etc.

Weather Data (NOAA)
Source: National Oceanic and Atmospheric Administration
Mapped to airports using ISD history dataset
Records: 79,000 (daily summaries)
Features: Temperature, visibility, precipitation, wind gust, etc.

Final dataset uploaded:
https://drive.google.com/drive/folders/1TMAxjkM6HJXUq2FgLpeZ49Qzu1p3LZfK?usp=drive_link

Preprocessing Steps:
--------------------
Dropped irrelevant and leaky columns (e.g., actual arrival time, wheels-off)
Handled missing values (dropped features with >30% missing)
Outlier detection using IQR method (outliers retained if realistic)
Features added: Binary weather indicators from FRSHTT
Categorical WEATHER_CONDITION
Encoding: Ordinal encoding for categorical columns (e.g., ORIGIN, CARRIER)
Scaling: StandardScaler applied to numeric features (for linear models only)

We trained and evaluated multiple classifiers, including:
------------------
Logistic Regression, Decision Trees, XGBoost, Naive Bayes, Random Forest
Amongst all the models, XGBoost gave the best performance

