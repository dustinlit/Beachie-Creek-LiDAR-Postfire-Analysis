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

## Data
I used LiDAR collected by the USGS. The 2008 data was collected as a baseline to accurately map the regions elevation as part of the 3D elevation program. The 2022 set was part of a series of targeted projects to use LiDAR to study wildfires impacts on terrain in the western united states. The vertical datum was initially undefined in the 2008 data, but most USGS scans from the period were compatible with the NAVD88 datum from the 2022 set. Each series also uses different sensors with different scan angles and number of returns that affect their final point densities.

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

**Location:** Santiam Canyon, Marion County, Oregon, US <br>

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 2.</strong> Overview of Beachie Creek fire perimeter and selected study area.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: WGS 1984 UTM 10N<br>
    Source: Copernicus Data Space Ecosystem (Sentinel‑2B MSI), European Union/ESA</em>
  </figcaption>
  <img src="Overview.jpg" width="1000" alt="">
</figure>

### Description:
 The Beachie Creek fire was part of a complex of fires along the west coast whose intensity were sparked by an extreme wind event in Autumn of 2020. The fire devastated a large swath of forest in northwest Oregon as it burnt approximately a total of 190,000 acres. Its effects were felt in three counties and destroyed two towns. To better understand the spatial patterns of the fires severity, I selected a small study area within the burn. This area is limited in sized to focus on providing greater detail and to expedite point processing.
 
 A 160 acre site was selected at random in the extent of the overlapping coverage zones of available LIDAR data. The chosen area contains 4 distinct regions of interest. There is a riparian corridor in a ravine carved by fish creek which is flanked to the east and west by steep rising slopes. The western slope is dominated by mature forest, while the eastern slopes, contain younger vegetation that shows evidence of post-harvest regeneration. Finally, in the center and southeast portions of the study area there are two open areas that appear to have been harvested prior to the 2008 USGS 3DEP scans.


<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 3.</strong> Pre- and post-fire detailed view of 160-acre study area in Beachie Creek Fire.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: Oregon Statewide Lambert (ft) <br>
    Source: 2020 NAIP Orthophoto (0.60 m), 2022 NAIP Orthophoto (0.30 m) 
    </em>
  </figcaption>
  <img src="study area.jpg" width="1000" alt="">
</figure>

Using NAIP imagery, I identified four distinct areas of interest that I feel are typical for the region. a surviving grove in the north, a heavily burned grove in the south, a pre‑fire timber clearing, and a ravine containing fish creek that divides the study area. The western region was actively being cleared after the fire, so I decided to exclude it from the canopy analysis, but I still classified those points to provide topological context. Cleared patches from industrial timber operations are typical and scattered all throughout this area of the western cascades. Since It is state law in Oregon and good practice that all trees harvested must be replaced, both groves of interest in this study are likely composed of managed regrowth.

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 4.</strong> Pre-fire profile view of 160-acre study area in Beachie Creek Fire.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Source: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530) 
    </em>
  </figcaption>
  <img src="Lidar.jpg" width="600" alt="">
</figure>


## Preprocessing
- **ArcGIS Pro**
  - Identify Extent of Study Area
  - Define Projection of 2008 Lidar Dataset
  - Extract LAS using mask of study area <br>

## Methods
<p align="center">
  <img src="workflow.jpg" width="800" title="Beachie Creek Burn Severity">
</p>

### Quality Control

Evaluating the quality of both datasets. Each was verified to contain a point density well above the QL1 minimum of 0.743 points per feet squared. Due to different scan angles, the number of flightpaths required to capture the extent of the study area were dramatically different. The 2008 dataset contains 9 flightpaths and had good coverage and good overlap. The 2022 only consists of three flightpaths but there is still consistent overlap throughout the area and adequate coverage.

- **Point Density:** NPS for both years, density raster, scan angle review  
- **Flight Lines:** check for gaps, visual vertical alignment, generate rasters + RMSE  
- **Ground Consistency:** stable sites only (8–15 patches), avoid canopy cover,  
  DoD = DEM₍2022₎ – DEM₍2008₎, compute zonal RMSE


### Ground Classification

I found ground classification to be the most important and critical preprocessing step. After some experimentation, I ended up using conservative settings to try to avoid including excess vegetation and debris. However, the ground surface was still quite rough like in figure 3. I applied ground thinning to reduce remaining vertical noise, and finish with some manual cleanup. The surface is still not perfect as I found the region around the ravine to be particularly challenging. However, when compared with the 2008 provider classified ground surface, the mean difference was about +0.42 ft. This degree of bias is acceptable for canopy‑height work but might cause an issue with finer scale work like debris quantification.

