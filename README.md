# South Caucasus Hydroclimate Analysis using ERA5 Reanalysis Data

## Overview

This repository contains the computational workflows, preprocessing scripts, hydroclimatic diagnostics, and visualization procedures developed during an internship focused on atmospheric and hydroclimatic analysis of the South Caucasus region.

The project investigates seasonal hydroclimatic variability, atmospheric moisture transport, extreme precipitation behavior, temperature trends, evaporation variability, and atmospheric water-budget dynamics using ERA5 atmospheric reanalysis datasets.

The workflows were implemented using Python-based scientific computing tools within Google Colab environments.

---

## Objectives

The main objectives of this project include:

- Processing multidimensional ERA5 NetCDF climate datasets
- Investigating regional hydroclimatic variability
- Analyzing seasonal precipitation and temperature behavior
- Studying atmospheric moisture transport patterns
- Generating hydroclimatic diagnostics and visualizations
- Developing computational workflows for climate-data analysis
- Preparing datasets compatible with future AI-based climate-analysis workflows

---

## Study Region

South Caucasus Region

Geographical domain:
- Latitude: 38°N – 43°N
- Longitude: 38°E – 51°E

The region is characterized by:
- Complex mountainous terrain
- Strong seasonal climate variability
- Orographic precipitation processes
- Hydroclimatic sensitivity to atmospheric circulation

---

## Datasets

### ERA5 Reanalysis Dataset
Source:
- ECMWF Copernicus Climate Data Store (CDS)

Variables used:
- 2m temperature (`t2m`)
- Total precipitation (`tp`)
- Evaporation (`e`)
- 10m u-component of wind (`u10`)
- 10m v-component of wind (`v10`)

Temporal coverage:
- 2025

Format:
- NetCDF (.nc)

---

## Tools and Libraries

The project was implemented using:

- Python
- Google Colab
- xarray
- NumPy
- Pandas
- Matplotlib
- Cartopy
- NetCDF4
- CDS API

---

## Implemented Analyses

### Seasonal Hydroclimate Variability
- Seasonal precipitation analysis
- Monthly climatologies
- Hydroclimatic variability diagnostics

### Extreme Precipitation Analysis
- Heavy precipitation diagnostics
- Percentile-based precipitation analysis
- Seasonal precipitation anomalies

### Moisture Transport Patterns
- Atmospheric circulation analysis
- Wind vector-field visualization
- Moisture-transport diagnostics

### Temperature Trends
- Monthly temperature variability
- Seasonal warming analysis
- Regional climate diagnostics

### Evaporation Variability
- Monthly evaporation analysis
- Water-cycle variability diagnostics

### Atmospheric Water Budget
- Precipitation-minus-evaporation analysis
- Seasonal atmospheric water-cycle diagnostics

---

## Example Workflow

1. Download ERA5 datasets using CDS API
2. Load NetCDF datasets using xarray
3. Perform preprocessing and temporal aggregation
4. Generate climate diagnostics
5. Visualize atmospheric variability
6. Export hydroclimatic figures

---

## Example ERA5 Download Script

```python
import cdsapi

client = cdsapi.Client()

client.retrieve(
    "reanalysis-era5-single-levels",
    {
        "product_type": "reanalysis",
        "variable": [
            "2m_temperature",
            "total_precipitation",
            "evaporation",
            "10m_u_component_of_wind",
            "10m_v_component_of_wind"
        ],
        "year": ["2025"],
        "time": ["00:00", "06:00", "12:00", "18:00"],
        "area": [43, 38, 38, 51],
        "data_format": "netcdf",
        "download_format": "unarchived"
    },
    "era5_south_caucasus_2025.nc"
)
