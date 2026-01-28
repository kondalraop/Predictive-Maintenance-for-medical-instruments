## Data Set Information:

The data belongs to a medical device compnay and it is obtained from CRM Data base and modified for capstone project.

#### Business Understanding

Predictive Maintenance (PdM) is a data-driven approach that uses historical and real-time data to predict when equipment is likely to fail. Instead of performing maintenance on a fixed schedule or after a breakdown occurs, predictive maintenance enables organizations to service equipment just in time, reducing downtime, costs, and operational risk.

In healthcare, predictive maintenance is especially critical because medical instruments directly impact patient safety, procedure efficiency, and regulatory compliance. Unexpected instrument failures can delay surgeries, increase operational costs, and compromise care quality.

This project applies predictive maintenance concepts to medical instruments, using regression models to predict instrument failure counts over the last 12 months based on operational, maintenance, and sterilization data.

What factors contribute most to medical instrument failures, and can we accurately predict the failure count over the last 12 months based on operational and maintenance logs?

## Data Understanding
Initial data exploration focuses on:

- Distribution of failure counts across instruments

- Correlation between usage intensity and failures

- Impact of maintenance frequency on reliability

- Relationship between surgery complexity and instrument wear

Key observations include:

- Higher usage and complex surgeries tend to increase failure rates

- Longer gaps between maintenance correlate with higher failure counts

- Frequent sterilization may contribute to long-term material degradation

#### Attribute Information
Instrument_ID:            Unique identifier for each medical instrument

Usage_Count:              Number of times the instrument was used

Surgery_Type:             Category of surgery performed

Surgery_Complexity:	      Complexity level (e.g., low, medium, high)

Surgeon_Experience:	      Years or level of surgeon experience

Time_Since_Maintenance:	  Time elapsed since last maintenance (days/months)

Repair_Count:	            Number of historical repairs

Sterilization_Frequency:	Number of sterilization cycles

Failure_Count_12M:      	Number of failures in the last 12 months (target variable)

#### Data Preparation and Visualization
Data preparation steps include:

- Encoding categorical variables (surgery type, complexity)

- Normalizing or scaling numerical features

- Aggregating time-based metrics where required

Visualization techniques used:

- Histograms and box plots for failure distributions

- Correlation heatmaps

- Scatter plots comparing usage, maintenance, and failures

These visualizations help identify trends, outliers, and relationships before modeling.

## Data Cleansing, Processing, and Modeling

#### Data Cleansing
- Removal of duplicate records

- Handling missing values using imputation or removal

- Outlier detection and treatment

#### Data Processing
- Feature engineering (e.g., maintenance-to-usage ratios)

- Encoding categorical variables

- Train-test data split

#### Modeling

- Regression models (Linear Regression, Random Forest)

- Model evaluation using metrics such as MAE and RMSE 

- Comparison of model performance to select the best predictor

## Process Summary
- Defined the predictive maintenance problem in a healthcare context

- Collected and understood operational and maintenance data

- Cleaned and prepared the dataset for analysis

- Visualized key trends and relationships

- Built regression models to predict 12-month failure counts

- Evaluated model accuracy and identified key failure drivers

## Model Performacnce Evaluation

Two regression models were trained and evaluated to predict the failure count over the last 12 months:

- Linear Regression

- Random Forest Regressor
  
- Jupiner notebook updated in Github repository "https://github.com/kondalraop/Predictive-Maintenance-for-medical-instruments/blob/main/Predictive-Maintenance-for-medical-instruments.ipynb"

  The models were evaluated using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE), where lower values indicate better predictive performance.

#### Model Performance Summary

| Model            | MAE        | RMSE       |
|------------------|------------|------------|
| Linear Regression| 1.272980   | 1.589070   |
| Random Forest    | 1.301347   | 1.629951   |

  
## Interpretation of Results

- Linear Regression achieved the lowest MAE and RMSE, indicating slightly better overall prediction accuracy compared to Random Forest.

- The lower MAE suggests that, on average, Linear Regression predictions are closer to the actual failure counts.

- The lower RMSE indicates fewer large prediction errors, making Linear Regression more stable and reliable for this dataset.

## Model Comparison Insights

- Although Random Forest is capable of capturing non-linear relationships, its performance did not surpass Linear Regression in this case.

- This outcome suggests that the relationship between operational/maintenance variables and failure counts is largely linear in nature.

- The relatively close performance values indicate that both models are viable, but Linear Regression offers better interpretability and simplicity, which is advantageous in healthcare and maintenance decision-making contexts.

## Model Selection Decision

- Based on the evaluation metrics:

- Linear Regression is selected as the preferred model due to its superior accuracy, lower error metrics, and ease of interpretation.

- The model provides clear insights into how usage, maintenance frequency, and sterilization practices influence instrument failures.

## Key Outcomes
The predictive maintenance model demonstrates that medical instrument failures can be effectively predicted using historical operational and maintenance data. Among the models evaluated, Linear Regression performed marginally better than Random Forest, indicating that simpler statistical models can be highly effective when the underlying relationships are well-structured.

These results support the use of regression-based predictive maintenance to:

- Proactively schedule maintenance

- Reduce unexpected equipment downtime

- Improve patient safety and operational efficiency


