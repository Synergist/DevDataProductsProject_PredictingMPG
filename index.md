---
title       : Predicting MPG for cars
subtitle    : Course Project for Developing Data Products - Coursera | JHU
author      : Pranav Singh
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {selfcontained, standalone, draft}
knit        : slidify::knit2slides
---

## Shiny App - Predicting MPG

The shiny app is located at https://synergist.shinyapps.io/CourseProject_PredictMPG/

This project involves predicting the MPG value of a car using some various other features about the car. We use the `mtcars` dataset to train a generalized linear model (GLM). The shiny app takes in user-inputted features via various widgets in the sidebar. It then reactively computes the predicted mpg value for those features by using the GLM. 


```r
library(caret)
mpg.model <- train(mpg ~ disp + wt + hp + cyl + am, data = mtcars, method='glm')
```

--- .class #id 
## Feature Selection

We limit our small application to use only the following features, since they're most likely to be readily available to the end user:

* 'cyl' - the number of cylinders, ranging from 1 to 12
* 'disp' - the engine displacement in cubic inches, ranging from 200 to 1000
* 'wt' - the weight of the car in 1000 lbs, ranging from 1 to 6
* 'hp' - the gross horsepower of the car, ranging from 100 to 1500 
* 'am' - the transmission type, either 0 for 'Automatic' or 1 for 'Manual'

--- .class #id
## Shiny app display
![The shiny app](/home/psingh/Pictures/Screenshot from 2016-01-29 16:53:28.png)

--- .class #id
## What next?

Some possible extensions to this small project would be:
* display graphs that show the interactions/relationships between the individual features and the outcome
* allow a user to request a recommendation for a car from the `mtcars` dataset by providing their desired mpg value
* allow a user to improve the model by supplying their own sample of (features, mpg value) observation
