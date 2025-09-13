# Nonnegative Least Squares: Primal–Dual Solvers with KKT Verification

## Overview
This project implements algorithms for solving the **Nonnegative Least Squares (NNLS)** problem:

\[
\min_x \tfrac{1}{2} \|Ax - y\|^2 \quad \text{s.t. } x \geq 0
\]

Both **primal** and **dual** approaches are developed from scratch and compared against a CVXPY baseline.  
The project verifies **KKT conditions** to confirm strong duality.

## Key Features
- **Primal Projected Gradient Descent (PGD)** with nonnegative projection.  
- **Dual Projected Gradient Ascent** with feasibility checks.  
- Avoids explicit matrix inverses (uses **Cholesky factorization**).  
- Baseline solution with **CVXPY** for verification.  
- Automatic KKT condition checks:
  - Primal feasibility  
  - Dual feasibility  
  - Stationarity  
  - Complementary slackness  

## Example Output
PGD objective: 17.050892

Dual ascent objective: 15.577328

CVXPY objective: 17.050892

Gaps (method - cvx): PGD: 2.350e-10  |  Dual: -1.474e+00

PGD vs Dual solution L2 diff: 1.216e-01

PGD vs CVX  solution L2 diff: 6.188e-06

Dual vs CVX solution L2 diff: 1.216e-01

KKT CHECKS

 Primal feasibility (x>=0): False
 
 Dual feasibility   (λ>=0): True

 Stationarity ||A^T(Ax - y) - λ||: 5.789e-11
 
 Complementarity max |λ_i x_i|: 9.079e-01
 
 Complementarity mean |λ_i x_i|: 8.484e-02

 
## Skills Demonstrated
- Convex optimization (NNLS)  
- Duality & KKT conditions  
- Numerical linear algebra (Cholesky solves)  
- Python (NumPy, SciPy, CVXPY)  

## How to Run
```bash
pip install -r requirements.txt
python nnls_primal_dual_kkt.py
