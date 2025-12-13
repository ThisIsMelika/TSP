
Traveling Salesman Problem (TSP) – AI Project
Project Overview
This project focuses on solving the Traveling Salesman Problem (TSP) using a variety of exact, heuristic, and metaheuristic algorithms.
The goal of TSP is to find the shortest possible route that visits each city exactly once and returns to the starting city.
Since TSP is an NP-hard problem, different approaches are implemented and compared in terms of:
•	Solution quality (total distance)
•	Execution time

Project Structure
├── tsp_project.ipynb        # Main Jupyter Notebook (implementation & experiments)
├── sample_input.json        # Input data (cities & distances)
└── README.md                # Project documentation
________________________________________
Input Format
The input data is provided in a JSON file with the following structure:
{
  "cities": ["A", "B", "C", "D"],
  "distances": [
    ["A", "B", 10],
    ["B", "C", 15],
    ["C", "D", 20],
    ["D", "A", 25],
    ["A", "C", 30],
    ["B", "D", 35]
  ]
}
•	cities: List of city names
•	distances: Each entry represents the distance between two cities
Distances are stored internally using a dictionary for O(1) access.

Implemented Algorithms
Exact Algorithms (Optimal Solution Guaranteed)
1.	Backtracking
o	Explores all possible permutations of cities.
o	Uses pruning to cut branches with higher partial cost.
o	Guarantees optimal solution.
o	Time complexity grows factorially.
2.	Forward Checking
o	Models TSP as a constraint satisfaction problem (CSP).
o	Reduces future domains after each assignment.
o	Detects dead-ends early.
3.	MVC (Minimum Value Constraint)
o	A heuristic-enhanced backtracking approach.
o	Prioritizes cities with fewer valid connections.
4.	MRV (Minimum Remaining Values)
o	Chooses the next city based on the most constrained option.
o	Improves pruning efficiency.

Heuristic & Metaheuristic Algorithms
5.	Hill Climbing
o	Starts from a random solution.
o	Iteratively improves by swapping cities.
o	Fast but can get stuck in local optima.
6.	Simulated Annealing
o	Extension of Hill Climbing.
o	Allows acceptance of worse solutions with a probability.
o	Uses temperature cooling to escape local optima.
7.	Genetic Algorithm
o	Population-based search method.
o	Uses:
	Tournament selection
	Ordered crossover (OX)
	Swap mutation
o	Balances exploration and exploitation.
8.	Genetic Algorithm (Dynamic Version)
o	Adaptive mutation rate based on stagnation.
o	Similarity penalty to preserve population diversity.
o	More robust against premature convergence.

Evaluation Metrics
Each algorithm is evaluated using:
•	Total Distance: Length of the final tour (lower is better)
•	Execution Time: Runtime in seconds (lower is faster)
For stochastic algorithms, multiple runs are performed and the best result is reported.

Visualizations
The project generates the following plots:
1.	Route Distance Comparison
o	Compares solution quality across algorithms.
2.	Runtime Comparison (Linear Scale)
o	Highlights performance differences.
3.	Runtime Comparison (Log Scale)
o	Useful when time differences span multiple orders of magnitude.

How to Run
1.	Make sure you have Python 3 installed.
2.	Install required libraries:
3.	pip install matplotlib
4.	Open the notebook:
5.	jupyter notebook tsp_project.ipynb
6.	Run all cells sequentially.

Notes & Observations
•	Exact algorithms guarantee optimal solutions but do not scale well.
•	Heuristic methods provide near-optimal solutions with significantly lower runtime.
•	The Dynamic Genetic Algorithm achieves a good balance between solution quality and convergence speed.

Future Improvements
•	Implement local search optimizations (2-opt, 3-opt).
•	Automatic hyperparameter tuning.
•	Test scalability with larger datasets.
•	Parallel execution for population-based algorithms.
Author
•	Name: Melika 
•	Course: Artificial Intelligence
•	Project: TSP – Search & Optimization Algorithms

