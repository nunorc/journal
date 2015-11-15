---
title: Haskell Main Is
tags: Haskell
---

When using ghc to compile a module, the linked binary file will only be created if the main function is provided

    main = putStrLn "Hello world"

This works because the main function module is defined and we have only one module. If the application has several modules, either one of them is called Main:

    module Main where
    main = putStrLn "Hello world"

if not the main cmodule cn be specified when compiling:

    module Test where
    main = putStrLn "Hello world"

and compile the file using:

    $ ghc -main-is Test Test.hs
