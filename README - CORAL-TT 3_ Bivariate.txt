========================
 CORAL-TT 3: Bivariate_Charts
========================

Date Created: October 29, 2018

The bivariate portion of the Google Earth Engine (GEE) tool combines Sea Surface Temperature (SST) and Normalized Difference Turbidity Index (NDTI) data by using a bivariate key to overlay the fluctuations of these variables. Combining the processing and analysis of seasonal fluctuations for both parameters into one map enables the user to pinpoint areas that are best suited for coral restoration. Areas of white represent low turbidity and SST, areas of red represent high turbidity and low SST. Areas of blue represent areas of low turbidity and high SST, and areas of purple represent areas of high turbidity and high SST. The code also creates downloadable charts in the console for SST and NDTI changes over time. Mean NDTI and SST time series charts over the Golfo Dulce are plotted for 2003-2013 and 2014-2017 periods separately, producing a total of 4 charts. 

Required Packages
===================
* Google Earth Engine API


 Required Data Inputs
=====================
* Ocean Color SMI: Standard Mapped Image MODIS Aqua Data
* USGS/NASA's Landsat 8 surface reflectance tier 1 dataset
* Study Area Shapefile
* Coordinates of desired region for exporting


Tool Use
-------------
To edit the code indirectly, open the tool and click “Get Link” in the top right of the code editor box. Copy the link that appears in the web browser and paste it into a new tab. When finished, save the edited code to your own repository. 


1. If the user wishes to make any parameter updates, do so as outlined in the section below.
2. Save any updates by clicking the ‘Save’ button before clicking ‘ Run’ to execute the code.
3. The user can toggle between layers for each study area by navigating to the ‘Layers’ button in the map panel and selecting or deselecting maps to display.
4. To download charts, the user can click the the pop-out button in the console next to the chart and select a download option (PNG, CSV, or SVG) in the new tab.
5. To export maps, the user can go to the ‘Tasks’ tab in the right console and click ‘Run’ for any file they wish to save to the drive. These will automatically be saved in a folder called “Bivariate SST NDTI” on the user’s Google Drive.


Parameters
-------------
Most parameters to adjust this analysis can be done in the Parameters section of the code, which starts on line 11. 
1. For the guf outline import a study area shapefile as an asset
1. Upload a shapefile of the gulf as a GEE asset. Choose the 'Assets' tab in GEE in the left top panel, choose 'New', and then 'Table Upload'. Select the .shp, .shp.xml, .dbf, .cpg, .prj, .sbn, and .shx from your database (omit .sbx).
2. Replace the study area path on line 17 with the path of the new asset. This will most likely be ‘'users/yourUsername/yourAssetName'. yourAssetName can be found in the 'Assets' Tab. 
2. On line 19, edit the geometry for which the exported map should include.
3. The start and end of the study range can be specified on lines 22 and 23.
4. The bivariate key colors can be specified on lines 26 and 27. The first color represents on the color that will appear in the left hand, bottom corner. The subsequent colors are the left color, middle row color, with the color specified after that being the top left color. The fourth color is the bottom color in the second column.
5. The opacity, palette, and number of cells for the key appearing on the UI panel can be altered in line 30.
6. Binary color thresholds will need to be adjusted based on the study area. After running the code once to see the minimum, median and maximum of the SST and NDTI fluctuations, the user should update the thresholds in lines 49 through 54. 
7. User can change charts’ title, units, and grid line intervals in “set options” lines for each chart (lines 400-402, 411-413, 422-424, and 433-435).
8. Save the code with any updates.


Contact
---------
Name: Hikari Murayama
E-mail: hmurayam@wellesley.edu