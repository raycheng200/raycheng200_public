Predicting Irrigation Need (Kaggle Playground Series)

Summary: Predict agricultural water demand using XGBoost and Optuna. Accurately predicting irrigation needs (Low/Medium/High) based on environmental sensor data. Achieved a balanced accuracy of 0.96243.

In numerical columns, I imputed median instead of mean because median is more robust when the data is skewed. I filled a value of "Missing" in absent categorical columns.

Engineered Features:
I created features "Climate_Stress" and "Water_Source_Efficiency". When the temperature is much higher, the irrigation need is higher. When the humidity is higher, the irrigation need is lower. So I defined a nonlinear interaction X_train['Climate_Stress']=X_train['Temperature_C']/(X_train['Humidity']+1) to avoid division by zero.
When 'Soil_Moisture' is higher, the irrigation need is lower. Same for 'Rainfall_mm'. So I defined X_train['Water_Source_Efficiency'] = X_train['Soil_Moisture'] + X_train['Rainfall_mm'].

Model Architecture: XGBoost is a gradient boosting library and Optuna is a hyperparameter optimization framework. I utilized T4 GPUs (CUDA) to accelerate the 50 trial search. I used 5-Fold stratified cross-validation to ensure the model generalizes across all irrigation levels.

License of the Kaggle Dataset:
Attribution 4.0 International (CC BY 4.0)
https://creativecommons.org/licenses/by/4.0/

Citation:
Yao Yan, Walter Reade, Elizabeth Park. Predicting Irrigation Need. https://kaggle.com/competitions/playground-series-s6e4, 2026. Kaggle.
