# Optimal Production Planning Using Linear Programming

## Overview
This project demonstrates the application of **Linear Programming (LP)** to optimize production quantities for three products (A, B, and C) under resource constraints. The goal is to maximize profit while considering limitations on glass, labor, and machine time, along with a pre-order requirement for Product C. The solution was implemented using **Excel Solver**.

## Problem Description
A manufacturer produces three products with the following profit contributions and resource requirements:

### Products and Profits:
- Product A: \$9/unit
- Product B: \$13/unit
- Product C: \$17/unit

### Resource Constraints:
| Resource       | Product A | Product B | Product C | Total Available |
|----------------|-----------|-----------|-----------|-----------------|
| Glass (kg)     | 0.25      | 0.35      | 0.50      | 120            |
| Labour (hrs)   | 0.25      | 0.35      | 0.60      | 48             |
| Machine (hrs)  | 0.20      | 0.30      | 0.40      | 130            |

### Additional Constraint:
- Product C must have at least 45 units produced (pre-order requirement).

## Mathematical Formulation
### Decision Variables:
A: Units of Product A to produce  
B: Units of Product B to produce  
C: Units of Product C to produce  

### Objective Function:
Maximize:  
Profit = 9A + 13B + 17C


### Constraints:

- Glass: 0.25A + 0.35B + 0.5C <= 120
- Labour: 0.25A + 0.35B + 0.6C <= 48
- Machine: 0.2A + 0.3B + 0.4C <= 130
- Pre-Order: C >= 45
- Non-negativity: A, B, C >= 0


## Solution Method
- Tool used: **Excel Solver** with the **Simplex LP** method.
- Steps included:
  - Defining decision variables.
  - Setting up the objective function.
  - Adding constraints.
  - Generating Answer and Sensitivity reports.

## Results
### Optimal Production Plan:
- Product A: 0 units  
- Product B: 60 units  
- Product C: 45 units  

### Maximum Profit:
\$1,545

### Resource Utilization:
- Glass: 43.5 kg (used) / 120 kg (available)  
- Labour: 48 hrs (fully utilized)  
- Machine: 36 hrs (used) / 130 hrs (available)  

## Sensitivity Analysis Insights
### Reduced Costs:
- Product A: -\$0.2857 (not profitable to produce)
- Products B and C: \$0 (already in optimal solution)

### Shadow Prices:
- Labour: \$37.143 (most valuable resource per additional unit)

### Range of Optimality:
- Product A: Profit coefficient ≤ \$9.2857
- Product B: Profit coefficient ≥ \$12.60
- Product C: Profit coefficient ≤ \$22.286

### Range of Feasibility:
- Labour: between 27 and 127.5 hours

## Key Takeaways
- Labour is the **binding constraint**.
- Product A is not produced due to lower profit per labour hour.
- Increasing labour capacity within feasible range can increase profit by \$37.143 per additional hour.
- Overtime labour at \$40/hour is not cost-effective.

## Conclusion
Linear Programming via Excel Solver provides a powerful and accessible method for optimizing production planning under constraints. The recommended production plan maximizes profit while efficiently utilizing available resources.

## Appendix
### Enabling Solver in Excel:
1. Go to `File > Options > Add-ins`
2. Under `Manage`, select `Excel Add-ins` → `Go`
3. Check `Solver Add-in` → `OK`

---

**Author**: roslan.amin@gmail.com  
**Date**: September 2025
