# Quantification of Inter-Limb Asymmetry During Self-Feeding Tasks Using OpenSim-Based Upper Limb Kinematic Analysis

Course project for **Biomechanics – Q1 2026**, Universitat Politècnica de Catalunya (UPC), ETSEIB.

This repository contains the report for a study that quantifies inter-limb (dominant vs. non-dominant) kinematic asymmetry during standardized self-feeding tasks in healthy individuals, using an OpenSim-based musculoskeletal modelling and inverse kinematics framework.

## Document

- [`Quantification of Inter-Limb Asymmetry During Self-Feeding Tasks.pdf`](Quantification of Inter-Limb Asymmetry During Self-Feeding Tasks.pdf) — Full report (9 pages).

## Authors

Raïd Houms · Marcos Oriol · Òscar Palau · Marc Rodriguez · Fernando Sala-Vivé

## Overview

The goal was to evaluate the feasibility of an OpenSim-based pipeline for measuring inter-limb asymmetry during eating-related activities and to obtain preliminary baseline data from healthy participants that could later serve as a reference for neurological populations (e.g., post-stroke patients).

**Research question:** How does the non-dominant upper limb differ biomechanically from the dominant limb during standardized self-feeding tasks in healthy individuals?

## Methods

- **Participants:** 2 healthy male volunteers (23 and 24 years old), no neurological or musculoskeletal history.
- **Tasks (4):** bottle opening, spoon use, drinking from a glass, and cutting with knife and fork. Each performed with both the dominant (D) and non-dominant (ND) limb, 2 repetitions each (16 dynamic trials per participant).
- **Motion capture:** Protocol B with 18 reflective markers + 2 extra dorsal-hand markers (20 total) for wrist tracking. Data collected at the BIOMEC Lab, ETSEIB–UPC.
- **Modelling:** Generic OpenSim upper-body model scaled per subject from a static trial; quality assessed via RMS marker error and visual inspection.
- **Inverse Kinematics (IK):** Joint angles estimated from marker trajectories (no force data recorded, so analysis is kinematic only). Marker weighting tuned by reliability.
- **Post-processing (MATLAB):** Repetitions averaged per task/limb; trajectories time-normalized (0–100%); computation of movement duration, Range of Motion (ROM), and Symmetry Index (SI).

### Metrics

- **Movement duration:** `T = t_final − t_initial`
- **Range of Motion:** `ROM = θ_max − θ_min`
- **Symmetry Index:** `SI = |X_D − X_ND| / (0.5·(X_D + X_ND)) × 100`

ROM was computed for shoulder flexion/extension, shoulder abduction/adduction, elbow flexion/extension, and forearm pronation/supination.

## Key results

- **Task-dependent asymmetry:** more complex tasks (cutting, bottle opening) produced larger asymmetries than spoon use and drinking.
- **Shoulder abduction/adduction** was consistently the most asymmetric and variable degree of freedom (SI up to ~52–54% in bottle opening; **84.5%** for Subject 2 in cutting).
- **Shoulder flexion/extension** was the most consistent between limbs in several conditions (SI as low as 0.2%).
- **Temporal vs. kinematic asymmetry** did not always align, suggesting they reflect different aspects of motor control.
- Notable **inter-subject variability** despite both participants being healthy.

## Limitations

Only two participants (no statistical analysis), movement smoothness and trunk compensation excluded due to time constraints, and variability in initial posture may have influenced results.

## Usage and licensing

All rights to this work are reserved by the authors. This material is shared for academic and informational purposes only.

If you wish to use, cite, build upon, or reproduce any part of this paper — including its methodology, data, figures, or results — **you must notify the authors in advance and obtain their permission**. Please get in touch before any use, and provide appropriate attribution to the authors and to Universitat Politècnica de Catalunya (UPC), ETSEIB.

## References

1. I. Aprile et al., *Kinematic analysis of the upper limb motor strategies in stroke patients...*, Biomed Res Int (2014). DOI: 10.1155/2014/636123
2. Y.-W. Chen et al., *Kinematic descriptions of upper limb function using simulated tasks in ADLs after stroke*, Human Movement Science 79 (2021), 102834. DOI: 10.1016/j.humov.2021.102834
3. A. Favata et al., *Feasibility study of a sensor-to-segment calibration method...*, PLOS ONE 20.10 (2025), 1–17. DOI: 10.1371/journal.pone.0334177
4. R. Queen et al., *A novel method for measuring asymmetry in kinematic and kinetic variables: The normalized symmetry index*, J Biomech 99 (2020), 109531. DOI: 10.1016/j.jbiomech.2019.109531
