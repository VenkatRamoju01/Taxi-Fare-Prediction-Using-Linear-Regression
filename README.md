# NYC Taxi Fare Prediction Using Multiple Linear Regression

## Project Overview
This project aims to build a multiple linear regression model to predict taxi fares for New York City taxis. The NYC Taxi and Limousine Commission (NYC TLC) is responsible for licensing and regulating the city's taxis and for-hire vehicles. This model can assist in estimating taxi fares before the ride, aiding both customers and regulatory processes.

The project follows the **PACE** framework:
- **Plan**: Understanding the problem and dataset.
- **Analyze**: Conducting Exploratory Data Analysis (EDA) and Feature Engineering.
- **Construct**: Building and training the regression model.
- **Evaluate**: Assessing the model's performance and making recommendations.

## Dataset
The dataset used in this project is based on historical data provided by the NYC TLC, including trip details such as pickup and dropoff times, trip distance, and fare amounts.

## Project Structure
### Plan Stage
**Task 1**: Import necessary libraries and load the dataset.  
Objective: Gain a business understanding of the problem.

### Analyze Stage
**Task 2a**: Perform Exploratory Data Analysis (EDA)  
- Check dataset shape and information.
- Identify and handle missing data or duplicates (none were found).
- Conduct descriptive statistics, uncovering potential outliers in columns like `tip_amount` and `total_amount`.

**Task 2b**: Convert datetime columns  
- Convert `tpep_pickup_datetime` and `tpep_dropoff_datetime` to datetime objects to allow for time-based analysis.

**Task 2c**: Create a `duration` column  
- Calculate trip duration by subtracting pickup time from dropoff time.

**Task 2d**: Handle outliers  
- Use interquartile range (IQR) to cap extreme outliers in `fare_amount` and `duration` columns.

### Feature Engineering
**Task 3a**: Create a `mean_distance` column  
- Group trips by pickup and dropoff locations to calculate the mean distance for each group.

**Task 3b**: Scatter plot  
- Visualize the relationship between `mean_duration` and `fare_amount`.

### Construct Stage
**Task 4**: Model Preparation  
- Drop redundant or irrelevant features.
- Encode categorical variables and split the data into training and testing sets.
- Standardize the feature variables to ensure they contribute equally to the model.

**Task 5**: Train the Model  
- Fit the multiple linear regression model to the training data.

### Evaluate Stage
**Task 6**: Model Evaluation  
- Evaluate model performance using metrics such as **Mean Absolute Error (MAE)**, **Root Mean Squared Error (RMSE)**, and **R-squared**.
- Perform residual analysis to check for model bias.

**Task 7**: Results Visualization  
- Create scatterplots to visualize actual vs. predicted values.
- Plot residuals to ensure the errors are evenly distributed.

**Task 8**: Model Coefficients  
- Retrieve the model coefficients to understand the relative importance of each feature in predicting taxi fares.

## Results
- The final model achieved an R² score of **0.868**, indicating that approximately 86.8% of the variance in fare amounts can be explained by the model.
- **Mean Absolute Error** on test data was low, indicating the model's ability to predict fares with reasonable accuracy.
- Residuals were normally distributed, confirming that the model is not biased and is generalizing well.

## Conclusion
- The **Multiple Linear Regression** model successfully predicts taxi fares based on features like trip distance, duration, and pickup/dropoff locations.
- The project highlights the importance of **exploratory data analysis** and **feature engineering** in improving the model’s predictive performance.
- Further improvements can be made by incorporating additional variables or using more advanced machine learning techniques like **Gradient Boosting**.

