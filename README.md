# Python Arithmographs
Arithmographs in Python.

An arithmograph is a kind of a numeric crossword puzzle, where instead of filling the rows and columns with words, digits must be found that give numbers that fit the equations.

ABC | - | BBD | = | DEF
------------------------
 / |    | + |   | -
------------------------
GH |  * | GD |  = | BGC
------------------------
 = |    = |     = |
------------------------
DI |  + | BJI | = | BIF

Each letter corresponds to a digit, always the same one, and different digits for different letters.

To check all possibilities, 10! = 3628800 permutations would have to be checked. A brief analysis of the equation system allows us to reduce this number significantly.

First, we can see from III-down that C = 0. From II-down, I is even, non-zero. from I-down and II-down, H = 5. Further, we can see that some digits are no greater than a certain number, like from II-across we can see that (10*G)2 < 1000, hence G2 < 10, hence G <= 3, and since we already know that 0 is taken by C, G is in (1, 2, 3), etc.

All resulting constraints are specified in the CONSTRAINTS array. As a result, we now have less than 294912 permutations to check.

--------------------------------------------------------------------------


`def DigitPoly(letterdigits):`
    """Creates polynomial from digit IDs specified as abc..."""


`def Equation(eqndata):`
    """Creates equation test function from eqndata."""


`def check_permutations(constraints, equations, digits):`
    """Recursively checks all permutations in constraints on equations."""
