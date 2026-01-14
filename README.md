# Efficiency versus Robustness under Tail Misspecification

This repository contains the source code, simulation results, and LaTeX files for the paper  
**“Efficiency versus Robustness under Tail Misspecification: Importance Sampling and Moment-Based VaR Bracketing.”**

The project studies the behavior of simulation-based Value-at-Risk (VaR) estimators at high confidence levels, where tail risk and model misspecification play a central role. In particular, it examines the trade-off between estimator efficiency and robustness when the assumed return distribution differs from the true data-generating process.

---

## Abstract

Value-at-Risk (VaR) estimation at high confidence levels is inherently a rare-event problem and is particularly sensitive to tail behavior and model misspecification. This paper studies the performance of two simulation-based VaR estimation approaches—importance sampling and discrete moment matching—under controlled tail misspecification. The analysis separates the nominal model used for estimator construction from the true data-generating process used for evaluation, allowing the effects of heavy-tailed returns to be examined in a transparent and reproducible setting.

Daily returns of a broad equity market proxy are used to calibrate a nominal Gaussian model, while true returns are generated from Student-t distributions with varying degrees of freedom to represent increasingly heavy tails. Importance sampling is implemented via exponential tilting of the Gaussian model and VaR is estimated through likelihood-weighted root-finding. Discrete moment matching constructs deterministic lower and upper VaR bounds by enforcing a finite number of moment constraints on a discretized loss distribution.

The results demonstrate a clear trade-off between efficiency and robustness. Importance sampling produces low-variance VaR estimates under the nominal model but systematically underestimates the true VaR under heavy-tailed returns, with bias increasing at higher confidence levels and for thicker tails. In contrast, discrete moment matching yields conservative VaR bracketing that remains robust under tail misspecification. These findings highlight that variance reduction alone is insufficient for reliable tail risk estimation when model uncertainty is significant.

---

## Repository Structure
├── paper/
│ ├── main.tex # LaTeX source of the paper
│ ├── references.bib # Bibliography
│ └── figures/ # Simulation figures used in the paper
│
├── code/ # Simulation and analysis notebooks/scripts
│
├── README.md
└── LICENSE


---

## Methods Overview

- **Nominal Model:** Gaussian returns calibrated to empirical daily equity index data  
- **True Data-Generating Process:** Student-t distributions with varying degrees of freedom  
- **Importance Sampling:** Exponential tilting of the nominal Gaussian distribution with likelihood-weighted VaR estimation  
- **Discrete Moment Matching:** Deterministic VaR bracketing under finite moment constraints via discretized loss distributions  

The framework explicitly decouples estimator construction from evaluation, enabling a clean study of tail misspecification effects.

---

## Key Findings

- Importance sampling is **efficient but fragile** under tail misspecification  
- Bias in IS-based VaR estimates increases with confidence level and tail thickness  
- Discrete moment matching provides **conservative but robust** VaR bounds  
- Variance reduction alone is not sufficient for reliable tail risk estimation under model uncertainty  

---

## Reproducibility

All figures in the paper are generated from the scripts and notebooks provided in the `code/` directory.  
The LaTeX source in `paper/` reproduces the manuscript and figures used in the arXiv submission.

---

## arXiv

The paper has been submitted to arXiv and is currently under moderation.  
The arXiv link will be added here once the paper is publicly announced.

---

## License

This repository is released under the MIT License.  
The paper text remains the intellectual property of the author.

