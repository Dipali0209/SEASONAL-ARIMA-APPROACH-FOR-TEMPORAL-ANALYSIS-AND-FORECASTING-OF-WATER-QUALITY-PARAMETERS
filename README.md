# SEASONAL-ARIMA-APPROACH-FOR-TEMPORAL-ANALYSIS-AND-FORECASTING-OF-WATER-QUALITY-PARAMETERS

## Project Overview
This project addresses water pollution in the National Capital Territory (NCT) of Delhi, India, where the water quality of the Yamuna River and various groundwater sources is severely affected by pollutants like industrial effluents, untreated sewage, and agricultural runoff. 

We utilized **remote sensing technology** to assess water quality over a multi-year period. Using **Sentinel-2 satellite data**, we extracted key water quality parameters, including **turbidity**, **suspended sediment concentration (SSC)**, **dissolved organic matter (DOM)**, **chlorophyll-a**, **NDWI (Normalized Difference Water Index)**, and **NDVI (Normalized Difference Vegetation Index)**.

To forecast future water pollution trends, we applied **Seasonal Autoregressive Integrated Moving Average (SARIMA)** models, a machine learning approach for time-series data analysis.

## Objectives
- Extract water quality parameters from satellite imagery for the region of interest.
- Analyze temporal and geographical changes in water quality across Delhi.
- Forecast future water quality trends using SARIMA models.
- Evaluate the SARIMA models using standard metrics to ensure reliable predictions.

## Methodology

### 1. Data Collection
We collected water quality data for the NCT of Delhi over a 5-year period (2018-2023) using **Google Earth Engine (GEE)**. The data included the following indicators:
- **Turbidity**: Normalized Difference Turbidity Index (NDTI)
- **Chlorophyll-a**: Normalized Difference Chlorophyll Index (NDCI)
- **Suspended Sediment Concentration (SSC)**: Derived from the Red and NIR bands combination
- **Dissolved Organic Matter (DOM)**: Derived from the Blue (B2) and Green (B3) bands combination
- **NDWI** and **NDVI**

### 2. Time-Series Analysis
To model the water quality parameters, we used the **SARIMA model**. The process involved:
- **Differencing** to make the time-series data stationary.
- **ACF and PACF plots** to identify appropriate values for the autoregressive (p), moving average (q), and differencing (d) components.
- Seasonal parameters `(P, D, Q, s)` were determined based on periodic patterns in the data.

### 3. Model Evaluation
We evaluated the models using:
- **Mean Squared Error (MSE)**
- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**
- **Akaike Information Criterion (AIC)**
- **Bayesian Information Criterion (BIC)**

The lower the values of these metrics, the better the model's performance.

## Results and Discussion
The SARIMA models produced varying levels of accuracy for each water quality parameter. Below is a summary of the best model performance for each parameter:

| **Parameter**  | **Order** | **Seasonal Order** | **MSE**   | **RMSE**   | **MAE**    | **AIC**        | **BIC**         |
|----------------|-----------|--------------------|-----------|------------|------------|----------------|-----------------|
| **Turbidity**  | (1, 1, 1) | (2, 1, 1, 12)      | 0.00045   | 0.021218   | 0.01676    | -225.559486    | -214.4586       |
| **Chlorophyll-a** | (2, 1, 2) | (1, 1, 1, 12)      | 0.000345  | 0.018575   | 0.014663   | -238.368237    | -225.417203     |
| **SSC**        | (2, 1, 2) | (2, 1, 2, 12)      | 0.007427  | 0.086178   | 0.064635   | -91.344099     | -74.692771      |
| **DOM**        | (1, 1, 1) | (2, 1, 1, 12)      | 0.006117  | 0.078212   | 0.025275   | -235.73287     | -224.631984     |
| **NDWI**       | (2, 1, 2) | (1, 1, 1, 12)      | 0.001918  | 0.043794   | 0.033936   | -153.056565    | -140.105532     |
| **NDVI**       | (2, 1, 2) | (1, 1, 1, 12)      | 0.003382  | 0.058151   | 0.045835   | -125.781392    | -112.830359     |

**Table 1.** Best SARIMA model performance for each water quality parameter.

While most SARIMA models demonstrated strong predictive capabilities, further refinement is needed for models like **DOM** to ensure reliable forecasts. The **Turbidity** and **Chlorophyll-a** models performed exceptionally well, highlighting their robustness in water quality forecasting.

## Future Work
- Refine models, particularly for DOM, to enhance prediction accuracy.
- Incorporate real-time data for continuous monitoring and timely decision-making.
- Explore alternative models for water quality forecasting.

## Conclusion
This project demonstrates the utility of remote sensing and SARIMA models in forecasting water quality. Our findings provide valuable insights for water management in Delhi, with certain models showing high accuracy in predicting future pollution levels.

