---
title: R Flash Card 4
tags: R
---

#### Control structures

* if, else
* for
* while
* repeat
* break
* next
* return

For loop for all elements in a matrix x:

	for (i in seq_len(nrow(x))) {
	  for (j in seq_len(ncol(x))) {
	    print(x[i, j])
	  }
	}

#### Functions

* functions are first class objects
* can pass functions to functions
* can define functions inside functions
* last expression == return value
* formal arguments are included in the function definition
* functions arguments can be give by name

#### Scoping rules

* global env (users’ workspace) is always searched first
* the base is the last
* packages loaded using library in the middle, library loads to position 2, and shifts everything else
* search() — view searching elements
* free variable, a variable in a function that is not in the argument list definition and it’s not local to the function

