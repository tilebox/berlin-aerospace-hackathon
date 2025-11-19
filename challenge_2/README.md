<h1 align="center">
  <img src="https://media.licdn.com/dms/image/v2/D4E22AQHrBW2ZtY0Qrw/feedshare-shrink_800/B4EZqCHpgsIwAg-/0/1763119636548?e=1765411200&v=beta&t=u_-aelnclw9Na6I2a2I5SKnqhWvKknj8ZBtcpfF02A8" width="400" height="350" alt="High resolution satellite image of the Earth, showcasing a river">
</h1>

# Challenge Briefing: Earth Observation Change Detection & Risk Assessment

## 🧠 The Core Problem

Natural disasters and human-caused events have severe impacts on communities and infrastructure.

### Your mission

Build a **multi-temporal change detection + risk assessment system** using optical, thermal, or SAR satellite imagery. Choose one scenario (or combine several) and generate a **severity/risk map** backed by quantitative analysis.

This challenge is ideal for hackers into EO data, climate, disasters, geospatial AI, SAR, spectral indices, and large-scale pipeline design.

## 🧩 Suggested Scenarios

### 🔥 Wildfire Burn Scars

Use before/after NBR or dNBR (Sentinel-2) to map burn severity.

### 🌆 Urban Heat Islands

Combine thermal imagery (Landsat-8 TIRS) with NDVI (Sentinel-2 / Satellogic) to find high-risk heat zones.

### 🌊 Flood Extent Mapping

Detect / quantify flooded areas using Sentinel-1 SAR or optical Sentinel-2.

### 🏚️ Building Damage Assessment

Map destroyed/damaged infrastructure (Ukraine or similar AOIs) using Sentinel-1 + Sentinel-2 + Satellogic.

### 🌋 Volcanic Activity

Track thermal anomalies & ash plumes with Landsat-8 TIRS + Sentinel-2.

## 📦 Deliverables

- A clear change detection or risk assessment map (with legend & classes)
- Quantitative analysis: affected area, severity stats, or temporal change
- Vector AOI overlays with relevant context layers
- Short, clear methodology documentation

### Bonus points

Your solution can answer questions from city officials:

- Where do I allocate resources to cool down the city?
- Which area should we reinforce to prepare for the next disaster?
- Where do we pre-position emergency equipment?
- What if I build a park here, how does it affect the surrounding areas?
- Should we evacuate this neighborhood?

## 📂 Provided Materials

- [Sample AOIs + event metadata for historical events](./events.md)
- Starter notebook: [Earth_Observation_Challenge.ipynb](Earth_Observation_Challenge.ipynb)
- Tilebox Open Data (see overview below)

## ⚙️ Relevant Tilebox Features

