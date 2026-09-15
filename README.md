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

[`NSGA-II-and-MLP-Integration`](https://anonymous.4open.science/r/NSGA-II-and-MLP-Integration-B068)

This repository contains the computational framework used for **geometric optimization of the adaptive Fin-Ray finger**.

Finite-element simulation data are used to train a **Multi-Layer Perceptron (MLP)** model that predicts the mechanical response of candidate finger geometries under different contact conditions. The trained MLP is subsequently integrated with an **NSGA-II-based multi-objective optimization framework** to efficiently explore the design space without requiring repeated finite-element simulations for every newly generated candidate.

The final constrained Pareto front is evaluated using a normalized **minimum-distance-to-utopia** approach to identify the five highest-ranked finger designs for subsequent validation.

---

## 2. Experimental Validation Setup for Optimal Design Testing

[`Experimental-Validation-Setup-for-Optimal-design-testing`](https://anonymous.4open.science/r/Experimental_Validation_Setup_for_Optimal_design_testing-7CFE)

This repository contains the experimental setup and image-processing workflow used to **validate the deformation behaviour of the optimized Fin-Ray finger designs**.

The validation system combines Dynamixel-based finger actuation, a deformable Ecoflex 00-50 half-proxy with a rigid core, and two approximately orthogonal camera views. A calibrated red-marker tracking method is used to quantify the three-dimensional fingertip displacement and obtain the corresponding **Δx, Δy, and Δz** components for comparison with the computational predictions.

The repository includes the camera acquisition, actuator-control, calibration, marker-detection, and fingertip-displacement calculation procedures required for the experimental evaluation.

---

## 3. 6D Grasping using HCA and PCA Grippers

[`6D-Grasping-using-HCA-and-PCA-grippers`](https://anonymous.4open.science/r/6D-Grasping-using-HCA-and-PCA-grippers-8E5B)

This repository contains two **6D robotic grasping pipelines for cluttered waste sorting**, implemented using the **Hybrid Compliance Activation (HCA) gripper** and the **Passive Compliance Activation (PCA) gripper**.

The pipelines integrate robotic perception, 6D grasp generation, motion planning, gripper actuation, and pick-and-place execution to evaluate grasping performance in cluttered environments containing heterogeneous inorganic waste objects.

A common experimental framework is maintained between the HCA and PCA implementations, enabling consistent comparative evaluation of the two gripper mechanisms.

---

## Accessing the Complete Project

For double-anonymous review, the three project components are provided as separately anonymized repositories. The corresponding anonymized repository links are provided under each section above.

Each repository can be downloaded or cloned independently and contains its own `README.md` with detailed installation, configuration, and execution instructions.

> **Note:** The original project uses Git submodules; however, submodule contents
> are not included directly by Anonymous GitHub. Please use the anonymized
> repository links above to access each component.
---

## Overall Workflow

<p align="center">
  <img src="workflow.png" alt="workflow" width="100%">
</p>
