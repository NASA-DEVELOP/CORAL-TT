====================
CORAL-TT 2: NDTI Tool
====================

Date Created: October 10, 2018

This executable Google Earth Engine (GEE) code calculates and visualizes median Normalized Difference Turbidity Index (NDTI) values over the Golfo Dulce region using surface reflectance data (red and green bands) from the Landsat platform. The retrieval periods are wet seasons (August through November) from 1991 to 2016 at a 5 year interval. Furthermore, using Quality Assessment (QA) bands provided  by the Landsat platform, clouds are filtered out over the study region. At the end, NDTI maps can be exported as GeoTIF files for further analysis. In general the code can be used for other regions too. However, it should be noted that it is not applicable to compare NDTI over different regions because the output values are relative within the study area.

Required Packages
===================
* Google Earth Engine API


Required Data Inputs 
===================
* USGS/NASA's Landsat 8 surface reflectance tier 1 dataset (2014-2017)
* USGS/NASA's Landsat 7 surface reflectance tier 1 dataset (2003-2013)
* USGS/NASA's Landsat 5 surface reflectance tier 1 dataset (1991-2002)
* Study Area Geometry

Tool Use
-------------
To edit the code indirectly, open the tool and click “Get Link” in the top right of the code editor box. Copy the link that appears in the web browser and paste it into a new tab. When finished, save the edited code to your own repository. 


1. If the user wishes to make any parameter updates, do so as outlined in the section below.
2. Save any updates by clicking the ‘Save’ button before clicking ‘ Run’ to execute the code.
3. Note that pixels with no data from Landsat, are replaced with “9999” value so they can be filtered in post-processing/visualization softwares.
4. Two masks will be created after running the script: mask_vis and mask_data. The mask_vis image is used to filter out land for visualization (with -9999 pixel value over land), and mask-data is used for results analyses (with -9999 pixel values over the gulf).
5. A list of images to be exported is available under “task” tab. These must be run individually. This process may take a few minutes. 
6. The user can toggle between layers for each study area by navigating to the ‘Layers’ button in the map panel and selecting or deselecting maps to display.
7. To export maps, the user can go to the ‘Tasks’ tab in the right console and click ‘Run’ for any file they wish to save to the drive.

Parameters
------------------
Note: It is not recommended to change the dates within the code because image collections and reflectance bands would then also have to be changed.


1. The user can define any study area in line 31 through 53. If using a shapefile, study area shapefile should be imported in “Assets” tab.
1. Upload a shapefile of the desired coastline as a GEE asset. Choose the ‘Assets’ tab in GEE in the left top panel, choose ‘New’, and then ‘Table Upload’. Select the .shp, .shp.xml. .dbf, .cpg, .prj, .sbn, and .shx  files from your database (omit .sbx file).
2. Replace the study area path on line 31 with the path of the new asset. This will most likely be something like “user/yourUsername/yourAssetName’. yourAssetName can be found in the ‘Assets’ tab.
2. User can define min/max values for color legend and also the color palette in line 128.
3. User can define map center and zoom level by editing “(Longitude, Latitude, Zoom level)” in line 136. Please note that these changes do not affect exported images.
4. Save the code with any updates. 


Contact
------------
Name: Soroush E. Neyestani
E-mail address: seneyestani@uga.edu