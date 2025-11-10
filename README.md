# Inventory Demand Forecasting using Prophet and LSTM

A reproducible time series forecasting project comparing classical and deep learning methods on a multi-store retail dataset.  
Developed to demonstrate data preprocessing, temporal modeling, and model evaluation using Python, Prophet, and PyTorch.

---

## Overview

This project investigates short-term demand forecasting at the store-item level.  
The objective is to predict daily sales, evaluate model performance, and visualize temporal dynamics in a clear and interpretable way.

---

## Objective

- Forecast daily product-level demand for multiple stores.  
- Compare statistical and deep learning models.  
- Evaluate performance using MAE, RMSE, and MAPE.  
- Ensure transparency and reproducibility in the modeling workflow.

---

## Dataset

- **Source:** [Kaggle – Demand Forecasting Challenge](https://www.kaggle.com/competitions/demand-forecasting-kernels-only)  
- **Period:** 2013–2017  
- **Entities:** 10 stores × 50 items  
- **Variables:** `date`, `store`, `item`, `sales`  

This dataset provides a stable, univariate structure suitable for benchmarking forecasting models.

---

## Methods

| Model | Description | Library |
|-------|--------------|----------|
| Naive and Moving Average | Simple baseline models based on recent values | pandas |
| Prophet | Additive model capturing trend and yearly seasonality | Prophet (cmdstan) |
| LSTM | Neural sequence model using sliding windows | PyTorch |

---

## Results

### Quantitative Summary

| Model | MAE | RMSE | MAPE |
|:------|----:|----:|----:|
| Prophet | **6.80** | **8.46** | **14.41** |
| LSTM | 8.65 | 10.81 | 18.59 |
| Naive | 17.53 | 21.31 | 28.64 |
| MA(30d) | 18.06 | 22.10 | 28.41 |

Prophet achieved the lowest overall error across all metrics, while LSTM also performed well on smoother time series.

---

### Forecast Examples

**Baseline Forecast**
<img width="1000" height="490" alt="image" src="https://github.com/user-attachments/assets/9c75035e-a35e-4aa8-a04a-572a8f7508d2" /> 

**Prophet Forecast**
<img width="1000" height="490" alt="image" src="https://github.com/user-attachments/assets/6027f41b-02b6-4bef-b3da-06901425f7d0" /> 

**LSTM Forecast**
<img width="1000" height="490" alt="image" src="https://github.com/user-attachments/assets/7eb9252f-7c54-4196-b732-183856613a7e" /> 

### Aggregated Metrics Visualization  
<img width="590" height="290" alt="image" src="https://github.com/user-attachments/assets/4ad3f0cd-8b54-48a1-a0df-9e8a58b1904e" />

---

## Insights

- Clear annual seasonality and trend patterns are visible in most store–item combinations.  
- Prophet captured long-term trends efficiently with minimal tuning.  
- LSTM performed competitively but tended to smooth rapid variations.  
- Baseline models provide transparent performance references for context.

---
