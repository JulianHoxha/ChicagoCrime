[README_chicago_crime.md](https://github.com/user-attachments/files/30858618/README_chicago_crime.md)
# Chicago Crime & Census Data Analysis

Analysis of crime patterns in Chicago (2008–2012), combined with socioeconomic
census data, to explore trends in crime type, timing, location, and their
relationship to neighborhood hardship levels.

## Overview

This project works with two large public datasets from the City of Chicago's
open data portal:

- **Crime data** (2001–2025, 2GB+): individual crime records including type,
  location, date/time, arrest status, and domestic classification.
- **Census data** (2008–2012): socioeconomic indicators by community area,
  including a computed hardship index.

The crime dataset was filtered down to the 2008–2012 period to align with the
census data, then cleaned, transformed, and merged for analysis.

## What the project covers

- **Data cleaning**: checked for duplicates and missing values, and made
  explicit decisions on how to handle each (e.g. filling missing location
  descriptions with `"Unknown"` rather than dropping rows).
- **Feature engineering**: parsed the `Date` column into `datetime` and
  derived `month`, `day`, `hour`, `minute`, and `weekday` fields to support
  time-based analysis.
- **Exploratory analysis**, including:
  - Year-over-year crime trends and percentage change (2008 vs. 2012)
  - Which crime types increased or decreased the most
  - Police arrest rates overall, and by year/month/crime type
  - Domestic crime patterns, including offenses involving children
  - Weekday and time-of-day patterns (daytime vs. nighttime crime)
  - Highest-risk weekdays and locations for specific crimes (e.g. motor
    vehicle theft)
  - Top and bottom 10 most common crime types
- **Merging datasets**: joined the crime and census data on `Community Area`
  to relate crime types to the socioeconomic hardship index of the
  neighborhood where they occurred.
- **Geospatial visualization**: plotted crime locations on interactive maps,
  colored by hardship index, to visually identify high-crime and
  high-hardship areas.

## Tools & libraries

`Python` · `Pandas` · `NumPy` · `Plotly Express` · `Matplotlib` · `Seaborn`

## Data sources

- [Chicago Crime Data (2001–present)](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2)
- [Chicago Census Data — Selected Socioeconomic Indicators](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)

> Datasets are not included in this repository due to size. Download both as
> CSV from the links above, rename them `chicago_crime.csv` and
> `chicago_census.csv`, and place them in the same folder as the notebook.

## How to run

```bash
pip install pandas numpy matplotlib seaborn plotly_express
jupyter notebook julian_hoxha_databehandling.ipynb
```
