# Numerical Analysis of Film Cooling Effectiveness in High-Pressure Turbines

## Overview
This repository presents a numerical investigation of **active film cooling** for thermal protection of high-pressure turbine components. The study combines a **custom Python-based thermodynamic solver** with **high-fidelity CFD simulations (ANSYS Fluent)** to evaluate coolant requirements under extreme operating conditions.

The primary goal is to determine the **maximum allowable coolant-to-mainstream mass flow ratio** required to ensure turbine wall temperatures remain below a critical structural limit.

---

##  Executive Summary
- A **2D computational framework** was developed to simulate the interaction between:
  - High-temperature mainstream flow  
    - Stagnation temperature: **T₀₁ = 1500 K**
  - Discrete coolant jet injection  
- The study evaluates the **thermal effectiveness of film cooling** using:
  - Iterative thermodynamic property calculations
  - CFD-based flow and heat transfer analysis  
- The key objective was to determine the inlet mass flow ratio **(ṁ₂ / ṁ₁)** required to maintain the turbine wall temperature below **1200 K**.

---

##  Technical Specifications

### Mainstream Flow Conditions
- Total Pressure: **P₀₁ = 500 kPa**
- Total Temperature: **T₀₁ = 1500 K**
- Mach Number: **M = 0.25**

### Coolant Injection Geometry
- Single cooling hole
- Inclination angle: **θ = 30°**

### Fluid and Material Modeling
- Working fluid: **Air (real gas)**
- Temperature-dependent specific heat:

  Cp = 1.05 − 0.365ξ + 0.85ξ² − 0.39ξ³  (kJ/kg·K)

  where:

  ξ = T / 1000

- Molecular weight: **28.8 kg/kmol**

---

## Computational Methodology

### A. Python-Based Iterative Solver
A custom Python code was developed to iteratively resolve thermodynamic properties:

- **Algorithm Workflow**
  1. Assume initial specific heat ratio (γ)
  2. Compute stagnation properties
  3. Update Cp(T) using polynomial correlation
  4. Recalculate γ
  5. Iterate until convergence (Δγ < 0.01)

- **Mass Flow Estimation**
  - Area-based mass flow ratios computed to achieve required cooling effectiveness
  - Coupled with wall temperature constraints

---

### B. CFD Simulation (ANSYS Fluent)

- **Governing Equations**
  - Continuity
  - Navier–Stokes (Momentum)
  - Energy equation

- **Turbulence Modeling**
  - Reynolds-Averaged Navier–Stokes (RANS)
  - Suitable for boundary-layer-dominated turbine flows

- **Boundary Conditions**
  - **Inlet:** Total pressure and total temperature
  - **Blade Surface:** No-slip, adiabatic wall
  - **Outlet:** Pressure outlet

---

##  Key Results

- **Required Coolant Mass Flow Ratio**

  **ṁ₂ / ṁ₁ = 0.235**

  This ratio is sufficient to maintain wall temperature at **1200 K**.

- **Model Validation**
  - Python iterative solver predicts: **γ ≈ 1.007**
  - Results show strong agreement with ANSYS Fluent CFD simulations

---

##  Authors
- **Gokul Govind TK**


**Affiliation:**  
Indian Institute of Technology

---

## 📁 Repository Structure (Suggested)

