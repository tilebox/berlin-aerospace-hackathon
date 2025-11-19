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

- A clear change detection map (with legend & classes)
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
- Tilebox Open Data:
  - [Sentinel-2](https://console.tilebox.com/datasets/explorer/34d7b08b-8a27-4b40-819b-b11c6189695a) (Optical) – burn scars, NDVI, building damage
  - [Landsat-8 TIRS](https://console.tilebox.com/datasets/explorer/d6969fca-60b5-4a1d-9668-715e08cf80da) & [Landsat-9 TIRS](https://console.tilebox.com/datasets/explorer/b985e6d7-e539-4283-b879-274a810fdb7c) (Thermal) – heat islands, volcanic anomalies
  - [Sentinel-1 SAR](https://console.tilebox.com/datasets/explorer/3ca428b2-756f-45a0-a699-1cbd1add44f7) – floods, structural damage
  - [Satellogic](https://console.tilebox.com/datasets/explorer/e44cd367-5464-415a-b1bd-2f24692049ad) Optical – high-res NDVI & visual analysis
  - [All Open Datasets](https://console.tilebox.com/datasets/open-data)

## ⚙️ Relevant Tilebox Features

- [Spatio-temporal queries](https://docs.tilebox.com/datasets/query/filter-by-location) for Sentinel Data, Landsat, and more
- [Workflow orchestration](https://docs.tilebox.com/workflows/introduction) for multi-temporal change detection pipelines
- [Spatial tiling](https://github.com/tilebox/examples/blob/main/wyvern-hyperspectral-pca/wyvern_pca.py#L35) + parallel processing across hundreds/thousands of imagery tiles.
- [Task dependencies](https://docs.tilebox.com/workflows/concepts/tasks#dependencies) (baseline composite → indices → change metrics → vectorization)
