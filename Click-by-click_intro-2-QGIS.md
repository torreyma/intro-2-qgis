---
title: "**A First Map in QGIS: click-by-click instructions**"
author: "Mark Torrey"
date: "2024-05-30"
---


# Let's get into QGIS

## **A new project**
1. Start QGIS
2. From the menu at the top, click on: \boxed{Project} &rarr; \boxed{New} (Or click the new button) <!-- \rightarrow causes an error here and there's no simple html way to box text. So a mix of html and latex. Thank you so much pandoc. -->

## **Adding your first data**
1. In the "Browser" panel (on the left), open the "Home" folder and browse for the QGIS demo data I sent you.
2. Go into the "NYC-community-districts" folder and select the file that ends with .shp
3. Now just drag that .shp file over to the map window and drop it there.
    * You should see a map of NYC


## **Adjust the Properties**
1. Right-click your "NYC CDs" layer in the layer window on the left again, and click on \boxed{Properties...}
    * (This will open the Properties window)
2. Make sure the \boxed{Symbology} tab on the left is selected, and then click on the line that says \boxed{Simple Fill}. Click on the drop-down box for "Fill style" and select \boxed{No Brush}
3. Click the \boxed{OK} button.
    * This will leave you with outlines of the community districts polygons with no fill.

<!-- TODO: add image of empty NYC CDs outline -->

## **Select The Bronx**
1. From the menu at the top, click on \boxed{Edit} &rarr; \boxed{Select} &rarr; \boxed{Select Feature(s)} (or click the tool button) to activate the selection tool.
2. Hold down Ctrl and click on each of the community districts in The Bronx. They will light up yellow as you select them.
* (While still holding down Ctrl, click again on anything you might have selected by accident to unselect it.)


## **Let's look at the Attribute Table**
1. Without changing your selection, right-click on the *NYC-CDs_PM25* layer in the "Layers" panel on the left and And select \boxed{Open Attribute Table}
    * The Attribute Table will open in a new window --- this is the spreadsheet table view of the data for that layer in the map window
* Notice the selected rows: each row represents one of the community districts on the map, so you can hold down Ctrl and right-click the row number to select or unselect a community district there too. (Notice the selection changes on the map at the same time.)
2. Look at the column names at the top. Notice we have columns with the CD names, and information about the pollution levels in each CD as well as some other data.
3. You can close the Attribute Table window.


## **Export The Bronx data**
1. Without changing your selection, right-click on the *NYC-CDs_PM25* layer in the "Layers" panel on the left again, and select \boxed{Export} &rarr; \boxed{Save Selected Features As...}
2. From the "Format" drop-down menu, select \boxed{GeoJSON}
    * (Notice that "ESRI Shapefile" is also on that list)
3. Click the \boxed{...} button and make sure you are saving in a directory that makes sense. Give the file a name like "Bronx-CDs_PM25". Click \boxed{Save} to get back to the export data window.
4. Everything else you can leave at the defaults. Click \boxed{OK} to export your data.
    * Your new layer of just Bronx CDs will be added to the map in a new color.
