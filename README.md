# simulated_annealing


Simulated Annealing (SA) is a probabilistic optimization algorithm inspired by the annealing process in metallurgy. It is used to find an approximate global minimum of a function, particularly in large search spaces where traditional optimization methods might get stuck in local minima.


Objective Function:
The objective function f(x) is the function we want to minimize. The goal of Simulated Annealing is to find the value of x that results in the smallest possible value of f(x).

Search Space:
The search space is the domain of the objective function, which includes all possible solutions x. Simulated Annealing explores this space to find the global minimum.

Temperature:
Temperature (T) is a key parameter in Simulated Annealing, analogous to the temperature in physical annealing processes. The temperature controls the probability of accepting worse solutions as the algorithm explores the search space.

Cooling Schedule:
The cooling schedule defines how the temperature decreases over time. A typical cooling schedule is an exponential decay:
T_k = T_0 * alpha^k
Here, T_0 is the initial temperature, alpha is the cooling rate (a value slightly less than 1), and k is the iteration number.


Initialization:
Start with an initial solution x_0 and an initial temperature T_0.
Set the current solution x_current = x_0 and evaluate its objective function value f_current = f(x_0).

Iteration:
For each iteration k:
Generate a New Candidate Solution:
Perturb the current solution slightly to create a new candidate solution x_new

Evaluate the New Solution:
Calculate the objective function value f_new = f(x_new).

Compute the difference in objective values:
delta = f_new - f_current

Acceptance Probability:
If delta <= 0 (i.e., f_new is better), accept the new solution: x_current = x_new.
If delta > 0 (i.e., f_new is worse), accept the new solution with a probability:
P_accept = exp(-delta / T_k)
This probability allows the algorithm to escape local minima by occasionally accepting worse solutions.

Update Temperature:
Reduce the temperature according to the cooling schedule.

Termination:
The algorithm terminates after a predefined number of iterations or when the temperature becomes sufficiently low. The best solution found during the process is returned as the approximate global minimum.
