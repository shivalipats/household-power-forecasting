# Household Power Consumption Forecasting

This project compares traditional and deep learning models for short-term time series forecasting using the UCI Individual Household Electric Power Consumption dataset.

The goal is to forecast `Global_active_power` for the next 15 minutes using the previous 120 minutes of historical data.

## Models Compared

- Naive baseline
- ARIMA
- RNN
- LSTM
- GRU
- Conv1D

## Dataset

Dataset source: UCI Machine Learning Repository  
Individual Household Electric Power Consumption dataset, ID 235.

The code downloads the dataset automatically using `ucimlrepo`.

## Project Structure

```text
household-power-forecasting/
├── README.md
├── requirements.txt
├── .gitignore
├── src/
│   └── power_forecasting.py
├── notebooks/
│   └── README.md
├── outputs/
│   └── figures/
└── data/
```

## Setup

Create and activate a virtual environment:

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

Mac/Linux:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Run

```bash
python src/power_forecasting.py
```

The script will:

1. Download the dataset.
2. Clean and interpolate missing values.
3. Create chronological train, validation, and test splits.
4. Train and evaluate all models.
5. Save comparison plots to `outputs/figures/`.

## Notes

ARIMA is evaluated on a limited number of test windows by default because refitting ARIMA repeatedly is slow. You can adjust `N_ARIMA_EVAL` in the script.
