---
title: "Steam Games"
author: "Joe DiNoto"
date: "3/21/2021"
output: 
  html_document: 
    keep_md: yes
---



First, load packages.


```r
library(tidytuesdayR)
library(tidyverse)
library(ggplot2)
library(dplyr)
```

Second, grab the data.


```r
tuesdata <- tidytuesdayR::tt_load('2021-03-16')
```

```
## 
## 	Downloading file 1 of 1: `games.csv`
```

```r
games <- tuesdata$games
```


