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