- [Spatio-temporal queries](https://docs.tilebox.com/datasets/query/filter-by-location) for Sentinel Data, Landsat, and more
- [Workflow orchestration](https://docs.tilebox.com/workflows/introduction) for multi-temporal change detection pipelines
- [Spatial tiling](https://github.com/tilebox/examples/blob/main/wyvern-hyperspectral-pca/wyvern_pca.py#L35) + parallel processing across hundreds/thousands of imagery tiles.
- [Task dependencies](https://docs.tilebox.com/workflows/concepts/tasks#dependencies) (baseline composite → indices → change metrics → vectorization)

## 📋 Overview of available Open-Data Datasets on Tilebox

Tilebox hosts a metadata catalogue indexing many Open Data EO datasets. Below is a list of some of the most relevant ones for this challenge. However, other datasets may also be useful.

| Satellite                                                                                                  | Instrument (Type)                              | Spectral Channels                                          | Spatial Resolution                                             | Temporal Extent                                                        |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------- | ---------------------------------------------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------- |
| [Sentinel-1](https://console.tilebox.com/datasets/explorer/3ca428b2-756f-45a0-a699-1cbd1add44f7)           | C-SAR (Synthetic Aperture Radar)               | C-band (Microwave) with dual polarization (VV, VH, HH, HV) | 5 m (SM mode), 5m x 20m (IW mode), 20m x 40m (EW mode)         | 2014 – Present (6-12 day revisit)                                      |
| [Sentinel-2](https://console.tilebox.com/datasets/explorer/34d7b08b-8a27-4b40-819b-b11c6189695a)           | MSI (Optical Multispectral Imager)             | 13 bands (Visible, Red-Edge, NIR, SWIR, Cirrus)            | 10 m (Visible, NIR), 20 m (Red-Edge, SWIR), 60 m (Atmospheric) | 2015 – Present (5-day revisit)                                         |
| [Sentinel-3](https://console.tilebox.com/datasets/explorer/cbf98188-bc07-4c41-a532-189f910ff28b)           | OLCI (Optical, Ocean/Land Colour Imager)       | 21 bands (VNIR/SWIR)                                       | 300 m                                                          | 2016 – Present (1-2 day global)                                        |
|                                                                                                            | SLSTR (Radiometer, Sea and Land Surface Temp.) | 11 bands (VNIR, SWIR, MWIR, TIR)                           | 500 m (VNIR/SWIR), 1 km (TIR)                                  | 2016 – Present (1-2 day global)                                        |
|                                                                                                            | SRAL (Radar Altimeter)                         | Ku/C-band                                                  | 300 m (footprint)                                              | 2016 – Present                                                         |
| [Sentinel-5P](https://console.tilebox.com/datasets/explorer/bb394de4-b47f-4069-bc4c-6e6a2c9f0641)          | TROPOMI (Imaging Spectrometer)                 | 8 bands (UV to SWIR)                                       | 5.5 km x 3.5 km (Most products)                                | 2017 – Present (Daily global)                                          |
| [Sentinel-6](https://console.tilebox.com/datasets/explorer/b8eb059a-c83d-4425-af87-7ee2e7bb93ac)           | Poseidon-4 (SAR Altimeter)                     | Ku/C-band                                                  | Nadir track only (Altimetry)                                   | 2020 – Present (10-day exact repeat)                                   |
| [Umbra SAR](https://console.tilebox.com/datasets/explorer/b70b5be3-6eab-448d-a820-faee63ca573f)            | High-Res SAR (Synthetic Aperture Radar)        | X-band (Microwave)                                         | 25 cm - 1 m (High-Res modes)                                   | 2023 – Present (Flexible revisit)                                      |
| [Landsat-8/9 TIRS](https://console.tilebox.com/datasets/explorer/d6969fca-60b5-4a1d-9668-715e08cf80da)     | OLI/TIRS (Optical/Thermal)                     | ~4 to 11 bands (Visible to Thermal IR)                     | 15 m (Panchromatic), 30 m (Multispectral), 100 m (Thermal IR)  | 2013 – Present (8-16 day revisit)                                      |
| [Wyvern Dragonette](https://console.tilebox.com/datasets/explorer/32d74bb5-3c01-477b-aec5-03dd3b7b12f2)    | Hyperspectral Imager                           | 23 bands (VNIR)                                            | 5.3 m                                                          | 2023 – Present (~2.1 day revisit at Equator)                           |
| [Satellogic EarthView](https://console.tilebox.com/datasets/explorer/e44cd367-5464-415a-b1bd-2f24692049ad) | Optical Imaging                                | 4 bands (RGB, Near-Infrared)                               | 1 m (High Resolution)                                          | Varies (Portion of data July-Dec 2022 available for EarthView dataset) |

### 🎯 Key Challenge Relevance

- **Sentinel-1 SAR**: Essential for Flood Extent Mapping and Building Damage Assessment due to its all-weather, day/night capability and sensitivity to structural changes.

- **Sentinel-2 MSI**: The primary dataset for Wildfire Burn Scars (using NBR/dNBR) and base layers for Urban Heat Islands (using NDVI) and Building Damage Assessment. Its 10 m resolution is a good balance of detail and coverage.

- **Landsat-8/9 TIRS**: Crucial for thermal analysis in Urban Heat Islands and Volcanic Activity, providing the necessary long-wave infrared bands.

- **Satellogic EarthView** / Wyvern Dragonette / Umbra SAR: These provide higher resolution and/or more specialized spectral data (Hyperspectral/High-Res SAR) to enhance the precision of Building Damage Assessment and fine-scale change detection. Wyvern's hyperspectral bands in the VNIR are excellent for detailed vegetation state analysis.
