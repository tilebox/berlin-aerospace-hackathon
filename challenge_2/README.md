<h1 align="center">
  <img src="https://media.licdn.com/dms/image/v2/D4E22AQHrBW2ZtY0Qrw/feedshare-shrink_800/B4EZqCHpgsIwAg-/0/1763119636548?e=1765411200&v=beta&t=u_-aelnclw9Na6I2a2I5SKnqhWvKknj8ZBtcpfF02A8" width="400" height="350" alt="High resolution satellite image of the Earth, showcasing a river">
</h1>

# Challenge Briefing: Earth Observation Change Detection & Risk Assessment

Your mission: build a **multi-temporal change detection + risk assessment system** using optical, thermal, or SAR satellite imagery. Choose one scenario (or combine several) and generate a **severity/risk map** backed by quantitative analysis.

This challenge is ideal for hackers into EO data, climate, disasters, geospatial AI, SAR, spectral indices, and large-scale pipeline design.

## 🧩 Suggested Scenarios

Choose one or mix multiple:

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

## ⚙️ Relevant Tilebox Features

- [Spatio-temporal queries](https://docs.tilebox.com/datasets/query/filter-by-location) for Sentinel Data, Landsat, and more
- [Workflow orchestration](https://docs.tilebox.com/workflows/introduction) for multi-temporal change detection pipelines
- [Spatial tiling](https://github.com/tilebox/examples/blob/main/wyvern-hyperspectral-pca/wyvern_pca.py#L35) + parallel processing across hundreds/thousands of imagery tiles.
- [Task dependencies](https://docs.tilebox.com/workflows/concepts/tasks#dependencies) (baseline composite → indices → change metrics → vectorization)

## 📈 Deliverables

- A clear change detection map (with legend & classes)
- Quantitative analysis: affected area, severity stats, or temporal change
- Vector AOI overlays with relevant context layers
- Short, clear methodology documentation

## 🗂️ Provided Materials

- [Sample AOIs + event metadata for historical events](./events.md)
- Tilebox Open Data links:
  - Sentinel-2 (Optical) – burn scars, NDVI, building damage
  - Landsat-8 TIRS (Thermal) – heat islands, volcanic anomalies
  - Sentinel-1 SAR – floods, structural damage
  - Satellogic Optical – high-res NDVI & visual analysis
  - Sample scripts for NBR, NDVI, NDWI, thermal indices, etc.

This challenge is all about detecting change, quantifying impact, and turning satellite data into actionable insights. Perfect for EO engineers, ML practitioners, and geospatial hackers.
