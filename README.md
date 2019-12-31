# RADAR Sentinel-1A/B
## Mondego flood monitoring with Sentinel-1 using Snap Toolbox and QGIS.
### Introduction
Synthetic Aperture Radar (SAR) can observe the Earth's surface day and night, through most weather conditions, 
and the signal can penetrate the vegetation canopy. Unlike optical images, SAR is not depends on cloudless, 
well-illuminated areas to produce quality data. For more details please check the page of the ESA.

### Metodology
#### Data and Software
Data of images
Two Sentinel-1A IW GRDH images with VV polarization acquired before the flood event on 11 December 2019 
and after the flood event on 23 December. The images are downloadable in https://scihub.copernicus.eu/

- Before flood: S1A_IW_GRDH_1SDV_20191211T064251_20191211T064316_030297_03770D_7B8C
- After flood:  S1A_IW_GRDH_1SDV_20191223T064251_20191223T064316_030472_037D16_1012

Software: SNAP Toolbox for image processing and QGIS to visualize and build maps.

#### Processing images (Steps)
- Open SNAP Desktop and subset images according to scene start X:708;scene start Y:4248;scene end X:1912;scene end Y:1151
- Radiometric Calibration (Menu RADAR -> Radiometric -> Calibrate)
- Speckle Reduction (Menu Radar -> Multilook)
- Geometric Calibration (RADAR -> Geometric -> Terrain Correction -> Range Dopler Terrain Correction with UTM/WGS 84 coordinates)
- Convert Sigma0 into dB by highlighting Sigma0_VH and left clicking5.A menu will pop up.
- Histogram Analysis 
- Creating a Threshold to Separate Water and Land (based on histogram analysis)
- Band calc (255*(Sigma0_VHdB<[Value])
- Open QGIS and visualize the images.

### Results
#### 11 December 2019

![Image](https://github.com/DuarteAndre/RADAR_Sentinel1/blob/master/20191211_Water.png)

#### 23 December 2019
![Image](https://github.com/DuarteAndre/RADAR_Sentinel1/blob/master/20191223_Water.png)

### Conclusions
Image processing is very simple and fast. We don't have images captured during the critical period, so it was necessary to use the 23 December Sentinel-1 image. Despite the dates of the pictures it was possible to monitor the flood.The range of values through the histogram for reclassification is a subjective process.
QGIS help us to preform the visualization and the final maps. 

### References
Fayne, J., Bolten, J., Lakshmi, V., & Ahamed, A. (2017). Optical and Physical Methods for Mapping Flooding with Satellite Imagery. In Remote Sensing of Hydrological Extremes (pp. 83–103). Springer, Cham. https://doi.org/10.1007/978-3-319-43744-6_5

NASA ARSET (2017). Introduction to Synthetic Aperture Radar;Introducción al Radar de Apertura Sintética. Applied Remote Sensing Training. Available online: https://arset.gsfc.nasa.gov/. 

Serco Italia SPA (2018). Flood Monitoring with Sentinel-1 Using S-1 Toolbox - January 2015, Malawi (version 1.2). Retrieved from RUS Lectures at https://rus-copernicus.eu/portal/the-rus-library/learn-by-yourself/

