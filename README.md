---
title: "taggart"
output: 
  html_document: 
    keep_md: yes
---



For now just a test.

Do:

```r
devtools::install_github("fishvice/taggart", dependencies = FALSE)
```

Load library:

```r
library(taggart)
```

Get the data and have a peek

```r
tg_catches()         %>% glimpse()
```

```
## Observations: 4,964
## Variables: 19
## $ pkid                   <chr> "644d94dc-62d2-4eb4-9e33-082f902a4940",...
## $ ices_rectangle         <chr> "58D9", "58D7", "57D7", "57D7", "55C8",...
## $ catchdate              <int> 2015, 2016, 2017, 2016, 2016, 2017, 201...
## $ reference_plant        <chr> "758459f7-a4f4-43e8-830e-06c270d2da84",...
## $ plant_name             <chr> "IC02 Neskaupstad", "IC02 Neskaupstad",...
## $ plant_ices_rectangle   <chr> "59D6", "59D6", "59D6", "59D6", "59D6",...
## $ weight                 <dbl> 356403, 482060, 547359, 286168, 706663,...
## $ weightavg              <dbl> 0.4230, 0.4260, 0.4840, 0.4202, 0.3662,...
## $ recatch_ices_rectangle <chr> "Va2", "Va2", "Va2", "Va2", "Va2", "IIa...
## $ shep_regmark           <chr> "2862", "2900", "2865", "2909", "2909",...
## $ catch_number           <int> 1254, 1508, 872490, 1475, 1463, 879014,...
## $ ship_name              <chr> NA, "2900", NA, "2909", "2909", NA, "29...
## $ nation                 <chr> "IS", "IS", "IS", "IS", "IS", "IS", "IS...
## $ processing_date        <dttm> 2015-08-19 23:59:00, 2016-09-01 23:59:...
## $ cLon                   <dbl> -10.5, -12.5, -12.5, -12.5, -21.5, 0.5,...
## $ cLat                   <dbl> 64.75, 64.75, 64.25, 64.25, 63.25, 66.7...
## $ pLon                   <dbl> -13.5, -13.5, -13.5, -13.5, -13.5, -13....
## $ pLat                   <dbl> 65.25, 65.25, 65.25, 65.25, 65.25, 65.2...
## $ species                <chr> "mackerel", "mackerel", "mackerel", "ma...
```

```r
tg_catches_bio()     %>% glimpse()
```

```
## Observations: 25,305
## Variables: 21
## $ lo             <dbl> -1.500000, 1.016667, -1.500000, 0.000000, -2.15...
## $ la             <dbl> 60.25000, 63.60000, 60.25000, 64.50000, 62.2000...
## $ ices_rectangle <chr> "49E8", "56F1", "49E8", "57F0", "53E7", "48E4",...
## $ ices_area      <chr> "IVa", "IIa2", "IVa", "IIa2", "IVa", "VIa", "II...
## $ sex            <int> 1, 2, 1, 2, 1, 1, 1, 1, 1, 2, 1, 2, 1, 2, 1, 2,...
## $ fishno         <chr> "28", "10", "20", "6", "46", "13", "93", "14", ...
## $ station        <chr> "8089", "8018", "8093", "36", "20145026", "3", ...
## $ catch_gear     <chr> "3500", "3712", "3500", "3712", "FL", "3500", "...
## $ catch_date     <dttm> 2015-10-29, 2014-09-16, 2015-10-25, 2017-09-12...
## $ land           <lgl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA,...
## $ ship_radio     <chr> "ZQMP4", "LLRG", "ZQMP4", "LMMC", "FD0042", "GU...
## $ nation         <chr> "74", "58", "74", "58", "FO", "74", "FO", "58",...
## $ sampleno       <chr> "38089", "38018", "38093", "38036", "20145026",...
## $ maturity       <int> 3, 8, 8, 8, 8, 4, 8, 8, 6, 6, 6, 3, 8, 8, 6, 6,...
## $ weight         <dbl> 0.4920, 0.3730, 0.3100, 0.4680, 0.3400, 0.5230,...
## $ length         <dbl> 0.38, 0.36, 0.33, 0.36, 0.33, 0.40, 0.37, 0.38,...
## $ age            <int> 8, 5, 5, 7, 4, 11, 9, 8, 5, 6, 5, 3, 3, 4, 4, 3...
## $ year_class     <int> 2007, 2009, 2010, 2010, 2010, 2007, 2006, 2008,...
## $ lon            <dbl> -1.5, 1.5, -1.5, 0.5, -2.5, -5.5, -6.5, 2.5, -1...
## $ lat            <dbl> 60.25, 63.75, 60.25, 64.25, 62.25, 59.75, 64.75...
## $ species        <chr> "mackerel", "mackerel", "mackerel", "mackerel",...
```

