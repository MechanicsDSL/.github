# Contributing to MechanicsDSL

Thank you for your interest in contributing. This guide covers the contribution process across all MechanicsDSL repositories.

---

## Where to Contribute

| You want to... | Contribute to |
|----------------|---------------|
| Fix a compiler bug or add a physics module | [mechanicsdsl](https://github.com/MechanicsDSL/mechanicsdsl) |
| Add Arduino/RPi examples or embedded targets | [mechanicsdsl-embedded](https://github.com/MechanicsDSL/mechanicsdsl-embedded) |
| Add ROS2 nodes or robot examples | [mechanicsdsl-ros2](https://github.com/MechanicsDSL/mechanicsdsl-ros2) |
| Add Unity/Unreal components | [mechanicsdsl-unity](https://github.com/MechanicsDSL/mechanicsdsl-unity) |
| Add or improve Jupyter notebooks | [mechanicsdsl-notebooks](https://github.com/MechanicsDSL/mechanicsdsl-notebooks) |
| Contribute a physics dataset | [mechanicsdsl-datasets](https://github.com/MechanicsDSL/mechanicsdsl-datasets) |

---

## General Workflow

1. **Fork** the relevant repository
2. **Create a branch**: `git checkout -b feature/your-feature-name`
3. **Make your changes** with clear, well-commented code
4. **Test** your changes (see Testing section below)
5. **Open a pull request** using the PR template

---

## Contribution Types

### Physics Modules and Notebooks
- All physics must be derived from first principles with citations
- Conservation laws must be verified numerically
- DSL specifications must be included alongside any generated code

### Datasets
- Provide `metadata.json` following the existing schema
- Include at least one example estimation or validation script
- Document uncertainty budgets for experimental data

### Embedded and ROS2 Examples
- Test on real hardware where possible; note if untested
- Include wiring diagrams or hardware setup instructions
- Generated code must include the originating DSL specification as a comment

### Bug Fixes
- Include a minimal reproducible example in the PR description
- Add a regression test if applicable

---

## Testing

Each repository has its own test instructions. In general:

```bash
pip install pytest
pytest tests/ -v
```

For notebooks:
```bash
pip install nbconvert
jupyter nbconvert --to notebook --execute notebooks/*.ipynb
```

---

## Code Style

- **Python**: PEP 8, formatted with `ruff`
- **C++**: Google style, `clang-format` with provided `.clang-format`
- **C#**: Microsoft conventions
- **Comments**: Explain the physics, not just the code

---

## Questions

Open an issue with the `question` label or start a GitHub Discussion.
