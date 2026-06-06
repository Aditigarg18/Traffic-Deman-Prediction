Traffic Demand Prediction – Hackathon Submission

Overview

For this challenge, the objective was to predict traffic demand using information related to location, road characteristics, weather conditions, and time of day. Since traffic patterns are influenced by both location and timing, I focused on extracting useful information from the available features while keeping the solution simple, reliable, and easy to reproduce.

Approach

I started by exploring the dataset to understand the available features, identify missing values, and examine the overall structure of the data.

One of the most important features was the timestamp column. Instead of using the raw timestamp directly, I extracted the hour and minute information because traffic demand typically changes throughout the day. I also created an additional feature called is_peak_hour to capture common rush-hour periods when traffic volume is generally higher.

After extracting these features, the original timestamp column was removed since its information had already been represented in a more useful form.

Data Cleaning and Preprocessing

Before training the model, missing values were handled appropriately.

Missing values in categorical columns such as RoadType and Weather were replaced with the value "missing".
Missing values in the Temperature column were filled using the median temperature from the training dataset.
Categorical columns were converted to string format to ensure compatibility with the selected machine learning model.

These preprocessing steps helped create a clean and consistent dataset for training.

Features Used

The final model was trained using the following features:

geohash
day
RoadType
NumberofLanes
LargeVehicles
Landmarks
Temperature
Weather
hour
minute
is_peak_hour

These features provide information about location, road infrastructure, weather conditions, and time-based traffic behavior.

Model Selection

For this problem, I selected CatBoost Regressor because it performs well on structured tabular datasets and handles categorical features effectively with minimal preprocessing.

Model configuration:

Iterations: 2000
Depth: 8
Learning Rate: 0.05
Loss Function: RMSE

Validation

To evaluate performance before generating final predictions, the training dataset was split into training and validation sets.

The model achieved a validation R² score of approximately 0.945, indicating strong predictive performance on the validation data.

Tools and Libraries Used

The solution was implemented using:

Python
Jupyter Notebook
Pandas
NumPy
Scikit-learn
CatBoost

These libraries were used for data preprocessing, feature engineering, model training, validation, and prediction generation.

Files Included

This submission package contains:

traffic_prediction.ipynb – Complete implementation notebook.
submission.csv – Final prediction file generated for the test dataset.
README.txt – Description of the methodology and approach.

Conclusion

This solution combines straightforward feature engineering with a robust machine learning model. The focus was on extracting useful information from time-based features, handling missing values appropriately, and leveraging CatBoost's ability to work efficiently with categorical and numerical data. The trained model was then used to generate traffic demand predictions for the provided test dataset.
