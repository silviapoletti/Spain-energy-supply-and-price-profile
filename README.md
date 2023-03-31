# Spain: Energy supply and Energy price profile

<img align="right" width="30%" src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/c24908090611c859eef82dde638011d796fead0c/slides%20and%20plots/logo.png">

Authors: Chiara Bigarella, Luca Pessina, Silvia Poletti.

Dataset: Hourly energy demand, generation and weather (Spain, 2015-2018) available [here](https://www.kaggle.com/datasets/nicholasjhana/energy-consumption-generation-prices-and-weather).

Language: R

Notebook outline:
- Data pre-processing and exploratory data analysis
- Statistical methods for modeling the energy supply from different sources
- Understand the possible competition/collaboration dynamic between sources of energy
- Energy price forecasting

Important disclaimer: Our analysis is based on data, articles and scientific sources available before 2022.


# Data Pre-processing and Exploratory Analysis

We deal with hourly data. We aggregated the data using the mean by year, months, weeks and days. For our analysis we'll mostly use weekly or daily data separated by year. As expected, time aggregation lowers the autocorrelation in the data.

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/7e5e92a79fc8c5c1ed2d3885c7d48c9fdcd1ed87/slides%20and%20plots/aggregation-autocorrelation.png" width="80%">
</p>

We also aggregate some features:
- `brown coal lignite`, `hard coal`, `oil` and `gas` are aggegated as `fossil`
- `biomass` and `waste` are aggregated as `biomass waste`
- `hydro pumped storage consumption`, `hydro run of river and poundage` and `hydro water reservoir` are aggregated as `hydro`
- `hydro`, `wind onshore`, `solar` and `other renewable` are aggregated as `renewables`.

<img align="right" width="55%" src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/c20cac3481a9580524dd98289a53ac2faae68e1b/slides%20and%20plots/energy-supply-boxplot.png">

## 🔌Energy supply 

The energy supply distribution is as follows:
- Fossil: 37%
- Nuclear: 22%
- Renewables: 39%
  - Wind: 19%
  - Hydroelectric: 14%
  - Solar: 5%
  - Other renewables: 1%
- Biomass & waste: 2%

## 💸 Energy price

The price is highly influenced by the amount of energy produced by the different sources. From the radar-plot we can see that, in general, the higher the production of nuclear power the lower the price. The opposite trend holds for the fossil energy supply.

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/8e935fca6471bd4812543f48150116b500744761/slides%20and%20plots/supply-price.png">
</p>

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/8e935fca6471bd4812543f48150116b500744761/slides%20and%20plots/supply-price.png" width="60%">
    <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/8e935fca6471bd4812543f48150116b500744761/slides%20and%20plots/supply-price.png" width="60%">
</p>

