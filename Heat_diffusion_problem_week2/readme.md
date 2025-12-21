# 2D Heat Diffusion Solver (Finite Difference Method)

## Overview
This project implements a **2D transient heat diffusion solver** using the **Finite Difference Method (FDM)**.  
It numerically solves the heat equation on a Cartesian grid and visualizes temperature evolution over time.

This project demonstrates fundamental concepts used in:
- Computational Heat Transfer
- CFD (Computational Fluid Dynamics)
- Numerical Methods for PDEs
- Scientific Computing in Mechanical Engineering

---

##  Governing Equation
The 2D transient heat conduction equation is:

∂T/∂t = α ( ∂²T/∂x² + ∂²T/∂y² )

Where:
- T(x, y, t) = temperature
- α = thermal diffusivity

---

## Numerical Method

### Spatial Discretization
- Second-order **central difference scheme**
- Uniform Cartesian grid in both x and y directions

### Time Integration
- **Explicit Forward Euler method**

Discrete form of the governing equation:

T(i,j)ⁿ⁺¹ = T(i,j)ⁿ  
+ α Δt [ (T(i+1,j)ⁿ − 2T(i,j)ⁿ + T(i−1,j)ⁿ) / Δx²  
+ (T(i,j+1)ⁿ − 2T(i,j)ⁿ + T(i,j−1)ⁿ) / Δy² ]

---
 Stability Condition
For numerical stability of the explicit scheme, the time step must satisfy:

Δt ≤ 1 / ( 2α ( 1/Δx² + 1/Δy² ) )

The solver automatically checks this condition and raises an error if it is violated.

---

## Boundary Conditions
The following boundary conditions are implemented:

- **Dirichlet Boundary Condition**
  - Fixed temperature on the top and bottom boundaries

- **Neumann Boundary Condition**
  - Zero heat flux (zero temperature gradient) on the left and right boundaries

Boundary conditions are modular and can be easily modified or extended.

---

##  Initial Condition
- Entire domain initialized to zero temperature
- Central square region initialized to a higher temperature to initiate heat diffusion

---


---

##  Dependencies
- Python 3.9+
- NumPy
- SciPy
- Matplotlib

Install dependencies using:
```bash
pip install numpy scipy matplotlib


