---
layout: post
title: Dygraphs visualization of temperature trend
subtitle: Shiny app tutorial for temperature trend of major Indian cities
fb-img: https://github.com/loiyumba/loiyumba.github.io/blob/master/img/temperature/home_page2.png
---

Here's the look of shiny app to visualize the temperature trend of major cities of India for the last 200 years. And I am going to write how I made this.  
This is the landing page -  

[![homepage]({{ site.url }}/img/temperature/home_page2.png)]({{ site.url }}/img/temperature/home_page2.png)

This is what we see after we entered the city name and click on submit -  

[![entered]({{ site.url }}/img/temperature/city_entered.png)]({{ site.url }}/img/temperature/city_entered.png)

We will divide the tasks into two -  
* Getting and preparing data  
* Shiny app

# Getting and preparing data 
 --- 

First of all, we need to get the data. The data is available at [kaggle](https://www.kaggle.com/berkeleyearth/climate-change-earth-surface-temperature-data). You can download it in your local computer and read it in r as

```r
temp_data <- read.csv("temp_data.csv", stringsAsFactor = FALSE)
```

I usually read it with `data.table` package so that I can manipulate data using its functions. Alternatively, if the data is big, I use `readr` package for fast reading. So if you want to load the data using data.table then this is how you do it.

```r
require(data.table)
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

If we see the class of features in the data, we will notice that the date feature is in character class. We will change that to date class.

```r
india$dt <- as.Date(india$dt, format = "%Y-%m-%d")
```

We can save this data to our local directory so that we can put this data into the folder from where shiny app is going to launch. In order for shiny app to work, the folder has to have shiny code and the data together.

```r
write.csv(india, "india.csv", row.names = FALSE) # to save the data)
```


# Shiny app 
 --- 
 
If you are not familiar with shiny, tutorial to learn shiny is available at shiny [homepage](http://shiny.rstudio.com/). Not only tutorial, shiny apps gallery and articles are also available. So much we can learn, so much we can do with shiny. Before we start shiny, we need to install `shiny` package.

```r
install.packages("shiny")
```

Once the package is installed, we can run a demo to confirm whether the installation went through smoothly.

```r
require(shiny)
runExample("01_hello")
```

Shiny app is made of two parts - *ui* and *server*. *ui* is the web page/document that we see. Whatever we want users to see on shiny app is made in *ui*. The *server* is the function that powers the shiny app to run. Whatever the users interact with on shiny app *ui*, it's the server that helps to execute it seamlessly. So we build the *ui* and *server* to get shiny app.


First we will create an empty shiny app. All shiny apps follow the same template.

```r
require(shiny)
ui <- fluidpage()
server <- function(input, output){}
shinyApp(ui = ui, server = server)
```

To successfully run this app, we have to save it as **app.R**. And the data should be in the same folder where this **app.R** is. Once we save it, we will see something like this in our rstudio console.

[![shinylook]({{ site.url }}/img/temperature/shiny-runapp.png)]({{ site.url }}/img/temperature/shiny-runapp.png)

Once you click on Run App button on the right, your app should run. 

We will split this part into two-   
* UI part
* Server part

### UI part

First we add title of the app. Once we add title and run the app, you will see whatever text we have added in the title appears in the app. Interaction options in the app will be in *fluidpage* function, and to add different options we use different function. For title, this function adds title in the shiny app.

```r
ui <- fluidpage(
       titlePanel("Average Temperature of Indian Cities"),
```
 
In the app layout, we will have the option to choose city and display text info on the left, and the remaining part of the layout as dygraph output. So we continue our *ui* code as follows-

```r
ui <- fluidpage(
       titlePanel("Average Temperture of Indian Cities"),
       sidebarLayout(
         sidebarPanel(
```
 
 










