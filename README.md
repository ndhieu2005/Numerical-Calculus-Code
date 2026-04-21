# Numerical Calculus Code

A structured collection of Jupyter notebooks implementing core numerical analysis algorithms, developed as coursework for **Giải Tích Số** (Numerical Analysis) — a university-level mathematics course. Covers root-finding methods, fixed-point iteration, and direct/iterative solvers for linear systems.

---

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Setup](#setup)
- [Project Structure](#project-structure)
- [Weekly Module Breakdown](#weekly-module-breakdown)
- [Algorithm Reference](#algorithm-reference)
- [Usage Examples](#usage-examples)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)

---

## Overview

| Property       | Details                                         |
|----------------|-------------------------------------------------|
| Language       | Python 3.10+                                    |
| Format         | Jupyter Notebooks (`.ipynb`)                    |
| Core Libraries | `numpy`, `matplotlib`, `math`                   |
| Domain         | Numerical Analysis / Scientific Computing       |
| Topics         | Root-finding, Fixed-point iteration, Linear system solvers |

Each notebook follows a consistent structure:

1. **Mathematical formulation** — LaTeX-rendered theory and convergence conditions
2. **Algorithm pseudocode** — written in markdown before implementation
3. **Python implementation** — clean, readable code cells
4. **Iteration tables** — showing `k`, `xₖ`, `xₖ₊₁`, `f(xₖ₊₁)`, and error at each step
5. **Verification** — solutions substituted back to confirm correctness
6. **Visualizations** — matplotlib plots for function graphs and root annotations

---

## Prerequisites

| Requirement      | Minimum version |
|------------------|-----------------|
| Python           | 3.10            |
| Jupyter Notebook / JupyterLab | any recent |
| numpy            | 1.24            |
| matplotlib       | 3.7             |

No deep mathematical background is required to *run* the notebooks — all theory is explained inline. Familiarity with single-variable calculus and basic linear algebra is helpful to fully understand the algorithms.

---

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/Numerical-Calculus-Code.git
cd Numerical-Calculus-Code
```

### 2. Create and activate a virtual environment

```bash
# Create
python -m venv .venv

# Activate — Linux / macOS
source .venv/bin/activate

# Activate — Windows (PowerShell)
.venv\Scripts\Activate.ps1

# Activate — Windows (CMD)
.venv\Scripts\activate.bat
```

### 3. Install dependencies

```bash
pip install numpy matplotlib jupyterlab
```

> **Tip:** A `requirements.txt` is planned — see [Contributing](#contributing) if you would like to add one.

### 4. Launch Jupyter

```bash
jupyter lab
```

Open any `WeekN.ipynb` file from the sidebar and run all cells with **Kernel → Restart & Run All**.

---

## Project Structure

```
Numerical-Calculus-Code/
├── Week2.ipynb          # Bisection method, Taylor series for e
├── Week3.ipynb          # Chord method, Newton's method, computing π and e
├── Week4.ipynb          # Practical root-finding: negative roots, relative error
├── Week5.ipynb          # Simple iteration / fixed-point method
├── Week6.ipynb          # Fixed-point for harder equations, physical applications
├── Week7.ipynb          # Nonlinear systems + linear system solvers
├── Baitap GTS full 15 tuần.pdf          # Full problem set (Vietnamese)
└── giai-tich-so-pham-ky-anh_compress.pdf  # Course textbook (Vietnamese)
```

The notebooks are numbered by course week and are designed to be read in order, as each week builds on the previous.

---

## Weekly Module Breakdown

### Week 2 — Bisection Method

**Algorithms:** Bisection (binary search for roots), Taylor series approximation of *e*

**Problems solved:**
- `eˣ − cos(2x) = 0` → root ≈ −0.4322
- `x⁵ − 3x³ + 2x² − x + 5 = 0` → root ≈ −2.1548

**Key function signature:**
```python
def bisection(f, a, b, epsilon):
    """
    f       : callable, the function whose root we seek
    a, b    : float, bracketing interval where f(a)*f(b) < 0
    epsilon : float, convergence tolerance
    Returns : (root, iteration_count, convergence_table)
    """
```

**Convergence guarantee:** Always converges for a continuous function with a sign change on `[a, b]`.
Error after *n* iterations: `|xₙ − x*| ≤ (b − a) / 2ⁿ`

---

### Week 3 — Chord Method & Newton's Method

**Algorithms:** Chord method (secant-like), Newton's method (tangent line), Nth-root computation

**Problems solved:**
- Compute *e* via `f(x) = ln(x) − 1`  →  *e* ≈ 2.7182818338 (chord, 9 iter) / 2.7182818285 (Newton, 4 iter)
- Compute *π* via `f(x) = tan(x/4) − 1`  →  π ≈ 3.1415926 (Newton, 5 iter)
- Cube root: ∛17 ≈ 2.5712815907

**Chord method update rule:**
```
xₙ₊₁ = xₙ − f(xₙ) · (xₙ − d) / (f(xₙ) − f(d))
```
where `d` is a fixed endpoint of the bracketing interval.

**Newton's method update rule:**
```
xₙ₊₁ = xₙ − f(xₙ) / f′(xₙ)
```
Quadratic convergence near the root when `f′(x*)  ≠ 0`.

---

### Week 4 — Applied Root-Finding

**Focus:** Handling negative roots, applying relative error stopping criteria, multi-equation practice

**Target accuracy:** relative error ≤ 0.05% (`δ = 5 × 10⁻⁴`)

**Problems solved:**
- Smallest negative root of `eˣ − cos(2x) = 0`  →  x ≈ −0.432219611385
- `x⁵ − 3x³ + 2x² − x + 5 = 0`  →  x ≈ −2.154820141192
- Graphical isolation of roots for `2ˣ − 5x + sin(x) = 0` and `e⁻ˣ − x = 0`

---

### Week 5 — Simple Iteration (Fixed-Point Method)

**Algorithm:** Fixed-point iteration `xₙ₊₁ = φ(xₙ)`

**Convergence condition:** `|φ′(x)| ≤ q < 1` for all `x` in the working interval

**A posteriori error bound:**
```
|xₙ − x*| ≤ q/(1 − q) · |xₙ − xₙ₋₁|
```

**Problem solved:**
- `x³ + 3x² − 1 = 0`, transformed to `φ(x) = 1/(x² + 3)`, q = 0.2
- Result: x ≈ 0.3221853556 (7 iterations, 8 significant digits)

---

### Week 6 — Fixed-Point for Harder Equations & Physical Applications

**Algorithms:** Fixed-point iteration (Newton-form transformation), bisection applied to physical model

**Problems solved:**
1. `x² + 4sin(x) − 1 = 0`  →  x ≈ −2.1068670794 (q = 0.3, 5 iter)
2. `eˣ − 10x + 7 = 0`  →  x ≈ 0.9615835502 (q = 0.5, 4 iter)
3. **Archimedes' principle** — sphere equilibrium depth:
   - Sphere radius r = 1 m, ρ_sphere = 201 kg/m³, ρ_water = 1000 kg/m³
   - Find depth `h` satisfying buoyancy equation using bisection

---

### Week 7 — Nonlinear Systems & Linear System Solvers

This is the most content-rich notebook, covering two major topics.

#### Part A — Nonlinear Systems

**Simple iteration for 2D system:**
```python
x1 = (cos(x2) + 1) / 3
x2 = (sin(x1) + 2) / 4
# Result: [0.60044897, 0.64125317]  (9 iterations, q = 0.5, ε = 1e-6)
```

**Newton's method for nonlinear systems (Jacobian-based):**
```
J_F(xᵏ) · δ = −F(xᵏ)
xᵏ⁺¹ = xᵏ + δ
```
Applied to 2D and 3D systems with 5–6 iterations to `ε = 1e-8`.

#### Part B — Linear System Solvers

| Method                   | Type       | Matrix Requirement         | Iterations |
|--------------------------|------------|----------------------------|------------|
| Gaussian Elimination     | Direct     | General square             | O(n³)      |
| Gauss-Jordan             | Direct     | General square             | O(n³)      |
| LU Decomposition (Doolittle) | Direct | General square             | O(n³)      |
| Cholesky Decomposition   | Direct     | Symmetric positive-definite | O(n³/3)   |

All solvers verified with `‖A·X − B‖∞ < 1e-9`. Test cases include 4×4, 6×6, 7×7, and 8×8 tridiagonal systems.

---

## Algorithm Reference

Quick lookup table for all implemented algorithms:

| Algorithm                       | Week | Category          | Convergence      |
|---------------------------------|------|-------------------|------------------|
| Bisection                       | 2    | Scalar root       | Linear (order 1) |
| Taylor series (constants)       | 2    | Approximation     | —                |
| Chord method                    | 3    | Scalar root       | Superlinear      |
| Newton's method (scalar)        | 3    | Scalar root       | Quadratic        |
| Simple iteration (scalar)       | 5    | Scalar root       | Linear           |
| Simple iteration (vector)       | 6–7  | Nonlinear system  | Linear           |
| Newton's method (systems)       | 7    | Nonlinear system  | Quadratic        |
| Gaussian elimination            | 7    | Linear system     | Direct           |
| Gauss-Jordan elimination        | 7    | Linear system     | Direct           |
| LU decomposition (Doolittle)    | 7    | Linear system     | Direct           |
| Cholesky decomposition          | 7    | Linear system (SPD) | Direct         |

---

## Usage Examples

### Running a bisection root-find

```python
import math

def f(x):
    return math.exp(x) - math.cos(2 * x)

root, n_iter, table = bisection(f, a=-1, b=0, epsilon=1e-8)
print(f"Root: {root:.10f}  ({n_iter} iterations)")
# Root: -0.4322196114  (28 iterations)
```

### Solving a linear system with LU decomposition

```python
import numpy as np

A = np.array([[4, -1, 0, 0],
              [-1, 4, -1, 0],
              [0, -1, 4, -1],
              [0, 0, -1, 4]], dtype=float)
B = np.array([[1], [2], [2], [1]], dtype=float)

X = lu_solve(A, B)   # Doolittle's method from Week7.ipynb
print(X)
```

### Newton's method for a nonlinear system

```python
# Solve: x1² + x2² = 5,  x1 − x2 = 1
def F(x):
    return np.array([x[0]**2 + x[1]**2 - 5,
                     x[0] - x[1] - 1])

def J(x):
    return np.array([[2*x[0], 2*x[1]],
                     [1, -1]])

x = newton_system(F, J, x0=[1.5, 0.5], tol=1e-8)
# x ≈ [2.0, 1.0]
```

---

## Contributing

Contributions are welcome! Here are the highest-priority areas:

### How to contribute

1. **Fork** the repository and create a feature branch:
   ```bash
   git checkout -b feature/your-topic
   ```
2. Follow the existing notebook structure (theory → algorithm → code → table → plot).
3. Verify your solution by substituting back into the original equation.
4. **Open a pull request** with a clear description of what was added or fixed.

### Suggested contributions

- [ ] Add `requirements.txt` (pinned versions of numpy, matplotlib, jupyterlab)
- [ ] **Week 8+:** Numerical integration (Riemann, Trapezoidal, Simpson's rules)
- [ ] **Week 9+:** Numerical differentiation and finite differences
- [ ] **Week 10+:** ODE solvers (Euler, Runge-Kutta)
- [ ] Interpolation methods (Lagrange, Newton divided differences, splines)
- [ ] Refactor repeated utility code (iteration tables, convergence plots) into a shared `utils.py`
- [ ] Add a `requirements.txt` and a `Makefile`/`run_all.sh` script
- [ ] Add English inline comments to all code cells (currently Vietnamese-dominant)
- [ ] CI: GitHub Actions workflow to run all notebooks with `nbconvert --execute`

### Code style

- Use descriptive variable names (`x_k`, `epsilon`, `jacobian` — not `xk`, `eps`, `j`)
- Include units in variable names or comments when working on physical problems
- Print convergence tables using Python f-strings aligned with `{val:>12.10f}`
- Keep each notebook cell focused on one logical step

---

## Acknowledgements

- **Textbook:** *Giải Tích Số* by Phạm Kỳ Anh — the primary reference for all algorithms and problem sets in this repository.
- **Problem set:** *Bài Tập Giải Tích Số* (full 15-week problem sheet), included as PDF for reference.
- Course: Numerical Analysis (Giải Tích Số), Vietnam National University or equivalent institution.

---

*If you find a bug or a better way to implement any of the algorithms here, please open an issue or a pull request — all improvements are appreciated.*
