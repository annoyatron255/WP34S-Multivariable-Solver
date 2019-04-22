WP34S Multivariable System Solver
=================================
A solver using Newton's Method for the WP34S which accepts systems of up to 10 (non)linear equations and 10 variables
# Usage
1. Write programs for each equation in the system using global registers 01-10 as the variables
    * Each equation must start with a label name '1' though '10'*
    * Equations should be written such that they equal zero
2. Enter initial guesses for each variable into R01-R10**
3. Run the solver by typing `XEQ'MLS'` or by browsing for it in the catalog (`h CAT`) and pressing `XEQ`
4. When asked, enter the number of equations and press `R/S`
5. Wait. This can take a long time to complete***
6. The solutions will be stored in R01-R10 and R01 up will also be pushed to the stack for convenience
# Notes
*These quotes are important! They mean that the the label is global which allows the solver to be placed in flash. You can enter these types of labels by entering alpha mode and then pressing `f` to enter the numbers.
For example, to enter `LBL'3'` in program mode type: `f LBL ENTER f 3`

**most errors occur because the initial guesses have an issue. Avoiding making each variable have the same initial guess will solve most common problems

***Sometimes, the solver can be sped up by changing the display mode. Set `h SCI 4` (or similar) for faster convergence.

All calculations are done internally with local registers. Ensure that enough memory is available for the calculator to allocate on the SRS. The program uses x^2+x+6 local registers where x is the number of equations. Multiply that by 4 to know the number of program steps which need to be free.
