---
title: "**A First Map in QGIS**"
author: "Mark Torrey"
date: "2024-05-30"
theme: "Pittsburgh"
colortheme: "dove"
---

<!--
Compile with: pandoc -t beamer -s Mark-Torrey_intro-2-QGIS.md -o Mark-Torrey_intro-2-QGIS_slides.pdf
-->

<!--
Title slide gets inserted here automatically, generated from yaml block. No separator necessary between title and first content slide.
-->

<!-- Intro TPs: ----
* Most of what I'm going to do is a click-by-click walkthrough, which is maybe not the most exciting thing, but I think it's about the best way to learn software, unfortunately.
* GIS get complicated pretty quickly, so there's a lot to cover. So I'm going to dive right in. 
-->

## What is **GIS**?

### An acronym, it stands for...

. . . 

**G**eographic **I**nformation **S**ystem

<!-- TPs: ----
* What does GIS stand for?
    * Geographic Information System
* And does anyone know what it does?
    * Makes maps
-->

. . . 

### Why isn't it just called "mapping" software?

. . . 

"Geographic Information" more accurately describes what the software does: Think of it like an extension to your spreadsheet software that lets you look at your data from a geographic perspective (if your data includes a geographic component).

<!-- TPs: ----
* Why isn't it just called mapping software?
    * "Geographic Information" more accurately describes what the software does. It's not primarily about making maps, it's about poking your data. Maybe the simplest way to think of it is as an extension of your spreadsheet software like Excel. An extension that lets you look at your spreadsheet from a mappy kind of perspective (if you can). If all you wanted to do was make pretty maps, you want to be working in Illustrator and getting a lesson from a graphic designer (a useful, but different expertise). You can get pretty maps out of GIS, but that's kinda the secondary function after data analysis. Keep this in mind because it will help you understand some the of the more byzatine methods that come up in GIS sometimes.
-->

---

### GIS software you need to know the names of:
* GUI: 
    * ArcGIS: expensive commercial GIS software made by ESRI <!-- TODO: Add logos? --> 
    * QGIS: Open-source free ArcGIS work-alike software made by volunteers
* (R and Python: programming languages, also open-source)

<!-- TPs: ----
* Software:
    * If you're going to do anything in GIS you need to know that ArcGIS exists: it's the main commercial software that comapnies buy if they have tons of money to spend on their GIS work. It's made by a company called ESRI. 
    * QGIS is the open-source and free and designed to work similarly to ArcGIS. It does all the core things ArcGIS does, and is sometimes simpler to use.
    * These are both primarily graphical user interface GIS software. 
    * You should also know that pretty much everything you can do in gui GIS you can also do in programming languages like R and Python, and a lot of people do. The big benefit to a GIS is you get a point-and-clicky interface, instead of having to write code.
-->

---


## **QGIS Main Window**

![](images/gui_numbered.png){width=100% height=100%}

<!--
  If you omit width and height, the images tend to appear pixel-for-pixel at the resolution of the screen.  This often means: very huge. Pandoc can resize the images for you.
  Remember that you need to keep the image files with your presentation's HTML file or they won't show up.
-->

:::::::::::::: {.columns}
::: {.column width="50%"}

