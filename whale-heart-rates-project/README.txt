
Data Source:
Goldbogen, Jeremy A., et al. "Extreme bradycardia and tachycardia in the world’s largest animal." Proceedings of the National Academy of Sciences 116.50 (2019): 25329-25332.

Specifically, from: https://purl.stanford.edu/zp260dk8787

Dive Heart Rate Analysis Project
================================

Project Overview
----------------
This project analyzes heart rate data collected during different dive phases. The goal is to explore how dive duration relates to the maximum heart rate recorded at the surface after each dive.

The project uses Python data analysis tools to clean timestamp data, calculate dive durations, summarize heart rate patterns, merge derived datasets, and visualize the relationship between dive duration and post-dive surface heart rate.

Project Questions
-----------------
Warmup:
- Calculate the average heart rate for each dive phase.

Challenge:
- Investigate the relationship between dive duration and the maximum heart rate at the surface following each dive.

Dataset Description
-------------------
The dataset includes dive-related records with columns such as:

- dive_id: Unique identifier for each dive
- timestamp: Time when each heart rate measurement was recorded
- dive_phase: Phase of the dive, such as descent, ascent, or surface
- heart_rate: Recorded heart rate value

Tools and Libraries Used
------------------------
- Python
- pandas
- matplotlib

Main Steps
----------
1. Data Preparation
   - Converted the timestamp column into datetime format using pandas.
   - This allowed time-based calculations to be performed accurately.

2. Dive Duration Calculation
   - Filtered the dataset to identify descent phase records.
   - Found the earliest descent timestamp for each dive_id.
   - Filtered the dataset to identify ascent phase records.
   - Found the latest ascent timestamp for each dive_id.
   - Calculated dive duration by subtracting the descent start time from the ascent end time.
   - Converted the duration from seconds to minutes using dt.total_seconds() / 60.
   - Stored the results in a dataframe with the columns dive_id and dive_duration.

3. Maximum Surface Heart Rate Calculation
   - Filtered the dataset to include only surface phase records.
   - Grouped the data by dive_id.
   - Calculated the maximum heart rate recorded at the surface after each dive.
   - Stored the results in a dataframe with the columns dive_id and max_surface_heart_rate.

4. DataFrame Merge
   - Merged the dive duration dataframe with the maximum surface heart rate dataframe using dive_id.
   - This created one final analysis dataframe containing both dive duration and maximum surface heart rate for each dive.

5. Data Visualization
   - Created a scatter plot using matplotlib.
   - The x-axis represents dive duration in minutes.
   - The y-axis represents maximum surface heart rate.
   - The visualization helps show whether longer dives appear to be associated with higher or lower surface heart rates.

Important Code Note
-------------------
When converting seconds to minutes, use:

    dt.total_seconds() / 60

Do not divide by 6. Dividing by 6 will produce incorrect duration values.

Also, when calculating dive duration, it is safer to merge the descent and ascent timestamp dataframes on dive_id before subtracting timestamps. This helps avoid incorrect calculations if the rows are not perfectly aligned.

Example Improved Duration Logic
-------------------------------
    descent_start = df[df['dive_phase'] == 'descent'].groupby('dive_id')['timestamp'].min().reset_index()
    ascent_end = df[df['dive_phase'] == 'ascent'].groupby('dive_id')['timestamp'].max().reset_index()

    duration_df = descent_start.merge(ascent_end, on='dive_id', suffixes=('_descent_start', '_ascent_end'))
    duration_df['dive_duration'] = (
        duration_df['timestamp_ascent_end'] - duration_df['timestamp_descent_start']
    ).dt.total_seconds() / 60

    duration_df = duration_df[['dive_id', 'dive_duration']]

Expected Output
---------------
The final output is a scatter plot showing the relationship between dive duration and maximum surface heart rate after each dive.

This analysis can help identify patterns in physiological response after dives and support further investigation into how dive behavior may affect heart rate recovery at the surface.

Skills Demonstrated
-------------------
- Data cleaning
- Datetime conversion
- Time-series analysis
- GroupBy aggregation
- Feature engineering
- DataFrame merging
- Exploratory data analysis
- Data visualization
- Python programming
- pandas data manipulation
- matplotlib visualization

----------------------------------------------------------- Resume-ready bullet point: -----------------------------------------------

Dive Heart Rate Analysis Project

    Analyzed time-series dive and heart-rate data using Python, pandas, and matplotlib by converting timestamps, grouping dive phases, calculating dive durations, and aggregating maximum surface heart rate after each dive.
    Performed exploratory data analysis and data visualization by merging engineered features into an analytical dataset and creating a scatter plot to investigate the relationship between dive duration and post-dive surface heart rate.

For a tighter resume version, use just this one:

    Analyzed time-series physiological data using Python, pandas, and matplotlib by engineering dive-duration features, aggregating maximum surface heart rate, merging analytical datasets, and visualizing relationships through exploratory data analysis.
