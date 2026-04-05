# Prana Sentinel
### Space-Enabled Health Intelligence System (SEHIS)

A satellite-native infectious disease outbreak prediction system 
using NASA Earth observation data and public health records to 
forecast dengue fever at sub-national resolution in Brazil.

---

## What It Does

Prana Sentinel predicts weekly dengue case counts at the 
municipality level by combining:
- **NASA MODIS** Land Surface Temperature (LST) and NDVI 
  via Google Earth Engine
- **NASA CHIRPS** precipitation data at 5-day resolution
- **Brazil SINAN** dengue notification records (2015–2023)

The model demonstrates that satellite-derived environmental 
variables carry genuine predictive signal for outbreak dynamics —
validated across 8 years of data and 469+ weekly observations.

---

## Results

| Metric | Baseline (2yr) | Current (8yr) |
|--------|---------------|---------------|
| R² Score | 0.773 | **0.949** |
| MAE (cases/week) | 103.0 | **72.8** |
| Training window | 2022–2023 | 2015–2023 |
| Features | 6 | 14 |

**Key finding:** Land Surface Temperature (LST) emerges as the 
second most important predictor when sufficient historical data 
is available, validating the satellite-native architecture as a 
genuine early warning signal — not just a correlate of prior 
case counts.

---

## Notebook Pipeline

| Notebook | Description |
|----------|-------------|
| [01_dengue_data](notebooks/01_dengue_data.ipynb) | SINAN dengue case ingestion and cleaning |
| [02_satellite_data](notebooks/02_satellite_data.ipynb) | GEE MODIS LST + NDVI extraction |
| [03_model_baseline](notebooks/03_model_baseline.ipynb) | Baseline predictive model (2yr window) |
| [04_extended_dataset](notebooks/04_extended_dataset.ipynb) | Extended dataset + satellite signal validation |
| [05_precipitation](notebooks/05_precipitation.ipynb) | CHIRPS precipitation integration |

---

## Data Sources

All data is sourced from free, publicly available platforms:

- **[SINAN](http://sinan.saude.gov.br/)** — Brazil Ministry of Health 
  dengue notification system
- **[NASA MODIS](https://modis.gsfc.nasa.gov/)** — Land Surface 
  Temperature and Vegetation Index via Google Earth Engine
- **[CHIRPS](https://www.chc.ucsb.edu/data/chirps)** — Climate 
  Hazards Group InfraRed Precipitation with Station data

Raw data files are not included in this repo. See each notebook 
for data access instructions.

---

## How To Run

1. Open any notebook in [Google Colab](https://colab.research.google.com)
2. Mount your Google Drive when prompted
3. Follow the setup cell at the top of each notebook
4. Run cells sequentially

Requirements are handled automatically via `!pip install` 
commands within each notebook.

---

## Current Status

✅ Full pipeline demonstrated — dengue data through predictive model  
✅ Satellite signal validated (LST = #2 predictor at 8yr window)  
✅ Precipitation integrated as third environmental variable  
🟡 Next: Longer lag windows (4–6 weeks) for early warning capability  
🟡 Next: Humidity variables  
🟡 Next: Geographic expansion to 5+ Brazilian cities  

---

## About

Prana Sentinel is developed by 
**[Prana Collaborative](https://pranacollaborative.com)** as a 
commercially-oriented outbreak intelligence platform targeting 
private sector buyers in insurance, logistics, and global health.

**Contact:** sam@pranacollaborative.com  
**GitHub:** [pranacollab](https://github.com/pranacollab)
