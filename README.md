# India-Power-Sector-Generation-Emissions-Analysis-and-Forecasting

## Project Overview
This project focuses on analyzing and forecasting electricity generation and emissions in India's power sector using Python and Power BI. The goal is to derive insights at both the national and state levels and predict future trends for CO₂ emissions using robust time series forecasting models.

## Objectives

- Perform exploratory data analysis (EDA) on India's electricity generation and emissions by fuel source and state.
- Understand trends, seasonality, and regional patterns in emissions and generation.
- Build and evaluate time series forecasting models to predict future emissions.
- Develop an interactive Power BI dashboard for visualization and stakeholder reporting.

## Data Source

- Monthly electricity generation and emissions data for Indian states from Jan 2019 to Dec 2023.
- Data includes:
         - Generation (GWh): Source-wise monthly electricity generation.
         - Emissions (ktCO₂): Source-wise monthly carbon emissions.
         - Emission Intensity (gCO₂/kWh): Emissions per unit of electricity.
         - States & Union Territories: Regional granularity included for localized analysis.
  
## Data Preparation & Transformation
- Cleaned and reshaped the raw long-format data.
- Normalized column names and converted all time series to monthly DateTime index.
- Aggregated data at:
-         - National level (India total)
-         - State level (per individual state/UT)
-     
## Exploratory Data Analysis (EDA)
- Monthly and yearly trends in generation and emissions.
- Contribution analysis using pie and bar charts for.
- Total emissions by energy source.
Created custom visualizations using matplotlib and seaborn.

## Time Series Modeling
- Selected emissions as the target variable for forecasting.
- Used two robust time series models:

### A. ETS (Error-Trend-Seasonal) Model
- Captures level, trend, and seasonality explicitly.
- Provided a baseline forecast for emissions with seasonal cycles.

### B. SARIMAX (Seasonal AutoRegressive Integrated Moving Average with Exogenous Variables)
- Tuned using AIC minimization and auto-ARIMA logic.
- Modeled with seasonal parameters to capture 12-month patterns.
- Produced a more stable and accurate forecast for monthly emissions.

##### Forecast Horizon: 12 months ahead
##### Model Evaluation: RMSE and MAPE calculated on validation data

## Power BI Dashboard
- An interactive dashboard was developed in Microsoft Power BI to empower decision-makers and energy analysts.
- Key Features:
       - National Overview: Total generation & emissions trend, source-wise breakdown.
       - State-Level Drilldown: Compare states by emission intensity, generation mix.
       - Dynamic Filters: Time period.
       - Custom Visuals: Pie charts, line plots, bar charts, KPI cards.
