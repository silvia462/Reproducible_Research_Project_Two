# Reproducible Research: Peer Assessment 1
## Loading and preprocessing the data
```r
unzip(zipfile = "activity.zip")
data <- read.csv("activity.csv")
```
## What is mean total number of steps taken per day?
```r
library(ggplot2)
total.steps <- tapply(data$steps, data$date, FUN = sum, na.rm = TRUE)
 qplot(total.steps, binwidth = 1000, xlab = "total number of steps taken each day")
 ```

 ![plot of chunk jagunnamed-chunk-1](https://github.com/JAgOneill/coursera-reproducible-research-peer-assessment1/blob/master/%20jagunnamed-chunk-1.png) 
 ![plot of chunk jagunnamed-chunk-1](https://github.com/JAgOneill/coursera-reproducible-research-peer-assessment1/blob/master/figures/%20jagunnamed-chunk-1.png) 

 ```r
 mean(total.steps, na.rm = TRUE)
 @@ -45,7 +45,7 @@ ggplot(data = averages, aes(x = interval, y = steps)) + geom_line() + xlab("5-mi
     ylab("average number of steps taken")
 ```

 ![plot of chunk jagunnamed-chunk-2](https://github.com/JAgOneill/coursera-reproducible-research-peer-assessment1/blob/master/jagunnamed-chunk-2.png) 
 ![plot of chunk jagunnamed-chunk-2](https://github.com/JAgOneill/coursera-reproducible-research-peer-assessment1/blob/master/figures/jagunnamed-chunk-2.png) 


 On average across all the days in the dataset, the 5-minute interval contains
 @@ -103,7 +103,7 @@ total.steps <- tapply(filled.data$steps, filled.data$date, FUN = sum)
 qplot(total.steps, binwidth = 1000, xlab = "total number of steps taken each day")
 ```

 ![plot of chunk jagunnamed-chunk-5](https://github.com/JAgOneill/coursera-reproducible-research-peer-assessment1/blob/master/jagunnamed-chunk-5.png) 
 ![plot of chunk jagunnamed-chunk-5](https://github.com/JAgOneill/coursera-reproducible-research-peer-assessment1/blob/master/figures/jagunnamed-chunk-5.png) 

 ```r
 mean(total.steps)
 @@ -155,4 +155,4 @@ ggplot(averages, aes(interval, steps)) + geom_line() + facet_grid(day ~ .) +
     xlab("5-minute interval") + ylab("Number of steps")
 ```

 ![plot of chunk jagunnamed-chunk-7](https://github.com/JAgOneill/coursera-reproducible-research-peer-assessment1/blob/master/jagunnamed-chunk-7.png) 
 ![plot of chunk jagunnamed-chunk-7](https://github.com/JAgOneill/coursera-reproducible-research-peer-assessment1/blob/master/figures/jagunnamed-chunk-7.png) 
