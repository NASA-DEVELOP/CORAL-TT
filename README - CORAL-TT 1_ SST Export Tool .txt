=======================
CORAL-TT 1: SST Export Tool
=======================

Date Created: October 18, 2018

GEE API code was used to create an interactive tool to display and export maps of Sea Surface Temperature (SST) data taken from Aqua MODIS. The code is set to focus on the Osa Peninsula region of Costa Rica and seasonal calculations are based on weather patterns in the area. The median values were calculated for each season (dry: February-May, rainy: August-November) from 2002 to 2018. The maps can then be exported as GeoTIF files for further analysis using other GIS softwares. Additionally, the tool has another interactive component where a user can select any point and a chart will be generated for SST data available over the given time frame. Two tools were made: one for 2008 through 2018, one for 2002 through 2007 based on partner request and limitation of Google Earth Engine (GEE) to process more than 5000 data points. 

Required Packages
===================
* Google Earth Engine API


Required Data Inputs 
===================
* Ocean Color SMI: Standard Mapped Image MODIS Aqua Data
* Study Area Shapefile (optional but useful for delineating which pixels cover both land and water)
* Coordinates of desired region for exporting


Tool Use
-------------
1. If the user wishes to make any parameter updates, do so as outlined in the section below.
2. Save any updates by clicking the ‘Save’ button before clicking ‘ Run’ to execute the code.
3. SST Data Chart: Select a point on the map to display a chart of SST over the given time span. The latitude and longitude will be displayed for reference. To export the chart for further analysis, click the grey arrow in the top right corner. A new tab will open with an expanded image of the map. Use your mouse to hover over individual data points or download the chart as a CSV or PNG file. 
4. SST Map Viewer: Using the drop-down menus in the user interface, select a year and season of interest and select “Display Map”. The map will then appear in the display area. More years and seasons can be selected and displayed and then be toggled between using the “Layers” toolbar in the top right corner of the map display area. 
5. SST Map Exporter: To export the most recently selected map, click “Export Map”. A task will appear in the the Tasks zone of your Google Earth Engine screen. Click on the tab and run the highlighted task. It may take a few minutes for the map to download. When finished, a GeoTIF file will be saved which can be imported into ArcGIS or another mapping software for further analysis. 


Parameters
-------------
Note: These instructions work for either the 2002-2007 or the 2008-2018 tool.
To edit the code indirectly, open the tool and click “Get Link” in the top right of the code editor box. Copy the link that appears in the web browser and paste it into a new tab. When finished, save the edited code to your own repository. 

1. Line 16: Identify dates of interest and edit them using the filterDate command.
2. Line 19 (and 20): Ensure that the dictionary for years matches up with the years of interest selected in step 1. 
3. Line 23: Identify starting months of seasons of interests and adjust the season dictionary. 
4. Line 26 and 27: Adjust the minimum and maximum temperatures as necessary depending on the region.
5. Line 33: Import study area outline if needed from personal downloaded assets:
1. Upload a shapefile of the desired coastline as a GEE asset. Choose the ‘Assets’ tab in GEE in the left top panel, choose ‘New’, and then ‘Table Upload’. Select the .shp, .shp.xml. .dbf, .cpg, .prj, .sbn, and .shx  files from your database (omit .sbx file).
2. Replace the study area path on line 33 with the path of the new asset. This will most likely be something like “user/yourUsername/yourAssetName’. yourAssetName can be found in the ‘Assets’ tab. 
3. If electing not to include a study area outline in the tool, comment out line 33 and any other mention of studyArea. 
6. Line 36: Change the initial point to be within the region of interest. 
7. Line 37: Change the coordinates of the region of interest.
8. Line 40: Change the season length if necessary. For example, if your season lasts 5 months the season length will be 4, as in 4 months after the initial month. 
9. Line 92: Adjust the label to explain the seasons you have selected, if necessary. 
10. Line 267 and 270: Change titles for season of interest if necessary. 
11. Save the code with any updates. 


Contact
---------
Name: McKenna Barney
E-mail: mckenna.a.barney@gmail.com