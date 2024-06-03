# Formula 1 Driver Performance Analysis

## Situation

The goal of this project was to analyze the performance of Formula 1 drivers using data analysis tools. The project was conducted during the 2021 Formula 1 season.

## Task

As part of a team of data analysts, my role was to develop a methodology for analyzing driver performance and to implement this methodology using Python and Tableau.

## Action

We began by collecting data on driver performance during the season, including lap times, qualifying positions, and race results. We then used Python to clean and process this data, calculating various metrics such as average lap time and consistency. We also used Tableau to visualize and explore the data, identifying trends and patterns in driver performance.

### Python Code Example

Here is an example of the Python code used to calculate driver consistency:

```python
import pandas as pd

# Load data
data = pd.read_csv('data/driver_value.csv')

# Calculate standard deviation of lap times
lap_time_std = data.groupby('Driver Name')['lap_time'].std()

# Calculate consistency score as inverse of standard deviation
consistency_score = 1 / lap_time_std

# Normalize consistency scores to range from 0 to 1
consistency_score_norm = (consistency_score - consistency_score.min()) / (consistency_score.max() - consistency_score.min())

print(consistency_score_norm)
