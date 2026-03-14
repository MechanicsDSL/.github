<p align="center">
  <img src="https://raw.githubusercontent.com/MechanicsDSL/mechanicsdsl/main/docs/images/logo.png" alt="MechanicsDSL Logo" width="420">
</p>

<h1 align="center">MechanicsDSL</h1>

<p align="center">
  <em>A compiler-based framework for computational physics — describe it once, simulate it anywhere.</em>
</p>

<p align="center">
  <a href="https://github.com/MechanicsDSL/mechanicsdsl"><img src="https://github.com/MechanicsDSL/mechanicsdsl/actions/workflows/python-app.yml/badge.svg" alt="CI"></a>
  <a href="https://pepy.tech/projects/mechanicsdsl-core"><img src="https://static.pepy.tech/personalized-badge/mechanicsdsl-core?period=total&units=INTERNATIONAL_SYSTEM&left_color=GRAY&right_color=BLUE&left_text=Downloads" alt="PyPI Downloads"></a>
  <img src="https://img.shields.io/badge/python-3.9%2B-blue" alt="Python 3.9+">
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License"></a>
  <a href="https://doi.org/10.5281/zenodo.17771040"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.17771040.svg" alt="DOI"></a>
  <a href="https://mechanicsdsl.readthedocs.io/en/latest/?badge=latest"><img src="https://readthedocs.org/projects/mechanicsdsl/badge/?version=latest" alt="Docs"></a>
  <a href="https://mybinder.org/v2/gh/MechanicsDSL/mechanicsdsl-notebooks/main"><img src="https://mybinder.org/badge_logo.svg" alt="Binder"></a>
</p>

---

## What Is MechanicsDSL?

MechanicsDSL is an open-source computational physics organization building a full compiler toolchain for physical simulation. Our flagship package lets researchers, engineers, and educators define physical systems in natural, LaTeX-inspired notation — and automatically derives equations of motion, handles constraints, identifies conservation laws, and generates high-performance simulation code for 12+ target platforms.

We are not a wrapper around existing tools. We are a **compiler**. The user writes physics; we write the code.

```
\system{double_pendulum}
\parameter{m}{1.0}{kg}
\parameter{l}{1.0}{m}
\lagrangian{
    0.5*m*l^2*(\dot{theta1}^2 + \dot{theta2}^2 + 2*\dot{theta1}*\dot{theta2}*cos(theta1-theta2))
    - m*g*l*(2*cos(theta1) + cos(theta2))
}
\initial{theta1: 1.0, theta2: 0.5}
\target{python_jax}
\solve{t_span: [0, 30], dt: 0.005}
```

That's it. The compiler handles symbolic derivation, conservation law detection, GPU-accelerated integration, and phase space visualization.

---

## Organization Repositories

### Core

