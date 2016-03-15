---
layout: post
title: "India by Religious Community"
subtitle: "India's religious population as per 2011 census"
date: 2016-03-15
fb-img: https://github.com/loiyumba/loiyumba.github.io/tree/master/img/ind_rel/hindu_india.png
---

Census department of India released 2011 population by religion data last year if I am not wrong. I always wanted to play with this data.
Not just religious data, any data related to states is interesting. Because I can compare how the states are doing in any given data. I
visualized this data with barplots, compared different religions population across the states. But one thing I wanted to do was to visualize this data into India map to see how the data varies from one state to another. By doing this we get to see the overview of this data. This became possible with few lines of code with [choroplethr](https://cran.r-project.org/web/packages/choroplethr/index.html)
 and [choroplethrAdmin1](https://cran.r-project.org/web/packages/choroplethrAdmin1/index.html) package. Even though you can create similar maps in many ways in r, I found creating country map with these two packages quite easy.

Here are the maps. It's self explanatory  
[![hindu population]({{ site.url }}/img/ind_rel/hindu_india.png)]({{ site.url }}/img/ind_rel/hindu_india.png)  
[![muslim population]({{ site.url }}/img/ind_rel/muslim_india.png)]({{ site.url }}/img/ind_rel/muslim_india.png)  
[![christian population]({{ site.url }}/img/ind_rel/christian_india.png)]({{ site.url }}/img/ind_rel/christian_india.png)  
[![buddhist population]({{ site.url }}/img/ind_rel/buddhist_india.png)]({{ site.url }}/img/ind_rel/buddhist_india.png)  
[![sikh population]({{ site.url }}/img/ind_rel/sikh_india.png)]({{ site.url }}/img/ind_rel/sikh_india.png)  
[![jain population]({{ site.url }}/img/ind_rel/jain_india.png)]({{ site.url }}/img/ind_rel/jain_india.png)  
[![other population]({{ site.url }}/img/ind_rel/other_believer_india.png)]({{ site.url }}/img/ind_rel/other_believer_india.png)  
[![not stated population]({{ site.url }}/img/ind_rel/not_stated_india.png)]({{ site.url }}/img/ind_rel/not_stated_india.png)

We can also select certain regions of the country. Here I zoomed the northeastern part of the country for the same data.  
[![hindu]({{ site.url }}/img/ind_rel/hindu.png)]({{ site.url }}/img/ind_rel/hindu.png)  
[![muslim]({{ site.url }}/img/ind_rel/muslim.png)]({{ site.url }}/img/ind_rel/muslim.png)  
[![christian]({{ site.url }}/img/ind_rel/christian.png)]({{ site.url }}/img/ind_rel/christian.png)

Here's the code fo recreate these maps.  
[Data Source](http://www.censusindia.gov.in/2011census/C-01.html)
