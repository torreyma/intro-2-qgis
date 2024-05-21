---
title: "A First Map in QGIS"
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

## What is "GIS'?

### An acronym, it stands for...

. . . 

Geographic Information System

. . . 

### Why isn't it just called "mapping" software?

. . . 

"Geographic Information" more accurately describes what the software does: Think of it like an extension to your spreadsheet software that lets you look at your data from a geographic perspective (if your data includes a geographic component).

<!--
* What does GIS stand for?
    * Geographic Information System
* And does anyone know what it does?
    * Makes maps
* Why isn't it just called mapping software?
    * "Geographic Information" more accurately describes what the software does. It's not primarily about making maps, it's about poking your data. The simplest way to think of it is as an extension of your spreadsheet software like Excel. An extension that lets you look at your spreadsheet from a mappy kind of perspective (if you can). If all you wanted to do was make pretty maps, you want to be working in Illustrator and getting a lesson from a graphic designer (a useful, but different expertise). You can get pretty maps out of GIS, but that's kinda the secondary function after data analysis. Keep this in mind because it will help you understand some the of the more byzatine methods that come up in GIS sometimes.
-->

---

### GIS software you need to know the names of:
* ArcGIS: expensive commercial GIS software made by ESRI <!-- TODO: Add logos? --> 
* QGIS: Open-source free ArcGIS work-alike software made by volunteers
* (R and Python: programming languages, also open-source)

<!--
* Software:
    * If you're going to do anything in GIS you need to know that ArcGIS exists: that's the main commercial software comapnies buy if they have tons of money to spend on their GIS work. It's made by a company called ESRI. 
    * QGIS is the open-source and free and designed to work similarly to ArcGIS. It does all the core things ArcGIS does, and is sometimes simpler to use.
    * You should also know that almost everything you can do in GIS you can do in programming languages like R and Python, and a lot of people do. The big benefit to a GIS is you get a point-and-clicky interface, instead of having to write code.
-->

---


## QGIS Main Window

![](images/gui_numbered.png){width=100% height=100%}

<!--
  If you omit width and height, the images tend to
  appear pixel-for-pixel at the resolution of the screen.
  This often means: very huge. Pandoc can resize the
  images for you.
  
  Remember that you need to keep the image files with your
  presentation's HTML file or they won't show up.
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

<!--
* So QGIS is going to be our focus today, and most of the rest of what I'll show you will be a walk-through of getting started with a map
* This is what the main windows looks like. Most of it should be pretty familiar from any other office software you've used.
* Pay attention to this Layers list though: each bit of data you add -- the equivalent to a sheet in Excel -- will show up here.
* The stack order really matters -- what is on top of this layers list is what you will see in the map window. Make sense?
-->

---

# Let's get into QGIS

## Adding your first data
1. Start QGIS
2. Select: \boxed{Project \rightarrow New}
3. Select: \boxed{Layer \rightarrow Add Layer \rightarrow Add Vector Layer...} This will open a new window.

<!--
* OK, fire up QGIS. Let me know if you have any trouble with that.
* Select Project -> New to get a blank map space (I like menus, but if you want to mouseover the buttons to figure out which does what, that's cool too)
-->

---

# Resources

<!--
TODO: URLS are breaking beamer. Maybe wrap in \url?
## Other trainings:
- QGIS Training Manual: [https://docs.qgis.org/3.34/en/docs/training_manual/index.html](https://docs.qgis.org/3.34/en/docs/training_manual/index.html)

## Data sources: 
1. Download CD geography from NYC open data: https://data.cityofnewyork.us/City-Government/Community-Districts/yfnk-k7r4
2. Download PM 2.5 data by CD from NYC environmental health portal: https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/air-quality/?id=2023#display=map
3. Download hospital location points from NYS: https://health.data.ny.gov/Health/Health-Facility-General-Information/vn5v-hh5r/about_data
-->



