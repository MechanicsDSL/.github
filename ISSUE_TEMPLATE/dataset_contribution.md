---
name: Dataset Contribution
about: Contribute a new physics dataset to mechanicsdsl-datasets
title: "[DATASET] "
labels: ["dataset", "contribution"]
assignees: []
---

## Dataset Name

Proposed repository name: `datasets/<your_dataset_name>/`

---

## Physical System

Describe the physical system this dataset represents. Include the governing equations and the MechanicsDSL DSL specification if available:

```
\system{...}
\lagrangian{...}
```

---

## Dataset Type

- [ ] Synthetic (generated from forward simulation, known ground truth)
- [ ] Experimental (real hardware measurements)
- [ ] Hybrid (synthetic with experimentally calibrated parameters)

---

## Contents

What files will the dataset include?

- [ ] `data.csv`
- [ ] `data.hdf5`
- [ ] `metadata.json`
- [ ] `README.md`
- [ ] Example scripts

---

## Ground Truth / Parameters

For synthetic datasets, list the ground-truth parameters:

| Parameter | Value | Unit |
|-----------|-------|------|
| | | |

For experimental datasets, describe the instrumentation and calibration:

---

## Noise Model

Describe any noise present in the observations (type, magnitude, distribution):

---

## Intended Use

What estimation or benchmarking tasks is this dataset designed for?

---

## Hardware / Collection Method (experimental only)

Describe sensors, sampling rate, duration, and any post-processing applied:

---

## Additional Notes
