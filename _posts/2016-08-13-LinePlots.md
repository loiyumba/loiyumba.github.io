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
actual initial learning started with **Bike Sharing Demand** competition. Though there were multiple dataset in **Bike Sharing Demand**
competition, I am going to use a dataset call 'Day'.     

I load all the libraries needed, set the directory and load the data from the local disk.   

```r
require(dplyr) # for data manipulation
require(ggplot2) # for visualization
require(extrafont) # for font change in visualization

setwd("..\\Kaggle\\Bike Sharing\\Data")

day <- read.csv("day.csv", stringsAsFactors = FALSE)
```   

Let's see what are all the features data came with.    

```r
names(day)
 [1] "instant"    "dteday"     "season"     "yr"         "mnth"      
 [6] "holiday"    "weekday"    "workingday" "weathersit" "temp"      
[11] "atemp"      "hum"        "windspeed"  "casual"     "registered"
[16] "cnt"  
```    

I need "dteday" and "cnt" for constructing like plot. "dteday" is date and "cnt" is the total bike rental count. Let's the structure of the data as well.    

```r
str(day)
'data.frame':	731 obs. of  16 variables:
 $ instant   : int  1 2 3 4 5 6 7 8 9 10 ...
 $ dteday    : chr  "2011-01-01" "2011-01-02" "2011-01-03" "2011-01-04" ...
 $ season    : int  1 1 1 1 1 1 1 1 1 1 ...
 $ yr        : int  0 0 0 0 0 0 0 0 0 0 ...
 $ mnth      : int  1 1 1 1 1 1 1 1 1 1 ...
 $ holiday   : int  0 0 0 0 0 0 0 0 0 0 ...
 $ weekday   : int  6 0 1 2 3 4 5 6 0 1 ...
 $ workingday: int  0 0 1 1 1 1 1 0 0 1 ...
 $ weathersit: int  2 2 1 1 1 1 2 2 1 1 ...
 $ temp      : num  0.344 0.363 0.196 0.2 0.227 ...
 $ atemp     : num  0.364 0.354 0.189 0.212 0.229 ...
 $ hum       : num  0.806 0.696 0.437 0.59 0.437 ...
 $ windspeed : num  0.16 0.249 0.248 0.16 0.187 ...
 $ casual    : int  331 131 120 108 82 88 148 68 54 41 ...
 $ registered: int  654 670 1229 1454 1518 1518 1362 891 768 1280 ...
 $ cnt       : int  985 801 1349 1562 1600 1606 1510 959 822 1321 ...
```   


