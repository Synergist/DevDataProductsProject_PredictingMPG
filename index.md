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

## Read-And-Delete

1. Edit YAML front matter
2. Write using R Markdown
3. Use an empty line followed by three dashes to separate slides!

--- .class #id 

## Slide 2


```r
suppressMessages(library(caret))
par(mfrow=c(1,2))
mpg.model <- train(mpg ~ ., data = mtcars, method='glm')
varImp(mpg.model) #$importance
```

```
## glm variable importance
## 
##      Overall
## wt    100.00
## am     60.33
## qsec   54.83
## hp     47.46
## disp   34.52
## drat   20.20
## gear   17.92
## carb    7.22
## vs      2.39
## cyl     0.00
```

```r
# asd
# confusionMatrix(mpg.model)
```
