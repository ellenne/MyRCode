Maps in R
---------

Aim of this document is to show all the possible maps that are available
in R

Terrain
-------

    library(ggmap)
    Ireland1 <- get_map(location = 'Ireland', zoom = 7, maptype = "terrain")

![](Ireland1.jpeg)

Satellite
---------

    library(ggmap)
    Ireland3 <- get_map(location = 'Ireland', zoom = 7, maptype = "satellite")
    
![](Ireland3.bmp)   

Roadmap
-------

    library(ggmap)
    Ireland4 <- get_map(location = 'Ireland', zoom = 7, maptype = "roadmap")
    
![](Ireland4.bmp)
    
Hybrid
------

    library(ggmap)
    Ireland5 <- get_map(location = 'Ireland', zoom = 7, maptype = "hybrid")
    
![](Ireland5.bmp)   

Toner
-----

    library(ggmap)
    Ireland6 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner", source = "stamen")
    
![](Ireland6.bmp)    

Water Color
-----------

    library(ggmap)
    Ireland7 <- get_map(location = 'Ireland', zoom = 7, maptype = "watercolor", source = "stamen")

![](Ireland7.bmp)

Terrain-lines
-------------

    library(ggmap)
    Ireland9 <- get_map(location = 'Ireland', zoom = 7, maptype = "terrain-lines", source = "stamen")

![](Ireland9.bmp)

Toner-2010
----------

    library(ggmap)
    Ireland10 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-2010", source = "stamen")
    
![](Ireland10.bmp)

Toner-2011
----------

    library(ggmap)
    Ireland11 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-2011", source = "stamen")

![](Ireland11.bmp)    

Toner-background
----------------

    library(ggmap)
    Ireland12 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-background")

![](Ireland12.bmp)    

Toner-hybrid
------------

    library(ggmap)
    Ireland13 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-hybrid", source = "stamen")

![](Ireland13.bmp)

Toner-labels
------------

    library(ggmap)
    Ireland14 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-labels", source = "stamen")

![](Ireland14.bmp)   

Toner-lines
-----------

    library(ggmap)
    Ireland15 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-lines", source = "stamen")

![](Ireland15.bmp)    

Toner-lite
----------
    
    library(ggmap)
    Ireland16 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-lite", source = "stamen")

![](Ireland16.bmp)
