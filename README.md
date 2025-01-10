# Rainfall Prediction in Bangladesh

## 1. Introduction
Bangladesh is an agricultural country where rainfall prediction plays a crucial role due to the heavy reliance of its population on agriculture. Accurate rainfall forecasting is a challenging and complex task, given the dynamic and unpredictable nature of rainfall patterns in the region.

In this study, we focus on monthly rainfall prediction across 35 weather stations in Bangladesh, using data collected from 1948-2022. The rainfall data was sourced from various online platforms and carefully processed to create a comprehensive weather dataset. For prediction, we implemented a range of machine learning models, including Linear Regression and Random Forest, as well as several deep learning models. Additionally, this project introduces a novel GRU-Attention with XGBoost architecture, which demonstrates superior performance compared to the other models evaluated.

---

## 2. Dataset Preparation
Preparing the dataset was one of the most challenging aspects of this project, as rainfall data for Bangladesh is not readily available in a centralized source. To address this, a multi-step process was adopted:

1. **Data Collection**: A dataset was initially sourced from Kaggle, containing weather data for various stations in Bangladesh from 1948 to 2013. To extend this dataset, additional data was collected from the official website of the Bangladesh Agricultural Research Council, covering rainfall records for various stations up to 2022.

2. **Data Concatenation**: The datasets were concatenated to form a unified dataset. This required:
   - Resolving inconsistencies in data formats.
   - Handling missing values.
   - Ensuring accurate alignment of records across time and stations.

The resulting dataset provided a robust foundation for analysis and modeling. A preview of the dataset is shown in Figure 1.

---

## 3. Compilation of Results
For the models tested, the compiled results are summarized in Table 2.

| ML Model                   | R² Score  | RMSE Score  |
|----------------------------|------------|-------------|
| Multiple Linear Regression | 0.676096   | 117.853209  |
| Polynomial Regression      | 0.779087   | 97.329476   |
| Decision Tree Model        | 0.737548   | 106.085994  |
| k-Nearest Neighbors        | 0.751117   | 103.307324  |
| Support Vector Machine     | 0.670801   | 118.812651  |
| Random Forest Model        | 0.780543   | 97.008062   |
| AdaBoost Regressor         | 0.718801   | 109.809502  |
| Stacking Regressor         | 0.756089   | 102.270203  |
| Artificial Neural Network  | 0.778553   | 97.446908   |
| GRU with Attention + XGBoost | 0.795308 | 93.687942   |
| **LSTM with Attention + XGBoost** | **0.8033**  | **65.25**    |

The **LSTM with Attention and XGBoost** model achieves the highest R² score of 0.8033 and the lowest RMSE score of 65.25, indicating superior performance compared to other models. The GRU with Attention and XGBoost model also shows strong results with an R² score of 0.7953 and RMSE score of 93.6879.

Deep learning models consistently outperform traditional machine learning models in both R² score and RMSE.

---

## 4. Comparison with Benchmark Models
In the paper under consideration [3], a different dataset was used, consisting of two datasets (1200 data points each) for the cities of Darwin and Perth. Table 3 compares the performance of our model with the benchmark Encoder-Decoder with Attention Mechanism model:

| Dataset       | Model from Paper (R²) | Our Model (R²) |
|---------------|------------------------|----------------|
| Darwin        | 0.832                  | 0.805          |
| Perth         | 0.796                  | 0.753          |
| Bangladesh    | 0.7094                 | **0.8033**     |

Our model achieves superior performance on the Bangladeshi dataset compared to the benchmark Encoder-Decoder with Attention Mechanism model, demonstrating its adaptability and effectiveness for rainfall prediction in Bangladesh.

---

## 5. Conclusion
In this project, we proposed an **LSTM model with Attention Mechanism combined with XGBoost** to predict rainfall at various stations in Bangladesh. The results highlight the effectiveness of our proposed model, which outperforms traditional machine learning models and is competitive with benchmark models from the literature.

### Future Work
Future work could focus on:
- Integrating additional features, such as external climate indices or satellite data.
- Optimizing hyperparameters to further enhance performance.
- Extending this framework to other datasets and regions.

