# Structured Extrema Errors in Classical Surrogates for Viscous Burgers

Research paper on the structured prediction errors of machine-learning surrogates for the one-dimensional viscous Burgers equation.

**Author:** Youssef Oubari — IMT Atlantique, France

📄 [Read the paper](structured_extrema_burgers.pdf)

> **Status:** arXiv submission pending.  
> Submitted to **XAI4Science @ NeurIPS 2026** and **ML4PS** — awaiting review.

---

## Overview

This work studies **where machine-learning PDE surrogates make errors and why those errors appear**.

We compare several classical ML models:

- RBF Kernel Ridge Regression
- Linear Ridge Regression
- ExtraTrees
- Random Forests

Across these models, prediction residuals show clear structured branches near predicted maxima and minima.

For Kernel Ridge and Ridge, we investigate this structure using:

- local curvature and spatial derivatives;
- geometric analysis near extrema;
- regression against the Burgers advection and diffusion terms;
- spatial negative controls;
- spectral analysis;
- effective-diffusion diagnostics;
- learned residual correction;
- recursive rollout evaluation.

The results are consistent with **insufficient viscous smoothing** for Kernel Ridge and Ridge at moderate and high viscosity, while the same physical explanation is much weaker for the tree models.

---

## Residual structure across ML models

The same type of structured residual pattern appears across several classical surrogate families, although its shape and magnitude depend on the model.

<p align="center">
  <img src="figures/residual_comparison_common_scale.png" width="850"/>
</p>

---

## Errors near predicted extrema

For Kernel Ridge, many of the largest residuals occur near predicted maxima and minima. These points trace the main off-axis residual branches.

<p align="center">
  <img src="figures/part1_plain_krr_one_step_residual_arcs_near_extrema.png" width="700"/>
</p>

This observation motivates the geometric and physics-based analysis developed in the paper.

---

## Main results

- Structured residual branches appear across **Kernel Ridge, Ridge, ExtraTrees, and Random Forests**.
- Large Kernel Ridge errors are concentrated near predicted extrema.
- The residual is much more strongly related to **local curvature** than to the first spatial derivative.
- A local analysis of smooth extrema explains why a near-parabolic residual structure can appear.
- For Kernel Ridge and Ridge, several independent tests are consistent with **insufficient viscous smoothing** at moderate and high viscosity.
- A correction using only predicted quantities reduces both **one-step prediction error** and **recursive rollout error**.

---

## Related project

This paper grew from an earlier project in which I developed and compared classical ML surrogates for Burgers dynamics, including Ridge, polynomial regression, RBF Kernel Ridge, gradient-boosting residual correction, model selection, and recursive rollout evaluation.

[Classical ML Surrogates for the 1D Burgers Equation](https://github.com/Youssef-obr/pde-surrogate-learning)

---

## Repository

For now, this repository contains the paper and selected figures.

Experimental code and reproduction scripts may be added progressively.

---

## Citation

The arXiv citation will be added once the submission is publicly available.

---

## Contact

**Youssef Oubari**  
IMT Atlantique, France  
📫 youssef.oubari@imt-atlantique.net