1. Layers List / Browser Panel <!-- ^[https://docs.qgis.org/3.34/en/docs/training_manual/basic_map/overview.html] -->
2. Toolbars
3. Map canvas

:::
::: {.column width="50%"}

4. Status bar
5. Side Toolbar
6. Locator bar

:::
::::::::::::::

<!-- TPs: ----
* So QGIS is going to be our focus today, and most of the rest of what I'll show you will be my QGIS walk-through of getting started with a map
* This is what the main windows looks like. Most of it should be pretty familiar from any other office software you've used.
* Pay attention to this Layers list though: each bit of data you add -- the equivalent to a sheet in Excel -- will show up here.
* The stack order really matters -- what is on top of this layers list is what you will see in the map window. Make sense?
-->

---

# Let's get into QGIS

## **Adding your first data**
1. Start QGIS
<!-- TPs: ----
* OK, fire up QGIS. Let me know if you have any trouble with that.
-->
2. Click on: \boxed{Project} &rarr; \boxed{New} <!-- \rightarrow causes an error here and there's no simple html way to box text. So a mix of html and latex. Thank you so much pandoc. -->
3. Click on: \boxed{Layer} &rarr; \boxed{Add Layer} &rarr; \boxed{Add Vector Layer...}
<!-- TPs: ----
* (I like menus, but if you want to mouseover the buttons to figure out which does what, that's cool too)
-->
    * This will open a new window: the add-layers window.

<!-- note: you can't add a comment just after an indented bullet -- it breaks pandoc -->

---

## **Adding your first data --- in the add-layers window**
1. Click the \boxed{...} button (next to the "Vector Dataset(s)" blank box).
2. This will open a file browser. Go into the "NYC-community-districts" folder and select the file that ends with .shp and open it.
<!-- TPs: ----
* (.shp are "shapefiles" --- a format ESRI developed for geographic information. It's not the only file that GIS data comes in, but it's a common one. Unfortunately the "shapefile format" requires a half-dozen or so other files with different endings/formats to go along with the .shp file. You need to remember this sometime when downloading and opening data --- it can be annoying/tricky.)
* All of the data we are using today is just as it is when you download it from the various data sources on the internet. I'll give you the links at the end.
-->
3. Back in the add-layers window, Click the \boxed{Add} button. You should see NYC appear in the map window.
4. Click \boxed{Close} in the add-layers window.
    * (Somewhat confusingly, it doesn't close on its own.)

<!-- TODO: add image of add layer window, either here or next slide -->


---

## **A little layer organizing**
1. In the layer window, right-click your data layer with the crazy geo_export_blahblahblah name, and click on \boxed{Rename Layer}
    * Name it something like "NYC CDs" (for Community Districts)
2. Right-click your "NYC CDs" layer in the layer window again, and click on \boxed{Properties...}
    * (This will open the Properties window)
3. Select \boxed{Symbology} and then click on the line that says \boxed{Simple Fill}. Click on the drop-down box for "Fill style" and select \boxed{No Brush}
<!-- TPs: ----
* This should be familiar if you have used PowerPoint or Illustrator. Those are "vector based" drawing programs. Remember we chose "vector" data? It's one of the main formats of GIS data (though you should be aware there's others, like Raster). So like PowerPoint and Illustrator, you can change the color of the fill, or the outline of the vector object. (The outline is called stroke.) Does that make sense?
* UNLIKE Powerpoint and Illustrator, in GIS you can't just grab the object and change it's size or shape. That's because it's not just a drawing, what you see is tied to an underlying spreadsheet of data, remember? In this case the spreadsheet just says where each of these districts is located.
* You CAN edit the data, but it's more involved than Illustrator or Powerpoint and we won't really get to that today.
* (BONUS): What is a vector? A picture, like a jpg, is made up of lots of tiny dots, right? In a vector image, each line and object is actually described by fancy math inside the software that tells the software how long each line is supposed to be, and it's curve, and color. Because everything is just a math eqution, it can be scaled up and down without losing quality. In graphics that have a few shapes and colors, it can be very very small (because it's stored as just a bit of math). But if you wanted to make a photograph all vectors, it ends up being huge because you need a bit of math to describe every pixel.
-->
4. Click the \boxed{OK} button.
    * This will leave you with outlines of the community districts.

<!-- TODO: add image of empty NYC CDs outline -->

---

## **Add more data --- hospital location points**
<!-- TPs: ----
* So now we have this start of a NYC map, even if it's really boring.
* Let's add more data that might be a bit more interesting to us.
-->
1. Again, click on: \boxed{Layer} &rarr; \boxed{Add Layer} But this time select \boxed{Add Delimited Text Layer...}
2. In the add-layers window, click the \boxed{...} button, and browse to *Health_Facility_General_Information_20240520.csv* and open it.
<!-- TPs: ----
* In step 2: Notice on the right we are in the "Delimited Text" tab of the add-layers window.
-->
3. Make sure the "Point coordinates" radio button is selected.
<!-- TPs: ----
* Since we are loading a plain ol' csv file (y'all know about those, right?), we need to tell QGIS where it can find the geographic information: In the Facility Longitude and Facility Latitude columns. QGIS will use those coodinates to put a point on our map for each hospital location.
-->
    * The "X field" should have "Facility Longitude" selected and the "Y field" should have "Facility Latitude" selected.
    * Notice in in the "Sample Data" section, you can see a preview of what looks an awful lot like an Excel spreadsheet, and it includes the "Facility Longitude" and "Facility Latitude" columns.
4. Click the \boxed{Add} button to add your data to the map, and then the \boxed{Close} button.


---

## **Let's look at the Attribute Table**
1. Right-click on the new layer you have in the layer panel now: *Health_Facility_General_Information_20240520* And select \boxed{Zoom to Layer(s)}
    * This always shows you the full extent of the data in the layer you right-clicked.
2. Let's look at the hospital point data in spreadsheet view: Right-click the hospitals layer again, and select \boxed{Open Attribute Table}
<!-- TPs: ----
* You can see this hospital data includes all of New York State. We want to work with something less than that, so we're going to select just the points in the Bronx.
* Note that the Attribute Table looks a lot like Excel. You can look at the Attribute Table of the CDs layer too, but it's pretty boring.
    * You can also see that there's a LOT of information (address, phone number, fax number, description) in here about these hospitals. A lot of it could potentially be mapped.
