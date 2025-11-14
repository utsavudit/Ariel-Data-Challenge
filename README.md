# Ariel Data Challenge: Feature Engineering & LightGBM Modeling

## **Overview**

This repository contains code and documentation for the **Ariel Data Challenge 2025**. The objective is to build a robust machine learning pipeline to predict exoplanet transit properties from time-series telescope observations and calibration data. The approach combines extensive feature engineering with state-of-the-art LightGBM models.

## **Dataset**

- Time-series flux and calibration files in parquet format (FGS1, AIRS-CH0)
- Supplemental metadata for planets and stars

## **Pipeline Steps**

- **Data Loading:** Efficient batch loading of parquet files using pandas.
- **Feature Engineering:**
  - Rolling mean and windowed statistics on flux signals  
  - Signal smoothing, detrending, autocorrelation  
  - Extraction of astrophysically relevant metrics (transit depth, flux variance, skewness, etc.)
- **Model Training:**  
  - Cross-validated LightGBM regression  
  - Centralized configuration
- **Validation:**  
  - Cross-validation to avoid overfitting  
  - Metric: Calibrated OOF GLL Score
- **Prediction & Submission:**  
  - Prediction on test planets  
  - Batch submission CSV creation

## **Usage**

1. Place the Ariel datasets under your configured input directory.
2. Run the notebook completely in a Jupyter environment with all dependencies (`pandas`, `numpy`, `lightgbm`, `scikit-learn`, `matplotlib`, `tqdm`, `scipy`, `joblib`, `pickle`).
3. Configuration and paths are handled by the `Config` class in the notebook.
4. Output predictions and model files are saved in designated directories.

## **Key Results**

- Achieved a calibrated out-of-fold GLL score of **0.227** (update with your score)
- Feature engineering dramatically improved model accuracy for detection/regression

## **Visualizations**

- Light curve and raw/processed signal plots for multiple exoplanets
- Demonstrates both raw and cleaned data

## **Acknowledgements**

- Ariel Data Challenge organizers  
- Libraries: [LightGBM](https://github.com/microsoft/LightGBM), [scikit-learn](https://scikit-learn.org/), [pandas](https://pandas.pydata.org/)

## **License**

MIT License
