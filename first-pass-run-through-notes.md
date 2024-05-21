first-pass-run-through-notes.md
Last modified: 2024-05-21 18:49

# A first pass at the run-through order of things, the demo portion:
(Other topics to cover, like 'drawing with data' not covered here)

## Get data (you should probably do this ahead of time):
1. Download CD geography from NYC open data: https://data.cityofnewyork.us/City-Government/Community-Districts/yfnk-k7r4
2. Download PM 2.5 data by CD from NYC environmental health portal: https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/air-quality/?id=2023#display=map
3. Download hospital location points from NYS: https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r/about_data

## Add and classify hospitals data
1. Add CD geography (select single symbol and set no brush for fill so we only have outlines)
2. Add csv text-delimited NYS hospitals points
    * Set point coordinates
3. Use attribute table to select County "Bronx"
    * Use info tool to check the ones that are mistakes, CLEARLY mistakes in data entry
    * Hit unselect button
4. Select only points in city "Bronx" 
    * use info button to note that a bunch of points are in "River" and unselected
    * Use right-click -> toggle feature selection to add unselected dots in the Bronx
        * Don't worry too much about it, we don't need perfect data for what we are doing today
        * You could also just fix this data: edit in QGIS (kinda complicated) or just edit the csv before you import it to QGIS
5. Export selected features (make sure it's selected features!) as geojson
    * remove all state facilities layer. Now you have just hospitals in the Bronx!
6. Let's use properties to classify them: Select Categorized from drop-down menu
    * For value, use Description. Use random colors. Pick a symbol you like. Apply.
    * Too many rainbow of dots! Select just the schools dots
* Now we are starting to see how QGIS is useful for looking at our data -- you couldn't have done that bit where you are selecting by location in Excel, right? -- but not a very attractive map, and no data that really tells us anything yet.

## Add and classify PM 2.5 data
1. Add csv text-delimited (no geo) of PM 2.5 data
    * (Not sure I actually have time to do this, but it feels important for giving the sense of doing something _useful_)
    * (Maybe this is the bit we can have them try on their own?)
2. Join PM data (on 'value') to CD geography. 
    * Classify with 'Categorized' from drop-down. 
        * (If you turned the brush off in the first part, you need to turn it back on here)
        * (Mess with categorization here to get it more like the map from environmental health portal?)
    * Change 'all other values' (that is, the parks and airports) to gray.

## Project and save
1. Set projection for the project to NAD83 LI 
2. Use layout manager to create a map and save it
    * (My god, is there any other way? Maybe it can be exported for ppt or something easy for people to manage? Or save just the map as png, and tell people to use ppt to lay it out?)