| Repository | Description | Status |
|------------|-------------|--------|
| [**mechanicsdsl**](https://github.com/MechanicsDSL/mechanicsdsl) | Core DSL compiler, symbolic engine, 8 physics domains, 17+ classical mechanics modules, 12+ code generation backends, JAX/GPU support, LSP server, Jupyter magic commands, FastAPI server | `v2.0 stable` |

### Deployment & Integration

| Repository | Description | Status |
|------------|-------------|--------|
| [**mechanicsdsl-embedded**](https://github.com/MechanicsDSL/mechanicsdsl-embedded) | Embedded and edge deployment for Arduino, Raspberry Pi, and ARM platforms. Arduino and RPi pendulum/double pendulum examples, ARM cross-compilation via Docker, POSIX real-time scheduling, IMU integration, serial monitor tooling. | `active` |
| [**mechanicsdsl-ros2**](https://github.com/MechanicsDSL/mechanicsdsl-ros2) | Dedicated ROS2 integration layer. Complete `mechanicsdsl_pendulum` package with generated C++ nodes, custom messages (`PendulumState`, `SystemState`), launch files, parameter configs, GTest physics tests, and ROS2 integration tests. | `active` |
| [**mechanicsdsl-unity**](https://github.com/MechanicsDSL/mechanicsdsl-unity) | Unity and Unreal Engine plugin packages. `PendulumComponent`, `DoublePendulumComponent`, `CoupledPendulumsComponent` MonoBehaviours; `ConservationMonitor`, `PhaseSpaceTrail`, `MechanicsDSLMath` utilities; custom Inspectors; UPM manifest; runtime test suite. | `active` |

### Data & Education

| Repository | Description | Status |
|------------|-------------|--------|
| [**mechanicsdsl-notebooks**](https://github.com/MechanicsDSL/mechanicsdsl-notebooks) | Curated Jupyter notebooks spanning all eight MechanicsDSL physics domains. Currently: double pendulum (chaos, Lyapunov), coupled oscillators (normal modes, beating), constraints (Baumgarte), central forces (Kepler), Hamiltonian mechanics (phase space, symplectic integration). Binder-launchable. | `active` |
| [**mechanicsdsl-datasets**](https://github.com/MechanicsDSL/mechanicsdsl-datasets) | Reference datasets for physics parameter estimation and inverse problem benchmarking. Currently: `pendulum_synthetic`, `double_pendulum_synthetic`, `coupled_oscillators_synthetic` — each with CSV, HDF5, metadata, and estimation/validation scripts. | `active` |

---

## Adoption

Since release on PyPI, MechanicsDSL has accumulated **8,300+ downloads across 54 countries**, with institutional mirrors (bandersnatch, Nexus, devpi) confirmed in multiple national research computing environments. The package is published with a formal Zenodo DOI ([10.5281/zenodo.17771040](https://doi.org/10.5281/zenodo.17771040)) and is the subject of ongoing peer-reviewed research:

> Parsons, N. *Decoupling Programming from Physics: A Compiler-Based Approach to Teaching Lagrangian Mechanics.* Under review at **American Journal of Physics** (submitted January 2026).

> Parsons, N. *MechanicsDSL: A Compiler-Based Domain-Specific Language for Automated Physics Simulation in Python.* In preparation, **PEARC26 RSE Track** (deadline March 30, 2026).

---

## Quick Start

```bash
pip install mechanicsdsl-core          # core compiler
pip install mechanicsdsl-core[jax]     # + GPU acceleration
pip install mechanicsdsl-datasets      # physics datasets
pip install mechanicsdsl-core[all]     # everything
```

**Docker:**
```bash
docker pull ghcr.io/mechanicsdsl/mechanicsdsl:latest
docker run -it ghcr.io/mechanicsdsl/mechanicsdsl:latest
```

Full documentation: **[mechanicsdsl.readthedocs.io](https://mechanicsdsl.readthedocs.io)**

---

## Research & Citation

```bibtex
@software{mechanicsdsl2026,
  author  = {Parsons, Noah},
  title   = {{MechanicsDSL}: A Domain-Specific Language for Computational Physics Simulation},
  year    = {2026},
  doi     = {10.5281/zenodo.17771040},
  url     = {https://github.com/MechanicsDSL/mechanicsdsl},
  license = {MIT}
}
```

---

## License

All MechanicsDSL repositories are released under the **MIT License** unless otherwise noted.

---

<p align="center">
  <em>Built for physicists, engineers, and curious minds.</em><br>
  <a href="https://mechanicsdsl.readthedocs.io">Docs</a> ·
  <a href="https://github.com/MechanicsDSL/mechanicsdsl">Core Repo</a> ·
  <a href="https://doi.org/10.5281/zenodo.17771040">Zenodo</a> ·
  <a href="https://pypi.org/project/mechanicsdsl-core/">PyPI</a> ·
  <a href="https://pypi.org/project/mechanicsdsl-datasets/">Datasets on PyPI</a>
</p>
