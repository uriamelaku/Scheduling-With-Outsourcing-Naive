# Scheduling With Outsourcing (Naive Solver)

A C++ implementation of a **naive exhaustive search algorithm** for solving a scheduling problem with outsourcing constraints.

This project was developed as part of an academic scheduling optimization project and demonstrates how an exhaustive search approach can find the optimal outsourcing decision under a budget constraint.

---

# Overview

The scheduling problem consists of:

- A set of jobs
- Multiple identical parallel machines
- Processing time for each job
- Weight for each job
- Outsourcing cost for each job
- Maximum outsourcing budget

The objective is to determine:

- Which jobs should be outsourced.
- Which jobs should remain for processing.
- The processing order of the remaining jobs.

while respecting the outsourcing budget and minimizing the scheduling objective.

---

# Features

- Random instance generation
- Exhaustive search over every outsourcing subset (2ⁿ possibilities)
- Budget constraint validation
- WSPT (Weighted Shortest Processing Time) ordering
- Scheduling cost computation
- Prints the optimal outsourcing decision
- Simple Makefile for compilation

---

# Algorithm

For every generated instance:

1. Generate every possible outsourcing subset.
2. Compute the outsourcing cost.
3. Discard subsets that exceed the outsourcing budget.
4. Sort the remaining jobs using the WSPT rule.
5. Compute the scheduling objective.
6. Keep the best feasible solution.

Because every feasible subset is evaluated, the algorithm always returns the optimal solution for the tested instance.

---

# Scheduling Objective

The objective minimized by the algorithm is

Σ wⱼ · Cⱼ

where

- **wⱼ** = job weight
- **Cⱼ** = completion time of job *j*

Only solutions satisfying

Σ uⱼ ≤ U

are considered feasible.

---

# Project Structure

```text
Scheduling-With-Outsourcing-Naive/

├── Common.h
├── Common.cpp
├── OutsourceNaive.h
├── OutsourceNaive.cpp
├── main_naive.cpp
├── Makefile
├── README.md
└── Project_Report.pdf (optional)
```

---

# Build

Compile using Make:

```bash
make
```

or directly with g++:

```bash
g++ *.cpp -o naive
```

---

# Run

```bash
./naive
```

The program automatically:

- Generates a random scheduling instance
- Prints all generated jobs
- Finds the optimal outsourcing decision
- Prints the best scheduling order
- Displays the outsourcing cost
- Displays the scheduling objective value

---

# Example Output

```text
========== Experiment 1 ==========

=== Instance ===

n = 9
m = 3
U = 18

Job    p    w    u
---------------------
J1     4    9    2
J2     8    5    7
...

=== BEST SOLUTION ===

Outsourced R = {J2, J6}

Processed jobs =
J4 -> J8 -> J1 -> J3 -> ...

Outsourcing Cost = 13

Scheduling Cost = 582
```

---

# Technologies

- C++17
- Standard Template Library (STL)
- Vectors
- Sorting
- Exhaustive Search
- Makefile

---

# Complexity

Time Complexity

```text
O(2ⁿ · n log n)
```

Space Complexity

```text
O(n)
```

Since every outsourcing subset is evaluated, this implementation is intended for relatively small instances (approximately n ≤ 10).

---

# Report

For a complete explanation of:

- Mathematical formulation
- Scheduling model
- Algorithm design
- Complexity analysis
- Experimental results

see:

```text
Project_Report.pdf
```

(if included in the repository)

---

# Learning Objectives

This project demonstrates several important algorithmic concepts:

- Exhaustive Search
- Combinatorial Optimization
- Scheduling Algorithms
- Parallel Machine Scheduling
- WSPT Priority Rule
- Constraint Satisfaction
- Time Complexity Analysis

---

# Author

Developed as part of an academic project in Scheduling and Combinatorial Optimization.
