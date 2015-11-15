---
title: R Flash Card 2
tags: R
---

Some quick comments about programming in R:

  * Everything in R is an object.
  * Five atomic classes of objects: char, numeric (real), int, complex, logical.
  * The most basic object is a vector, can only contain objects of the same class.
  * A list is a vector of anythings.
  * create empty vectors: `> vector()`
  * Infinity is represented as ‘Inf’
  * NaN - not a number
  * Objects can have attribues (e.g. names, dimensions): `> attributes()`

#### Vectors

    > x <- c(1,2,3)
    > x <- c(True, False)
    > x <- c(T, F)
    > vector(“numeric”, length = 10)

#### Explicit coercion:

  * as.numeric(x)
  * as.logical(x)
  * as.character(x)

#### Lists:

    > x <- list(1, “a”, TRUE, 1+4i)

#### Matrices

    > m <- matrix(nrow=2, ncol=3)
    > dim(m)  # [1] 2 3
    > attributes(m)  # $dim [1] 2 3
    > matrices are constructed column-wise
    > cbind and bind, column and row bind vector

#### Factors

Used to represent categorical data.

    > x <- factor(c(“yes”, “yes”, “no”, “yes”, “no”))
    > x <- factor(c(“yes”, “yes”, “no”, “yes”, “no”), levels = c(“yes”,”no”) )
    > table(x)
    > unclass(x) 

#### Missing values:

  * is.na() — missing value
  * is.nan() — is not a number

#### Data Frames:

Use to store tabular data.

  - read.table()
  - read.csv()

