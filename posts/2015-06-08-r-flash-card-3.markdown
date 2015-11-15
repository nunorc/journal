---
title: R Flash Card 3
tags: R
---

#### Names

Objects can have names:

    > x <- 1:3
    > names(x) <- c(“foo”, “bar”, “zbr”)

#### Read Data

* read.table() — read tabular data (default column sep is space)
* read.csv() — read tabular data (default column sep is comma), header is always true
* readLines — read lines in text files
* source — read code

Using the colClasses argument:

	> init <- read.csv(“file.txt”, nrows = 10)
	> classes <- sapply(init, class)
	> data <- read.csv(“file.txt”, colClasses = classes)

Memory requirements of numeric values
* ncols x nrows x 8 bytes
* convert from bytes to GB

#### Textual Formats

Using put and get

	> dput(data, file=“data.R”)
	> data <- dget(“data.R”)

Using dump:

	> x <- ….
	> y <- ….
	> dump( c(x, y), file=“data.R”)
	> source(“data.R”)   # x and y are back

#### Subsetting

	> x <- c(“a”, “b”, “c”, “c”, “d”, “a”)
	> x[1]  # “a”
	> x[2]  # “b”
	> x[1:4]  # “a” “b” “c” “c” — first 4 elements
	> x[ x > “a” ]   # “b” “c” “c” “d”  — elements greater than “a”

#### Removing NA values

	> data <- c(…..)
	> bad <- is.na(data)  # bool values for missing NA
	> data[!bad]

#### Logical operators

* >, >=, <, <=
* == (equality)
* != (inequality)
* ! (not)
* | (or) & (and)

