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
The SARIMA models produced varying levels of accuracy for each water quality parameter. Below is a summary of the model performance for key indicators:

1. **Turbidity**:
   - **Model Order**: (1, 1, 1), Seasonal Order: (2, 1, 1, 12)
   - **MSE**: 0.00045, **RMSE**: 0.0212, **MAE**: 0.0168
   - **AIC**: -225.56

2. **Chlorophyll-a**:
   - **Model Order**: (2, 1, 2), Seasonal Order: (1, 1, 1, 12)
   - **MSE**: 0.00035, **RMSE**: 0.0186, **MAE**: 0.0147
   - **AIC**: -238.37

3. **SSC**:
   - **Model Order**: (2, 1, 2), Seasonal Order: (2, 1, 2, 12)
   - **MSE**: 0.00743, **RMSE**: 0.0862, **MAE**: 0.0646
   - **AIC**: -91.34

4. **DOM**:
   - **Model Order**: (1, 1, 1), Seasonal Order: (2, 1, 1, 12)
   - **MSE**: 0.00612, **RMSE**: 0.0782, **MAE**: 0.0253
   - **AIC**: -235.73
   - *Note*: DOM model displayed inconsistent long-term predictions, suggesting possible overfitting.

5. **NDWI**:
   - **Model Order**: (2, 1, 2), Seasonal Order: (1, 1, 1, 12)
   - **MSE**: 0.00192, **RMSE**: 0.0438, **MAE**: 0.0339
   - **AIC**: -153.06

6. **NDVI**:
   - **Model Order**: (2, 1, 2), Seasonal Order: (1, 1, 1, 12)
   - **MSE**: 0.00338, **RMSE**: 0.0582, **MAE**: 0.0458
   - **AIC**: -125.78

While most SARIMA models demonstrated strong predictive capabilities, further refinement is needed for models like DOM to ensure reliable forecasts. The turbidity and chlorophyll-a models performed exceptionally well, highlighting their robustness in water quality forecasting.

## Future Work
- Refine models, particularly for DOM, to enhance prediction accuracy.
- Incorporate real-time data for continuous monitoring and timely decision-making.
- Explore alternative models for water quality forecasting.

## Conclusion
This project demonstrates the utility of remote sensing and SARIMA models in forecasting water quality. Our findings provide valuable insights for water management in Delhi, with certain models showing high accuracy in predicting future pollution levels.

