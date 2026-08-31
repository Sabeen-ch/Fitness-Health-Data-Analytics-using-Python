# 🏋️ Fitness & Health Data Analytics

A comprehensive Python analytics project that cleans, explores, and visualizes fitness-tracking data — covering workout habits, calorie burn, BMI, heart rate, sleep, hydration, and daily activity across a synthetic user base.

Built with **Pandas**, **NumPy**, **Matplotlib**, and **Seaborn**.

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📋 Overview

This project takes a raw fitness-tracking dataset (intentionally messy — missing values, invalid entries, duplicates) and runs it through a full analytics pipeline:

- **Data cleaning** — missing value imputation, invalid-value detection, deduplication, type conversion
- **18 analysis modules** — user, workout, calorie, BMI, heart rate, sleep, hydration, steps, fitness level, city, age group, advanced filtering, statistics, correlation, and date-based trends
- **12 visualizations** — bar charts, histograms, scatter plots, a pie chart, and a correlation heatmap
- **A custom Fitness Score** — a weighted, normalized performance metric ranking users across five key indicators
- **Summary report** — headline metrics exported to CSV

---

## 📁 Project Structure

```
fitness-analytics/
├── dataset/
│   └── fitness_health_data.csv          # Raw dataset (synthetic, ~320 records)
├── charts/                              # 12 generated charts (PNG)
├── results/
│   └── full_analysis_log.txt            # Full console output from the run
├── generate_dataset.py                  # Builds the synthetic raw dataset
├── fitness_analysis.py                  # Main analysis script
├── fitness_analysis.ipynb               # Same analysis as a Jupyter notebook
├── analyzed_fitness_health_data.csv     # Cleaned dataset with engineered columns
├── fitness_summary.csv                  # Headline summary metrics
├── requirements.txt
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.9+
- pip

### Installation

```bash
git clone https://github.com/<your-username>/fitness-analytics.git
cd fitness-analytics
pip install -r requirements.txt
```

### Usage

```bash
# (Optional) Regenerate the raw synthetic dataset
python generate_dataset.py

# Run the full analysis — cleans data, computes metrics, saves charts + reports
python fitness_analysis.py
```

Or open `fitness_analysis.ipynb` in Jupyter to run it interactively, cell by cell, with charts rendered inline.

**requirements.txt**
```
pandas
numpy
matplotlib
seaborn
```

---

## 🔍 What Gets Analyzed

| Module | Highlights |
|---|---|
| **Data Cleaning** | Missing values, duplicates, invalid ages/heights/weights/calories/heart rates/sleep/water — detected and corrected |
| **User Analysis** | Unique users, top performers by calories/steps/duration, gender breakdowns |
| **Workout Analysis** | Most/least common workout types, calories & heart rate by workout type |
| **Calorie Analysis** | Totals, extremes, top 10 calorie-burning sessions, gender/age comparisons |
| **BMI Analysis** | BMI calculation & categorization (Underweight → Obese), breakdowns by gender/city |
| **Heart Rate Analysis** | Averages, outliers, correlation with duration and calories |
| **Sleep & Recovery** | Sleep patterns by gender and fitness level, link to calorie burn |
| **Water Intake** | Hydration patterns across fitness levels and workout types |
| **Steps & Activity** | Daily step distribution, city and fitness-level comparisons |
| **Fitness Level** | Beginner → Professional performance comparison across all metrics |
| **City-Based** | Regional averages, most active city |
| **Age Group** | 18–25 through 56+ breakdowns |
| **Advanced Filtering** | 10 compound conditions (e.g. high BMI + high fitness level) |
| **Statistics** | Mean, median, std dev, variance across key metrics |
| **Correlation Analysis** | 8 named correlations + full correlation matrix with strongest/weakest pairs |
| **Fitness Performance Ranking** | A weighted, normalized composite score with Low/Moderate/Good/Excellent tiers |
| **Date-Based Analysis** | Monthly trends, weekday vs. weekend activity |

---

## 📊 Sample Visualizations

| Chart | Description |
|---|---|
| `01_workout_type_distribution.png` | Bar chart of workout type frequency |
| `04_bmi_category_distribution.png` | Pie chart of BMI category split |
| `08_calories_vs_duration.png` | Scatter plot of calories vs. workout duration |
| `12_correlation_matrix_heatmap.png` | Full correlation heatmap across all numeric metrics |

*(See the `charts/` folder for all 12.)*

---

## 🧮 The Fitness Score

There's no universal formula for a composite fitness score, so this project uses min-max normalization across five metrics, weighted by rough importance:

| Metric | Weight |
|---|---|
| Calories Burned | 30% |
| Steps | 25% |
| Workout Duration | 20% |
| Workout Frequency | 15% |
| Sleep Hours | 10% |

Users are ranked and bucketed into **Low / Moderate / Good / Excellent** tiers. Weights are easy to adjust in `fitness_analysis.py` — search for `Fitness Score`.

---

## 📈 Output Files

Running the analysis produces:

- **`analyzed_fitness_health_data.csv`** — cleaned dataset with engineered columns (BMI, BMI Category, Age Group, Fitness Score, Fitness Rank, etc.)
- **`fitness_summary.csv`** — headline metrics (total users, averages, most popular workout, top city, top user, etc.)
- **`charts/`** — 12 PNG visualizations
- **`results/full_analysis_log.txt`** — full console output for traceability

---

## 📝 Notes on the Dataset

The raw dataset is synthetic (built with `generate_dataset.py`) since no real dataset was supplied. It models 60 users across 8 cities performing 8 workout types, with realistic relationships baked in (e.g. HIIT burns more calories per minute than yoga, higher fitness levels correlate with better performance metrics). Missing values, invalid entries, and duplicate rows were intentionally mixed in so the cleaning pipeline has real work to do.

To use your own dataset instead, drop it into `dataset/` and update `DATA_PATH` in `fitness_analysis.py`.

---

## 🛠️ Built With

- [Python](https://www.python.org/)
- [Pandas](https://pandas.pydata.org/)
- [NumPy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/)

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome. Feel free to check the [issues page](../../issues) or open a pull request.
