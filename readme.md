# F1 Championship Predictor

## Overview

The **F1 Championship Predictor** is a tool designed to predict the final standings of the Formula 1 Drivers' and Constructors' Championships for the current season. Utilising historical data and statistical modeling, it estimates each driver's and constructor's final points based on their recent performance trends.

## How It Works

The predictor operates through the following steps:

1. **Data Collection**: Uses the `fastf1` library to fetch historical race data, including driver standings, race results, and event schedules.

2. **Data Preparation**: Splits the season's calendar into past and future events relative to the current date. It then collects points scored by drivers in past races.

3. **Rate Calculation**: Calculates an Exponential Moving Average (EMA) for each driver to determine their recent rate of scoring points. An optimal alpha value for the EMA is found by testing different values across past seasons to minimize prediction error.

4. **Prediction**: Estimates the final points for each driver and constructor by projecting their performance over the remaining races, considering both standard and sprint events.

5. **Visualization**: Displays the results in tabular form and generates bump charts to illustrate changes in positions from the current standings to the predicted final standings.

## Installation

### Prerequisites

- Python 3.7 or higher
- Jupyter Notebook or JupyterLab

### Steps

1. **Clone the Repository**

   ```bash
   git clone "{this_repo_url}"
   cd f1-championship-predictor
   ```

2. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

   The `requirements.txt` file includes all necessary Python packages:
   - `fastf1`
   - `pandas`
   - `matplotlib`
   - `tqdm`

## Usage
1. **Open and Run the Notebook**

   - Open the `f1_championship_predictor.ipynb` notebook.
   - Run all cells sequentially.
   - The notebook will:
     - Calculate the optimal alpha value for the EMA.
     - Predict the final standings for the current season.
     - Display tables and generate bump charts for both Drivers' and Constructors' Championships.

## Requirements

- **Python Packages**:
  - `fastf1`
  - `pandas`
  - `matplotlib`
  - `tqdm`

- **Internet Connection**: Required to fetch data using the `fastf1` library.

## Notes

- **Optimal Alpha Value**: The alpha value for the EMA is crucial for prediction accuracy. The notebook includes a method to determine the optimal alpha by testing different values across previous seasons (2018-2023). By default, recalculate variable is false and therefore this alpha value will use a default which makes the notebook run a lot faster.

- **Data Accuracy**: Predictions are based on data provided by the `fastf1` library and the model's assumptions.

- **Limitations**:
  - Assumes drivers will continue performing at their recent rate.
  - Does not account for unforeseen events (e.g., injuries, team changes, penalties, car updates).
  - Does not factor in substitute drivers

## Acknowledgments

- **fastf1**: For providing access to Formula 1 data.
- **Ergast API**: For historical F1 data.