# Trajectory-Optimization-Engine

[![Language](https://img.shields.io/badge/C++17-%2300599C?style=flat-square&logo=c%2B%2B&logoColor=white)](https://github.com/skytruong90/Trajectory-Optimization-Engine)
[![Domain](https://img.shields.io/badge/Domain-Defense_M%26S-red?style=flat-square)](https://github.com/skytruong90/Trajectory-Optimization-Engine)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Trajectory-Optimization-Engine)

## Project Overview

A C++ trajectory optimization engine for defense ballistic systems — computing optimal flight paths that minimize time-of-flight, maximize range, or minimize fuel consumption under aerodynamic and mission constraints. Implements direct collocation and gradient-based optimization methods used in professional defense M&S environments.

---

## Features

- **Multi-Objective Optimization** — Minimize time-of-flight, fuel consumption, or miss distance simultaneously.
- **Constraint Handling** — Enforces aerodynamic limits, no-fly zones, and terminal guidance constraints.
- **Direct Collocation** — Discretizes trajectory into nodes and solves as a nonlinear programming problem.
- **Gradient-Based Solver** — Implements SLSQP and interior-point methods for fast convergence.
- **6DOF Integration** — Full rigid-body dynamics integration along optimized trajectory.

---

## Technical Background

| Concept | Implementation |
|--------|----------------|
| Optimization Method | Direct collocation / SLSQP |
| Dynamics | 6DOF rigid-body equations of motion |
| Constraints | Aerodynamic limits, terminal conditions |
| Output | Optimal state/control history + trajectory CSV |

---

## Getting Started

```bash
git clone https://github.com/skytruong90/Trajectory-Optimization-Engine.git
cd Trajectory-Optimization-Engine
mkdir build && cd build
cmake ..
make -j4
./traj_opt --config config/mission_params.yaml
```

---

## Future Enhancements

- Pseudospectral methods (Gauss-Lobatto collocation)
- Real-time trajectory reshaping for mid-course guidance
- Multi-vehicle cooperative trajectory planning

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Trajectory-Optimization-Engine)

</div>
