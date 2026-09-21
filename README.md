# NYC Motor Vehicle Collisions: A Spatiotemporal & Time-Series Analysis

> **Author:** Atman Ainapure | MS in Data Science, Columbia University 
> **Dataset:** 50,000-row sample of NYC NYPD Motor Vehicle Collisions (2020–2021)

## Overview
This repository contains a comprehensive data science investigation into the physical, spatial, and temporal dynamics of vehicular traffic in New York City. Moving beyond basic aggregate statistics, this project utilizes Time Series Analysis (TSA) and street-level Geospatial Mapping to uncover how road infrastructure, human behavior, and external environmental shocks dictate crash volume and lethality.

The analysis specifically explores the "Empty Road Paradox" during the 2020–2021 timeline, proving that while lockdown measures drastically reduced overall traffic volume, the resulting lack of congestion removed natural speed limiters, leading to high-velocity, fatal collisions.

## Key Analytical Features
* **Time Series Decomposition:** Broke down daily crash volumes into Trend, Seasonality, and Residual components using `statsmodels` to isolate underlying traffic rhythms from chaotic noise.
* **Granular Seasonality Profiling:** Segmented temporal data to reveal contrasting driver behaviors, specifically mapping the "Bimodal Commute" (weekday rush hours) against the "Nightlife Shift" (weekend late-night spikes).
* **Algorithmic Anomaly Detection:** Extracted mathematical outliers from the TSA residuals and successfully mapped the most massive, unexplainable crash spikes directly to historical NYC weather events (e.g., the January 2021 Nor'easter Blizzard).
* **Interactive Geospatial Mapping:** Engineered an interactive `folium` heatmap utilizing Esri map tiles to bypass API restrictions, featuring a dynamic layer-control system to visually separate high-volume property damage from localized fatal crash hotspots.
* **Severity-Weighted Intersection Profiling:** Developed a custom scoring algorithm ($1\times\text{Crash} + 3\times\text{Injury} + 10\times\text{Fatality}$) to mathematically identify and rank the Top 10 Deadliest Intersections in the city.

## Technical Stack
* **Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Time Series Modeling:** `statsmodels` (Seasonal Decomposition)
* **Data Visualization:** `matplotlib`, `seaborn`
* **Geospatial Analysis:** `folium`, Esri Light Gray Canvas Basemaps

## Core Insights
1. **The Physics of Traffic (Volume vs. Velocity):** Geospatial severity mapping proves that high-volume areas (like the Manhattan grid) primarily generate survivable, low-speed fender-benders, whereas the widest arterial highways in the outer boroughs generate the highest concentration of fatalities.
2. **Weather-Driven Systemic Shocks:** Traffic networks are highly vulnerable to meteorological events. Isolated residual spikes in the data perfectly align with historical blizzards and flash flood warnings, indicating that predictive safety models must incorporate weather data.
3. **Data Collection Artifacts:** The analysis uncovered a structural flaw in municipal reporting regarding highways (the "BELT PARKWAY & UNSPECIFIED" anomaly), proving that standard intersection-based geospatial aggregation fails on expressway infrastructure due to the lack of traditional cross-streets.
