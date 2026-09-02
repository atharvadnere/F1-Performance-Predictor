# F1 Race Position Predictor

A simple machine learning project that predicts a driver's finishing position in a Formula 1 race based on their starting grid position. I have chosen this topic because of my obsession with Formula 1 and the way that the strategies are made based on realtime telemetric data.

![Grid vs Finish Position](Data/grid_vs_finish.png)

## Dataset

Data from [toUpperCase78/formula1-datasets](https://github.com/toUpperCase78/formula1-datasets), seasons 2021–2024.

## What it contains

I have built a Linear Regression model trained on race data from the 2021 to 2024 seasons. The model takes a driver's starting grid position and predicts their finishing position. I have also made sure that the predictions are visualized through graphs, and the notebook includes metrics evaluating the model's performance.

**Tech:** Python, pandas, matplotlib, scikit-learn

## Key Insight

> I observed that the model's predictions are capped between **3.33** (for a P1 start) and **15.68** (for a P20 start). This means that it can never predict a podium finish or a last-place finish, no matter how well or badly a driver actually performs.

This isn't because of real-world race unpredictability. I found mathematics to be the reason behind this. It's a structural limit of linear regression itself. The model learns a fixed slope and intercept, and that equation mathematically caps how extreme its output can ever be. A driver starting on pole is *always* predicted to finish somewhere between P3 and P4, even in a race where they dominate from lights to flag.


## Results

| Metric | Value |
|--------|-------|
| MAE    | 2.60  |
| RMSE   | 3.37  |
| R²     | 0.57  |

## Limitations

I chose for the model to have a single feature, which is the starting grid position to predict finishing position. In reality, race outcomes depend on a lot more factors like weather conditions, tire compound and strategy, pit stop timing, mechanical or electrical failures, safety cars, and driver/team form on the day. None of that is captured here.

An R² of 0.57 reflects this directly as grid position explains a meaningful share of the outcome, but a large part is left to factors outside this model's scope. Extending it with additional features (team/constructor strength, weather data, tire choice) or trying a more flexible model (like Random Forest) would likely close some of that gap. See the notebook's conclusion for more on this.

## How to run

1. Clone this repository
2. Install the required libraries: `pip install pandas matplotlib scikit-learn`
3. Make sure the CSV files are in the same folder as `f1_predictor.ipynb`
4. Open [`f1_predictor.ipynb`](f1_predictor.ipynb) and run all cells in order
