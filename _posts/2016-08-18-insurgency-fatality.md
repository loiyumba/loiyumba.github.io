---
layout: post
title: Insurgency Fatality in the Northeast India
subtitle: Casualties due to insurgency from 2005 to 2015
fb-img: https://github.com/loiyumba/loiyumba.github.io/blob/master/img/NEinsurgency/manipur05-15Pix.png
---

The north-eastern part of India has seen insurgency uprising since Independence of India. Before British took over the entire northeast
India, some of the states were kingdom and rest of the places unexplored, inhabited by tribals population. After British left, India took
over the entire northeast India one by one. Before India took over and British left, these places were independent. Some of the places were
taken forcefully, some places even had a war like situation, for some transitions were smooth. Most of the people are not worried about
this because for general masses, earning a livelihood is what matter most. However, some are not happy about it and become revolutionary
or insurgent working towards achieving independence from India. They form groups, took up arms and fight against govt. Now, many decades
have been passed but till today there is no solution to it. It's been going on. With time, things have changed, leaders have changed so the
agenda and mission also changed. It's more of politics now. That's my personal opinion.       

I am trying to tell a story via data visualization. Because of the insurgency problem in the entire northeast, the people living in this
region is paying a high price in terms of human lives, development, education, economy, healthcare, etc. The number of fatalities due to
insurgency is high. The casualties are on all sides - the civilians, security personnels and insurgents. Let's see how this has been going
on for the last 10 years through data visualizations.     

Data is scrapped from [SATP](http://www.satp.org/satporgtp/countries/india/database/fatalitiesnorteast2006.htm) and the cleaned data is
stored [here](https://github.com/loiyumba/Dataset/tree/master/NEinsurgency). 

Let's look at the total fatalities in the last 10 years because of insurgency.        

[![total]({{ site.url }}/img/NEinsurgency/TotalFatalitiesPix.png)]({{ site.url }}/img/NEinsurgency/TotalFatalitiesPix.png)    

Good news is fatalities is trending low since 2005. Fatalities of security personnel has been almost constant in the last 10 years. Let's break it down by states.   

[![civilians]({{ site.url }}/img/NEinsurgency/civiliansPix.png)]({{ site.url }}/img/NEinsurgency/civiliansPix.png)      

Civilians fatality was always high in Assam followed by Manipur. Rest of the states were constantly low compare to Assam and Manipur.   

[![security]({{ site.url }}/img/NEinsurgency/securityPix.png)]({{ site.url }}/img/NEinsurgency/securityPix.png)     

Security personnels fatality was high in Manipur then got lowered between 2008 and 2014 and suddenly spiked in 2015. Assam too noticed high fatality of security personnels but the trend is going downward. Tripura also witnessed high fatality of security personnels during 2005, 2006 and 2007.    

[![terrorist]({{ site.url }}/img/NEinsurgency/terroristPix.png)]({{ site.url }}/img/NEinsurgency/terroristPix.png)     

Insurgents fatality is high in Manipur and Assam. The fatalities of insurgents in Manipur were high in 2008 and 2009, and it's been low since then, followed by Assam. Nagaland too had high fatalities of insurgents during 2006, 2007 and 2008.     

How about ordering states by number of total fatalities of civilians, security personnels and insurgents? We can do so.    

[![totalcivilians]({{ site.url }}/img/NEinsurgency/civilians_totalPix.png)]({{ site.url }}/img/NEinsurgency/civilians_totalPix.png)   

[![totalsecurity]({{ site.url }}/img/NEinsurgency/security_totalPix.png)]({{ site.url }}/img/NEinsurgency/security_totalPix.png)   

[![totalinsurgents]({{ site.url }}/img/NEinsurgency/terrorist_totalPix.png)]({{ site.url }}/img/NEinsurgency/terrorist_totalPix.png)   

Manipur and Assam are the most disturbed states in the northeast region of India while Arunachal Pradesh and Mizoram are the most peacegul states.    

R code to extract data from the webpage and to generate plots from data is [here](https://gist.github.com/loiyumba/5aaef1ba5b386b83386b4b6d1c43f2a0).     

Thank you for reading!










