---
title: MapReduce？
author: Curve
date: '2018-04-10'
slug: mapreduce
categories:
  - Zen
tags:
  - Zen
---

一直以来都很好奇 MapReduce 到底是个啥。自己也查阅了一些资料，并未成功的将这个抽象的概念转化为具体的事物。直到前几天帮朋友处理数据的时候，顿时茅塞顿开。原本也并不是什么很困难的事情，只不过友人的电脑可能有些陈旧，读取并合并28个各百万行的数据有些吃力。

想来最近学习了 [purrr](http://purrr.tidyverse.org/) 包，正好可以一展拳脚。

```{r}
library(data.table)
library(purrr)
## 获取所有 csv 文件(并不严谨哦)
csvs <- grep(".csv", list.files(), value = TRUE)

data <- map(csvs, fread) %>% 
  reduce(rbind)
```

(28个csv，用 map，fread 读取大概要 27s。reduce(., rbind) 部分要18秒左右。最后得到一个不到3000W行的dataframe。如果你看过我朋友，一个一个 data_i <- read.csv(...) 的话，你会发现上面的方式是多么的简洁高效。)
  
 map？reduce？MapReduce？似乎在那一刻我明白了点什么。
 
