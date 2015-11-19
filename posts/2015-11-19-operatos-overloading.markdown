---
title: Overloading Operators
tags: Haskell
---

Let's say we have defined a type to store pairs of type `a` as:

    data Pair a = Pair a a deriving (Eq, Show)

Now we want to use typical operations (eg, addition) with our pairs. We
define the behavior of each operation for our type:

    instance (Num a) => Num (Pair a) where
      Pair a b + Pair c d = Pair (a+c) (b+d)
      Pair a b * Pair c d = Pair (a*c) (b*d)
      Pair a b - Pair c d = Pair (a-c) (b-d)
      abs (Pair a b)      = Pair (abs a) (abs b)
      signum (Pair a b)   = Pair (signum a) (signum b) 
      fromInteger i       = Pair (fromInteger i) (fromInteger i)

For example, we can now use the `+` operator to add pairs:

    *ghci> let p1 = Pair 2 3
    *Main> let p2 = Pair 4 5
    *ghci> p1+p2
    Pair 6 8
    it :: Num a => Pair a