- Classified **2022** LiDAR ground; used **2008 USGS 3DEP** ground as reference  
- Removed low noise prior to ground modeling  
- Applied **Seed & Densify** with conservative settings to avoid misclassifying debris or vegetation  
- Performed **ground thinning** to smooth remaining artifacts  
- Identified a **+0.46 ft bias** in the 2022 ground surface relative to 2008  
  - Too high for fine‑scale debris analysis  
  - Acceptable for canopy‑height modeling

### Vegetation Classification

Next step was the vegetation classification. One factor that made this simpler was the lack of buildings and man-made structures in the area, which is a consistent pattern seen throughout most of the region. Calculating by height above ground, I have matched thresholds to current general practicing standards in the pacific northwest, where mature trees can realistically reach heights around 200 ft. The post fire classification likely includes a good amount of debris in the low vegetation category but in this case I feel it is acceptable for canopy measurements.


  - Both 2008 and 2022 scans require vegetation classification
  - Focus on **tall vegetation** for canopy height modeling
  - Classified using current standards in Pacific Northwest.
  - Method: *Height Above Ground*
  - Thresholds
    - Low Vegetation = < 6.5 ft
    - Medium Vegetation = 6.5 - 33 ft
    - High Vegetation = 33 - 250 ft

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 5.</strong> Profile view of vegetation classification of 160-acre study area in Beachie Creek Fire.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Sources: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530), 2022 USGS Western Wildfires A22 LiDAR </em>
  </figcaption>
  <img src="veg_class.jpg" width="800" alt="">
</figure>

### Vegetation Change Detection

#### Canopy Height Model (CHM)
The canopy height model visualizes the vertical structure of the study area. A DEM from comparable pre-and post-fire ground surface and respective quality digital surface models generated from first returns are used to create a canopy height model. To learn more about the pattern of changes that were caused by the fire, contrasting CHMs from both time periods are used to generate a difference CHM to identify areas with net canopy loss or gain.

<div style="text-align:center; margin: 8px 0; font-style:italic;">
  CHM = DSM − DEM
</div>

  - Digital Surface Model (DSM) - Vegetation and Ground classifications, First returns only
  - Digital Elevation Model (DEM) - Ground Points only
  - Canopy Height Model (CHM) = tallest vegetation pixel as height above ground.


#### Difference Canopy Height Model (dCHM)

The dCHM is a raster with measurable differences in elevation where canopy is either gained or lost (forested or burnt). This can be used to **classify burn severity** and identify **areas of interest**.

<div style="text-align:center; font-style:italic; margin:10px 0;">
  dCHM = CHM<sub>2008&nbsp;prefire</sub> − CHM<sub>2022&nbsp;postfire</sub>
</div>

  - *Positive value = Net canopy growth*
  - *Negative value = Net canopy loss*
<br>

## Results

### Terrain

The resulting products generated from the 2022 LiDAR gives a good understanding of the topography of the study area. The entire region descends in elevation from about 2200 feet in the north to about 1300 ft in the south. The ravine in the center is flanked by steep slopes to the west and gentler slopes in the east. Overall, the region is dominated by southern and eastern facing slopes and very few northern facing slopes are present. This makes this area particularly vulnerable to severe fire damage as it tends to experience drier conditions from additional solar exposure. 
<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 6.</strong> 2022 LiDAR‑derived slope map with 10‑ft contours for the 160‑acre study area within the Beachie Creek Fire perimeter. Steeper slopes are concentrated along the central ridgeline, while gentler terrain occupies the lower benches and drainage corridors.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Sources: 2022 USGS Western Wildfires A22 LiDAR </em>
  </figcaption>
  <img src="topo.jpg" width="800" alt="">
</figure>

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 7.</strong> 2022 LiDAR‑derived aspect map showing directional slope exposure across the 160‑acre study area. South‑ and east‑facing slopes dominate the ridgeline, while cooler north‑facing aspects are rare.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Sources: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530), 2022 USGS Western Wildfires A22 LiDAR </em>
  </figcaption>
  <img src="aspect.jpg" width="800" alt="">
</figure>

## Vegetation

