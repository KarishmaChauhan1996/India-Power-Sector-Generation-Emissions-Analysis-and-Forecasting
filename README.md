# India-Power-Sector-Generation-Emissions-Analysis-and-Forecasting

## Project Overview
This project presents a comprehensive data analysis and time series forecasting of electricity generation and power sector emissions in India at both national and state levels. The analysis spans historical monthly data and aims to uncover trends, quantify emission contributions by energy sources, and forecast future emissions using statistical models.

In addition to the analytical modeling in Python, the project features a dynamic Power BI dashboard to visualize key metrics and enable interactive exploration by stakeholders and policymakers.

## Objectives

- Perform exploratory data analysis (EDA) on India's electricity generation and emissions by fuel source and state.
- Understand trends, seasonality, and regional patterns in emissions and generation.
- Build and evaluate time series forecasting models to predict future emissions.
- Develop an interactive Power BI dashboard for visualization and stakeholder reporting.

## Data Overview

- Monthly electricity generation and emissions data for Indian states from Jan 2019 to Dec 2023.
- Data includes:
         - Generation (GWh): Source-wise monthly electricity generation.
         - Emissions (ktCO₂): Source-wise monthly carbon emissions.
         - Emission Intensity (gCO₂/kWh): Emissions per unit of electricity.
         - States & Union Territories: Regional granularity included for localized analysis.
  
## Tools & Technologies

- Data Analysis	Python- Pandas, NumPy, Matplolib
- ML Modeling	Python – Pandas, NumPy,Statsmodel, Scikit-learn, Matplotlib, Seaborn

## Data Analysis and Modeling

### Data Preparation & Transformation

- Cleaned and reshaped the raw long-format data.
- Normalized column names and converted all time series to monthly DateTime index.
- Aggregated data at:
         - National level (India total)
         - State level (per individual state/UT)
    
### Exploratory Data Analysis (EDA)

- Monthly and yearly trends in generation and emissions.
- Contribution analysis using pie and bar charts for.
- Total emissions by energy source.
- Created custom visualizations using matplotlib and seaborn.

### Time Series Analysis

- Checked the Seasonality and Trend.
- Checked the statinarity of the series using Adfuller test.
- Checked Autocorrleation using ACF and PACF
- Checked Moving Average trend for differnet windows (3,6,9,12).

### Time Series Modeling
A core component of this project involved building robust forecasting models to predict India’s monthly power sector emissions for the next 12 months. We implemented and compared two advanced time series models — Exponential Smoothing (ETS) and Seasonal AutoRegressive Integrated Moving Average with eXogenous regressors (SARIMAX) — using Python’s statsmodels library.
We use:
- Selected emissions as the target variable for forecasting.
- Two robust time series models:

#### A. ETS (Error-Trend-Seasonal) Model
- The Holt-Winters Exponential Smoothing (ETS) model was configured with:
- Trend: Additive
- Seasonality: Multiplicative
- Seasonal Periods: 12 (Monthly data)
- Captures level, trend, and seasonality explicitly.
- Provided a baseline forecast for emissions with seasonal cycles.

#### B. SARIMAX (Seasonal AutoRegressive Integrated Moving Average with Exogenous Variables)
- Tuned using AIC minimization and auto-ARIMA logic.
- Modeled with seasonal parameters to capture 12-month patterns.
- Produced a more stable and accurate forecast for monthly emissions.

###### Forecast Horizon: 
- Forecasted for next 12 months ( Starting from March 2025 till March 2026)
  
##### Model Evaluation: 
- Forecasts were compared against the actual validation data (last 12 months).
- Key metrics used: RMSE, MAPE, and RMSPE.

#### Results
- ETS Model Evaluation:

| Metric             | Value                              |
| ------------------ | ---------------------------------- |
| MAPE           | 0.07202                              |
| RMSE      | 16640.653                             |
| RMSPE | 9.1033                              |

- SARIMAX Model Evaluation:

| Metric             | Value                              |
| ------------------ | ---------------------------------- |
| MAPE           | 0.07631                              |
| RMSE      | 14617.199                            |
| RMSPE | 8.3804                             |

- ETS provided strong seasonal pattern capture but underperformed slightly when structural shifts occurred.
- SARIMAX outperformed ETS across all evaluation metrics. It handled both trend and seasonal components effectively and yielded smoother forecasts with tighter residual bounds.



## Power BI Dashboard
- An interactive dashboard was developed in Microsoft Power BI to empower decision-makers and energy analysts.
- Key Features:
       - National Overview: Total generation & emissions trend, source-wise breakdown.
       - State-Level Drilldown: Compare states by emission intensity, generation mix.
       - Dynamic Filters: Time period.
       - Custom Visuals: Pie charts, line plots, bar charts, KPI cards.
