# Traveling Salesman Problem (TSP) – AI Project

**Course:** Artificial Intelligence  
**Author:** Melika  
**Date:** February 2026

## Project Overview

This project implements and compares multiple algorithms to solve the **Traveling Salesman Problem (TSP)**: finding the shortest possible route that visits each city exactly once and returns to the starting city.

TSP is a classic **NP-hard** problem, so we explore:

- **Exact** methods (guarantee optimal solution, but scale poorly)
- **Heuristic** and **metaheuristic** methods (fast, good-quality approximate solutions)

Algorithms are evaluated based on:

- **Solution quality** (total tour distance – lower is better)
- **Execution time** (seconds – lower is better)


## Input Format (JSON)

```json
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
```

cities: list of city names
distances: list of [city1, city2, distance] triples
→ converted to a symmetric distance dictionary for O(1) lookups

Implemented Algorithms
Exact Algorithms (Optimal but exponential time)

Backtracking
Full permutation exploration with cost-based pruning

Forward Checking
Constraint Satisfaction Problem (CSP) style
Domain reduction after each assignment

MRV (Minimum Remaining Values)
Variable ordering: choose most constrained city next

MVC (Most Constrained Value)
Value ordering heuristic combined with backtracking


##Heuristic & Metaheuristic Algorithms (Approximate & much faster)

Hill Climbing
Simple 2-city swap neighborhood
Greedy local search

Simulated Annealing
Probabilistic acceptance of worse moves
Exponential cooling schedule

Genetic Algorithm (Standard)
Representation: permutation of cities
Selection: Tournament
Crossover: Ordered Crossover (OX)
Mutation: Swap two cities

Genetic Algorithm (Dynamic/Adaptive)
Adaptive mutation rate (increases during stagnation)
Similarity penalty to maintain diversity
Helps avoid premature convergence


Evaluation & Visualization
Each method is run and compared on:

Best tour length
Runtime (s)

For stochastic algorithms → multiple runs → best result reported
Plots generated (using matplotlib):

Bar chart: Tour Distance Comparison
Bar chart: Runtime (linear scale)
Bar chart: Runtime (log scale)

##How to Run

Install dependencies (if needed):Bashpip install jupyter matplotlib
Start Jupyter Notebook:Bashjupyter notebook tsp_project.ipynb
Run all cells in order.

##Key Observations

Exact methods → only practical for very small instances (≈ 10–12 cities)
Metaheuristics → near-optimal solutions in seconds even for 20–50 cities
Dynamic Genetic Algorithm usually offers the best quality–speed trade-off

##Future Work Ideas

Local search improvements: 2-opt, 3-opt, Lin–Kernighan heuristic
Automatic hyperparameter optimization (e.g. grid search, Bayesian opt)
Larger benchmark instances (TSPLIB format)
Parallelization (especially for population-based methods)
Comparison with more modern methods (Ant Colony Optimization, etc.)
