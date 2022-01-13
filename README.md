# PyGAD TSP Solver
Implement a genetic algorithm using PyGad (Ahmed Fawzy Gad, 2021 https://pygad.readthedocs.io/en/latest/) in order to find a solution to the Travelling Salesman Problem (TSP).

## Packages required
- Pandas <br>
- NumPy <br>
- PyGAD <br>

## Input files
Create your own .csv files following the format of tsp1.csv or tsp2.csv in the project files.

## Tips for tweaking the genetic algorithm

- Solutions per population
    - Too low resulted in local minimum
    - Too high increased computation time

- Generations
    - Too low the plateau of the fitness funciton was never reached -> the optimal solution for the set of constraints was never found
    - Too high there were no more improvements to be found as the fitness function had reached its peak -> wasted computation time
        - The stop_gen function corrects for this

- Lower number of parents mating resulted in too much "elitism"
    - by mating with only a small subset of parents, we were stifling diversity and only getting the positive traits of a small portion of the population
        - doesn't play to the strengths of evolution in a genetic algorithm
        
- Parent selection type
   - Ranked appears to get to the local optimum faster, although steady state seems to get better results overall

- Adaptive mutation helped jump start the fitness and narrow the solution space quicker
    - One of the problems with random mutation is that we can throw away too much of a good solution and not enough of a bad one (see https://i2.wp.com/neptune.ai/wp-content/uploads/Mutation-probability.jpg?resize=768%2C254&ssl=1 for a excellent visual). Adaptive mutation aims to solve this by having a larger mutation percentage for all solutions worse than average, and a lower mutation percentage for all solutions better than average
