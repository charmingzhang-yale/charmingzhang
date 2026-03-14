---
layout: page
title: "CausalEGM"
permalink: /notes/causalegm/
---

# An encoding generative modeling approach to dimension reduction and covariate adjustment in causal inference with observational studies 

**Paper:** https://doi.org/10.1073/pnas.2322376121  
**Field:** Causal Inference · Deep Learning · Dimension Reduction

---

## Big picture: what problem the paper solves 🔎

- Goal: Estimate causal effects in observational studies with high-dimensional covariates.
- Key problem: When covariates are high dimensional, standard causal adjustment methods suffer from the curse of dimensionality.
- Traditional approaches try to reduce dimensionality using propensity scores, sufficient dimension reduction (SDR)
- Limitation of existing approaches:
  - mostly linear dimension reduction
  - cannot capture complex nonlinear relationships
- Motivation: modern datasets contain many covariates, so better dimension reduction methods are needed.

## Core idea 💡

- The paper proposes CausalEGM, a deep learning framework for dimension reduction + generative modeling in causal inference.
  - learn a low-dimensional latent representation of covariates
  - identify the latent confounders affecting both treatment and outcome
  - conditioning on them removes confounding bias.

## Model & Results ⚙️📊

- Continuous treatment experiments
  - Goal: estimate dose–response function
  - Result: CausalEGM consistently outperforms baseline methods.
- Binary treatment experiments
  - Goal: estimate ATE (Average Treatment Effect), ITE (Individual Treatment Effect)
  - Result: CausalEGM outperforms neural causal models such as CFR, Dragonnet, CEVAE, GANITE

## Strengths of the method 🚀

- Nonlinear dimension reduction
- Explicit latent confounder modeling
- Scalable to high-dimensional data

## Conclusions 🧾

- CausalEGM integrates deep generative modeling with causal inference to perform nonlinear dimension reduction and identify latent confounders in high-dimensional observational data.
- It improves causal effect estimation by learning a structured latent representation of covariates that separates confounders from irrelevant features.
