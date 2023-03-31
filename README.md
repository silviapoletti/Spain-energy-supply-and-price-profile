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
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/7e5e92a79fc8c5c1ed2d3885c7d48c9fdcd1ed87/slides%20and%20plots/aggregation-autocorrelation.png" width="100%">
</p>

We also aggregate some features:
- `brown coal lignite`, `hard coal`, `oil` and `gas` are aggegated as `fossil`
- `biomass` and `waste` are aggregated as `biomass waste`
- `hydro pumped storage consumption`, `hydro run of river and poundage` and `hydro water reservoir` are aggregated as `hydro`
- `hydro`, `wind onshore`, `solar` and `other renewable` are aggregated as `renewables`.

<br/>

## 🔌Energy supply 

<img align="right" width="55%" src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/c20cac3481a9580524dd98289a53ac2faae68e1b/slides%20and%20plots/energy-supply-boxplot.png">

The energy supply distribution is as follows:
- Fossil: 37%
- Nuclear: 22%
- Renewables: 39%
  - Wind: 19%
  - Hydroelectric: 14%
  - Solar: 5%
  - Other renewables: 1%
- Biomass & waste: 2%

<br/>

## 💸 Energy price

The price is highly influenced by the amount of energy produced by the different sources. From the radar-plot we can see that, in general, the higher the production of nuclear power the lower the price. The opposite trend holds for the fossil energy supply.

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/8e935fca6471bd4812543f48150116b500744761/slides%20and%20plots/supply-price.png">
</p>

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/f9fc9eb913d1748dbf5f4a2f73497342cabc9163/slides%20and%20plots/price-insights.png" width="90%">
    <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/f9fc9eb913d1748dbf5f4a2f73497342cabc9163/slides%20and%20plots/price-insights2.png" width="70%">
</p>

<br/>

# Statistical methods for modeling the energy supply

<img align="right" width="40%" src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/b475965afd9382ace213da4556d535e5b1740c18/slides%20and%20plots/residuals-analysis.png">

To understand the behavior of energy generation we will consider the following methods: Linear Regression, Generalized Additive Models (GAM) and diffusion-of-innovation models such as the Bass model and the Generalized Bass model with shocks.

For each method we model the residuals as displayed in the diagram on the right.

<br/>

The Generalized Bass model with exponential and mixed shocks captured some interesting behaviors regarding the generation of biomass and nuclear energy, as described in the following visualizations (plots on the right are generated by using a non-parametric regression model based on a smoothing parameter).

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/d32ca3d30b073ae66ed60a57da4140153c675888/slides%20and%20plots/biomass-series.png">
  <br/>
    <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/d32ca3d30b073ae66ed60a57da4140153c675888/slides%20and%20plots/nuclear-series.png" >
</p>

# Competition and collaboration dynamics between sources of energy

Since Spain is moving to green energy production, we want to explore the competitive power of renewables and the potential of biomass in the nation. Moreover, we will explore the convenience of the Spain's nuclear phase-out.

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/fd9fcda349658eaab6dd0663e7a5cf3526528b9d/slides%20and%20plots/renewable-insights.png" width="48%">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/fd9fcda349658eaab6dd0663e7a5cf3526528b9d/slides%20and%20plots/nuclear-debate.png" width="48%">
</p>

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/fd9fcda349658eaab6dd0663e7a5cf3526528b9d/slides%20and%20plots/biomass-action-plan.png" width="70%">
</p>

To model the different energy sources relationships, we applied the Unbalanced Competition and Regime Change Diachronic model (UCRCD) in its synchronous version, in which we simply don't consider the stand-alone phase of the first series.

## ☀️ Is the renewable energy industry competitive?

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/fd9fcda349658eaab6dd0663e7a5cf3526528b9d/slides%20and%20plots/fossil-vs-renewables.png" width="80%">
</p>


## 🌱 What is the biomass potential?

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/fd9fcda349658eaab6dd0663e7a5cf3526528b9d/slides%20and%20plots/fossil-vs-biomass.png" width="80%">
</p>

## ☢️ Is the nuclear phase-out convenient?

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/fd9fcda349658eaab6dd0663e7a5cf3526528b9d/slides%20and%20plots/fossil-vs-nuclear.png" width="80%">
</p>


# 📈 Price forecasting

<img align="right" width="50%" src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/5c9d80365d49d751112a3ee2016fadaaa6f05555/slides%20and%20plots/forecasting-assumptions.png">

Fist, we try to forecast the price for the first six months of 2018, based on 2016 and 2017 weekly data. However, we obtain much better results when focusing on daily data ad performing short-term forecasting. 

We consider the following approaches for forecasting: Linear Models, Gradient-Boost Models (GBOOST), Simple Exponential Smoothing (SES), the Holt variation and ARIMA Models.

### Linear Model

<p align="center">
  <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/adaa7b9582b0268a71836c076edd93e6f47af456/slides%20and%20plots/linear-forecasting.png" width="48%">
    <img src="https://github.com/silviapoletti/Spain-energy-supply-and-price-profile/blob/adaa7b9582b0268a71836c076edd93e6f47af456/slides%20and%20plots/linear-forecasting-corr.png" width="48%">
</p>

