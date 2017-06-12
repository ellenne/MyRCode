Maps in R
---------

Aim of this document is to show all the possible maps that are available
in R

    library(ggmap)
    Ireland <- get_map(location = 'Ireland', zoom = 7, maptype = "terrain")

Terrain
-------

![](Ireland1.jpeg)

    library(ggmap)
    Ireland3 <- get_map(location = 'Ireland', zoom = 7, maptype = "satellite")

Satellite
---------

![](Ireland3.bmp)

    library(ggmap)
    Ireland4 <- get_map(location = 'Ireland', zoom = 7, maptype = "roadmap")

Roadmap
-------

![](Ireland4.bmp)

    library(ggmap)
    Ireland5 <- get_map(location = 'Ireland', zoom = 7, maptype = "hybrid")

Hybrid
------

![](Ireland5.bmp)

    library(ggmap)
    Ireland6 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner")

Toner
-----

![](Ireland6.bmp)

    library(ggmap)
    Ireland7 <- get_map(location = 'Ireland', zoom = 7, maptype = "watercolor")

Water Color
-----------

![](Ireland7.bmp)

    library(ggmap)
    Ireland9 <- get_map(location = 'Ireland', zoom = 7, maptype = "terrain-lines", source = "stamen")

Terrain-lines
-------------

![](Ireland9.bmp)

    library(ggmap)
    Ireland10 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-2010", source = "stamen")

Toner-2010
----------

![](Ireland10.bmp)

    library(ggmap)
    Ireland11 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-2011", source = "stamen")

Toner-2011
----------

![](Ireland11.bmp)

    library(ggmap)
    Ireland12 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-background")

Toner-background
----------------

![](Ireland12.bmp)

    library(ggmap)
    Ireland13 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-hybrid", source = "stamen")

Toner-hybrid
------------

![](Ireland13.bmp)

    library(ggmap)
    Ireland14 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-labels", source = "stamen")

Toner-labels
------------

![](Ireland14.bmp)

    library(ggmap)
    Ireland15 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-lines", source = "stamen")

Toner-lines
-----------

![](Ireland15.bmp)

    library(ggmap)
    Ireland16 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-lite", source = "stamen")

Toner-lite
----------

![](Ireland16.bmp)
