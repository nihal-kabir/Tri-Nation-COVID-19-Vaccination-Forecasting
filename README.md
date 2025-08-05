# Comparative Time-Series Forecasting of COVID-19 Vaccination Uptake in Bangladesh, India, and Pakistan

## Overview

This project implements a standardized, end-to-end time-series forecasting pipeline to project 180-day COVID-19 vaccination totals across Bangladesh, India, and Pakistan. It focuses on reproducible data processing, robust model evaluation, and clear comparative insights.

## Key Features

* **Multi-country forecasting:** Uniform pipeline applied to three countries.
* **Model benchmarking:** Rigorous MAE comparisons for ARIMA, SARIMA, and a 3‑state Gaussian HMM.
* **Reproducibility:** Fixed train/test splits, scaling, and evaluation metrics for fair comparisons.

## Methodology

1. **Data Ingestion & Cleaning**

   * Load daily total vaccination time series for each country.
   * Apply mean-imputation to fill missing values and ensure continuous timelines.

2. **Train/Test Splitting & Scaling**

   * Split each country’s series into an 80/20 train/test split.
   * Standard-scale the training data and apply the same transform to testing.

3. **Model Implementation**

   * **ARIMA:** Autoregressive Integrated Moving Average models tuned via grid search on (p,d,q) parameters.
   * **SARIMA:** Seasonal ARIMA incorporating weekly seasonality (7-day).
   * **3-State Gaussian HMM:** Hidden Markov model assuming three latent regimes.

4. **Evaluation & Benchmarking**

   * Forecast 180 days ahead on test sets.
   * Compute Mean Absolute Error (MAE) for each model–country combination.
   * Compare relative performance: identify winner per country and highlight underperformers.

## Results

* **Pakistan:** SARIMA achieved MAE **11,482,748** vs ARIMA **19,449,151**.
* **Bangladesh:** ARIMA led with MAE **71,743** vs SARIMA **29,033,265**.
* **India:** ARIMA edged SARIMA (**21,617** vs **24,755**).
* **Gaussian HMM:** MAEs peaked at **1.9×10⁸**, **3.3×10⁸**, and **1.6×10⁹** for Pakistan, Bangladesh, and India respectively—excluded from production.

## Contributing

Contributions and issue reports are welcome! Please fork the repo, make your changes, and submit a pull request.



This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
