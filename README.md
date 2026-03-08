# module7_FinalProjectBetaVersion
This repository is created for the beta version of my final project for MAP 673 course
# Title : Urban Tree Phenophase Explorer

## Overview
The purpose of the project is to develop an interactive webmap that explores the phenophase of different trees across the UKY campus at species-level. It allows the user to view different phenophase of individual trees across multiple years. Phenophases are the different stages of biological events in a plant's life cycle such as greenip, sensescence, dormancy, maturity etc. The user can gain insight about the timing of these different stages across multiple years of more than 2600 trees.

## Data Source

The datasets include
 ### 1) UK Tree Inventory Data
 The spatial dataset contains the approximate canopy extent for these individual trees across the campus. The base dataset was collected from the UK Facilities and Management department and then later refined and converted into polygon data by using Arc GIS pro

 ### 2) Phenophase Data
 The phenophase were calculated using time-series NDVI data derived from PlanetScope imagwes. These represent key transition in tree canopy development. Six phenophase were calculated in this study. These are

 Greenup onset
 Mid Greenup
 Maturity
 Senescence onset
 Mid Senescence 
 Dormancy

 These datasets are included in the repository under the Data folder.

 ## Representation
 The map represents indivdual trees as color-coded polygon. Each tree is colored based on the species name derived from the inventory dataset. The legend shows all species and their corresponding color. The map has some interactive popups that allows the user to see the Tree Name, Tree ID (TARGET_FID) and the Phenophases for the selected year. Additional UI controls were added to the map that allows the user to toggle between the years and filter the trees by species name.

 ## UI Design
The interactive map follows a three column layout. The central panel includes the main map displaying the color coded polygons across the study area. The left panel contains the year toggle control, species filter and the legend. The right panel displays the information of the trees when the user clicks on a specific tree polygon. For the title display, the map uses a Playfair Display font and for the interface text it uses Inter font.

## Map Objective 

The objective of the map is to present the phenological data in an interactive format for broader audience. Though these type of data are mainly presented in scientific articles, rarely they are presented in an interactive way. Thus the main purpose of this is to show how hard scientific data can be presented in an interactive manner for the broader audience.


## Description about Beta Version

The beta version was created using single index html file. This integrates all the required libraries and the functions needed to load the spatial and the tabular datasets. The core logic of the application is implemented through several JavaScript functions within the index html file. The map was centerred on the UK campus and the dark CARTO was used as the basemap. The csv/tabular data which was the phenophase dataset was loaded using Papa Parse function. The shapefile zip was loaded using the shp.js function. JoinData () was used to join the shapefile and the CSV using the common TARGET_FID column. The result was the creation of a combined dataset that contained both geometric and phenophase attributes. speciesColorMap function was used to identify unique species name from the dataset and assign color to them. styleFeature() and fillcolor was used to draw polygons and apply the assigned color of that species. Legend was created using the buildLegend() functionwhich read the species name from the color map. renderInfo() was used to ensure that the righ-side information keeps on updating when a user clicks on a tree. When the user clicks on the year of the changes the species filter the map redraws with those specific data. This process was computed using the refreshMap() function.