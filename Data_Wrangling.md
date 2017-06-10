Data Wrangling
--------------

This is the exercise from R-Exercises about data wrangling. Let's see
the packages that we need to load:

    library(RCurl)
    library(rjson)
    library(XML)
    library(plyr)
    library(rvest)
    library(htmltab)

Exercise 1
----------

Retrieve the source of the web page and assign to the object "url"

    url_text <- "https://raw.githubusercontent.com/VasTsak/r-exercises-dw/master/part-1/data.csv"
    url <- readline(url_text)

    ## https://raw.githubusercontent.com/VasTsak/r-exercises-dw/master/part-1/data.csv

Using readline we close inside an R variable the content of the page not
the actual file. We notice that the url\_text point to a CSV file so it
would be good to download the file for further reference and access it.
There is also another way that allows to access directly to the file.
Let's see both method.

Method 1 - saving the file and access it:

    f <- file.path(folder_Location, filename)
    download.file(url_text, f)
    csv_file <- read.csv(f, header = TRUE, stringsAsFactors = FALSE)

Method 2 - direct access to the file:

    csv_file2 <- read.csv(url_text)

Let's make sure that the 2 R objects are the same. We want to make a
deep comparison element-by-element and we do in this way:

    all(csv_file == csv_file2)

    ## [1] TRUE

    identical(csv_file, csv_file2)

    ## [1] TRUE

Exercise 2
----------

Do the same but with another url. Import it in an appropriate R object

    url_text2 <- "https://raw.githubusercontent.com/VasTsak/r-exercises-dw/master/part-2/data.txt"
    f2 <- file.path(folder_Location, filename2)
    download.file(url_text2, f2)
    txt_file <- read.table(f2, 
                           header = TRUE, 
                           stringsAsFactors = FALSE,
                           sep = "")

    txt_file2 <- read.table(url_text2,
                            header = TRUE,
                            stringsAsFactors = FALSE,
                            sep = "")

    identical(txt_file, txt_file2)

    ## [1] TRUE

Exercise 4
----------

Do the same of exercise 1 but with a JSON URL

    jsonUrl <- "https://raw.githubusercontent.com/VasTsak/r-exercises-dw/master/part-2/data.json"
    json_file <- fromJSON(paste(readLines(jsonUrl),collapse = ""))

Note that if you do not use this trick (namely paste function specifying
the collapse argument) you can have an error that says: unexpected
character 'h'. Instead using this you avoid the error and everything
works.

Exercise 5
----------

Now it is time for XML. I looked at the solution because after half an
hour of trial and error I could not make it to work. The solution did
not work for me so I present the variation that worked. The first thing
I do is saving the file in my output folder and then access the file
rather than the link. Let's see here below the code:

    XMLUrl <- "https://raw.githubusercontent.com/VasTsak/r-exercises-dw/master/part-2/data.xml"
    f3 <- file.path(folder_Location, filename3)
    download.file(XMLUrl, f3)
    xml_file <- ldply(f3, data.frame)

I took the ldply function from the solution of the R exercises but
trying to access directly to the URL did give me an error. Reading some
forums online I learned that maybe the error is linked to the "https"
that should be "http" so if we use the function gsub I checked that it
worked:

    xml_file2 <- ldply(gsub(pattern = "https", replacement = "http", x = XMLUrl), data.frame)

Let's check if the 2 objects are the same:

    identical(xml_file, xml_file2)

    ## [1] FALSE

The objects result to be different. Anyway I think this is because R
fail to do a deep comparison of 2 XML objects.

Exercise 6
----------

Now the game becomes a little bit more interesting. In fact an URL is
provided and it is asked us to retrieve in R the table and make it
actionable.

    url_text6 <- "http://www.worldatlas.com/articles/largest-cities-in-europe-by-population.html"

So the first thing I did is to go to the page. I used Chrome and I press
F12 to see the attached HTML code. If we pass the mouse over the code
different elements of the page are highlighted. When we found the table,
Chrome allows to right-click and one of the option is to copy the XPath
associated with this element that in my case was the following:
//\*\[@id="artReg-table"\]/table

So all I had to do was to use it. The exercises was telling to use
html\_nodes and html\_table to do the job so I followed and wrote the
following code:

    url6 <- read_html(getURL(url_text6))

    myTableList <- url6 %>%
      html_nodes(xpath = '//*[@id="artReg-table"]/table') %>% 
      html_table()

    list <- myTableList[[1]]
    str(list)

    ## 'data.frame':    15 obs. of  3 variables:
    ##  $ Rank            : int  1 2 3 4 5 6 7 8 9 10 ...
    ##  $ Cities In Europe: chr  "Moscow, Russia" "Ruhr-Essen-Dusseldorf, Germany" "Paris, France" "London, United Kingdom" ...
    ##  $ Metro Population: chr  "16,200,000" "13,400,000" "10,900,000" "10,200,000" ...

We need the last instruction because the result of the pipes is a list
containing 1 elemenet only and in order to have the data.frame we access
the first element of it

We note that population is a string but can be replaced easily with the
number in this way:

    names(list) <- c("Rank", "City", "Population")
    list$Population <- as.numeric(gsub(pattern = ",", 
                            replacement = "",
                            x = list$Population))
    str(list)

    ## 'data.frame':    15 obs. of  3 variables:
    ##  $ Rank      : int  1 2 3 4 5 6 7 8 9 10 ...
    ##  $ City      : chr  "Moscow, Russia" "Ruhr-Essen-Dusseldorf, Germany" "Paris, France" "London, United Kingdom" ...
    ##  $ Population: num  16200000 13400000 10900000 10200000 7500000 6200000 6100000 5800000 5300000 5100000 ...

Here below I give the solutions provided by R exercises. All 3 work
well:

    ## 1st way
    tbls_read <- url6 %>%
      html_nodes("table") %>%
      html_table(fill = TRUE)

    ## 2nd way
    tbls_xml <- readHTMLTable(url_text6)

    ## 3rd way
    df_pop <- htmltab(doc = url_text6, 
                      which = "//th[text() = 'Rank']/ancestor::table")

    str(df_pop)

    ## 'data.frame':    15 obs. of  3 variables:
    ##  $ Rank            : chr  "1" "2" "3" "4" ...
    ##  $ Cities In Europe: chr  "Moscow, Russia" "Ruhr-Essen-Dusseldorf, Germany" "Paris, France" "London, United Kingdom" ...
    ##  $ Metro Population: chr  "16,200,000" "13,400,000" "10,900,000" "10,200,000" ...
