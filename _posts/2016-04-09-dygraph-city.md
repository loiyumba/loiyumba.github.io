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

I am assuming you are familiar with shinyapp. If not, a great material to learn shiny is available at shiny [homepage](http://shiny.rstudio.com/)
