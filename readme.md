# 🧊 Simulated Annealing for the Multidimensional Knapsack Problem

This project implements an enhanced **Simulated Annealing** algorithm to solve the **multidimensional multi-knapsack problem**. The goal is to assign items to knapsacks in a way that maximizes total value while respecting capacity constraints.

---

## ⚙️ Main Parameters

- `VALUES`: array of item values  
- `WEIGHTS`: matrix of item weights (items × dimensions)  
- `CONSTRAINTS`: maximum capacities for each knapsack and dimension  
- `max_steps`: maximum number of iterations  
- `temp_init`: initial temperature  
- `temp_decay`: cooling rate  
- `tweak_strength`: percentage of items modified per iteration  

---

## 🧩 Internal Methods

- **`generate_valid_initial_solution()`**  
  Builds a valid starting solution by assigning items based on their value-to-weight ratio.

- **`is_valid(solution)`**  
  Checks whether a solution respects all knapsack capacity constraints.

- **`total_value(solution)`**  
  Computes the total value of all items assigned to knapsacks.

- **`cost(solution)`**  
  Returns the solution's value, applying a proportional penalty for constraint violations.

- **`tweak(solution)`**  
  Modifies the solution by moving items between knapsacks only if the move remains valid.

---

## 🚀 Results Achieved

| Test Case | Items | Knapsacks | Dimensions | Iterations | Final Value |
|-----------|-------|-----------|------------|------------|-------------|
| TC1       | 10    | 3         | 2          | 10,000     | **1065**     |
| TC2       | 100   | 10        | 10         | 2,000      | **47,412**   |
| TC3       | 5000  | 100       | 100        | 3,000      | **1,809,461**|

---

## 📌 Notes

- The algorithm accepts worse solutions with a probability that decreases over time (simulated cooling).
- Proportional penalties allow exploration of partially valid solutions.
- The smart tweak function avoids invalid moves and guides the search toward feasible, high-value configurations.

