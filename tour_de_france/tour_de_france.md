---
title: "#TidyTuesday Tour de France"
output: 
  html_document: 
    keep_md: yes
---


```r
# Get the Data

tdf_winners <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-04-07/tdf_winners.csv')

# libraries
library(tidyverse)
library(lubridate)
library(ggplot2)
```


```r
# clean data
tdf_winners$start_date <- ymd(tdf_winners$start_date)
tdf_winners$born <- ymd(tdf_winners$born)
tdf_winners$died <- ymd(tdf_winners$died)
```



```r
tdf_winners %>%
  ggplot(aes(start_date,distance))+
  geom_line()
```

![](tour_de_france_files/figure-html/unnamed-chunk-3-1.png)<!-- -->


```r
tdf_winners %>%
  mutate(avg_speed = distance/time_overall) %>%
  ggplot(aes(start_date,avg_speed))+
  geom_line()
```

![](tour_de_france_files/figure-html/unnamed-chunk-4-1.png)<!-- -->


