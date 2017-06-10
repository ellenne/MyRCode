EDA
---

This is a file that I created following one blog. It want to be a
template to perform an EDA analysis

Library that the lady loads are the following:

    library(tidyverse)
    library(tidyquant)
    library(modelr)
    library(gridExtra)
    library(grid)

In order to prepare the data the file is download from this URL
"<http://archive.ics.uci.edu/ml/machine-learning-databases/00352/Online%20Retail.xlsx>"

I tried to save the file using download file but it does not quite work.
The file apparently seem to be downloaded and saved but it has some
problem when is opened. So I just download it and transform in a CSV
using Excel. Then here below she uses a brilliant code for the
processing. She can do that because it has few columns:

    retail <- read_csv(f, col_types = cols
            (
             InvoiceNo = col_character(),
             StockCode = col_character(),
             Description = col_character(),
             Quantity = col_integer(),
             InvoiceDate = col_datetime("%d/%m/%Y %H:%M"),
             UnitPrice = col_double(),
             CustomerID = col_integer(),
             Country = col_character()
            )) %>% 
      mutate(day = parse_date(format(InvoiceDate, "%Y-%m-%d")),
             day_of_week = wday(day, label = TRUE),
             time = parse_time(format(InvoiceDate, "%H:%M")),
             month = format(InvoiceDate, "%m"),
             income = Quantity * UnitPrice,
             income_return = ifelse(Quantity > 0, "income", "return"))

Then she prepares the 2 plot, that arranges using grid.arrange and plot
here below:

The result you can see is the following:

    grid.arrange(p1, p2, widths = c(0.2, 0.8))

![Chart1.](/chart1.jpeg)
