# F1 Race Position Predictor

A simple machine learning project that predicts a driver's finishing position in a Formula 1 race based on their starting grid position.

## Dataset

Data from [toUpperCase78/formula1-datasets](https://github.com/toUpperCase78/formula1-datasets), seasons 2021–2024.

## What it contains

A Linear Regression model trained on race data from the 2021 to 2024 seasons. The model takes a driver's starting grid position and predicts their finishing position. Predictions are visualized through graphs, and the notebook includes metrics evaluating the model's performance.

## How to run

1. Clone this repository
2. Install the required libraries: `pip install pandas matplotlib scikit-learn`
3. Make sure the CSV files are in the same folder as the notebook
4. Open `f1_predictor.ipynb` in the "Data" folder and run all cells in order

## Results

| Metric | Value |
|--------|-------|
| MAE    | 2.60  |
| RMSE   | 3.37  |
| R²     | 0.57  |
