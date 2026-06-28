# Mars Drone Landing — State Estimation & Control (Python)

Solo Python assignment for the **ES3J1 Advanced Systems and Software Engineering** module at the University of Warwick. Simulates the guided descent and safe landing of a drone on Mars, combining state-space modelling, Kalman filtering, and feedback control.

---

## Overview

The project models a drone descending through the Martian atmosphere (gravity g = 3.7 m/s²) and brings it to a safe landing while avoiding a forbidden region, using only noisy position measurements.

### Q1 — Mathematical Model
Derives the equations of motion from Newton's second law, expressed in state-space form `ẋ = Ax + B(G + u)` with state `x = (qₓ, q_z, pₓ, p_z)` (position and momentum).

### Q2 — Numerical Simulation
Solves the dynamics using an **implicit (backward) Euler scheme** for numerical stability, simulating the uncontrolled free-fall trajectory and detecting ground impact and forbidden-region violations.

### Q3 — Kalman Filter
Implements a **linear Kalman filter** to estimate the full state (including unobservable momentum) from noisy position observations. Demonstrates how the filter corrects an incorrect initial estimate as measurements arrive, with prediction-error bands at ±1 standard deviation.

### Q4 — Feedback Control & Safe Landing
Designs a **proportional–derivative (PD) controller** acting on the Kalman estimate to guide the drone through waypoints, hover, and land below the safe-speed threshold — all while respecting a force limit (‖u‖ ≤ 15 N) and avoiding the forbidden box.

---

## Key Techniques

- State-space dynamical modelling
- Implicit Euler numerical integration
- Kalman filtering / Bayesian state estimation
- PD feedback control with constraint handling (force clipping, waypoint navigation)
- Reproducible results (seeded RNG)

---

## Technologies

- Python — NumPy, Matplotlib
- Jupyter Notebook

---

## How to Run

1. Install dependencies:
   ```bash
   pip install numpy matplotlib jupyter
   ```
2. Launch the notebook:
   ```bash
   jupyter notebook mars_drone_landing.ipynb
   ```
3. Run all cells top to bottom — each question builds on the previous one.

---

## Module Context

**ES3J1 — Advanced Systems and Software Engineering**, University of Warwick, Year 3 (2025–26).
