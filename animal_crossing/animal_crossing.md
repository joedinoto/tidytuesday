---
title: "Animal Crossing"
output: 
  html_document: 
    keep_md: yes
---


```r
# Get the Data

critic <- readr::read_tsv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-05-05/critic.tsv')
user_reviews <- readr::read_tsv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-05-05/user_reviews.tsv')
items <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-05-05/items.csv')
```

```
## Warning: 2 parsing failures.
##  row          col           expected actual                                                                                                  file
## 4472 customizable 1/0/T/F/TRUE/FALSE    Yes 'https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-05-05/items.csv'
## 4473 customizable 1/0/T/F/TRUE/FALSE    Yes 'https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-05-05/items.csv'
```

```r
villagers <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-05-05/villagers.csv')
```

Let's look at the data. 

```r
summary(critic)
```

```
##      grade        publication            text                date           
##  Min.   : 70.00   Length:107         Length:107         Min.   :2020-03-16  
##  1st Qu.: 90.00   Class :character   Class :character   1st Qu.:2020-03-16  
##  Median : 90.00   Mode  :character   Mode  :character   Median :2020-03-23  
##  Mean   : 90.64                                         Mean   :2020-03-25  
##  3rd Qu.: 94.00                                         3rd Qu.:2020-04-02  
##  Max.   :100.00                                         Max.   :2020-05-01
```

```r
summary(user_reviews)
```

```
##      grade         user_name             text                date           
##  Min.   : 0.000   Length:2999        Length:2999        Min.   :2020-03-20  
##  1st Qu.: 0.000   Class :character   Class :character   1st Qu.:2020-03-24  
##  Median : 2.000   Mode  :character   Mode  :character   Median :2020-03-27  
##  Mean   : 4.217                                         Mean   :2020-04-01  
##  3rd Qu.:10.000                                         3rd Qu.:2020-04-06  
##  Max.   :10.000                                         Max.   :2020-05-03
```

