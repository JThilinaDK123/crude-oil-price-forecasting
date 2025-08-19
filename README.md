# Extreme Value Handling and Forecasting of WTI Crude Oil Prices

This research focuses on detecting and handling extreme values in WTI crude oil price data and evaluating the impact on forecasting using both statistical and deep learning models.

## High Level Rich Picture of the Proposed Solution:

<img width="315" height="426" alt="image" src="https://github.com/user-attachments/assets/66f36c02-cd51-4b13-bb80-af2841bfd05c" />

## Extreme Value Detection Techniques

Five techniques were applied to identify extreme values in the WTI crude oil price series:

1) Fixed Price Threshold (FPT) – Identifies extreme values based on predefined price limits.
2) Standard Deviation Filter on Prices (SFP) – Flags values that deviate significantly from the mean using standard deviation.
3) Moving Window Filter on Prices (MFP) – Uses a rolling window to detect local anomalies in the price series.
4) Recursive Filter on Prices (RFP) – Iteratively filters extreme values to refine the dataset.
5) Percentage Price Filter (PFP) – Detects extremes based on relative price changes over time.

## Extreme Value Replacement Techniques

Once detected, extreme values were treated using four replacement strategies:

1) Mean Value Replacement – Replaces extremes with the overall mean of the series.
2) Median Value Replacement – Uses the median value to reduce sensitivity to outliers.
3) Damping Scheme – Adjusts extreme values toward the center of the distribution using a damping factor.
4) Threshold Scheme – Replaces values exceeding predefined thresholds with the nearest threshold value.

## Methodology

### Data Acquisition

WTI crude oil price series (DCOILWTICO) was downloaded via the FRED API for the period from 2001-01-02 to 2023-10-10.

### Data Preprocessing

* Converted the date column to datetime format.
* Set the date column as the index of the DataFrame.
* Dataset Preparation – Created 21 datasets representing all combinations of the 5 detection techniques and 4 replacement methods. Each dataset contains: Date & WTI Crude Oil Price

### Modeling

* Implemented statistical forecasting models on all datasets individually.
* Applied deep learning architectures (RNN, LSTM, and GRU) to each dataset.
* Model Selection – The best-performing model was selected for deployment based on forecasting accuracy.

