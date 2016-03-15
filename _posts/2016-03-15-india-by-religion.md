---
layout: post
title: "India by Religion"
subtitle: "India's religious population as per 2011 census"
date: 2016-03-15
fb-img: https://github.com/loiyumba/loiyumba.github.io/tree/master/img/ind_rel/hindu_india.png
---

Census department of India released 2011 population by religion data last year if I am not wrong. I always wanted to play with this data.
Not just religious data, any data related to states is interesting. Because I can compare how the states are doing in any given data. I
visualized this data with barplots, compared different religions population across the states. But one thing I wanted to visualize was
pointing this data into India map. And this became possible with few lines of code with [choroplethr](https://cran.r-project.org/web/packages/choroplethr/index.html)
package. Even though you can create similar map in many ways in r, I found creating country map with this package quite easy.

Here's the one created with this package  
[![hindu population]({{ site.url }}/img/ind_rel/hindu_india.png)]({{ site.url }}/img/ind_rel/hindu_india.png)

Here's another one  
[![muslim population]({{ site.url }}/img/ind_rel/muslim_india.png)]({{ site.url }}/img/ind_rel/muslim_india.png)