# Optimal Production Planning Using Linear Programming

An Application using LP to Maximize Profit Under Resource Constraints

**Date:** September 2025

## Overview

This report demonstrates the use of linear programming (LP) to optimize production quantities for three products (A, B, and C) in a resource-constrained manufacturing environment. Using Excel Solver, the problem is modeled with the objective of maximizing profit while considering constraints on glass, labor, and machine time. The optimal solution suggests producing 0 units of Product A, 60 units of Product B, and 45 units of Product C, achieving a maximum profit of $1,545 while fully utilizing available labor hours. This analysis highlights the importance of mathematical optimization in decision-making and how LP can enhance profitability in real-world production scenarios.

## Purpose and Background

The report aims to:
- Illustrate the application of LP in production planning.
- Demonstrate how Excel Solver, a widely available tool, can solve real-world optimization problems.
- Provide insights into resource allocation, constraint management, and profit maximization.
- Use sensitivity analysis to assess the impact of parameter changes on the optimal solution.

**Context:** A manufacturer produces Products A, B, and C, each with different profit contributions ($9, $13, $17 per unit) and varying resource requirements (glass in kg, labor in hours, machine time in hours). Resource limits include:
- Glass: 120 kg
- Labor: 48 hours
- Machine: 130 hours
- Pre-order: At least 45 units of Product C

**Resource Requirements per Unit:**

| Resource      | Product A | Product B | Product C | Total Available |
|---------------|-----------|-----------|-----------|-----------------|
| Glass (kg)    | 0.25      | 0.35      | 0.50      | 120             |
| Labor (hrs)   | 0.25      | 0.35      | 0.60      | 48              |
| Machine (hrs) | 0.20      | 0.30      | 0.40      | 130             |

## Problem Formulation

- **Decision Variables:**
  - A = units of Product A
  - B = units of Product B
  - C = units of Product C

- **Objective Function:** Maximize Profit = 9A + 13B + 17C

- **Constraints:**
  - Glass: 0.25A + 0.35B + 0.5C ≤ 120
  - Labor: 0.25A + 0.35B + 0.6C ≤ 48
  - Machine: 0.2A + 0.3B + 0.4C ≤ 130
  - Pre-order: C ≥ 45
  - Non-negativity: A, B, C ≥ 0

## Solution Method

The problem is solved using Excel Solver with the Simplex LP method. The process involves:
1. Setting up the model in Excel with decision variables, objective, and constraints.
2. Configuring Solver: Select the profit cell as the objective, set to maximize, specify variable cells (A, B, C), add constraints, uncheck non-negative option (handled via constraints), and choose Simplex LP.
3. Running Solver and generating Answer and Sensitivity reports.

## Results

- **Optimal Solution:** A = 0 units, B = 60 units, C = 45 units
- **Maximum Profit:** $1,545
- **Resource Utilization:**
  - Glass: 43.5 kg used (≤ 120 kg)
  - Labor: 48 hours used (binding constraint)
  - Machine: 36 hours used (≤ 130 hours)
  - Pre-order: 45 units of Product C fulfilled

## Sensitivity Analysis

- **Range of Optimality** (profit coefficients maintaining optimal solution):
  - A: ≤ 9 + 0.286
  - B: ≥ 13 - 0.4
  - C: ≤ 17 + 5.286
- **Range of Feasibility** (resource changes without altering solution):
  - Glass: ≥ 120 - 76.5
  - Labor: 27 ≤ hours ≤ 127.5 (originally 48)
  - Machine: ≥ 130 - 94
- **Reduced Costs** (improvement needed for non-optimal variables):
  - A: -0.2857 (producing A reduces profit by this amount per unit)
  - B and C: 0 (already optimal)
- **Shadow Prices** (value of one extra unit of resource):
  - Labor: $37.143 (key bottleneck)
  - Others: 0 (slack resources)

## Discussion

- **Labor Constraint:** Labor hours are fully utilized, making them the limiting factor. Increasing labor within the feasible range (e.g., to 50 hours) boosts profit by $74.286 ($37.143 × 2). However, overtime at $40/hour is not cost-effective compared to the shadow price of $37.143.
- **Product A:** Not produced due to lower profit per labor hour compared to B. Forcing 1 unit of A reduces profit to $1,544.714. To make A viable, increase its profit to ≥$9.286 or reduce its labor requirement to ≤0.242 hours/unit.
- **Resource Slack:** Glass and machine resources remain underutilized.

## Conclusion

LP via Excel Solver provides an actionable solution to maximize profit ($1,545) by producing 0 units of A, 60 units of B, and 45 units of C, with labor as the binding constraint. Sensitivity analysis enhances decision-making under uncertainty.

## Appendix

Instructions to enable Solver in Excel if not visible:
- Go to File > Options > Add-ins
- Under Manage, select Excel Add-ins and click Go
- Check Solver Add-in and click OK
