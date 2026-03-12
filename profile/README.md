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
  <a href="https://mybinder.org/v2/gh/MechanicsDSL/mechanicsdsl/main?filepath=tutorials"><img src="https://mybinder.org/badge_logo.svg" alt="Binder"></a>
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

That's it. The compiler handles the rest — symbolic derivation, conservation law detection, GPU-accelerated integration, phase space visualization.

---

## Organization Repositories

This organization is actively growing across simulation, deployment, tooling, and educational content.

### Core

| Repository | Description | Status |
|------------|-------------|--------|
| [**mechanicsdsl**](https://github.com/MechanicsDSL/mechanicsdsl) | Core DSL compiler, symbolic engine, 8 physics domains, 17+ classical mechanics modules, 12+ code generation backends, JAX/GPU support, LSP server, Jupyter magic commands, FastAPI server | `v2.0 stable` |

### Deployment & Integration

| Repository | Description | Status |
|------------|-------------|--------|
| [**mechanicsdsl-embedded**](https://github.com/MechanicsDSL/mechanicsdsl-embedded) | Embedded and edge deployment for Arduino, Raspberry Pi, and ARM platforms. Generates optimized C++ with NEON intrinsics, real-time IMU sensor fusion examples, cross-compilation toolchains, and `no_std` Rust targets for microcontrollers. Designed for closed-loop control applications where simulation runs on-device. | `planned` |
| [**mechanicsdsl-ros2**](https://github.com/MechanicsDSL/mechanicsdsl-ros2) | Dedicated ROS2 integration layer. Compiles DSL specifications directly to ROS2 node packages with auto-generated `CMakeLists.txt`, message definitions, and launch files. Includes worked examples for manipulator dynamics, mobile robot kinematics, and real-time constraint-aware control. | `planned` |
| [**mechanicsdsl-unity**](https://github.com/MechanicsDSL/mechanicsdsl-unity) | Unity and Unreal Engine plugin packages. Exposes the MechanicsDSL compiler as an in-editor tool: define physical systems in DSL notation, generate C# (Unity) or C++ (Unreal) simulation components, and drop them directly into game or simulation scenes. Targets physically accurate game development, interactive science exhibits, and digital twin applications. | `planned` |

### Data & Education

| Repository | Description | Status |
|------------|-------------|--------|
| [**mechanicsdsl-notebooks**](https://github.com/MechanicsDSL/mechanicsdsl-notebooks) | Curated collection of Jupyter notebooks spanning all eight physics domains. Organized by difficulty from introductory pendulum problems through graduate-level general relativistic geodesics. Each notebook pairs DSL source with physics exposition, interactive widgets, and annotated output. Designed as a standalone curriculum resource for courses adopting MechanicsDSL. | `planned` |
| [**mechanicsdsl-datasets**](https://github.com/MechanicsDSL/mechanicsdsl-datasets) | Reference datasets for physics parameter estimation and inverse problem benchmarking. Includes experimentally measured trajectories, synthetic datasets with known ground-truth parameters, and noisy sensor data with documented uncertainty budgets. Paired with example estimation scripts using the JAX-backed MCMC and Sobol analysis infrastructure in the core package. | `planned` |

---

## What the Core Package Does Today

### Compiler Pipeline

The system follows a classical compiler architecture end to end:

**Source (DSL notation) → Lexer → Parser → AST → Semantic Analysis → SymPy Symbolic Engine → IR → Code Generator → Target**

No Python required for the simulation workflow. Users interact with physics; the compiler manages the programming.

### Physics Coverage

| Domain | Modules |
|--------|---------|
| **Classical Mechanics** | 17+ modules: Lagrangian & Hamiltonian formulations, constraints, rigid body dynamics, perturbation theory, central forces, canonical transformations, normal modes, SPH fluid solver, and more |
| **Quantum Mechanics** | Bound states, tunneling, scattering, semiclassical WKB, hydrogen atom |
| **Electromagnetism** | Charged particle dynamics, plane waves, waveguides, antennas, traps |
| **Special Relativity** | Lorentz kinematics, four-vectors, Doppler, synchrotron radiation |
| **General Relativity** | Schwarzschild & Kerr metrics, geodesics, gravitational lensing, FLRW cosmology |
| **Statistical Mechanics** | Microcanonical/canonical/grand canonical ensembles, Ising model, quantum distributions |
| **Thermodynamics** | Heat engine cycles, equations of state, phase transitions |
| **Fluid Dynamics** | SPH solver, Poly6/Spiky/Viscosity kernels, Tait EOS |

### Code Generation Targets

| Category | Backends |
|----------|---------|
| Scientific Python | NumPy, JAX (JIT + autodiff), SciPy |
| High-performance | C++, CUDA, OpenMP, Fortran |
| Modern systems | Rust, Julia |
| Embedded / real-time | Arduino, Modelica |
| Web / visualization | JavaScript, WebAssembly, Unity (C#), Unreal Engine (C++) |

### Advanced Numerical Capabilities

- **Constraint handling** — Lagrange multipliers with Baumgarte stabilization for holonomic and non-holonomic constraints; drift-free long-time integration
- **Conservation law identification** — Automatic Noether symmetry analysis (cyclic coordinates, time independence, rotational symmetry); runtime conservation monitoring
- **Symplectic integration** — Verlet, Ruth, Forest-Ruth methods preserving Hamiltonian structure
- **Stiffness detection** — Automatic selection between Runge-Kutta, LSODA, and Radau based on Jacobian eigenvalue heuristics
- **Inverse problems** — Adjoint-based parameter estimation, Sobol sensitivity analysis, MCMC uncertainty quantification via JAX-differentiated models
- **Ensemble simulation** — `jax.vmap` over batched initial conditions for GPU-accelerated phase space exploration

### Ecosystem Integration

| Platform | Integration |
|----------|-------------|
| **Jupyter** | `%%mechanicsdsl` magic commands with inline plot output |
| **VS Code** | LSP server with real-time autocomplete and diagnostics |
| **FastAPI** | WebSocket server for browser-based simulation without local install |
| **ROS2** | Generated C++ deploys directly as ROS2 nodes |
| **OpenMDAO** | Multidisciplinary design optimization integration |
| **Docker / Kubernetes** | Production containers for cloud and HPC; ARM and Raspberry Pi builds |

---

## Adoption

Since release on PyPI, MechanicsDSL has accumulated **8,300+ downloads across 53 countries**, with institutional mirrors (bandersnatch, Nexus, devpi) confirmed in multiple national research computing environments. The package is published with a formal Zenodo DOI ([10.5281/zenodo.17771040](https://doi.org/10.5281/zenodo.17771040)) and peer-reviewed through the scientific literature:

> Parsons, N. *Decoupling Programming from Physics: A Compiler-Based Approach to Teaching Lagrangian Mechanics.* Under review at **American Journal of Physics** (submitted January 2026).

---

## Quick Start

```bash
pip install mechanicsdsl-core          # core
pip install mechanicsdsl-core[jax]     # + GPU acceleration
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

If you use MechanicsDSL in your research, please cite:

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

## Contributing

Contributions are welcome across all repositories in this organization. See [CONTRIBUTING.md](https://github.com/MechanicsDSL/mechanicsdsl/blob/main/CONTRIBUTING.md) in the core repo for guidelines.

---

## License

All MechanicsDSL repositories are released under the **MIT License** unless otherwise noted.

---

<p align="center">
  <em>Built for physicists, engineers, and curious minds.</em><br>
  <a href="https://mechanicsdsl.readthedocs.io">Docs</a> ·
  <a href="https://github.com/MechanicsDSL/mechanicsdsl">Core Repo</a> ·
  <a href="https://doi.org/10.5281/zenodo.17771040">Zenodo</a> ·
  <a href="https://pypi.org/project/mechanicsdsl-core/">PyPI</a>
</p>
