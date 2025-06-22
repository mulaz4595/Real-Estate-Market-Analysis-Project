# Real Estate Price Prediction

A machine learning project to predict house prices using property features and location data.

## Dataset

This project uses a Kaggle dataset containing 2,226,382 real estate records with 12 features including property details, location, and pricing information.

### Dataset Overview
- **Records**: 2,226,382 properties
- **Features**: 12 columns (8 numerical, 4 categorical)
- **Memory Usage**: 203.8+ MB

### Key Features
- `price`: Property sale price (target variable)
- `house_size`: Square footage of the property
- `bed`: Number of bedrooms
- `bath`: Number of bathrooms
- `acre_lot`: Lot size in acres
- `city`, `state`, `zip_code`: Location information
- `status`: Property status
- `prev_sold_date`: Previous sale date
- `brokered_by`: Broker information

## Data Processing

### Missing Values Handling
The dataset contains missing values across multiple columns:
- `house_size`: 568,484 missing values
- `bed`: 481,317 missing values
- `bath`: 511,771 missing values
- `prev_sold_date`: 734,297 missing values
- Other columns have varying amounts of missing data

### Feature Engineering
Created additional features to improve model performance:
- **Price Categories**: Budget, Mid-range, High-end, Luxury
- **Price per Square Foot**: Calculated from price and house_size
- **Total Rooms**: Sum of bedrooms and bathrooms

### Geographic Distribution
Analysis focused on top 15 states by property count:
1. California: 190,055 properties
2. Florida: 182,543 properties
3. Texas: 158,107 properties
4. New York: 67,081 properties
5. Illinois: 64,057 properties

## Model Development

### Data Preparation
- Filtered to top 10 states for model training
- Final dataset: 936,955 properties
- Features: 13 columns including state dummy variables
- Train/Test split: 80/20

### Models Tested
1. **Linear Regression**
   - R² Score: 0.3984
   - Mean Absolute Error: $310,228

2. **Random Forest** (Best Model)
   - R² Score: 0.4566
   - Mean Absolute Error: $256,421

### Feature Importance
Top contributing features to price prediction:
1. House Size: 43.8%
2. Number of Bathrooms: 32.7%
3. California Location: 8.3%
4. Number of Bedrooms: 6.7%
5. New York Location: 3.0%

## Results

The Random Forest model achieved the best performance:
- **R² Score**: 0.4566 (explains 45.7% of price variation)
- **Mean Absolute Error**: $256,421

### Key Insights
- House size and bathroom count are the strongest predictors of price
- Geographic location significantly impacts property values
- California and New York show premium pricing effects
- Model explains nearly half of the price variation in the dataset

## Usage

The trained model can predict house prices based on:
- Property size and room configuration
- Location (state-level)
- Bathroom and bedroom counts

## Requirements

- Python 3.x
- pandas
- scikit-learn
- numpy
- matplotlib (for visualizations)

## Data Source

Dataset sourced from Kaggle containing comprehensive real estate transaction data across multiple U.S. states.
