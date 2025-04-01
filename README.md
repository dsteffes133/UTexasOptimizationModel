# UTexasOptimizationModel

Team built optimization model.

We had one night to take the case and generate a function to find global maxima profit in May.

Instantiated a linear programming (LP) optimization function utilizing the PuLP module in python in order to ensure we derived the optimal solution within the sample space.

PuLP acts similarly to an assistant, we introduce it to the decision variables and constraints, and it helps us build out an objective function and pass it through to the solver.

The solver we used was the CBC (COIN -OR Branch and Cut) solver. 

The CBC solver was easy, open-source, and free.

It does a few things, including simplifying early, to lessen the computational difficulty. This is essential because it (like all combinatorial algorithms) has a worst case complexity of O(2^n).

Branch and cut basically means it builds a search tree, solves an LP relaxation at each node, and then if the node is deemed unoptimal (not integer-feasible) it branches by choosing a variable that should be integer and creates two subproblems (branches) with bounds that force the variable toward integrality.

It also cuts. So that means it adds extra constraints to the LP relaxation to simplify more rapidly.
