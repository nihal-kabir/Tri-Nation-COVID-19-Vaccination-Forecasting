# Comparative Time-Series Forecasting of COVID-19 Vaccination Uptake in Bangladesh, India, and Pakistan

## Overview

This project implements a standardized, end-to-end time-series forecasting pipeline to project 180-day COVID-19 vaccination totals across Bangladesh, India, and Pakistan. It focuses on reproducible data processing, robust model evaluation, and clear comparative insights.

## Dataset
Link: https://drive.google.com/file/d/1bCxhq18K5KVFuOPxzrFzupyLPi2Q74aY/view?usp=sharing

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

## References

Mohan, S., Solanki, A. K., Taluja, H. K., Anuradha, Singh, A. (2022). Predicting the impact of the third wave of COVID-19 in India using hybrid statistical machine learning models: A time series forecasting and sentiment analysis approach. Computers in Biology and Medicine, 144, 105354. https://doi.org/10.1016/j.compbiomed.2022.105354

Dofadar, D. F., Khan, R. H., Alam, M. G. R. (2021). COVID-19 Confirmed Cases and Deaths Prediction in Bangladesh Using Hidden Markov Model. IEEE. https://doi.org/10.1109/biosmart54244.2021.9677841

Ye, J., Hai, J., Wang, Z., Wei, C., Song, J. (2023). Leveraging natural language processing and geospatial time series model to analyze COVID-19 vaccination sentiment dynamics on Tweets. JAMIA Open, 6(2). https://doi.org/10.1093/jamiaopen/ooad023

Zeitouny, S., Suda, K. J., Mitsantisuk, K., Law, M. R., Tadrous, M. (2021). Mapping global trends in vaccine sales before and during the first wave of the COVID-19 pandemic: a cross-sectional time-series analysis. BMJ Global Health, 6(12), e006874. https://doi.org/10.1136/bmjgh-2021-006874

Thorakkattle, M. N., Farhin, S., Khan, A. A. (2022). Forecasting the Trends of Covid-19 and Causal Impact of Vaccines Using Bayesian Structural time Series and ARIMA. Annals of Data Science, 9(5), 1025–1047. https://doi.org/10.1007/s40745-022-00418-4

Zaidi, S. a. J., Tariq, S., Belhaouari, S. B. (2021). Future prediction of COVID-19 vaccine trends using a voting classifier. Data, 6(11), 112. https://doi.org/10.3390/data6110112

Abdulkareem, N. M., Abdulazeez, A. M., Zeebaree, D. Q., Hasan, D. A. (2021). COVID-19 World vaccination progress using machine learning classification algorithms. Qubahan Academic Journal, 1(2), 100–105. https://doi.org/10.48161/qaj.v1n2a53