-->
    * This opens the Attribute Table window. There's a row for every hospital point.

---

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

---

## **A little data cleaning**
<!-- TPs: ----
* You can close the Attribute Table now if you want more space on your screen.
* Notice we are missing a few dots in our selection in the Bronx. What's going on there?
-->
1. Click the \boxed{Identify Features} button to activate that tool. <!-- TODO: add image of tool button -->
2. Left-click on the un-selected dots to see what's in the Attribute Table row for that item.
<!-- TPs: ----
* Looks like they entered "Riverdale" as their city instead of "Bronx". And there's one where someone entered "Melrose"
* This is how data goes. But it's also a cool thing about GIS --- it would have been harder to spot those missing data points in Excel.
* Let's add them to our selection. (Also remove the one spot down in Manhattan)
-->
    * (You might need to use the mouse scroll-wheel to zoom in)
3. With the dot highlighted for information (in red), right click on the \boxed{Identify Results} pane, and from the context menu select \boxed{Toggle Feature Selection}
    * This adds the dot to your selection.
4. Add the rest of the dots that are not highlighted in yellow yet, but are clearly in The Bronx.

---

## **Extract just our Bronx data points**
<!-- TPs: ----
* So let's get rid of all the rest of the dots that aren't in the Bronx now. 
* We'll do that by saving just our selection.
-->
1. Right-click on your *Health_Facility_General_Information_20240520* layer again, and select \boxed{Export} &rarr; \boxed{Save Selected Features As...}
    * This opens the export data window. <!-- TODO: add image of export data window-->
2. From the "Format" drop-down menu, select \boxed{GeoJSON}
<!-- TPs: ----
* GeoJSON is another commonly used GIS data format. You can't do as many things with it as you can with a Shapefile, but it conveniently only saves a single file, instead of that mess of files that the Shapefile format creates. So it's good for us right now.
-->
    * (Notice that "ESRI Shapefile" is also on that list)
3. Click the \boxed{...} button and make sure you are saving in a directory that makes sense. Give the file a name like "Bronx_hospital_points". Click \boxed{Save} to get back to the export data window.
4. Everything else you can leave at the defaults. Click \boxed{OK} to export your data.
    * Your new layer of just Bronx hospital points will be added to the map.
5. Right-click the old layer that has all of NYS hospitals, and select \boxed{Remove Layer...}. Click \boxed{OK}


---

## **Classify the hospitals by type**
<!-- TPs: ----
* Now we have just the hospitals in the Bronx, but that doesn't tell us much. Let's get QGIS to show us some more info.
-->
1. Right-click your "Bronx_hospital_points" layer and select \boxed{Properties...} to open the properties window again.
2. From the drop-down menu at the very top of the window where it says "Single Symbol" select \boxed{Categorized}
<!-- TPs: ----
* Categorized is going to split up our data based on categories within a column.
-->
3. From the "Value" drop-down menu select \boxed{Description}
<!-- TPs: ----
* "Description" is the column in our Attribute Table that has categories for the types of hospitals.
-->
* If you want, you can click the "Symbol" button and pick a different shape.
* Leave "Color ramp" on \boxed{Random Colors} for now
4. Click the \boxed{Classify} button
<!-- TPs: ----
* The classify button will add all the different categories of the column you selected in "Value" to the Properties window.
-->
5. click the \boxed{Apply} button to apply your classification to the dots on the map.


---

## **Just show some of the types of hospitals**
<!-- TPs: ----
* Our map is kinda full of a lot of colors, and that's not super useful.
* So let's just select a couple of the hospital types to show
* In the next section we'll be adding air pollution data to the map, so maybe we're interested in just hospitals associated with schools
-->
1. In the Symbology window, check the box next to "all other values" so it is *off*.
2. Check *off* the boxes for all the hospital types except the "School Based..." ones.
3. Click the \boxed{Apply} button to apply your new rule to the map.

<!-- TODO: add image of Symbology window with just the correct types checked off -->


---

# Resources

<!-- TODO: URLs are breaking beamer 
## Other trainings:
- QGIS Training Manual: [https://docs.qgis.org/3.34/en/docs/training_manual/index.html](https://docs.qgis.org/3.34/en/docs/training_manual/index.html)

## Data sources: 
1. Download CD geography from NYC open data: [https://data.cityofnewyork.us/City-Government/Community-Districts/yfnk-k7r4](https://data.cityofnewyork.us/City-Government/Community-Districts/yfnk-k7r4)
2. Download PM 2.5 data by CD from NYC environmental health portal: [https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/air-quality/?id=2023#display=map](https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/air-quality/?id=2023#display=map)
3. Download hospital location points from NYS: [https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r/about_data](https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r/about_data)
-->



