# Car Price Prediction

A machine learning model that predicts the resale price of used cars based on attributes such as brand, manufacturing year, kilometers driven, and fuel type. Includes an interactive Streamlit web app for live predictions.

## Overview

This project uses the CAR DETAILS FROM CAR DEKHO dataset (a public dataset of used car listings) to train a Linear Regression model that estimates a car's selling price. The trained model is deployed through a Streamlit interface where users can select a car's brand, year, mileage, fuel type, and other details to get an instant price estimate.

## Dataset

- Source: [CAR DETAILS FROM CAR DEKHO](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho) (Kaggle)
- 8,128 used car listings with features including name, year, selling price, km driven, fuel type, seller type, transmission, owner history, mileage, engine capacity, max power, and seat count
- Not included in this repo due to size — download it separately and save as `Cardetails.csv` in the project root before running the notebook

## Data Preprocessing

- Removed the `torque` column
- Dropped rows with missing values (221 rows missing mileage, engine, max power, or seats)
- Removed 1,189 duplicate listings, leaving 6,718 clean records
- Extracted the car brand from the full listing name (e.g., "Maruti Swift Dzire VDI" became "Maruti")
- Cleaned numeric fields with embedded units (e.g., "23.4 kmpl" became 23.4) for mileage, engine, and max power
- Label-encoded categorical columns: brand, fuel type, seller type, transmission, and owner history

## Model

- Algorithm: Linear Regression (scikit-learn)
- Train/test split: 80/20
- Input features: brand, year, km driven, fuel type, seller type, transmission, owner, mileage, engine, max power, seats
- Target: selling price

## Tech Stack

- Python
- pandas, numpy
- scikit-learn
- Streamlit (web app)

## Project Structure

```
├── Car_Price_Model.ipynb   # Data cleaning, preprocessing, and model training
├── app.py                  # Streamlit app for live predictions
├── model.pkl               # Trained Linear Regression model
├── requirements.txt
└── README.md
```

## Setup & Usage

1. Clone the repo and install dependencies:
   ```
   pip install -r requirements.txt
   ```
2. Download the dataset from Kaggle and place it as `Cardetails.csv` in the project root.
3. (Optional) Re-run `Car_Price_Model.ipynb` to retrain the model — this regenerates `model.pkl`.
4. Launch the app:
   ```
   streamlit run app.py
   ```
5. Select the car's brand, year, kilometers driven, fuel type, and other details in the app, then click **Predict** to get an estimated resale price.

## Future Improvements

- Add quantitative model evaluation (R², MAE, RMSE) and compare against other regression models such as Random Forest or XGBoost
- Replace manual label encoding with one-hot encoding for better generalization to unseen categories
- Add input validation and error handling in the Streamlit app

## Author

N Jhansi Mahalakshmi
[LinkedIn](https://linkedin.com/in/n-jhansi-mahalakshmi/) · [GitHub](https://github.com/NJhansiMahalakshmi)
