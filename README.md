# Spain: Energy supply and Energy price profile

Authors: Chiara Bigarella, Luca Pessina, Silvia Poletti.

Dataset: Hourly energy demand, generation and weather (Spain, 2015-2018) available [here](https://www.kaggle.com/datasets/nicholasjhana/energy-consumption-generation-prices-and-weather).

Language: R

Notebook outline:
- Data pre-processing and exploratory data analysis
- Statistical methods for modeling the energy supply from different sources
- Understand the possible competition/collaboration dynamic between sources of energy
- Energy price forecasting

Important disclaimer: Our analysis is based on data, articles and scientific sources available before 2022.


## Data Pre-processing and Exploratory Analysis

We deal with hourly data. We aggregated the data using the mean by year, months, weeks and days. For our analysis we'll mostly use weekly or daily data separated by year. 

We also aggregate some features:
- `brown coal lignite`, `hard coal`, `oil` and `gas` are aggegated as `fossil`
- `biomass` and `waste` are aggregated as `biomass waste`
- `hydro pumped storage consumption`, `hydro run of river and poundage` and `hydro water reservoir` are aggregated as `hydro`
- `hydro`, `wind onshore`, `solar` and `other renewable` are aggregated as `renewables`.



<p align="center">
  <img src="https://github.com/silviapoletti/Statistical-Analysis-on-Heart-failures-clinical-records/blob/f5e98e77fede14013e5d1c7c2152d1438784e002/report/serum_creatinine_outliers.png" width="70%">
</p>

blablabla

<img align="left" width="43%" src="https://github.com/silviapoletti/Statistical-Analysis-on-Heart-failures-clinical-records/blob/ab4e52c40e492f6e4c0b845cf6571df43c425162/report/high_leverage_point.png">
