---
title: "**A First Map in QGIS: click-by-click instructions**"
author: "Mark Torrey"
date: "2024-05-30"
---


# Let's get into QGIS

## **Adding your first data**
1. Start QGIS
2. Click on: \boxed{Project} &rarr; \boxed{New} <!-- \rightarrow causes an error here and there's no simple html way to box text. So a mix of html and latex. Thank you so much pandoc. -->
3. Click on: \boxed{Layer} &rarr; \boxed{Add Layer} &rarr; \boxed{Add Vector Layer...}
    * This will open a new window: the add-layers window.

<!-- note: you can't add a comment just after an indented bullet -- it breaks pandoc -->


## **Adding your first data --- in the add-layers window**
1. Click the \boxed{...} button (next to the "Vector Dataset(s)" blank box).
2. This will open a file browser. Go into the "NYC-community-districts" folder and select the file that ends with .shp and open it.
3. Back in the add-layers window, Click the \boxed{Add} button. You should see NYC appear in the map window.
4. Click \boxed{Close} in the add-layers window.
    * (Somewhat confusingly, it doesn't close on its own.)

<!-- TODO: add image of add layer window, either here or next slide -->
<!-- 	* ![connected.png](./screenshots/connected.png){ width=5in } -->

## **A little layer organizing**
1. In the layer window, right-click your data layer with the crazy geo_export_blahblahblah name, and click on \boxed{Rename Layer}
    * Name it something like "NYC CDs" (for Community Districts)
2. Right-click your "NYC CDs" layer in the layer window again, and click on \boxed{Properties...}
    * (This will open the Properties window)
3. Select \boxed{Symbology} and then click on the line that says \boxed{Simple Fill}. Click on the drop-down box for "Fill style" and select \boxed{No Brush}
4. Click the \boxed{OK} button.
    * This will leave you with outlines of the community districts.

<!-- TODO: add image of empty NYC CDs outline -->


## **Add more data --- hospital location points**
1. Again, click on: \boxed{Layer} &rarr; \boxed{Add Layer} But this time select \boxed{Add Delimited Text Layer...}
2. In the add-layers window, click the \boxed{...} button, and browse to *Health_Facility_General_Information_20240520.csv* and open it.
3. Make sure the "Point coordinates" radio button is selected.
    * The "X field" should have "Facility Longitude" selected and the "Y field" should have "Facility Latitude" selected.
    * Notice in in the "Sample Data" section, you can see a preview of what looks an awful lot like an Excel spreadsheet, and it includes the "Facility Longitude" and "Facility Latitude" columns.
4. Click the \boxed{Add} button to add your data to the map, and then the \boxed{Close} button.


## **Let's look at the Attribute Table**
1. Right-click on the new layer you have in the layer panel now: *Health_Facility_General_Information_20240520* And select \boxed{Zoom to Layer(s)}
    * This always shows you the full extent of the data in the layer you right-clicked.
2. Let's look at the hospital point data in spreadsheet view: Right-click the hospitals layer again, and select \boxed{Open Attribute Table}
    * This opens the Attribute Table window. There's a row for every hospital point.


## **"Subset" so we can work with a little less data**
1. Left-click on the *Facility City* column name.
    * This will sort the column alphabetically.
2. Scroll down until you see *Bronx* listed in the Facility City column. Left-click the row number on the left to highlight the whole row.
3. Now scroll down until you see the last row in the Bronx, and hold Shift while left-clicking on the row number.
    * To highlight all the rows from your first selected row. Just like Excel!
4. Don't close the Attribute Table. Right-click on your *Health_Facility_General_Information_20240520* again, And select \boxed{Zoom to Selection}
    * (You can also use mouse scroll wheel to zoom in and out, and the hand tool to grab-and-drag.)
    * You can see all the hospitals in the Bronx that you selected in the Attribute Table are highlighted in yellow.

<!-- TODO: add image of selected hospitals in the Bronx -->


## **A little data cleaning**
1. Click the \boxed{Identify Features} button to activate that tool. <!-- TODO: add image of tool button -->
2. Left-click on the un-selected dots to see what's in the Attribute Table row for that item.
    * (You might need to use the mouse scroll-wheel to zoom in)
3. With the dot highlighted for information (in red), right click on the \boxed{Identify Results} pane, and from the context menu select \boxed{Toggle Feature Selection}
    * This adds the dot to your selection.
4. Add the rest of the dots that are not highlighted in yellow yet, but are clearly in The Bronx.


## **Extract just our Bronx data points**
1. Right-click on your *Health_Facility_General_Information_20240520* layer again, and select \boxed{Export} &rarr; \boxed{Save Selected Features As...}
    * This opens the export data window. <!-- TODO: add image of export data window-->
2. From the "Format" drop-down menu, select \boxed{GeoJSON}
    * (Notice that "ESRI Shapefile" is also on that list)
3. Click the \boxed{...} button and make sure you are saving in a directory that makes sense. Give the file a name like "Bronx_hospital_points". Click \boxed{Save} to get back to the export data window.
4. Everything else you can leave at the defaults. Click \boxed{OK} to export your data.
    * Your new layer of just Bronx hospital points will be added to the map.
5. Right-click the old layer that has all of NYS hospitals, and select \boxed{Remove Layer...}. Click \boxed{OK}


## **Classify the hospitals by type**
1. Right-click your "Bronx_hospital_points" layer and select \boxed{Properties...} to open the properties window again.
2. From the drop-down menu at the very top of the window where it says "Single Symbol" select \boxed{Categorized}
3. From the "Value" drop-down menu select \boxed{Description}
* If you want, you can click the "Symbol" button and pick a different shape.
* Leave "Color ramp" on \boxed{Random Colors} for now
4. Click the \boxed{Classify} button
5. click the \boxed{Apply} button to apply your classification to the dots on the map.


## **Just show some of the types of hospitals**
1. In the Symbology window, check the box next to "all other values" so it is *off*.
2. Check *off* the boxes for all the hospital types except the "School Based..." ones.
3. Click the \boxed{Apply} button to apply your new rule to the map.

<!-- TODO: add image of Symbology window with just the correct types checked off -->


-------

# Resources

<!-- TODO: URLs are breaking beamer 
## Other trainings:
- QGIS Training Manual: [https://docs.qgis.org/3.34/en/docs/training_manual/index.html](https://docs.qgis.org/3.34/en/docs/training_manual/index.html)

## Data sources: 
1. Download CD geography from NYC open data: [https://data.cityofnewyork.us/City-Government/Community-Districts/yfnk-k7r4](https://data.cityofnewyork.us/City-Government/Community-Districts/yfnk-k7r4)
2. Download PM 2.5 data by CD from NYC environmental health portal: [https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/air-quality/?id=2023#display=map](https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/air-quality/?id=2023#display=map)
3. Download hospital location points from NYS: [https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r/about_data](https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r/about_data)
-->




