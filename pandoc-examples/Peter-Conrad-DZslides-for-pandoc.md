---
title: "DZslides template for Pandoc"
author: "original author: Peter Conrad"
date: "updates: 2024-05-17"
theme: "Pittsburgh"
colortheme: "dove"
---

<!-- Replaced default dzslides config with yaml block above which works for both dzslides-to-html and beamer-to-pdf output. The themes only apply to beamer. You can choose your beamer theme and colortheme from the awful options here: https://hartwork.org/beamer-theme-matrix/

Compile with: pandoc -t dzslides -s Peter-Conrad-DZslides-for-pandoc.md -o myslides.html   You can also use -t beamer and a .pdf -o file for a pdf output in a completely different style

Peter Conrad writeup is here: https://stymied.medium.com/what-slides-from-markdown-5239ed31e7ac  It includes info on how to create slides for ppt as well.
-->

# Section titles

- H1 or H2
- Centered on slide
- Not much room below

<!-- 
  An H1 or H2 renders as a large title in the middle of the slide.
  There is room for a small number of bullets below, but it looks
  nicer with the title alone.
-->

---

How to do a slide

- Use \-\-\- to separate slides
- Use regular text and bullets
- H1 or H2 for a section title

<!--
  Regular text starts closer to the top of the slide.
  A normal text phrase plus bullets makes for a simple,
  attractive slide.
-->

---

### Test super long line: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

---

# Images

---

You can use images.

 - Provide width and height
 - Keep them with the HTML file
 
![](bench.jpg){width=33% height=33%}

<!--
  If you omit width and height, the images tend to
  appear pixel-for-pixel at the resolution of the screen.
  This often means: very huge. Pandoc can resize the
  images for you.
  
  Remember that you need to keep the image files with your
  presentation's HTML file or they won't show up.
-->

---

![Full-screen image with alt text](bench.jpg){width=100% height=100%}

<!--
  For some reason, a full-screen image renders properly even if
  you omit the width and height tags. I have left them in to foster
  good habits.
-->

---

# Columns

---

2 Columns

:::::::::::::: {.columns}
::: {.column width="50%"}

![](bench.jpg){width=100% height=100%}

:::
::: {.column width="50%"}

- Bullet
- Bullet
- Bullet


<!-- 100% of this column, that is -->

:::
::::::::::::::

<!--
  Pandoc uses fenced div for multiple columns in slide shows.
  I get the impression that DZslides is designed to create
  a slide show with a very simple, uncluttered look.
  If you are using a lot of columns, you might consider
  a different slide format.
-->

---

> Blockquotes look like this

---

Incremental "build" slides

::: incremental

- Incremental slides work
- This is how they look
- It's fine

:::

---

A slide with a pause can work.

. . . 

Or can it? 

---


# Thank you
