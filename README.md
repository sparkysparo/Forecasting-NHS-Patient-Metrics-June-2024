# Forecasting-NHS-Patient-Metrics-from-2008---2024
 This report analyzes NHS data for June 2024 to identify trends, predict patient appointment metrics, and improve healthcare services. Using advanced data analysis and machine learning techniques, we aim to provide actionable insights to support NHS decision-making and enhance patient care.
# README

## Context

The dataset encompasses various healthcare metrics recorded monthly, offering valuable insights into patient appointments, emergency admissions, and procedural data. Understanding these trends helps improve healthcare resource allocation and patient care.

## Dataset Overview

- **Data Description**: [Hospital Episode Statistics Monthly Activity Report, June 2024](LINK)
- **Number of Entries**: 207
- **Number of Columns**: 18

## Data Cleaning

- Converted `CALENDAR_MONTH_END_DATE` to datetime format for time series analysis.
- Sorted data chronologically for accurate trend analysis.

## Methodology

### Tools and Libraries

- **Pandas**: Data manipulation and cleaning.
- **NumPy**: Numerical operations.
- **Matplotlib/Seaborn**: Data visualization.
- **Statsmodels**: Time series forecasting (ARIMA).
- **Scikit-learn**: Model evaluation metrics.

### Model Selection

- **ARIMA Model**: Chosen for time series forecasting due to its ability to model autocorrelations in time series data.

### Analysis Workflow

1. **Data Preparation**: Clean and preprocess data.
2. **Feature Selection**: Focus on key metrics such as `APC_Finished_Consultant` and `Outpatient_Total_Appointments`.
3. **Model Training**: Fit ARIMA model on historical data.
4. **Forecasting**: Predict future values until 2030.

## Results

### Trends Observed

- **APC Finished Consultant**: Fluctuates with peaks and troughs.
- **Outpatient Total Appointments**: Shows a significant increase or decrease over time.
- **APC Emergency**: Fluctuates, possibly due to seasonal factors.
- **APC Finished Admission Episodes**: Displays varying levels over time.

#### Key Observations

- **APC Finished Consultant Episodes**: Consistent upward trend with a noticeable dip around 2020-2021 due to the COVID-19 pandemic, followed by a sharp recovery.
- **Outpatient Total Appointments**: Strong growth pattern interrupted by a pandemic-related dip but quickly rebounded and continued upward.
- **APC Emergency Episodes**: Upward trend with significant volatility. Noticeable dip during the pandemic, stabilizing post-pandemic.
- **APC Finished Admission Episodes**: Steady increase with a pandemic-related dip, followed by recovery and some continuing volatility.

### Correlation Analysis

The correlation matrix reveals high positive correlations among most NHS healthcare metrics, especially APC activities, indicating they often increase together. Outpatient activities also show strong correlations with inpatient metrics. However, outpatient attendance rates have weaker or negative correlations, suggesting different behavior.

### Time Series Analysis

- The plot shows a steady increase in outpatient attended appointments from 2006 to 2020, followed by a sharp drop due to COVID-19. Post-2020, there's a recovery with some fluctuations, continuing the upward trend into 2024.
- Time series forecast:
  - **Training Data (2006-2020)**: Exhibits a steady increase.
  - **Actual Data (2020-2023)**: Shows recovery after a sharp drop due to COVID-19.
  - **Forecasted Data (2023-2024)**: Fails to capture the upward trend seen in actual data.

### Model Performance

- **Mean Absolute Error (MAE)**: Approximately 1.06 million, indicating significant inaccuracies in the forecast. This suggests the ARIMA model may not be effectively capturing the actual trends.

## Discussion

### Insights

- **APC Finished Consultant**: Reflects fluctuations that may require investigation into underlying causes.
- **Outpatient Total Appointments**: Trends suggest periods of high and low activity, impacting resource planning.
- **APC Emergency**: Fluctuations might be influenced by seasonal factors or external events.

### Challenges

- **Data Quality**: Missing values and anomalies were addressed through preprocessing.
- **Model Selection**: Ensuring ARIMA model's parameters were optimized for accurate forecasts.

### Limitations

- **Forecasting Accuracy**: Predictions beyond a certain point may become less reliable due to uncertainty in future trends.

## Conclusion

The analysis of NHS patient metrics over time reveals a consistent rise in demand for healthcare services, interrupted by the COVID-19 pandemic around 2020-2021. Despite this disruption, the metrics indicate a strong recovery across various services, demonstrating the resilience of the NHS. The high positive correlations among inpatient and outpatient activities suggest that as demand for one service increases, others tend to follow, reflecting the interconnectedness of NHS services. However, the time series forecast model for outpatient appointments shows significant inaccuracies, indicating the need for improved forecasting methods to better anticipate future healthcare demands. Overall, the data underscores the enduring growth in healthcare utilization within the NHS, with a clear recovery trajectory post-pandemic.

### Implications

These findings can guide NHS resource planning and improve patient care by anticipating demand and adjusting services accordingly.

## Future Work

- Explore additional forecasting models for comparison.
- Incorporate more features or external factors into the analysis to improve accuracy.
