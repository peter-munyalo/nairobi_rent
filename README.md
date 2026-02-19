# 🏠 Nairobi Rental Price Prediction

A machine learning project to predict monthly rent for properties in Nairobi, Kenya, using features like bedrooms, bathrooms, parking, location, and estimated distance to the CBD.

## 📌 Project Overview

This project uses a dataset of rental listings in Nairobi to build regression models that estimate monthly rent. The goal is to identify key price drivers and provide a baseline model for rental price prediction.

## 📊 Dataset

- **Source:** The dataset is from the [NairobiRentPrices GitHub repository](https://github.com/Mburu-Elvis/NairobiRentPrices) by Mburu-Elvis.
- **Original Data:** Contains 231,057 rows with columns: `City`, `Location`, `Bedrooms`, `Bathrooms`, `Parking`, `Price`.
- **Cleaning Steps:**
  - Filtered to Nairobi only.
  - Removed missing prices, bedrooms, and bathrooms.
  - Filled missing parking with 0.
  - Capped prices at the 99th percentile to remove extreme outliers.
  - Standardized location names.
  - Kept only properties with 1–6 bedrooms (typical residential).

## 🛠️ Feature Engineering

- **Location Dummies:** One-hot encoding of neighborhoods.
- **Estimated Size:** Approximate square meters based on number of bedrooms (e.g., 1 bed → 50 sqm, 2 bed → 70 sqm, etc.).
- **Distance to CBD:** Manual mapping of approximate distance (km) from Nairobi CBD for each neighborhood; missing values filled with median.

## 🤖 Models Used

- **Linear Regression** (baseline)
- **Random Forest Regressor** (final model)

## 📈 Results

| Model               | MAE (KES) | R²    |
|---------------------|-----------|-------|
| Linear Regression   | 86,305    | 0.091 |
| Random Forest       | 77,853    | 0.193 |

**Key insights:**
- The most important features are **Bedrooms**, **Parking**, and **Location** (especially Lavington, Kilimani, Kileleshwa).
- Adding estimated size improved the model slightly, but distance to CBD did not add much beyond location dummies.
- The current model explains about 19% of the variance in rental prices, indicating room for improvement with more data (actual size, amenities, precise coordinates).


