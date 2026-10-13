# ✈️ Airline Flights Data Analysis — Python for Data Science

Mini-project for the **Python Programming for Data Science** 


 
---

## 📌 Description

This project is a complete exploratory data analysis of a real-world dataset about **airline flights** (domestic flights between six major Indian cities). Using Python, we load, clean, analyze and visualize the data in order to understand **which factors drive ticket prices** and to give practical recommendations to travelers.

## 📂 Dataset

- **Source:** Kaggle — `airlines_flights_data`
- **Size:** 300,153 rows × 12 columns (well above the 1,000 rows / 4 variables required by the assignment)

| Column | Type | Description |
|--------|------|-------------|
| `index` | int | Record identifier |
| `airline` | category | Airline company |
| `flight` | category | Flight number |
| `source_city` | category | Departure city |
| `departure_time` | category | Time of day of departure |
| `stops` | category | Number of stops (`zero`, `one`, `two_or_more`) |
| `arrival_time` | category | Time of day of arrival |
| `destination_city` | category | Arrival city |
| `class` | category | Travel class (`Economy`, `Business`) |
| `duration` | float | Flight duration (hours) |
| `days_left` | int | Days between booking and departure |
| `price` | int | Ticket price (target variable) |



## 🧰 Technologies

- **Python 3**
- **Pandas** — data manipulation and aggregation
- **NumPy** — numerical computing
- **Matplotlib** and **Seaborn** — visualization
- **Jupyter Notebook**




## 🔬 Project Workflow

### 1. Data loading
Import of the CSV, preview of the first rows, shape, columns, data types (`info()`, `describe()`).

### 2. Data cleaning
- Missing values and duplicate rows (none found)
- Invalid values: negative prices, durations ≤ 0 or > 48 h, `days_left` outside 0–365
- Logical consistency: departure city ≠ arrival city
- Categorical checks: valid values for `class`, `stops` and `source_city`
- Price outliers removed with the **IQR method** (123 rows)
- Consistency checks between duration, stops and schedules; partial duplicates kept on purpose (dynamic pricing is realistic in the airline sector)
- Conversion of categorical columns to the `category` type

Result: **300,153 → 300,028 rows** (125 rows removed).

### 3. Data analysis
- Descriptive statistics of prices (mean, median, quartiles, standard deviation)
- Number of flights per airline, per departure city and per arrival city
- `groupby` analyses of price by airline, class, stops, departure/arrival time, route and days left
- Last-minute tickets (1–2 days before departure)
- Correlation between duration and price

### 4. Visualization
Bar plots, histogram + KDE, boxplot, heatmaps (price by airline and class, correlation matrix), radar chart, pie charts, line plot (price vs. days left) and scatter plot (duration vs. price).


## 📊 Key Findings

- **Concentrated market:** Vistara (42.6%), Air India (27.0%) and Indigo (14.4%) account for about 84% of all flights.
- **Skewed prices:** the mean price (≈ 20,855) is far above the median (≈ 7,425), pulled up by a minority of expensive Business tickets.
- **Class is the strongest factor:** Business tickets are roughly ten times more expensive than Economy ones.
- **Airline matters:** full-service airlines (Vistara, Air India) are much more expensive than low-cost ones (AirAsia, Indigo, GO FIRST, SpiceJet).
- **Book early:** prices increase sharply for last-minute bookings (1–2 days before departure).
- **Traffic is concentrated** in Delhi and Mumbai; Chennai is the least busy city.
- **Duration vs. price:** only a weak positive correlation (≈ 0.20).



