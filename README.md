# RADAR_Sentinel1
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

- Open SNAP Desktop and subset images according to 
- Geometric Calibration
- Radiometric Calibration
- Speckle Reduction
- Histogram Analysis 
- Creating a Threshold to Separate Water and Land (based on histogram analysis)
- Band calc (255*(Sigma0_VHdB<[Value])
- Open QGIS and visualize the images.

### Results
- 11 December 2019


- 23 December 2019


### Conclusions

### References
