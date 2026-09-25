# Week 3: Python & Data Wrangling

Cleaning a messy fitness-tracker dataset with Pandas, engineering new columns,
and visualizing the results with Matplotlib and Seaborn.

## Files

| File | Description |
|---|---|
| `raw_data.csv` | Original messy dataset (32 rows) |
| `week3_data_wrangling.ipynb` | Full notebook: cleaning → new columns → filtering → charts |
| `cleaned_data.csv` | Final cleaned dataset (31 rows, 7 columns) |
| `calories_over_time.png` | Calories burned per day, over the month |
| `duration_vs_calories.png` | Duration vs. Calories, colored by Pulse |
| `correlation_heatmap.png` | Correlation matrix across all numeric columns |

## What was cleaned

- **Dates**: stripped stray quotes, fixed one date stored as a plain integer
  (`20201226`), and inferred one missing date from its neighbors.
- **Duration**: corrected an outlier (`450` → `45`, clearly a typo).
- **Calories**: filled 2 missing values with the column mean.
- **Duplicates**: removed 1 exact duplicate row.

## New columns

- `Calories_per_Min` — calories burned per minute of exercise.
- `Pulse_Range` — `Maxpulse - Pulse`, a rough measure of exertion.

## How to run

```bash
pip install pandas matplotlib seaborn
jupyter notebook week3_data_wrangling.ipynb
```

## Key finding

`Calories_per_Min` correlates most strongly with `Calories` (0.71) and is
negatively correlated with `Duration` (-0.41) — shorter, higher-intensity
sessions tend to burn calories faster per minute than longer ones.
