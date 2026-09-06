<p align="center">
  <img src="https://raw.githubusercontent.com/MechanicsDSL/mechanicsdsl/main/docs/images/logo.png" alt="MechanicsDSL Logo" width="420">
</p>

<h1 align="center">MechanicsDSL</h1>

<p align="center">
  <em>A compiler-based framework for computational physics | Describe it once, simulate it anywhere.</em>
</p>

<p align="center">
  <a href="https://github.com/MechanicsDSL/mechanicsdsl"><img src="https://github.com/MechanicsDSL/mechanicsdsl/actions/workflows/python-app.yml/badge.svg" alt="CI"></a>
  <img src="https://img.shields.io/badge/python-3.9%2B-blue" alt="Python 3.9+">
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License"></a>
  <a href="https://doi.org/10.5281/zenodo.17771040"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.17771040.svg" alt="DOI"></a>
  <a href="https://mechanicsdsl.readthedocs.io/en/latest/?badge=latest"><img src="https://readthedocs.org/projects/mechanicsdsl/badge/?version=latest" alt="Docs"></a>
  <a href="https://mybinder.org/v2/gh/MechanicsDSL/mechanicsdsl-notebooks/main"><img src="https://mybinder.org/badge_logo.svg" alt="Binder"></a>
</p>

## What is MechanicsDSL?

MechanicsDSL is a domain-specific language and compiler for physical systems. You write a Lagrangian or Hamiltonian in a LaTeX-inspired syntax; the symbolic engine (built on SymPy) derives the equations of motion automatically, and the compiler generates simulation code in your choice of twelve target languages, plus a JAX runtime backend for GPU-accelerated, differentiable simulation.

The project is developed and maintained by [Noah Parsons](https://github.com/GuiloScion).

---

## Repositories

### Core

| Repository | Description |
|------------|-------------|
| [**mechanicsdsl**](https://github.com/MechanicsDSL/mechanicsdsl) | Core DSL compiler, symbolic engine, twelve physics domains, twelve code-generation backends plus a JAX runtime backend, LSP server, Jupyter magic commands, FastAPI server. |

### Deployment and integration

| Repository | Description |
|------------|-------------|
| [**mechanicsdsl-embedded**](https://github.com/MechanicsDSL/mechanicsdsl-embedded) | Embedded and edge deployment for Arduino, Raspberry Pi, and ARM platforms. Pendulum and double pendulum examples, ARM cross-compilation via Docker, POSIX real-time scheduling, IMU integration. |
| [**mechanicsdsl-ros2**](https://github.com/MechanicsDSL/mechanicsdsl-ros2) | ROS2 integration. Generated C++ nodes, custom messages, launch files, parameter configs, and integration tests. |
| [**mechanicsdsl-unity**](https://github.com/MechanicsDSL/mechanicsdsl-unity) | Unity and Unreal Engine plugin packages. Pendulum and coupled-pendulum components, conservation monitors, phase-space trails, custom Inspectors, runtime test suite. |

### Data and education

| Repository | Description |
|------------|-------------|
| [**mechanicsdsl-notebooks**](https://github.com/MechanicsDSL/mechanicsdsl-notebooks) | Worked-example Jupyter notebooks covering a selection of MechanicsDSL topics: double pendulum (chaos, Lyapunov), coupled oscillators (normal modes, beating), constraints (Baumgarte), central forces (Kepler), and Hamiltonian mechanics (phase space, symplectic integration). Binder-launchable. |
| [**mechanicsdsl-datasets**](https://github.com/MechanicsDSL/mechanicsdsl-datasets) | Reference datasets for physics parameter estimation and inverse problem benchmarking. Includes synthetic trajectories for pendulum, double pendulum, and coupled oscillators, with CSV, HDF5, metadata, and validation scripts. |

---

## Adoption

Measured via Google BigQuery (the public PyPI download dataset), MechanicsDSL has 495 organic installs from 838 raw, across 18 countries. Raw counts exclude automated clients, mirrors, CI runners, and requests without a reported installer, under the PyPI installer.name/null exclusion rule. Total file requests come to ~18,000 across 71 countries, but that figure is dominated by automatic PyPI mirrors (e.g. bandersnatch) and direct/web traffic, so it overstates real adoption. The package is published with a Zenodo DOI ([10.5281/zenodo.17771040](https://doi.org/10.5281/zenodo.17771040)).

---

## Quick start

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

## Citation

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

All MechanicsDSL repositories are released under the MIT License unless otherwise noted.

---

<p align="center">
  <a href="https://mechanicsdsl.readthedocs.io">Docs</a> ·
  <a href="https://github.com/MechanicsDSL/mechanicsdsl">Core repo</a> ·
  <a href="https://doi.org/10.5281/zenodo.17771040">Zenodo</a> ·
  <a href="https://pypi.org/search/?q=mechanicsdsl">PyPI</a>
</p>
