---
layout: post
title: Line Plot in ggplot2
subtitle: Construction of line plot using ggplot2 package
fb-img: https://github.com/loiyumba/loiyumba.github.io/blob/master/img/LinePlots/1st.png
---

This tutorial is on the line with visualization tutorial that I am doing using `ggplot2` package. I have done on how to construct bar plot in
with `ggplot2` package in my earlier post. All the post are meant for new learners. I do often stuck at choosing dataset for my tutorial.
After few thoughts, I have decided to use kaggle dataset on [Bike Sharing Demand](https://www.kaggle.com/c/bike-sharing-demand). Like
everyone else, I have also started participating kaggle competition with **Titanic** and at that time I had no idea what I was doing. My 
actual initial learning started with **Bike sharing Demand** competition. Though there were multiple dataset in **Bike Sharing Demand**
competition, I am going to use a dataset call 'Day'.     

I load all the libraries needed, set the directory and load the data from the local disk.   

```r
require(dplyr) # for data manipulation
require(ggplot2) # for visualization
require(extrafont) # for font change in visualization

setwd("..\\Kaggle\\Bike Sharing\\Data")

day <- read.csv("day.csv", stringsAsFactors = FALSE)
```   

```r
names(day)
 [1] "instant"    "dteday"     "season"     "yr"         "mnth"      
 [6] "holiday"    "weekday"    "workingday" "weathersit" "temp"      
[11] "atemp"      "hum"        "windspeed"  "casual"     "registered"
[16] "cnt"        "month"      "year"  
```
