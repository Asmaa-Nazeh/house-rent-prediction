
# House Rent Prediction Model

## Project Overview

This project aims to predict house rents based on various features such as the number of rooms (BHK), size, floor, and location. The goal is to develop a machine learning model that can estimate house rent prices accurately. The project involves **data preprocessing**, **feature engineering**, **model building**, and **evaluation**.

## Table of Contents

1. [Project Description](#project-description)
2. [Data](#data)
3. [Preprocessing Pipeline](#preprocessing-pipeline)
4. [Feature Engineering](#feature-engineering)
5. [Model Building](#model-building)
6. [Evaluation](#evaluation)
7. [Conclusion](#conclusion)

## Project Description

The dataset contains various features related to houses and apartments available for rent. The goal is to predict the `Rent` based on these features using regression models.

The project follows a clear sequence of steps to process and clean the data, engineer new features, and train a predictive model.

---

## Data

The dataset used for this project includes the following columns:
- `Posted On`: Date the listing was posted
- `BHK`: Number of bedrooms in the house
- `Rent`: Rent price of the house (target variable)
- `Size`: Size of the house in square feet
- `Floor`: Floor information (e.g., "Ground out of 2")
- `Area Type`: Type of area (e.g., "Super built-up area")
- `Area Locality`: Locality where the property is located
- `City`: City of the property
- `Furnishing Status`: Furnishing type of the property (e.g., "Unfurnished")
- `Tenant Preferred`: Tenant preference (e.g., "Family")
- `Bathroom`: Number of bathrooms
- `Point of Contact`: The person to contact for the listing

---

## Preprocessing Pipeline

The preprocessing steps include:

1. **Handling missing values**: 
   - Filled missing `Rent` values with the median value.
   - Filled missing values for numerical features with appropriate strategies (e.g., median for `Total_Floors`).

2. **Outlier removal**: 
   - Used the Interquartile Range (IQR) method to remove extreme outliers in the `Rent` column.

3. **Feature engineering**:
   - Created new features such as:
     - `Per_BHK_Size`: Size per BHK
     - `Bath_per_BHK`: Number of bathrooms per BHK
     - `Floor_No` and `Total_Floors`: Extracted from the `Floor` column
     - `Locality_Count`: Count of properties in each locality

4. **Column drop**:
   - Removed columns that were redundant or not useful for the model, such as `Posted On`, `Size`, `Bathroom`, and `BHK`.

5. **One-hot encoding**:
   - Categorical variables were one-hot encoded to convert them into numerical features.

6. **Feature scaling**:
   - Applied `StandardScaler` to scale numerical features.

---

## Feature Engineering

- **Per_BHK_Size**: Calculated the size of the house per BHK unit.
- **Bath_per_BHK**: Calculated the number of bathrooms per BHK.
- **Floor extraction**: Split the `Floor` column into `Floor_No` and `Total_Floors`.
- **Locality Count**: Count the number of listings per locality, providing additional contextual information.

---

## Model Building

After preprocessing, several models were trained on the dataset, including:

- **Linear Regression**
- **Naive Bayes**
- **K-Nearest Neighbors (KNN)**
- **Decision Tree**
- **Random Forest**
- **Support Vector Machine (SVM)**

The models were trained using the `Rent` as the target variable.

---

## Evaluation

The models were evaluated using the following metrics:

- **Mean Absolute Error (MAE)**
- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**

---

## Conclusion

In this project, we've built a rent prediction model by following a systematic data preprocessing pipeline, including handling missing data, removing outliers, feature engineering, and scaling. After building and evaluating multiple regression models, we were able to find an effective approach for predicting house rents. The model's performance can be further enhanced by tuning hyperparameters and using more advanced techniques.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

