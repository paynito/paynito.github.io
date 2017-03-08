---
layout: post
title: "Discovering Region Names-R as GIS"
date: 2017-03-08 05:34:23 
categories: mapping
lang: en
ref: map3
---
# mapping
## try again to access regions of the shape file:

## load:
load required libraries:

{% highlight R %}
library(maptools)
library(RColorBrewer)
colors <- brewer.pal(9, "BuGn")
library(ggmap)
{% endhighlight %}

Get the google map.
{% highlight R %}
mapImageData3 <- get_map(location = c(lon = 35.1660235,
                                      lat = 31.32226),
                         color="color",
                         source = "google",
                         maptype = "satellite",
                         zoom = 7) 
{% endhighlight %}
## read the shape file:
see previous post for code to download the shapes
{% highlight R %}
rgdal::readOGR(dsn="./includes/ISR_adm", layer="ISR_adm1", disambiguateFIDs = TRUE)
{% endhighlight %}

## Output of that command. Gives me the "NAME_1" field
This contains recognizable names. But how do I access these?
{% highlight R %}
 An object of class "SpatialPolygonsDataFrame"
 
 Slot "data":
 
   ID_0 ISO NAME_0 ID_1    NAME_1 TYPE_1 ENGTYPE_1 NL_NAME_1
   
 0  111 ISR Israel    1     Golan  Mehoz  District      <NA>
 
 1  111 ISR Israel    2   HaDarom  Mehoz  District      <NA>
 
 2  111 ISR Israel    3     Haifa  Mehoz  District      <NA>
 
 3  111 ISR Israel    4  HaMerkaz  Mehoz  District      <NA>
 
 4  111 ISR Israel    5   HaZafon  Mehoz  District      <NA>
 
 5  111 ISR Israel    6 Jerusalem  Mehoz  District      <NA>
 
 6  111 ISR Israel    7  Tel Aviv  Mehoz  District      <NA>

{% endhighlight %}

It looks like I need to use the NAME_1 field to color the individual districts
on the map.  Stopping for today.
