Overview

This project develops a predictive analytics framework to forecast the number of children in care under the U.S. Department of Health and Human Services (HHS) Unaccompanied Alien Children (UAC) Program. 
Using time-series analysis and machine learning models, the project transforms historical operational data into forward-looking insights. The goal is to enable proactive decision-making by predicting future care demand and system pressure.

Problem Statement

The UAC Program operates in a highly uncertain environment where sudden increases in border apprehensions can rapidly overload the system.
Currently, the system lacks:
* Short-term forecasts of children in HHS care
* Predictive insights into discharge (placement) demand
* Early warning signals for capacity stress

As a result, delayed responses can lead to:
* Overcrowding in shelters
* Increased workload on staff
* Longer stays for children

This project aims to shift from reactive reporting to proactive planning using predictive modeling.

 Dataset Description

The dataset consists of daily time-series data capturing the flow of children through the system:

* **Date** → Reporting date
* **Children apprehended and placed in CBP custody** → Daily intake at the border
* **Children in CBP custody** → Current number of children held in CBP facilities
* **Children transferred out of CBP custody** → Number of children moved into HHS care
* **Children in HHS Care** → Total number of children currently under HHS care
* **Children discharged from HHS Care** → Number of children placed with sponsors (exits)

These variables represent the full pipeline from intake to discharge, enabling analysis of system dynamics and forecasting of future demand.


methodology
1) Data Preparation

* Converted date column into datetime format
* Sorted data chronologically
* Handled missing values using interpolation and forward/backward filling

 2) Feature Engineering

* Lag features (t-1, t-7, t-14)
* Rolling statistics (7-day mean and standard deviation)
* Net pressure = Transfers – Discharges

 3) Modeling Approaches

* **ARIMA** → Time-series statistical model
* **Random Forest Regressor** → Captures non-linear relationships
* **Gradient Boosting Regressor** → Improves prediction accuracy

4) Train-Test Strategy

* Time-based split (no random sampling)
* Model trained on past data and tested on future data


Model Evaluation

Models were evaluated using:

* **MAE (Mean Absolute Error)** → Measures average prediction error
* **RMSE (Root Mean Squared Error)** → Penalizes large errors

Comparison of multiple models ensures robustness and reliability of forecasts.

 Conclusion

This project demonstrates how predictive analytics can transform historical data into actionable insights. By forecasting future care demand, it enables proactive planning, reduces operational risks, and improves outcomes in high-impact humanitarian systems.
The forecasting models successfully captured short-term fluctuations in care demand.
* Random Forest and Gradient Boosting showed strong predictive performance
* ARIMA provided a solid baseline for time-series trends
* Feature engineering significantly improved model accuracy

