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


## Data Pre-processing and Exploratory Analysis

We deal with hourly data. We aggregated the data using the mean by year, months, weeks and days. For our analysis we'll mostly use weekly or daily data separated by year. 

We also aggregate some features:
- `brown coal lignite`, `hard coal`, `oil` and `gas` are aggegated as `fossil`
- `biomass` and `waste` are aggregated as `biomass waste`
- `hydro pumped storage consumption`, `hydro run of river and poundage` and `hydro water reservoir` are aggregated as `hydro`
- `hydro`, `wind onshore`, `solar` and `other renewable` are aggregated as `renewables`.

#### 🔌Energy supply 

#### 💸 Energy price

<p align="center">
  <img src=" " width="70%">
</p>



