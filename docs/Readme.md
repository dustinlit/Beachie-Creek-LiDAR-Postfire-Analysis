# LiDAR Analysis of Pre‑ and Post‑Fire Forest Structure in the 2020 Beachie Creek Fire  

![Status: In Progress](https://img.shields.io/badge/Status-In%20Progress-yellow)
[![View Report](https://img.shields.io/badge/View-Full%20Report-blue?style=for-the-badge&logo=github)](https://dustinlit.github.io/Beachie-Creek-LiDAR-Postfire-Analysis/)
[![Repository](https://img.shields.io/badge/GitHub-Repo-black?style=for-the-badge&logo=github)](https://github.com/dustinlit/Beachie-Creek-LiDAR-Postfire-Analysis)


**Author:** Dustin Littlefield  
**Portfolio:** https://github.com/dustinlit  
**Project Type:** `LiDAR Analysis` `Post-Fire Assessment` `Forest Structure`  
**Technologies:** `USGS LiDAR` `LP360` `ArcGIS Pro` `Change Detection`  
**Last Updated:** April 2026

## Overview
This project utilizes multi-temporal LIDAR to quantify wildfire related impacts on forest and topographical within a portion of the 2020 Beachie Creek fire. By comparing pre‑fire and post‑fire datasets, the analysis evaluates canopy loss, surviving vegetation structure, debris accumulation, and topographic stability following a high‑severity wildfire event.

<p align="center">
  <img src="Ravine_Before_and_After.jpg" width="600" title="Beachie Creek Burn Severity">
</p>

<p align="center">
  <img src="Stand_before_and_after.jpg" width="600" title="Beachie Creek Burn Severity">
</p>

## Data
**2008 - OR Willamette Valley OLC 2008 (Tile: 001530)** <br>
Baseline pre‑fire dataset collected for the USGS 3DEP program representing forest and terrain conditions prior to the Beachie Creek Fire.
<br>
[Data Source](https://www.sciencebase.gov/catalog/item/64174dabd34eb496d1d165cb?utm_source=copilot.com)

**2022 - USGS Western Wildfires A22** <br>
Post‑fire dataset acquired after the burn, used to assess structural change and recovery patterns.

<p align="center">
  <img src="data.jpg" width="800" title="Beachie Creek Burn Severity">
</p>

## Study Area 

**Location:** Santiam Canyon, Marion County, Oregon, US <br>
<p align="left">
  <img src="Overview.jpg" width="600" title="Beachie Creek Burn Severity">
</p>

**Description:** A 160 acre site was selected at random in the extent of the overlapping coverage zones of available LIDAR data. The chosen area contains 4 distinct regions of interest. There is a riparian corridor in a ravine carved by fish creek which is flanked to the east and west by steep rising slopes. The western slope is dominated by mature forest, while the eastern slopes, contain younger vegetation that shows evidence of post-harvest regeneration. Finally, in the center and southeast portions of the study area there are two open areas that appear to have been harvested prior to the 2008 USGS 3DEP scans. **

<p align="center">
  <img src="study area.jpg" width="800" title="Beachie Creek Burn Severity">
</p>

<p align="center">
  <img src="Lidar.jpg" width="600" title="Beachie Creek Burn Severity">
</p>

## Workflow
<p align="center">
  <img src="workflow.jpg" width="800" title="Beachie Creek Burn Severity">
</p>

## Preprocessing preliminary workflow
- **ArcGIS Pro**
  - Identify Extent of Study Area
  - Define Projection of 2008 Lidar Dataset
  - Extract LAS using mask of study area <br>

## QC preliminary workflow
- **LP360**
  - Point Density
    - NPS from both dates
  - Scan Angle
  - Flight Lines
    - Check for Gaps
    - Point Density Raster
    - Vertical Accuracy (Visual)
    - Generate Rasters and calculate RMSE (Statistical)
    - Dz Raster
  - Point Consistency Check
    - Compare Raster of Ground from both dates
    - Identify Areas of interest for comparison
    - Known stable sites
    - Avoid ground under canopy
    - 8-15 patches
    - DoD = DEM 2022 – DEM 2008
    - Calculate Zonal Stats (RMSE)
