# Morocco Electricity Consumption and Environmental Factors Analysis

**Programme:** AnalystLab Africa -- Experience Lab Internship Programme\
**Week:** 5\
**Track:** Track 1 -- Data Analytics\
**Project:** Exploratory Analysis and Interactive Visualisation of
Morocco Electricity Consumption

## 1. Project Overview

This project analyses electricity consumption readings from three
geographical zones in Morocco and investigates how consumption varies
over time and relates to selected environmental measurements. The
analysis was completed in Python using Jupyter Notebook, Pandas, NumPy,
Matplotlib, Seaborn and Plotly.

The project addresses these questions: - How does electricity
consumption differ across the three zones? - At what times, days and
months is average consumption higher or lower? - Are temperature,
humidity and wind speed associated with electricity consumption? - How
can historical patterns support energy monitoring and planning?

## 2. Dataset

The supplied files are: - `powerconsumption.csv` -- main
electricity-consumption dataset. - `powerconsumption_datadictionary.csv`
-- definitions and descriptions of the dataset fields.

The main dataset contains 52,416 observations and nine original columns,
covering 1 January to 30 December 2017 at ten-minute intervals.

  -----------------------------------------------------------------------
  Field                               Description
  ----------------------------------- -----------------------------------
  `Datetime`                          Date and time of each observation

  `Temperature`                       Recorded temperature

  `Humidity`                          Recorded humidity

  `WindSpeed`                         Recorded wind speed

  `GeneralDiffuseFlows`               General diffuse-flow measurement;
                                      consult the supplied dictionary

  `DiffuseFlows`                      Diffuse-flow measurement; consult
                                      the supplied dictionary

  `PowerConsumption_Zone1`            Electricity consumption recorded
                                      for Zone 1

  `PowerConsumption_Zone2`            Electricity consumption recorded
                                      for Zone 2

  `PowerConsumption_Zone3`            Electricity consumption recorded
                                      for Zone 3
  -----------------------------------------------------------------------

**Measurement note:** Confirm the intended unit and meaning of each
electricity-consumption reading before treating a reading as energy
consumed during a ten-minute interval or summing readings into a total.
The physical meaning of the diffuse-flow fields should also be checked
against the supplied dictionary.

## 3. Tools and Libraries

-   Python and Jupyter Notebook
-   Pandas -- loading, inspection, cleaning and grouping
-   NumPy -- numerical operations
-   Matplotlib -- plotting
-   Seaborn -- statistical visualisation and correlation heatmap
-   Plotly -- interactive charts

Install the libraries with:

``` bash
pip install pandas numpy matplotlib seaborn plotly jupyter
```

## 4. Project Folder Structure

Organise the files as follows:

``` text
Week 5 – Full Name – Data Analytics/
├── Morocco Electricity Analysis.ipynb
├── powerconsumption.csv
├── powerconsumption_datadictionary.csv
├── powerconsumption_cleaned.csv
├── Morocco_Electricity_Consumption_Analytical_Report.pdf
├── README.md
└── Screenshots/
    ├── Daily Consumption Trend
    ├── Average Consumption by Zone
    ├── Hourly Consumption
    ├── Monthly Consumption
    ├── Day-of-Week Comparison
    └── Environmental Factors Heatmap
```

The cleaned CSV is a generated output. If it is not available, run the
notebook's preparation cells to recreate it. Keep the original CSV and
dictionary in the project folder, or update the file paths in the
notebook.

## 5. Setup and Reproduction Instructions

1.  Install Python using Anaconda/Miniconda or another Python
    distribution.

2.  Place the original CSV, data dictionary and notebook in the same
    project folder.

3.  Open Anaconda Prompt or a terminal in that folder.

4.  Install the required libraries using the command above.

5.  Start Jupyter Notebook:

    ``` bash
    jupyter notebook
    ```

6.  Open `Morocco Electricity Analysis.ipynb`.

7.  Run the notebook cells from top to bottom, starting with imports and
    data loading.

8.  Review the dataset and dictionary, then run the data-quality checks
    and preparation steps.

9.  Run the consumption analysis, environmental correlation analysis and
    visualisation cells.

10. Review the written findings, implications and recommendations.

11. Save the notebook after execution.

To check the notebook's current working directory:

``` python
import os
print(os.getcwd())
```

The notebook contains a CSV export step:

``` python
df.to_csv('powerconsumption_cleaned.csv', index=False)
```

Run this after cleaning and preparation. The file is saved in the
notebook's current working directory.

## 6. Data Quality and Preparation Summary

The recorded checks found: - Original dimensions: 52,416 rows and 9
columns. - Missing values: none identified. - Full-row duplicates: none
identified. - Duplicate timestamps: none identified. - Timestamp
intervals: consistent ten-minute intervals. - Infinite values: none
identified. - `Datetime` converted to datetime format. - Derived fields:
`Year`, `Month`, `Day`, `Hour`, `Day_of_Week` and `Date`. - Potential
outliers examined using the IQR method and retained because they may be
genuine observations.

## 7. Main Findings

-   Zone 1 had the highest average consumption (approximately
    32,344.97).
-   Zone 3 had the lowest average consumption (approximately 17,835.41).
-   Zone 1 had the greatest standard deviation (approximately 7,130.56),
    while Zone 2 had the lowest (approximately 5,201.47).
-   Average consumption generally peaked around 20:00 and was lowest
    around 06:00--07:00.
-   Zone 1 and Zone 2 had their highest monthly averages in August; Zone
    3 peaked in July.
-   Temperature was positively correlated with consumption in all zones.
    Humidity had a negative correlation, while wind speed had a weak
    positive correlation.
-   Correlation describes association and does not prove causation.

## 8. Visualisations

The notebook includes: 1. Electricity consumption trends over time. 2.
Average consumption by zone. 3. Hourly consumption patterns. 4. Monthly
consumption patterns. 5. Day-of-week comparisons. 6. Environmental
factor relationships, including a correlation heatmap and scatterplots.
7. Comparison of the three zones.

Plotly charts are interactive in a compatible Jupyter environment.
Matplotlib and Seaborn charts are static figures.

## 9. Business Recommendations

1.  Prioritise demand monitoring in Zone 1 because it has the highest
    average consumption and greatest variability.
2.  Use the recurring evening peak as an input to operational monitoring
    and resource planning.
3.  Develop zone-specific planning approaches that reflect differences
    in monthly, weekly and hourly patterns.
4.  Investigate environmental variables further using additional
    validated data before using them for forecasting or operational
    decisions.

## 10. Limitations and Responsible Use

-   The analysis covers one year, so longer-term trends cannot be
    established.
-   Correlation does not demonstrate causation.
-   Units and the precise interpretation of consumption readings should
    be confirmed before calculating total energy.
-   Interpret `GeneralDiffuseFlows` and `DiffuseFlows` using the
    supplied data dictionary.
-   Other operational, economic or behavioural factors not included in
    the dataset may influence demand.

Reproduce the analysis from the supplied source dataset and dictionary.
Do not remove or change observations without documenting the reason.
Retain the notebook's preparation steps so the cleaned dataset can be
regenerated. Communicate the dataset's coverage, measurement uncertainty
and analytical limitations when sharing the results.
