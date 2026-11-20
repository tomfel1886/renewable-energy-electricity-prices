# Impact of Renewable Energy on Electricity Prices

## Project Overview

This project is based on my Bachelor’s thesis in Economics at the University of Bern, completed in 2024.

The objective is to investigate how electricity generation from renewable energy sources affects day-ahead electricity prices in the German-Luxembourg (DE-LU) electricity market.

Using hourly electricity market data from October 2018 to February 2024, I conducted an econometric analysis in R to examine how wind and solar electricity generation influence wholesale electricity prices throughout the day.

The analysis focuses on the merit-order effect, which describes how electricity generation from renewable sources with low marginal costs can reduce wholesale electricity prices by displacing more expensive conventional generation.

## Research Questions

1. How does increased wind and solar electricity generation affect day-ahead electricity prices?
2. How do these effects differ across hours of the day?
3. How does renewable electricity generation affect conventional electricity production and net imports?

## Data

The analysis uses electricity market data for Germany and Luxembourg covering the period October 1, 2018 – February 29, 2024.

The dataset includes:

* Hourly day-ahead electricity prices
* Hourly solar and wind electricity generation
* Hourly electricity consumption (load)
* Daily natural gas prices
* Monthly lignite production
* Electricity generation from conventional sources
* Hourly net electricity imports

### Data Sources

The data originate from the following providers:

* **SMARD (Bundesnetzagentur):** Electricity prices, generation and consumption
* **ENTSO-E:** Net electricity imports
* **Eurostat:** Lignite production
* **LSEG Workspace:** Natural gas prices

The underlying datasets are not included in this repository due to potential redistribution restrictions.

## Methodology

**1. Data Preparation**

The analysis was conducted in R.

Electricity market data from different sources were imported, cleaned and combined into a consistent dataset.

Daily wind and solar generation were aggregated to investigate how total daily renewable output relates to electricity prices at different hours.

**2. Econometric Analysis**

I estimated linear regression models using Ordinary Least Squares (OLS) to investigate the relationship between renewable electricity generation and day-ahead electricity prices.

The models were estimated separately for each hour of the day, allowing the estimated effects to vary across hours.

The main explanatory variables are daily solar and wind electricity generation.

Additional controls include:

* Hourly electricity consumption
* Natural gas prices
* Monthly lignite production
* Monthly fixed effects

The estimated coefficients measure the change in hourly day-ahead electricity prices associated with an additional GWh of daily renewable electricity generation, conditional on the included controls.

**3. Substitution Between Energy Sources**

In a second step, I investigated how increased renewable electricity generation relates to electricity supplied by other sources.

Separate regression models were estimated for:

* Thermal electricity generation
* Nuclear electricity generation
* Other electricity sources
* Net electricity imports

Additional control variables account for the COVID-19 lockdown and selected power plant shutdowns.

**4. Data Visualization**

Regression coefficients and confidence intervals were visualized to illustrate how the estimated effects vary throughout the day.

## Main Findings

### Solar Electricity Generation

Higher daily solar generation is associated with significantly lower electricity prices during daylight hours.

* Between 8 a.m. and 6 p.m., higher solar generation is associated with lower day-ahead prices.
* Around noon, an additional 1 GWh of daily solar generation is associated with a €0.284/MWh reduction in the electricity price.
* During certain early morning and evening hours, higher daily solar generation is associated with higher prices.

These findings suggest that increasing solar generation changes the intraday price structure, with lower midday prices and relatively higher prices outside daylight hours.

### Wind Electricity Generation

Higher daily wind generation is associated with lower electricity prices throughout the day.

* The price-reducing effect is observed across all hours.
* The largest estimated reduction occurs around 2 p.m., at approximately €0.135/MWh per additional GWh of daily wind generation.
* The estimated effect is generally stronger during the morning and early afternoon.

### Substitution Between Energy Sources

The analysis also suggests that higher renewable electricity generation is associated with:

* Reduced thermal electricity generation.
* Lower net electricity imports, particularly during periods of high renewable output.
* Relatively stable nuclear electricity generation.

However, the substitution estimates should be interpreted cautiously because some electricity market balance conditions are not fully satisfied by the models.

## Tools and Packages

**Programming language:** R

**Methods and techniques:**

* Data cleaning and transformation
* Ordinary Least Squares (OLS)
* Hourly regression analysis
* Fixed effects
* Statistical inference
* Confidence intervals
* Data visualization

**R packages:**

* dplyr
* lubridate
* ggplot2
* broom
* readxl

## Code Availability and Reproducibility

This repository contains the R code developed for my bachelor’s thesis in Economics at the University of Bern.

The analysis includes data preparation, hourly OLS regressions, and visualizations of estimated coefficients and confidence intervals.

The underlying datasets are not included due to potential redistribution restrictions. Reproducing the analysis requires obtaining the relevant data from the original providers.

## Research Paper

The accompanying research paper (paper.pdf) provides a detailed explanation of the research question, methodology, empirical results, and interpretation of the findings.

## Author

**Thomas Felder**
BSc Economics
University of Bern

Bachelor’s thesis submitted: August 2024
