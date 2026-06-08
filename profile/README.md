The compiler handles symbolic derivation, conservation law detection, integration, and visualization.

---

## Repositories

### Core

| Repository | Description |
|------------|-------------|
| [**mechanicsdsl**](https://github.com/MechanicsDSL/mechanicsdsl) | Core DSL compiler, symbolic engine, eight physics domains, thirteen code generation backends, JAX/GPU support, LSP server, Jupyter magic commands, FastAPI server. |

### Deployment and integration

| Repository | Description |
|------------|-------------|
| [**mechanicsdsl-embedded**](https://github.com/MechanicsDSL/mechanicsdsl-embedded) | Embedded and edge deployment for Arduino, Raspberry Pi, and ARM platforms. Pendulum and double pendulum examples, ARM cross-compilation via Docker, POSIX real-time scheduling, IMU integration. |
| [**mechanicsdsl-ros2**](https://github.com/MechanicsDSL/mechanicsdsl-ros2) | ROS2 integration. Generated C++ nodes, custom messages, launch files, parameter configs, and integration tests. |
| [**mechanicsdsl-unity**](https://github.com/MechanicsDSL/mechanicsdsl-unity) | Unity and Unreal Engine plugin packages. Pendulum and coupled-pendulum components, conservation monitors, phase-space trails, custom Inspectors, runtime test suite. |

### Data and education

| Repository | Description |
|------------|-------------|
| [**mechanicsdsl-notebooks**](https://github.com/MechanicsDSL/mechanicsdsl-notebooks) | Jupyter notebooks across all eight MechanicsDSL physics domains. Double pendulum (chaos, Lyapunov), coupled oscillators (normal modes, beating), constraints (Baumgarte), central forces (Kepler), Hamiltonian mechanics (phase space, symplectic integration). Binder-launchable. |
| [**mechanicsdsl-datasets**](https://github.com/MechanicsDSL/mechanicsdsl-datasets) | Reference datasets for physics parameter estimation and inverse problem benchmarking. Includes synthetic trajectories for pendulum, double pendulum, and coupled oscillators, with CSV, HDF5, metadata, and validation scripts. |

---

## Adoption

Since release on PyPI, MechanicsDSL has accumulated 13,000+ downloads across 67 countries, with institutional mirrors (bandersnatch, Nexus, devpi) observed in multiple national research computing environments. The package is published with a Zenodo DOI ([10.5281/zenodo.17771040](https://doi.org/10.5281/zenodo.17771040)).

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
  <a href="https://pypi.org/project/mechanicsdsl-core/">PyPI</a> ·
  <a href="https://pypi.org/project/mechanicsdsl-datasets/">Datasets on PyPI</a>
</p>