```r
tg_expeditions()     %>% glimpse()
```

```
## Observations: 353,551
## Variables: 20
## $ mission           <chr> "2014809", "2018828-old", "2011808", "Icelan...
## $ when              <dttm> 2014-05-12 10:00:00, 2018-05-09 00:00:00, 2...
## $ experiment        <chr> "29", "1070", "3", "47", "27", "1069", "7", ...
## $ release           <chr> "5", "4", "2", "1", "6", "1", "3", "1", "6",...
## $ release_birds     <chr> "Medium", "Medium", NA, "None", "Medium", "M...
## $ release_waves     <chr> "None", "None", NA, "None", "Medium", "None"...
## $ release_mortality <int> 0, 0, 0, NA, 0, 0, 0, NA, 0, NA, 0, 0, 0, NA...
## $ fish              <chr> "Mackerel", "Mackerel", "Mackerel", "Mackere...
## $ rfid              <chr> "900196000215787", "900153000019134", "90019...
## $ ices              <chr> "32D8", "32D8", "39E0", "58C6", "38E0", "32D...
## $ assistent         <chr> "OS", "LK", NA, "SJ", "OS", "Alj", NA, "JR",...
## $ plantid           <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, ...
## $ catchid           <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, ...
## $ lo                <dbl> -11.964180, -11.430000, -9.972255, -23.97865...
## $ relesedate        <dttm> 2014-05-29 13:56:18, 2018-05-28 07:13:04, 2...
## $ recapturedate     <dttm> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA,...
## $ tagger            <chr> "EH", "EH", "JR", "HP", "EH", "eh", "JHN", "...
## $ la                <dbl> 51.89226, 51.95000, 55.29470, 64.88466, 54.8...
## $ length            <dbl> 38, 36, 29, 39, 37, 36, 36, 37, 37, 36, 28, ...
## $ species           <chr> "mackerel", "mackerel", "mackerel", "mackere...
```

```r
tg_expeditions_bio() %>% glimpse()
```

```
## Observations: 4,717
## Variables: 19
## $ lon            <dbl> -23.916667, -10.366667, -12.016667, -9.350000, ...
## $ lat            <dbl> 64.73333, 54.78333, 52.96667, 56.16667, 60.4316...
## $ ices_rectangle <chr> "58C6", "38D9", "34D7", "41E0", "49F1", "49E7",...
## $ ices_area      <chr> "Va2", "VIIb", "VIIc", "VIa", "IVa", "IVa", "VI...
## $ sex            <int> 2, 2, 1, 1, 2, 2, 1, 1, 2, 1, 2, 1, 1, 2, 2, 1,...
## $ fishno         <chr> "8", "17", "47", "17", "11", "12", "22", "6", "...
## $ station        <chr> "MMGE2-2017", "6", "7", "27", "75", "116", "13"...
## $ catch_gear     <chr> "3", "1", "5211", "5211", "3712", "3411", "5211...
## $ catch_date     <dttm> 2017-08-17, 2017-05-11, 2012-05-16, 2015-06-03...
## $ land           <lgl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA,...
## $ ship_radio     <chr> "2869", "LDFS", "LACT", "LCNX", "LIVA", "LLYM",...
## $ nation         <chr> "ICE", "58", "58", "NO", "58", "58", "58", "NO"...
## $ sampleno       <chr> "2", "37356", "37207", "37527", "86225", "86567...
## $ maturity       <int> 6, 8, 6, 6, 8, 8, 6, 6, 6, 6, 8, 6, 5, 8, 3, 5,...
## $ weight         <dbl> 0.6666, 0.3310, 0.4340, 0.2810, 0.3580, 0.4090,...
## $ length         <dbl> 0.40, 0.36, 0.39, 0.31, 0.33, 0.37, 0.31, 0.42,...
## $ age            <int> 10, 6, 10, 3, 4, 6, 3, 11, 11, 6, 6, 10, 4, 4, ...
## $ year_class     <int> 2007, 2011, 2002, 2012, 2007, 2005, 2008, 2003,...
## $ species        <chr> "mackerel", "mackerel", "mackerel", "mackerel",...
```
