---
title: "Dubois Challenge"
author: "Joe DiNoto"
date: "2/16/2021"
output: 
  html_document: 
    keep_md: yes
---

# Dubois Challenge

TidyTuesday page on github with data set and background info. https://github.com/rfordatascience/tidytuesday/blob/master/data/2021/2021-02-16/readme.md




```r
library(tidyverse)
library(dplyr)
library(ggplot2)
library(tidytuesdayR)
```


```r
tuesdata <- tidytuesdayR::tt_load(2021, week = 8)
```

```
## 
## 	Downloading file 1 of 8: `freed_slaves.csv`
## 	Downloading file 2 of 8: `census.csv`
## 	Downloading file 3 of 8: `furniture.csv`
## 	Downloading file 4 of 8: `city_rural.csv`
## 	Downloading file 5 of 8: `income.csv`
## 	Downloading file 6 of 8: `occupation.csv`
## 	Downloading file 7 of 8: `conjugal.csv`
## 	Downloading file 8 of 8: `georgia_pop.csv`
```

```r
ga_pop <- tuesdata$georgia_pop
```


```r
ga_pop %>%
  pivot_longer(Colored:White,names_to="race",values_to="pop") %>%
  mutate(pop=pop/100) %>%
  ggplot(aes(Year,pop,color=race)) +
  geom_point(size=3) +
  geom_line()+
  labs(title="comparative increasee in white and black population in GA",
       x="year",
       y="relative increase in population (% over previous year)")+
  scale_y_continuous(labels = scales::percent, minor_breaks = seq(0 , 1, .1),breaks =seq(0,1,.2))+
  scale_x_continuous(limits=c(1790,1890),minor_breaks = seq(1790 , 1890, 10),breaks=seq(1790,1890,20))+
  geom_vline(xintercept=1863,color="black",linetype="dotted")+
  theme_light()+
  coord_flip()
```

![](dubois_challenge_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

