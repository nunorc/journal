---
title: Downloading and Reading Data 
tags: R
---

#### Downloading files
  
    if (!file.exists(“data”)) {
      dir.create(“data”);
    }

    download.file(URL, DESTFILE)

    list.files(“./data”);

#### Reading Local Files

    read.table(FILE, sep=“,”)

    read.csv(FILE)   # sep=“,” and header=TRUE

#### Reading Excel Files

    library(xlsx)
    data <- read.xlsx(FILE, sheetIndex=1)

#### Reading XML

    library(XML)
    doc <- xmlTreeParse(URL, useInternal=TRUE)

    doc <- htmlTreeParse(URL, useInternal=TRUE)

    xpathSApply(doc, xpath, xmlValue)

#### Reading JSON

    library(jsonlite)
    data <- fromJSON(URL)
    json <- toJSON(data, pretty=TRUE)
    cat(json)

