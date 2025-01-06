# Churn Analysis for an E-commerce Platform

This project focuses on predicting user churn for an e-commerce platform and providing actionable insights to reduce churn. The analysis includes data cleaning, feature engineering, visualization, and predictive modeling using XGBoost.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)

## Overview
The goal of this project is to:
1. **Predict which users are most likely to churn**.
2. **Provide actionable insights** to reduce churn and improve customer retention.

The project involves:
- Data cleaning and preprocessing.
- Feature engineering to derive user behavior metrics.
- Exploratory data analysis (EDA) to understand user behavior.
- Predictive modeling using XGBoost to classify churned users.

## Dataset
The dataset used in this project is `events.csv` download it from [Here](https://drive.google.com/file/d/1EkyYEYf1ICcdLcRpFfYkeQNQzj-Os6-L/view?usp=sharing) , which contains user activity data on an e-commerce platform. It includes the following columns:
- `event_time`: Timestamp of the user activity.
- `event_type`: Type of event (e.g., view, cart, purchase).
- `user_id`: Unique identifier for the user.
- `product_id`: Unique identifier for the product.
- `category_id`: Category of the product.
- `category_code`: Hierarchical category code.
- `brand`: Brand of the product.
- `price`: Price of the product.

## Features
### Key Features Engineered:
1. **User Behavior Metrics**:
   - `total_views`: Total number of product views by a user.
   - `total_carts`: Total number of products added to the cart by a user.
   - `total_purchases`: Total number of purchases made by a user.
   - `cart_to_view_ratio`: Ratio of carts to views.
   - `purchase_to_cart_ratio`: Ratio of purchases to carts.

2. **Churn Definition**:
   - A user is considered churned if their last activity was more than 30 days ago.

3. **Temporal Features**:
   - Extracted year, month, day, and hour from the `event_time` column.

4. **Frequency Encoding**:
   - Categorical columns like `event_type`, `product_id`, `brand`, `category_code`, and `category_id` were encoded using their normalized frequency.

5. **Standardization**:
   - Numerical features like `number_of_purchases`, `price`, and temporal features were standardized using `StandardScaler`.

## Installation
To run this project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/mahmoudalrefaey/Churn-E-commerce-Platform.git
   cd Churn-E-commerce-Platform
   ```
## Usage

### Run the Jupyter Notebook:
1. Open the `Churn_for_an_E-commerce_Platform.ipynb` notebook in **Jupyter** or **Google Colab**.
2. Execute the cells to perform:
   - Data cleaning.
   - Feature engineering.
   - Visualization.
   - Modeling.

### Model Training:
- The **XGBoost model** is trained on the preprocessed data to predict churn.
- The model's performance is evaluated using a **classification report**, which includes:
  - Precision.
  - Recall.
  - F1-score.

### Visualizations:
The notebook includes visualizations for:
- **Distribution of user behavior metrics** (views, carts, purchases).
- **Relationships** between views, carts, and purchases.
- **Cart-to-view** and **purchase-to-cart** ratios.

---

## Results

### Key Insights:
1. **Low Engagement**:
   - Most users have low engagement (few views, carts, or purchases), indicating a high risk of churn.

2. **Barriers to Conversion**:
   - Low cart-to-view and purchase-to-cart ratios suggest barriers in the user journey, such as:
     - Unappealing products.
     - A complicated checkout process.

3. **Actionable Takeaways**:
   - Improve product recommendations.
   - Optimize the checkout process.
   - Offer incentives like discounts or free shipping to reduce cart abandonment.

### Model Performance:
The XGBoost model achieved the following results:
- Precision: 100%
- Recall: 100%
- F1-Score: 100%
