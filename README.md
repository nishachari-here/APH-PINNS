# Adaptive Hybrid Physics-Informed Neural Networks for Multi-Dimensional Singular Perturbation Problems (APH-PINNs)

## Overview

**APH-PINNs** is an advanced framework designed to tackle optimization challenges and boundary layer "stiff locking" in singularly perturbed time-dependent partial differential equations (PDEs) in 1D and 2D spaces. By integrating asymptotic coordinate stretching, dual-network component decomposition, and adaptive Shishkin-mesh sampling, this approach eliminates spectral bias, captures sharp spatial gradients, and accelerates convergence compared to standard neural PDE solvers.

---

## Key Features

* **Dual-Network Component Decomposition Architecture:** Separates regular and boundary layer components using individual Multi-Layer Perceptrons (MLPs) scaled independently via asymptotic coordinate stretching.
* **Shishkin Mesh Point Initialization:** Enhances spatial point distribution to resolve extremely sharp boundary layers efficiently.
* **Composite PINN Loss Function:** Integrates physics residuals, boundary conditions, and initial conditions into a balanced optimization objective.
* **Error-Based Adaptive Resampling:** Dynamically targets collocation points in regions with high residual errors.
* **L-BFGS Reactivation Loop:** Combines first-order gradient descent with explicit second-order L-BFGS optimization to consistently bypass plateau states.
* **Automated Regime-Based Scaling:** Maintains stability across shifting physical scales in complex multi-parameter problems.

---

## Methodology Pipeline

1. **Asymptotic Scaling & Regime Assessment:** Identifies perturbation parameters and sets up coordinate stretching factors.
2. **Dual-Network Component Decomposition:** Sets up localized left and right boundary layer MLPs.
3. **Mesh Initialization:** Populates domain points using Shishkin mesh generation.
4. **Training & Optimization:** Minimizes the composite loss function using Adam followed by the L-BFGS reactivation loop.
5. **Adaptive Resampling:** Iteratively refines point distribution based on local residual feedback.

---

## Results & Validation

* Successfully eliminates spectral bias and handles stiff locking in singular perturbation problems.
* Outperforms vanilla PINNs in capturing sharp spatial gradients and maintaining multi-regime physical scaling stability across 1D and 2D spatial dimensions.

---

## Future Work

* Extension to higher-dimensional systems and complex irregular geometries.
* Integration of advanced hardware acceleration for real-time PDE simulation.

---

## Citation & Acknowledgments

Based on the internship technical report draft by **Nithyashree S** (R V College of Engineering), conducted under the guidance of **Prof. Dr. E. Natarajan** (Mathematics Division, IIST).
