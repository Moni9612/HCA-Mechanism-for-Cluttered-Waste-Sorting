# HCA Mechanism for Cluttered Waste Sorting

This repository provides the complete computational and experimental framework developed for the **Hybrid Compliance Activation (HCA) gripper** for robotic manipulation in cluttered waste-sorting environments.

The framework covers three major stages: **MLP-assisted geometric optimization of the adaptive Fin-Ray finger, experimental validation of the optimized finger designs, and 6D robotic grasping evaluation using the HCA and PCA grippers**.

The complete project is organized into three repositories, included here as Git submodules.

---

## Repository Structure

HCA-Mechanism-for-Cluttered-Waste-Sorting

- NSGA-II-and-MLP-Integration:
  - MLP-assisted geometric optimization of the Fin-Ray finger
  
- Experimental-Validation-Setup-for-Optimal-design-testing:
  - Experimental validation and 3D fingertip displacement measurement
  
- 6D-Grasping-using-HCA-and-PCA-grippers:
  - 6D grasping evaluation using HCA and PCA grippers

---

## 1. NSGA-II and MLP Integration

[`NSGA-II-and-MLP-Integration`](NSGA-II-and-MLP-Integration)

This repository contains the computational framework used for **geometric optimization of the adaptive Fin-Ray finger**.

Finite-element simulation data are used to train a **Multi-Layer Perceptron (MLP)** surrogate model that predicts the mechanical response of candidate finger geometries under different contact conditions. The trained MLP is subsequently integrated with an **NSGA-II-based multi-objective optimization framework** to efficiently explore the design space without requiring repeated finite-element simulations for every newly generated candidate.

The final constrained Pareto front is evaluated using a normalized **minimum-distance-to-utopia** approach to identify the five highest-ranked finger designs for subsequent validation.

---

## 2. Experimental Validation Setup for Optimal Design Testing

[`Experimental-Validation-Setup-for-Optimal-design-testing`](Experimental-Validation-Setup-for-Optimal-design-testing)

This repository contains the experimental setup and image-processing workflow used to **validate the deformation behaviour of the optimized Fin-Ray finger designs**.

The validation system combines Dynamixel-based finger actuation, a deformable Ecoflex 00-50 half-proxy with a rigid core, and two approximately orthogonal camera views. A calibrated red-marker tracking method is used to quantify the three-dimensional fingertip displacement and obtain the corresponding **Δx, Δy, and Δz** components for comparison with the computational predictions.

The repository includes the camera acquisition, actuator-control, calibration, marker-detection, and fingertip-displacement calculation procedures required for the experimental evaluation.

---

## 3. 6D Grasping using HCA and PCA Grippers

[`6D-Grasping-using-HCA-and-PCA-grippers`](6D-Grasping-using-HCA-and-PCA-grippers)

This repository contains two **6D robotic grasping pipelines for cluttered waste sorting**, implemented using the **Hybrid Compliance Activation (HCA) gripper** and the **Passive Compliance Activation (PCA) gripper**.

The pipelines integrate robotic perception, 6D grasp generation, motion planning, gripper actuation, and pick-and-place execution to evaluate grasping performance in cluttered environments containing heterogeneous inorganic waste objects.

A common experimental framework is maintained between the HCA and PCA implementations, enabling consistent comparative evaluation of the two gripper mechanisms.

---

## Clone the Complete Project

Because the three components are included as **Git submodules**, clone the main repository together with all submodules using:

```bash
git clone --recurse-submodules <MAIN_REPOSITORY_URL>
```

If the main repository has already been cloned without its submodules, initialize and download them using:

```bash
git submodule update --init --recursive
```

Each submodule contains its own `README.md` with detailed installation, configuration, and execution instructions.

---

## Overall Workflow

```text
Finite-Element Simulation Data
            ↓
MLP Surrogate Model
            ↓
NSGA-II Geometric Optimization
            ↓
Highest-Ranked Pareto Finger Designs
            ↓
Experimental Validation
            ↓
Optimized HCA Finger Design
            ↓
HCA Gripper Integration
            ↓
6D Grasping Evaluation
            ↓
HCA vs PCA Comparison
```
