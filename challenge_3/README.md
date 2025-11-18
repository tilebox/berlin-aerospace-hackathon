<h1 align="center">
  <img src="https://media.licdn.com/dms/image/v2/D4E22AQGzX28pgwJsZA/feedshare-shrink_800/B4EZqWNcXVKkAg-/0/1763456701163?e=1764806400&v=beta&t=KYyDsMqqOoS66gmea1c6JUvgxi1GmVSI8vykeoiQ8d8" width="400" height="350" alt="Tilebox Logo">
</h1>

# Challenge Briefing: Mini-Constellation Tasking Planner

**​Difficulty:** Advanced

**Theme:** Mission Planning • Constellation Optimization • Cloud-Aware Scheduling

## ​🧠 The Core Problem

​You’re running a tiny virtual earth-observation constellation — 3 to 6 satellites.

### Your mission:

Plan the next 24–72 hours of imaging over a target AOI but with real-world constraints:

- ​Satellites move — you must propagate orbits and compute visibility windows
- ​Earth rotates — terrain masks, shadows, daylight constraints change constantly
- ​Weather is in the way — cloud forecasts must be avoided in planning
- ​Imaging geometry matters — off-nadir angles, sun angle constraints, slews, etc.
- ​Time is limited — you need the best coverage, not just the first-visible pass

### ​Your job:

Build a smart tasking planner that beats a naive baseline and proves it with maps, KPIs, and scheduled task timelines.

​This is essentially:

**Mission Planning + Optimization + Geospatial Reasoning + Satellite Ops in a Box.**

## ​🔧 Tools You Can Use

​You’re allowed - and encouraged - to combine these building blocks:

#### ​🛰 Orbital Mechanics

- ​SGP4 (provided propagation code)
- ​satellite.js or python-sgp4

#### ​🌤 Weather & Environment

- ​Provided cloud forecast rasters
- ​Tilebox time-series & spatio-temporal queries
- ​Solar geometry libraries (e.g., pvlib or simple sun-angle formulas)

#### ​🗺 Spatial Computation

- ​shapely, rasterio, geopandas
- ​CesiumJS for orbit visualization
- ​Tilebox Datasets API for storing/querying AOIs, forecast data, ephemerides

#### ​⚙️ Optimization & Workflow

- ​Tilebox Workflows for evaluating many candidate schedules
- ​Tilebox Job Cache for precomputed visibility windows
- ​Any optimization technique:
  - ​greedy
  - ​rule-based
  - ​beam search
  - ​heuristic scoring
  - ​even a lightweight constraint solver if you want

#### ​🌍 Visualization

- Coverage heatmaps
- ​Footprint overlays
- ​Timeline charts
- ​CesiumJS 3D scenes (optional but awesome)

## ​​📦 What You Must Deliver

1. ​A coverage map
   Footprints colored by satellite & timestamp.

2. ​Tasking schedule (CSV/JSON)
   With start/stop times, which constraints were satisfied, and which satellite executes each task.

3. ​Key performance metrics

- ​% of AOI covered
- ​cloud-free area achieved
- ​average off-nadir angle
- ​comparison vs naive “first visible = take image” baseline

### ​Bonus: Visualization / Demo

A clean, intuitive, hacker-friendly interface always scores extra points.

## ​📂 You Get

- ​TLEs for a 3–6-satellite constellation
- ​AOI shapefiles
- ​Cloud forecast rasters
- ​Imaging constraint parameters
- ​Sample SGP4 code
- ​Tilebox Datasets + Workflows + Query API access
  - ​Docs:
    - ​https://docs.tilebox.com
    - ​https://docs.tilebox.com/datasets
    - ​https://docs.tilebox.com/workflows

## ​🔑 Tips for Success

- ​Start with visibility windows only — then add clouds & sun angles
- ​Cache everything — visibility and weather lookups add up
- ​Visualize constraints early — footprints, sun angles, clouds
- ​Keep the scoring metric simple
- ​Use the provided data aggressively — it will save hours