* You can turn a layer on or off by clicking the checkbox. 
* (If you turn off your Bronx layer, you'll see that our whole-city layer still has the Bronx selected. You can click the \boxed{Deselect Features from All Layers} button now to clear your selection.)


## **Classify CDs by fine particle pollution**
1. Right-click your "Bronx-CDs_PM25" layer and select \boxed{Properties...} to open the properties window again. Make sure you are on the "Symbology" tab (on the left)
2. From the drop-down menu at the very top of the window where it says "Single Symbol" select \boxed{Categorized}
3. When you click the "Value" drop-down menu you can see the column names of all the data we saw in the Attribute Table spreadsheet view. Select \boxed{PM 2.5_Val}
4. From the "Color ramp" drop-down, select "Reds"
5. Click the \boxed{Classify} button
6. In the "all other values" line (which represents the parks), double-click on the color swatch. Left-click on the color bar where it says "Color". Change the color to some shade of gray and click \boxed{OK} and \boxed{OK} again to close the two color choice boxes.
7. click the \boxed{Apply} button to apply your classification to the dots on the map.


## **Save your map**
1. Click on \boxed{Project} &rarr; \boxed{Save} to open a file browswer window.
2. Browse to a location that makes sense, give your project a good name, and save it.
* Be aware that the project file (.qgz) will *not* include your data. So if you move the data your project depends on (or rename it) you will have to tell QGIS where it is when you open your project again later.



# Something to try on your own

## **Add more data --- hospital location points**
1. We'll add another layer of data, through the menu this time: click on: \boxed{Layer} &rarr; \boxed{Add Layer} &rarr; \boxed{Add Delimited Text Layer...}
2. In the add-layers window, click the \boxed{...} button, and browse to *Health_Facility_General_Information_20240520.csv* and open it.
3. Make sure the "Point coordinates" radio button is selected.
    * Since we are loading a plain csv file, we need to tell QGIS where it can find the geographic information: In the Facility Longitude and Facility Latitude columns. QGIS will use those coodinates to put a point on our map for each hospital location.
    * The "X field" should have "Facility Longitude" selected and the "Y field" should have "Facility Latitude" selected.
    * Notice in in the "Sample Data" section, you can see a preview of what looks an awful lot like an Excel spreadsheet, and it includes the "Facility Longitude" and "Facility Latitude" columns.
4. Click the \boxed{Add} button to add your data to the map, and then the \boxed{Close} button.


## **Open the Attribute Table for the Hospital Points**
1. Right-click on the new layer you have in the layer panel now: *Health_Facility_General_Information_20240520* And select \boxed{Zoom to Layer(s)}
    * This always shows you the full extent of the data in the layer you right-clicked.
2. Let's look at the hospital point data in spreadsheet view: Right-click the hospitals layer again, and select \boxed{Open Attribute Table}
    * This opens the Attribute Table window. There's a row for every hospital location point.
    * You can see this hospital data includes all of New York State. We want to work with something less than that, so we're going to select just the points in the Bronx.


## **"Subset" so we can work with a little less data**
1. Left-click on the *Facility City* column name at the top of the Attribute Table.
    * This will sort the column alphabetically.
2. Scroll down until you see *Bronx* listed in the Facility City column. Left-click the row number on the left to highlight the whole row.
3. Now scroll down until you see the last row in the Bronx, and hold Shift while left-clicking on the row number.
    * To highlight all the rows from your first selected row. Just like Excel!
4. Don't close the Attribute Table. Right-click on your *Health_Facility_General_Information_20240520* again, And select \boxed{Zoom to Selection}
    * (You can also use mouse scroll wheel to zoom in and out, and the hand tool to grab-and-drag.)
    * You can see all the hospitals in the Bronx that you selected in the Attribute Table are highlighted in yellow.

<!-- TODO: add image of selected hospitals in the Bronx -->


## **A little data cleaning**
* You can close the Attribute Table now if you want more space on your screen.
* Notice we are missing a few dots in our selection in the Bronx. What's going on there?
1. From the menu, click \boxed{View} &rarr; \boxed{Identify Features} to activate that tool (or use the tool button). <!-- TODO: add image of tool button -->
2. Left-click on the un-selected dots to see what's in the Attribute Table row for that item.
    * Looks like they entered "Riverdale" as their city instead of "Bronx". And there's one where someone entered "Melrose"
    * Let's add them to our selection.
    * (You might need to use the mouse scroll-wheel to zoom in)
3. With the dot highlighted for information (in red), right click anywhere on the \boxed{Identify Results} panel, and from the context menu select \boxed{Toggle Feature Selection}
    * This adds the dot to your selection.
4. Add the rest of the dots that are not highlighted in yellow yet, but are clearly in The Bronx.
    * (Also remove the one spot down in Manhattan)


## **Export just our Bronx data points**
* Let's get rid of all the rest of the dots that aren't in the Bronx now. We'll do that by saving just our selection.
1. Right-click on your *Health_Facility_General_Information_20240520* layer again, and select \boxed{Export} &rarr; \boxed{Save Selected Features As...}
    * This opens the export data window. <!-- TODO: add image of export data window-->
2. From the "Format" drop-down menu, select \boxed{GeoJSON}
3. Click the \boxed{...} button and make sure you are saving in a directory that makes sense. Give the file a name like "Bronx_hospital_points". Click \boxed{Save} to get back to the export data window.
4. Everything else you can leave at the defaults. Click \boxed{OK} to export your data.
    * Your new layer of just Bronx hospital points will be added to the map in a new color.
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
* Our map is kinda full of a lot of colors. It's hard for people to read more than 4 or 5 colors. So let's just select a couple of the hospital types to show
1. In the Symbology window, check the box next to "all other values" so it is *off*.
2. Check *off* the boxes for all the hospital types except the "School Based..." ones.
3. Click the \boxed{Apply} button to apply your new rule to the map.

## **Next steps**
* You now have a map of the location of school-based hospitals compared to neighborhood levels of fine particle pollution.
* This is probably a good time to save your project again.
* Your map is good for looking at geographic characteristics of your data, but if you want to share it with others, it will need a few more steps.
1. Project your map:
    * See: [https://docs.qgis.org/3.34/en/docs/training_manual/vector_analysis/reproject_transform.html](https://docs.qgis.org/3.34/en/docs/training_manual/vector_analysis/reproject_transform.html)
    * Change the projection to: \boxed{NAD83 / New York Long Island (ftUS)}
2. Layout your map for printing using the layout manager:
    * See: [https://docs.qgis.org/3.34/en/docs/training_manual/map_composer/index.html](https://docs.qgis.org/3.34/en/docs/training_manual/map_composer/index.html)
    

<!-- TODO: add image of Symbology window with just the correct types checked off -->

-------

# Resources

## Other trainings:
- QGIS Training Manual: [https://docs.qgis.org/3.34/en/docs/training_manual/index.html](https://docs.qgis.org/3.34/en/docs/training_manual/index.html)

## Data sources: 
1. Download CD geography from NYC open data: [https://data.cityofnewyork.us/City-Government/Community-Districts/yfnk-k7r4](https://data.cityofnewyork.us/City-Government/Community-Districts/yfnk-k7r4)
2. Download PM 2.5 data by CD from NYC environmental health portal: [https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/air-quality/?id=2023#display=map](https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/air-quality/?id=2023#display=map)
3. Download hospital location points from NYS: [https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r/about_data](https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r/about_data)




