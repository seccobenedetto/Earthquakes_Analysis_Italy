# Temporal and Spatial Analysis of Earthquakes in Italy (1925–2025)

Italy lies at the boundary of the African and Eurasian tectonic plates, and both plates move and smash
into each other releasing a lot of energy and making Italy a seismically active zone, especially central
Italy (mountain range). The last main earthquake was the MW 6.3 quake that struck L’Aquila (Abruzzo)
in the early morning of April 6, 2009: 297 people were killed, over 1,000 injured, 66,000 made homeless,
and many thousands of buildings were destroyed or damaged. In order to better study the relationship between 
the occurrence of earthquakes and the geological structure, we present the temporal and
spatial characteristics of earthquakes, explore the temporal and spatial rules of earthquake disasters and
determine the seismically active regions in Italy.
We investigate and analyze the earthquakes data coming from the USGS Earthquake Hazards Program
with the magnitude greater than MW 5.0 that occurred in Italy and surrounding countries during the
last hundred years: from 1925 to 2025.

(This repository contains the code and final report for a university project developed at the **Department of Physics and Astronomy "Galileo Galilei", University of Padova**.)

## Authors

* **Jamilov Javlon**


* **Pirazzo Tommaso**


* **Secco Benedetto**



---

## Project Overview

This project provides a comprehensive temporal and spatial analysis of seismic activity in Italy spanning a century (1925–2025). The study investigates earthquake distributions, tectonic boundaries, depth profiles, and applies time-series forecasting models (ARIMA and SSA) to predict future magnitude trends.

---

## Key Steps & Methodology

### 1. Data Preparation & Inspection

* Inspected historical earthquake datasets in Italy across magnitude and depth thresholds.


* Evaluated the **Gutenberg-Richter Law** ($\log_{10} N = a - b \cdot M$) to model the relationship between earthquake magnitude and frequency. The estimated $b$-value of $1.31 \pm 0.03$ indicates a high proportion of smaller earthquakes relative to larger ones.



### 2. Spatial Analysis & Seismic Hazard

* **Grid-Cell Mapping:** Divided the region into grid cells to calculate local $a$ and $b$ parameters via linear regression.


* **Tectonic Plate Integration:** Integrated USGS plate boundary data (`doc.kml`) using spatial features to analyze seismicity along the Eurasian, African, and Adriatic microplates.


* **Poisson Hazard Model:** Estimated the probability of experiencing at least one high-magnitude event ($M \ge 5$) over a 10-year window.


* **Hierarchical Clustering:** Grouped seismic events spatially to identify regional clusters.


* **Depth Analysis:** Identified three primary depth zones ($0\text{--}100\text{ km}$, $200\text{--}300\text{ km}$, and $380\text{--}520\text{ km}$), attributing deep events in the south to the subduction of the Ionian plate beneath the Calabrian arc.



### 3. Temporal Analysis & Forecasting

The project analyzed two main time series metrics:

* **AEM** (Average Earthquake Magnitude)


* **MEM** (Maximum Earthquake Magnitude)



Two primary modeling approaches were implemented and compared:

* **ARIMA (AutoRegressive Integrated Moving Average):** A classic parametric linear model tested across training ranges (1925–2015 for validation against 2016–2025 data, and full historical data for 2026–2035 projections).


* **SSA (Singular Spectrum Analysis):** A non-parametric method used to decompose the time series into trend, periodic/seasonal components, and noise without requiring strict distribution assumptions, making it highly robust for irregular seismic data.



---

## Tools & Libraries Used

* **Language:** `R`


* **Spatial Data & Mapping:** `sf` (`st_read`), `ggplot2`, `borders` (`world`)


* **Time Series & Modeling:** Native R time series packages, ARIMA (`forecast` / `stats`), and Singular Spectrum Analysis (SSA) libraries.

---

## Key Results & Conclusions

* **Model Comparison (RMSE):** **SSA consistently outperformed ARIMA**, yielding lower Root Mean Square Error (RMSE) values for both Average (AEM) and Maximum (MEM) magnitude series, proving its higher robustness and predictive capability for complex, non-stationary seismic patterns.


* **Magnitude Trends:** AEM shows a long-term decreasing trend post-1970s and is projected to continue decreasing, while MEM remains volatile with signs of stabilization.

