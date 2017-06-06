Maps in R
---------

Aim of this document is to show all the possible maps that are available
in R

    library(ggmap)
    Ireland <- get_map(location = 'Ireland', zoom = 7, maptype = "terrain")

Terrain
-------

![](MapsInR_MDv_files/figure-markdown_strict/map1Plot-1.png)

    library(ggmap)
    Ireland3 <- get_map(location = 'Ireland', zoom = 7, maptype = "satellite")

Satellite
---------

![](MapsInR_MDv_files/figure-markdown_strict/map3Plot-1.png)

    library(ggmap)
    Ireland4 <- get_map(location = 'Ireland', zoom = 7, maptype = "roadmap")

Roadmap
-------

![](MapsInR_MDv_files/figure-markdown_strict/map4Plot-1.png)

    library(ggmap)
    Ireland5 <- get_map(location = 'Ireland', zoom = 7, maptype = "hybrid")

Hybrid
------

![](MapsInR_MDv_files/figure-markdown_strict/map5Plot-1.png)

    library(ggmap)
    Ireland6 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner")

Toner
-----

![](MapsInR_MDv_files/figure-markdown_strict/map6Plot-1.png)

    library(ggmap)
    Ireland7 <- get_map(location = 'Ireland', zoom = 7, maptype = "watercolor")

Water Color
-----------

![](MapsInR_MDv_files/figure-markdown_strict/map7Plot-1.png)

    library(ggmap)
    Ireland9 <- get_map(location = 'Ireland', zoom = 7, maptype = "terrain-lines", source = "stamen")

Terrain-lines
-------------

![](MapsInR_MDv_files/figure-markdown_strict/map9Plot-1.png)

    library(ggmap)
    Ireland10 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-2010", source = "stamen")

Toner-2010
----------

![](MapsInR_MDv_files/figure-markdown_strict/map10Plot-1.png)

    library(ggmap)
    Ireland11 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-2011", source = "stamen")

Toner-2011
----------

![](MapsInR_MDv_files/figure-markdown_strict/map11Plot-1.png)

    library(ggmap)
    Ireland12 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-background")

Toner-background
----------------

![](MapsInR_MDv_files/figure-markdown_strict/map12Plot-1.png)

    library(ggmap)
    Ireland13 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-hybrid", source = "stamen")

Toner-hybrid
------------

![](MapsInR_MDv_files/figure-markdown_strict/map13Plot-1.png)

    library(ggmap)
    Ireland14 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-labels", source = "stamen")

Toner-labels
------------

![](MapsInR_MDv_files/figure-markdown_strict/map14Plot-1.png)

    library(ggmap)
    Ireland15 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-lines", source = "stamen")

Toner-lines
-----------

![](MapsInR_MDv_files/figure-markdown_strict/map15Plot-1.png)

    library(ggmap)
    Ireland16 <- get_map(location = 'Ireland', zoom = 7, maptype = "toner-lite", source = "stamen")

Toner-lite
----------

![](MapsInR_MDv_files/figure-markdown_strict/map16Plot-1.png)
