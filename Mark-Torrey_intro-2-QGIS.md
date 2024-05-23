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

<!-- TODO: Maybe have Susan print a bunch of copies of the step-by-step instructions? -->

## What is **GIS**?

### An acronym, it stands for...

. . . 

**G**eographic **I**nformation **S**ystem

. . . 

### Why isn't it just called "mapping" software?

. . . 

"Geographic Information" more accurately describes what the software does: Think of it like an extension to your spreadsheet software that lets you look at your data from a geographic perspective (if your data includes a geographic component).

---

### GIS software you need to know the names of:
* GUI: 
    * ArcGIS: expensive commercial GIS software made by ESRI <!-- TODO: Add logos? --> 
    * QGIS: Open-source free ArcGIS work-alike software made by volunteers
* (R and Python: programming languages, also open-source)

---

<!-- TODO: insert image of finished map here -->


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

---

