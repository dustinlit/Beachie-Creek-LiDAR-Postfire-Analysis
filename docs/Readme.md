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
This project utilizes multi-temporal LIDAR to quantify wildfire related impacts on forest and topography within a sample of the 2020 Beachie Creek fire. By comparing pre‑fire and post‑fire datasets, the analysis evaluates canopy loss, surviving vegetation structure, debris accumulation, and topographic stability following a high‑severity wildfire event.

<p align="center">
  <img src="Ravine_Before_and_After.jpg" width="800" title="Beachie Creek Burn Severity">
</p>

<p align="center">
  <img src="Stand_before_and_after.jpg" width="800" title="Beachie Creek Burn Severity">
</p>

## Data

**2008 – OR Willamette Valley OLC 2008 (Tile: 001530)**  
Baseline pre‑fire dataset collected for the USGS 3DEP program representing forest and terrain conditions prior to the Beachie Creek Fire.  
**Data Source:** https://www.sciencebase.gov/catalog/item/64174dabd34eb496d1d165cb

**2022 – USGS Western Wildfires A22**  
Post‑fire dataset acquired after the burn, used to assess structural change and recovery patterns.  
**Data Source:** https://rockyweb.usgs.gov/vdelivery/Datasets/Staged/Elevation/LPC/Projects/OR_WesternWildfires_A22/

**2020 – NAIP Orthophoto (0.60 m)**  
Four‑band CNIR aerial imagery collected pre‑fire, used for vegetation condition assessment and contextual mapping.  
**Data Source:** https://earthexplorer.usgs.gov/scene/metadata/full/5e83a340bf820c39/2991624/

**2022 – NAIP Orthophoto (0.30 m)**  
Higher‑resolution four‑band CNIR imagery collected post‑fire, supporting canopy‑loss interpretation and fine‑scale change detection.  
**Data Source:** https://earthexplorer.usgs.gov/scene/metadata/full/5e83a340bf820c39/3223342/


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

## Preprocessing preliminary workflow
- **ArcGIS Pro**
  - Identify Extent of Study Area
  - Define Projection of 2008 Lidar Dataset
  - Extract LAS using mask of study area <br>

## Methods
<p align="center">
  <img src="workflow.jpg" width="800" title="Beachie Creek Burn Severity">
</p>

### Quality control
#### Info
   - processed in *LP360*
#### Point Density
  - NPS from both dates
  - Point Density Raster
  - Scan Angle
#### Flight Lines
  - Check for Gaps
  - Vertical Accuracy (Visual)
  - Generate Rasters and calculate RMSE (Statistical)
#### Point Consistency Check for Ground Classification
  - Known stable sites
  - Avoid ground under canopy
  - 8-15 patches
  - DoD = DEM 2022 – DEM 2008
  - Calculate Zonal Stats (RMSE)

### Ground Classification
#### **Info**
  - Classify only 2022 scan
  - Use 2008 scan as reference
    - keep ground surface provided to USGS 3DEP

#### **Process**
  - Filter out low noise
  - Seed and Densify
    - Conservative settings to avoid misclassification of debris and vegetation
  - Ground thinning
    - smooth out remaining ground

#### **Ground Accuracy**
  - *(insert table of RMSE from 2008 surface)*
  - **+0.46** bias of 2022 surface compared to 2008 ground
    - too high for fine scale debris work
    - acceptable for canopy height work

### Vegetation Classification

#### **Info**
  - Both 2008 and 2022 scans require vegetation classification
  - Focus on **tall vegetation** for canopy height modeling
  - Classified using current standards in Pacific Northwest.

#### **Process**
  - Method: *Height Above Ground*
  - *(insert chart of classfication values)*
  - *(insert profile views of classification results)*

### Vegetation Change Detection

#### **Canopy Height Model (CHM)**
$ CHM = DSM - DEM $

  - Digital Surface Model (DSM) - Vegetation and Ground classifications, First returns only
  - Digital Elevation Model (DEM) - Ground Points only
  - Canopy Height Model (CHM) = DSM - DEM
    - Each pixel tallest vegetation as height above ground.
      - Resolution: *(insert res)*

#### **Difference Canopy Height Model (dCHM)**
The dCHM is a raster with measurable differences in elevation where canopy is either gained or lost (forested or burnt). This can be used to **classify burn severity** and identify **areas of interest**.
<br>
<br>
$ dCHM = CHM_{2008 prefire} - CHM_{2022 postfire} $
<br>

  - *Positive result = Net canopy growth*
  - *Negative result = Net canopy loss*
<br>

## Results
