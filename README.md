# Traffic Volume Analysis and Prediction | R Statistical Modelling

## Overview
This study examines hourly westbound Interstate 94 traffic in Minnesota (2012–2018) to identify calendar and weather-related traffic patterns, compare statistical models, and provide evidence for transport-planning decisions.

**Problem:** Highway planners need to anticipate high-volume periods while accounting for weekday, weekend, holiday and weather variation.

## Data and approach
- **Source:** UCI Machine Learning Repository — Metro Interstate Traffic Volume.
- **Preparation:** 48,204 original records; timestamp duplicates and implausible weather values assessed; **40,564 cleaned modelling observations**. Source coverage is incomplete and has gaps.
- **EDA:** Hourly, weekday/weekend, seasonal, holiday and weather comparisons.
- **Statistical inference:** Welch's t-tests, ANOVA and Fligner–Killeen dispersion checks.
- **Models:** Hour-by-weekday historical-mean baseline, ordinary least squares (OLS), Ridge, LASSO and Elastic Net regression.
- **Validation:** Chronological development (2012–2016), validation (2017) and testing (2018). The model is selected on the validation period, not on test results.
- **Further evaluation:** Exploratory PCA on weather inputs; conceptual discussions of Bayesian methods, experimental designs and future time-series forecasting.

## Reported results
- The observed weekday peak was approximately **6,241 vehicles/hour at 16:00**.
- **OLS** had the lowest (unrounded) validation RMSE among the compared models.
- Reported 2018 test **RMSE ≈ 422.17 vehicles/hour**, **MAE ≈ 256.27 vehicles/hour**, **R² ≈ 0.954**.
- These are **retrospective, single-station** results, not proof of live traffic forecasting or a deployed dashboard.

## Technologies
R, Quarto, tidyverse, lubridate, broom, glmnet, ggplot2, statistical hypothesis testing, regression diagnostics.
This was an academic **group** project, not an operational transport system. PCA was explored, not adopted in the main predictive model. Bayesian methods and ARIMA/time-series forecasting were discussed rather than implemented as production methods. Review group-member details and consultation evidence before publishing. Credit the UCI dataset and literature cited by the notebook. Add the project's actual contributors and your personal contributions below.

**My contribution:** _[Specify only tasks you personally completed.]_
