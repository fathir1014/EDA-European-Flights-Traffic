# European Flight Traffic Analysis

Exploratory data analysis of European flight traffic using airport-level and country-level flight data from 2016 to May 2022. The project studies traffic concentration, seasonality, COVID-19 disruption, airport recovery patterns, and IFR flight percentages.

## Project Goals

- Identify the busiest airports and countries in European flight traffic.
- Compare airport-level concentration with country-level activity.
- Analyze monthly and yearly seasonality.
- Examine the impact of COVID-19 on countries and major airports.
- Investigate the Istanbul airport transition in Turkiye.
- Review IFR flight percentages and highlight possible data-quality issues.

## Dataset

The dataset is downloaded with `kagglehub`:

```python
kagglehub.dataset_download("muqaddasejaz/european-flights-dataset")
```

Main file used:

```text
European Flights Dataset.csv
```

The analysis uses columns such as flight date, airport name, airport ICAO code, country, total flights, departure flights, arrival flights, and IFR flight counts.

## Repository Structure

```text
European_fligths/
|-- main.ipynb
|-- requirements.txt
|-- README.md
|-- report.html
`-- plots/
    |-- boxplot_country_flight_distribution.png
    |-- heatmap_country_vs_monthly_flights.png
    |-- monthly_flights.png
    |-- monthly_flights_over_time.png
    |-- top20_airports_ifr_percentage.png
    |-- top8_airports_flights.html
    |-- top8_countries_flights.html
    |-- total_country_flights.png
    |-- total_flights_by_airport.png
    |-- total_flights_per_year.png
    `-- turkey_airport_trends.png
```

## Key Findings

- Amsterdam Schiphol was the busiest airport, but the Netherlands was not the busiest country overall, indicating strong traffic concentration around one major hub.
- France, Germany, Spain, and the United Kingdom contributed nearly half of total European flight activity.
- European traffic showed a clear seasonal pattern before COVID-19, usually rising toward summer.
- COVID-19 caused a major collapse in 2020 and disrupted the stable seasonal pattern seen in previous years.
- Istanbul Ataturk had a distinct decline after 2019 due to the transition of passenger operations to IGA Istanbul Airport.
- Some IFR percentages exceeded 100%, suggesting reporting differences or inconsistencies in the source data.

## Final Report

A rendered HTML version of the notebook is available as `report.html`. This is useful for quickly reviewing the analysis without opening Jupyter Notebook.

## Visual Outputs

The notebook exports static charts as PNG files and interactive trend charts as HTML files in the `plots/` folder.

Examples of generated outputs:

- Top airports by total flights
- Top countries by total flights
- Monthly flight activity
- Country-by-month heatmap
- Yearly and monthly trends over time
- Top country and airport trends during COVID-19
- Turkiye airport transition trend
- Top airports by IFR percentage

## Limitations

- Missing IFR values were filled with `0`, which preserves records but may bias IFR percentage calculations.
- The dataset only includes data through May 2022, so 2022 is a partial year.
- IFR percentages above 100% indicate that IFR columns may use a different reporting method or contain source-data inconsistencies.
- This project is descriptive EDA and does not attempt causal modeling or forecasting.

## How to Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Open and run the notebook:

```bash
jupyter notebook main.ipynb
```

The notebook downloads the dataset, runs the analysis, and saves the charts into the `plots/` directory.

## Tools Used

- Python
- pandas
- matplotlib
- seaborn
- plotly
- kagglehub
