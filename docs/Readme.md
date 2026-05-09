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

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 1.</strong> 3D GIS fusion view of ravine in study area using LiDAR and NAIP imagery <br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet<br>
    Sources: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530), 2022 USGS Western Wildfires A22 LiDAR, 2020 NAIP Orthophoto (0.60 m), 2022 NAIP Orthophoto (0.30 m)</em>
  </figcaption>
  <img src="Ravine_Before_and_After.jpg" width="600" alt="3D GIS fusion view of ravine before and after fire">
</figure>

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 2.</strong> 3D GIS fusion view of stand before and after fire.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet<br>
    Sources: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530), 2022 USGS Western Wildfires A22 LiDAR, 2020 NAIP Orthophoto (0.60 m), 2022 NAIP Orthophoto (0.30 m)</em>
  </figcaption>
  <img src="Stand_before_and_after.jpg" width="600" alt="3D GIS fusion view of stand before and after fire">
</figure>


## Data

**2008 – OR Willamette Valley OLC 2008 (Tile: 001530)**  
Baseline pre‑fire dataset collected for the USGS 3DEP program representing forest and terrain conditions prior to the Beachie Creek Fire.  
**Data Source:** https://www.sciencebase.gov/catalog/item/64174dabd34eb496d1d165cb

**2022 – USGS Western Wildfires A22**  
Post‑fire dataset acquired after the burn, used to assess structural change and recovery patterns.  
**Data Source:** https://rockyweb.usgs.gov/vdelivery/Datasets/Staged/Elevation/LPC/Projects/OR_WesternWildfires_A22/

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;"> <strong>Table 1.</strong> LiDAR scan info<br>
  </figcaption>
  <img src="data.jpg" width="700" alt="3D GIS fusion view of stand before and after fire">
</figure>

**2020 – NAIP Orthophoto (0.60 m)**  
Four‑band CNIR aerial imagery collected pre‑fire, used for vegetation condition assessment and contextual mapping.  
**Data Source:** https://earthexplorer.usgs.gov/scene/metadata/full/5e83a340bf820c39/2991624/

**2022 – NAIP Orthophoto (0.30 m)**  
Higher‑resolution four‑band CNIR imagery collected post‑fire, supporting canopy‑loss interpretation and fine‑scale change detection.  
**Data Source:** https://earthexplorer.usgs.gov/scene/metadata/full/5e83a340bf820c39/3223342/

## Study Area 

### Location: 
  Santiam Canyon, Marion County, Oregon, US <br>

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 3.</strong> Overview of Beachie Creek fire perimeter and selected study area.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: WGS 1984 UTM 10N<br>
    Source: Copernicus Data Space Ecosystem (Sentinel‑2B MSI), European Union/ESA</em>
  </figcaption>
  <img src="Overview.jpg" width="1000" alt="">
</figure>

### Description:
 A 160 acre site was selected at random in the extent of the overlapping coverage zones of available LIDAR data. The chosen area contains 4 distinct regions of interest. There is a riparian corridor in a ravine carved by fish creek which is flanked to the east and west by steep rising slopes. The western slope is dominated by mature forest, while the eastern slopes, contain younger vegetation that shows evidence of post-harvest regeneration. Finally, in the center and southeast portions of the study area there are two open areas that appear to have been harvested prior to the 2008 USGS 3DEP scans. **

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 4.</strong> Pre- and post-fire detailed view of 160-acre study area in Beachie Creek Fire.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: Oregon Statewide Lambert (ft) <br>
    Source: 2020 NAIP Orthophoto (0.60 m), 2022 NAIP Orthophoto (0.30 m) 
    </em>
  </figcaption>
  <img src="study area.jpg" width="1000" alt="">
</figure>

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 5.</strong> Pre-fire profile view of 160-acre study area in Beachie Creek Fire.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Source: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530) 
    </em>
  </figcaption>
  <img src="Lidar.jpg" width="600" alt="">
</figure>


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

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 6.</strong> Profile view of vegetation classification of 160-acre study area in Beachie Creek Fire.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Sources: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530), 2022 USGS Western Wildfires A22 LiDAR </em>
  </figcaption>
  <img src="veg_class.jpg" width="800" alt="">
</figure>

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
