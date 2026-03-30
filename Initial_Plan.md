# Idea Pitch

## Slide 1 - Project Overview
- Building on prior wildfire analysis in the Pacific Northwest, including the Beachie Creek burn area
- Earlier work mapped regional burn severity; this project shifts to a fine‑scale LiDAR study
- Focus: a small portion of the burn scar to examine canopy loss, surviving structure, and terrain‑driven burn patterns
- (Graphic) Severity map of Santiam Canyon Region
<p align="center">
  <img src="Santiam_Canyon.jpg" width="400" title="Beachie Creek Burn Severity">
</p>

## Slide 2 - Data
- Data Source: USGS
- prefire: 2008–2009
    - USGS 3D Elevation Program (3DEP) 
    - Format: LAZ
- postfire: 2020 – 2022
    - Western Wildfires project
    - Format: LAZ
- Both datasets provide high‑resolution, multi‑return LiDAR suitable for canopy and terrain analysis
- Compatible resolution and classification allow direct pre/post comparison

## Slide 3 - Study Area
- Identify study area
    - Size
    - Relative location
    - Coordinates
- Initial Point Cloud Viability Stats
    - prefire
        - point density
        - total points
        - number of returns
        - Classification Status
    - postfire
        - point density
        - total points
        - number of returns
        - Classification Status

## Slide 4 - Analysis
- Canopy Loss
    - Canopy Height Models, pre and post fire
    - Summarize
- Trees still standing / surviving structure
    - Identify tall objects postfire
    - Profile views
- Identify factors with unburnt regions in study area
    - Classify pixels/points by canopy change (whats different)
    - Slope (from DTM)
    - Aspect (north vs. south facing)
    - Elevation

## Slide 5 - Lidar Techniques
- QA/QC
    - Metadata / projection verification
    - Point density check  
    - Return distribution check
    - Flight line overlap check
    - Elevation consistency check
    - Noise / outlier removal
    - Classification accuracy check
- Vegetation Classification
    - Canopy Height Model (CHM)
- Raster Generation
    - DTM (Digital Terrain Model) = ground surface
    - DSM (Digital Surface Model) = top of canopy
    - CHM (Canopy Height Model) - canopy height
        - CHM = DSM − DTM
- Profiles
    - Cross‑section profiles  
    - Identification of remaining tall trees 

## Slide 6 - Goals (Maybe)
- Quantify canopy loss in a high‑severity burn area
- Identify surviving structure and postfire forest patterns
- Understand terrain factors influencing unburnt patches
- Demonstrate a complete LiDAR workflow (QA/QC → DTM/DSM → CHM → change detection)