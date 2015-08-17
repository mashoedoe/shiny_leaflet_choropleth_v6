# Shiny Leaflet Choropleth (version 6)
A choropleth map of South Africa at ward, municipal & provincial level built in R using @RStudio's Shiny, their R package for @Leaflet and system call's to @mbloch's mapshaper to convert source map files from ESRI shapefiles to @mbostock's TopoJSON format.

R scripts to recreate the GIS data for this app can be sourced at [https://github.com/mashoedoe/shiny_leaflet_choropleth]. From version 4, reactiveValues  are used to allow different map levels to be called the same leafletProxy functions (where possible) no matter the map object sourced for that level. Version 5 added the option to choose $*click on*$ reactivity instead of $*hover over*$. The $*hover over*$ option now use the static topojson string objects (created during pre-processing with the R scripts) on all 3 levels. Because the topojson objects are static and individual geometry styles can't be manipulated in the App, single shape outlines to indicate which element is being hovered over are still produced dynamically by sub-setting a spatial polygon dataframe object in response to user mouse over events from the topojson object layers.

The $*click on*$ option uses the slower loading spatial polygon dataframe format objects for all 3 layers. The authors of Rstudio's Leaflet package have integrated the popups option into the leaflet calls for adding spatial polygons which gives it an advantage over topojson objects where $*click on*$ is preferred or mouse over is undetectable, for example when accessing the map on a mobile device.

Version 6 tries alternatives to underlying reactive code compared to version 5 in preparation for version 7.

Inspired by @jcheng5's [https://jcheng.shinyapps.io/choropleth3] and @jcheng5 & @yihui's [https://github.com/rstudio/leaflet/blob/master/inst/examples/shiny.R]