Here is the canopy height models for each of the two LiDAR datasets. 2008 represents the baseline pre‑fire canopy. You can see in the post fire image the dramatic reduction of canopy in the western and southern zones. Keep In mind that the loss in the western zone is mostly due to logging and some extreme values were generated along the ravine and are likely due to ground‑classification issues in that steep and rugged terrain, so those areas should be interpreted cautiously. One thing I want to point out here is how well the LiDAR captures the vertical structure. In the 2008 CHM, you can see a continuous canopy across most of the northern and western areas and can clearly differentiate the groves by height. The small grove in the north is clearly the youngest while the western zone is mostly mature trees hovering around 200 ft+, an indication that this may be old growth. In the 2022 CHM, that structure is broken apart with some areas dropping all the way to ground level, while the northern grove still shows mainly intact canopy. This contrast helps to tell the story of the fires behavior.

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 8.</strong> LiDAR‑derived Canopy Height Models (CHM). LEFT: 2008 (pre‑fire) RIGHT: 2022 (post‑fire) Illustrates major changes in forest structure following the Beachie Creek Fire. The pre‑fire CHM shows mature closed‑canopy forest, while the post‑fire CHM reveals widespread canopy removal and isolated pockets of surviving vegetation.<br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Sources: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530), 2022 USGS Western Wildfires A22 LiDAR </em>
  </figcaption>
  <img src="chm.jpg" width="1200" alt="">
</figure>

Subtracting the post‑fire CHM from the pre‑fire CHM gives us a difference CHM. The statistics calculated within the blue analysis area show a clear local trend in canopy loss. The northern grove, which sits at higher elevation where we may typically see greater canopy loss, actually shows net positive growth, while the southern grove — lower in the terrain — experienced severe canopy loss. 

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 9.</strong> LiDAR‑derived difference Canopy Height Model (dCHM) showing canopy height change between 2008 and 2022. Negative values (white) indicate canopy loss from the 2020 Beachie Creek Fire, with the largest reductions occurring on exposed slopes and ridge tops. Limited positive values (black) reflect regrowth or surviving structure in protected terrain. <br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Sources: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530), 2022 USGS Western Wildfires A22 LiDAR </em>
  </figcaption>
  <img src="dchm.jpg" width="800" alt="">
</figure>

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Table 2.</strong> Mean Canopy Loss by Terrain Class <br>
  </figcaption>
  <img src="table2.jpg" width="400" alt="">
</figure>

## Areas of Interest
The northern grove saws a 60 percent increase in high vegetation points reinforcing the canopy growth in the region. The notable decrease in mid-level vegetation points may be due to the lower vegetation being consumed by the fire, while also being possible that limited ladder fuels in the grove may have prevented significant damage to the canopy. The southern grove saw severe losses with over 80 percent reduction in both the medium and high vegetation. 

What’s interesting here is that these two groves aren’t very far apart. The northern grove sitting at a higher elevation and may have benefitted from slightly cooler conditions, and fewer ladder fuels. The southern grove, on the other hand, sits lower in the terrain and may have had more continuous fuels feeding the fire. This contrast shows how local conditions can create patchy results even though the broader region has a high burn‑severity classification. Its possible the clearing between these two groves may have created a break in the fire that which led to such dramatically different outcomes. However, many other factors contribute to fire behavior including wind speed and intensity and available fuel sources.

<figure>
  <figcaption style="font-size:0.9em; margin-bottom:8px;">
    <strong>Figure 10.</strong>  LiDAR‑based comparison of vegetation structure in the Northern (~14 acres) and Southern (~35 acres) groves using pre‑fire (2008) and post‑fire (2022) point clouds. <br>
    <em>Map Author: Dustin Littlefield <br>
    Spatial Reference: NAD 1983 (2011) Oregon Statewide Lambert (ft), NAVD88 (Geoid 18), US Survey Feet <br>
    Sources: 2008 USGS 3DEP LiDAR (OR Willamette Valley OLC 2008, Tile 001530), 2022 USGS Western Wildfires A22 LiDAR </em>
  </figcaption>
  <img src="groves.jpg" width="1800" alt="">
</figure>

## Lessons Learned
A few key lessons stood out for me while completing this project.
  1) Ground generation is critical and can be a laborious process. It is important to identify the level of accuracy necessary given specific use cases and study extent.
  2) Reducing the extent of this project made it much more manageable and allowed for more efficient experimentation. I can foresee how it is important to refine the process with a smaller area before processing the full extent. 
  3) Narrowing the focus to one specific effect delivers better quality results. 
For instance, the image on the right was part of my attempt at debris classification. And while there was slight success in identifying downed trees in the west and south, the overall raster was too noisy for meaningful analysis. It became evident that debris classification and fuel structure probably require a higher point density to create more accurate ground and vegetation accuracy to generate meaningful results.
