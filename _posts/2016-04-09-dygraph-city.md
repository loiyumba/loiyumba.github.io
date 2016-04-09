---
layout: post
title: Dygraphs visualization of temperature trend
subtitle: Shinyapp for spotting temperature trend of major Indian cities
fb-img: https://github.com/loiyumba/loiyumba.github.io/blob/master/img/temperature/home_page2.png
---

Here's the look of shinyapp to visualize the temperature trend of major cities of India for the last 200 years. And I am going to write how I made this.

[![homepage]({{ site.url }}/img/temperature/home_page2.png)]({{ site.url }}/img/temperature/home_page2.png)

First of all, we need to get the data. The data is available at [kaggle](https://www.kaggle.com/berkeleyearth/climate-change-earth-surface-temperature-data). You can download it in your local computer and read it in r as

```r
temp_data <- read.csv("temp_data.csv", stringsAsFactor = FALSE)
```

I usually read it with `data.table` package so that I can manipulate data using its functions. Alternatively, if the data is big, I use `readr` package for fast reading. So if you want to load the data using data.table then this is how you do it.

```r
temp_data <- fread("temp_data.csv")
```

Once the data is loaded in r, we can do data exploration like checking out structure, classes, summary, missing values, anything unusual. We can run some of these inbuilt functions to understand the data better.

```r
dim(temp_data) # checking the dimension of data
str(temp_data) # checking classes of features
summary(temp_data) # summarising data feature wise
sapply(temp_data, function(x) sum(is.na(x))) # checking missing values
```
If we see observations with missing values, we can remove those values.

```r
temp_data <- na.omit(temp_data)
```

In the beginning I wanted to do this for all the cities listed in the data but the file is about 500 mb, so I decided to do only for Indian cities. Of course, India because I am from India. We subset all the observations where feature Country is listed as India and in data.table, we can do something like this

```r
india <- temp_data[Country == "India", ]
```

We don't need all the other features for plotting temperature trend. So we go ahead and select required features such as Date, City name and Temperature data.

```r
india <- india[, c(dt, AverageTemperature, City)]
```



I am assuming you are familiar with shinyapp. If not, a great material to learn shiny is available at shiny [homepage](http://shiny.rstudio.com/)
