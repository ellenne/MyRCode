Maps in R
---------

Aim of this document is to show all the possible maps that are available
in R

Terrain
-------

    library(ggmap)
    Ireland1 <- get_map(location = 'Ireland', zoom = 7, maptype = "terrain")

![](Img/Ireland1.jpeg)

Satellite
---------

    library(ggmap)
    Ireland3 <- get_map(location = 'Ireland', zoom = 7, maptype = "satellite")
    
![](Img/Ireland3.bmp)   

Roadmap
-------

    library(ggmap)
    Ireland4 <- get_map(location = 'Ireland', zoom = 7, maptype = "roadmap")
    
![](Img/Ireland4.bmp)
    
Hybrid
------

    library(ggmap)
    Ireland5 <- get_map(location = 'Ireland', zoom = 7, maptype = "hybrid")
    
![](Img/Ireland5.bmp)   

Toner
-----

    library(ggmap)
    Ireland6 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner", source = "stamen")
    
![](Img/Ireland6.bmp)    

Water Color
-----------

    library(ggmap)
    Ireland7 <- get_map(location = 'Ireland', zoom = 7, maptype = "watercolor", source = "stamen")

![](Img/Ireland7.bmp)

Terrain-lines
-------------

    library(ggmap)
    Ireland9 <- get_map(location = 'Ireland', zoom = 7, maptype = "terrain-lines", source = "stamen")

![](Img/Ireland9.bmp)

Toner-2010
----------

    library(ggmap)
    Ireland10 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-2010", source = "stamen")
    
![](Img/Ireland10.bmp)

Toner-2011
----------

    library(ggmap)
    Ireland11 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-2011", source = "stamen")

![](Img/Ireland11.bmp)    

Toner-background
----------------

    library(ggmap)
    Ireland12 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-background")

![](Img/Ireland12.bmp)    

Toner-hybrid
------------

    library(ggmap)
    Ireland13 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-hybrid", source = "stamen")

![](Img/Ireland13.bmp)

Toner-labels
------------

    library(ggmap)
    Ireland14 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-labels", source = "stamen")

![](Img/Ireland14.bmp)   

Toner-lines
-----------

    library(ggmap)
    Ireland15 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-lines", source = "stamen")

![](Img/Ireland15.bmp)    

Toner-lite
----------
    
    library(ggmap)
    Ireland16 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-lite", source = "stamen")

![](Img/Ireland16.bmp)
