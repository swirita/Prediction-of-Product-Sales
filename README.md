# Prediction-of-Product-Sales

## Project Overview

This project explores Product Sales dataset to better understand the factors that affect item sales across different outlets.
The analysis includes data exploration and visualization of numerical and categorical features to identify trends, patterns, and possible relationships between variables.

The project uses:

* Python
* Pandas
* Matplotlib
* Seaborn

---

# Key Visuals & Insights

## 1. Histogram of Item_Outlet_Sales
<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/a1c0ed87-b3c9-483f-b26e-d8e6e6b46912" />

### Insight:

Most items have relatively low sales, while a small number of items have very high sales, creating a right-skewed distribution.

---

## 2. Correlation Heatmap
<img width="928" height="699" alt="image" src="https://github.com/user-attachments/assets/42d0440a-931a-4bf4-96cd-b6c1a879dceb" />

### Insight:

Maximum Retail Price showed one of the strongest positive relationships with Item_Outlet_Sales, suggesting that higher-priced items tend to generate higher sales.

## 3. Regression Plot: Maximum Retail Price vs Item Outlet Sales
<img width="558" height="393" alt="image" src="https://github.com/user-attachments/assets/6a75d8c0-35af-4882-9ae0-d8f8b9bacdd6" />

### Insight:

Items with higher retail prices tend to have higher outlet sales, showing a positive relationship between price and sales.

## 4. Countplot of Item Type
<img width="859" height="550" alt="image" src="https://github.com/user-attachments/assets/360cb170-eb34-4c0a-a88a-ce767ac05d61" />

### Insight:

Fruits and Vegetables and Snack Foods are the most common item categories, while Seafood and Breakfast items appear least frequently.

### Insight:

Fruits and Vegetables and Snack Foods are the most common item categories, while Seafood and Breakfast items appear least frequently.

## Model Information

This project uses a **Random Forest Regressor** to predict **Item Outlet Sales**. The model was optimized using **GridSearchCV** with 3-fold cross-validation to find the best combination of hyperparameters.

### Feature Engineering

Several preprocessing and feature engineering steps were applied before training:

* Created **`Outlet_Age`** from `Outlet_Establishment_Year`.
* Extracted **`Item_Category`** from `Item_Identifier`.
* Labeled non-consumable (`NC`) items as **`Non-Edible`** in `Item_Fat_Content`.
* Grouped `Item_MRP` into **Low**, **Medium**, and **High** price categories.
* Standardized inconsistent `Item_Fat_Content` values (e.g., `LF` → `Low Fat`, `reg` → `Regular`).
* Removed identifier columns (`Item_Identifier` and `Outlet_Identifier`) since they do not provide predictive value.

### Model Performance

The tuned model achieved an **R² score of 0.602** on the test set, indicating that it explains about **60.2% of the variation** in outlet sales. The training and testing scores are very similar, suggesting that the model generalizes well and does not suffer from significant overfitting.

While there is room for further improvement, the current model provides stable and reliable predictions for this dataset.
