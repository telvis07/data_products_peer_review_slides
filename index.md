---
title       : Prince Song Recommender
subtitle    : Building a song recommender using the Million Song Dataset
author      : Telvis Calhoun
job         : Research Engineer
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      #
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Goals

- Create a song recommender using metadata from the [Million Song Dataset](http://labrosa.ee.columbia.edu/millionsong/).  
- Create a demo recommender application using [R and Shiny](http://shiny.rstudio.com/)
- Recommend songs by [US recording artist 'Prince'](https://en.wikipedia.org/wiki/Prince_(musician) )

--- .class #id

## Getting and Cleaning the Data

- The entire dataset is 280GB and Stored in Amazon S3 in [HDF5](https://www.hdfgroup.org/HDF5/) format.
- We ran a data extraction script on EC2 to a serialized R file containing the features.


```r
df <- readRDS("data/songs.rds")
names(df)
```

```
##  [1] "artist_name"               "title"                    
##  [3] "release"                   "song_hotttnesss"          
##  [5] "tempo"                     "loudness"                 
##  [7] "energy"                    "danceability"             
##  [9] "duration"                  "artist_familiarity"       
## [11] "artist_hotttnesss"         "artist_latitude"          
## [13] "artist_location"           "artist_longitude"         
## [15] "end_of_fade_in"            "key"                      
## [17] "key_confidence"            "song_id"                  
## [19] "start_of_fade_out"         "time_signature"           
## [21] "time_signature_confidence" "track_id"
```

--- .class #id

## Feature Selection

Song Hotttnesss : Measures the popularity of the song.



![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3-1.png)

***

Loudness : Measures the audio volume of the song.

![plot of chunk unnamed-chunk-4](assets/fig/unnamed-chunk-4-1.png)
