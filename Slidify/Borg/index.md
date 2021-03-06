---
title       : MiBand Library and Products
subtitle    : 
author      : Borg
job         : Data Scientist
framework   : shower       # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

# MiBand Shiny Application
[MiBand shiny app](https://github.com/BigBorg/MiBand-Products/tree/master/ShinyApp) demonstrates how to use my [MiBand R package](https://github.com/BigBorg/MiBand_R_Package).   
You could upload your own databases.zip file or you can use my built-in data to play aroud. To get your own databases.zip file, you need to compress folder /data/data/com.xiaomi.hm.health/databases from android. Then you'll need your own user id which can be found inside MiBand's official android app.  
To use my built-in data, click the **demo data** button to decompress my own zip file, then you can click the **submit** button to produce output.

---
# Load Data
The first tab panel will print out brief summary of the loaded MiBand data after submit button is clicked. 
<code>
<img src="http://7xshuq.com1.z0.glb.clouddn.com/blog/img/Load.png", width=750>
</code>

---
# Sleep
Switch to sleep tab panel, you can drag the slider on the left to control how many bars will be presented. Also remember to roll down to see other plots. Every ggplot is converted to ggplotly, which means you can easily see values in the plot and even to zoom in and out.
<code>
<img src="http://7xshuq.com1.z0.glb.clouddn.com/blog/img/sleep.gif" width=550/>
</code>

---
# Step
Similar to the sleep tab panel, you can still use the slider to conrol the hist plot.  
<code>
<img src="http://7xshuq.com1.z0.glb.clouddn.com/blog/img/step.gif" width=550/>
</code>

---
# About My Package
I've packaged a bunch of codes for MiBand data cleaning and plotting. Since XiaoMi encodes step, light sleep and deep sleep variables into jason and put them in **ONE** single column in database file, data cleaning for MiBand is not quite easy. But with my package, you only need to use loadMiData function and provide database folder path and user id.  
For plotting, I put various ggplot inside miPlot function. The parameter **type** specifies which type of plot you want to make. It could be one of "hist", "ts", "box", "week". The **y** parameter specifies the variable to be plotted. It could be one of "light", "deep", "sleep", "efficiency". 
