# Planetary-Habitable-Zone-Hypothesis-Testing
An investigation of exoplanets in their star(s)'s habitable zone and whether they differ from the other planets surrounding them. A broader analysis into the possibility of significant differences between these formations, to see if there is concrete evidence to support placing these as primary life forming candidates.

# Statistical Hypothesis Testing of Exoplanet Composition and Habitability

## Overview

This project investigates whether exoplanets located within the Habitable Zone (HZ) differ statistically from those outside it, with a particular focus on **planetary composition (rocky vs. gaseous)** and key physical properties such as radius, mass, density, and equilibrium temperature.

Rather than attempting to *predict* habitability, this work asks a more defensible scientific question:

> **Are planets inside the Habitable Zone statistically different from those outside it?**

The project emphasizes **statistical inference**, hypothesis testing, and robustness analysis, using machine learning only as a hypothesis-generation tool, not as a decision-maker.

---

## Scientific Framing

### Key Principles

- **No claims of causality or discovery**
- **Explicit null and alternative hypotheses**
- **Statistical tests take precedence over models**
- **Physical interpretability is prioritized**

Habitable Zone membership is treated as a conditioning variable, not a causal mechanism. All conclusions are framed within clearly stated inferential limits.

---

## Core Research Questions

1. Do rocky and gaseous exoplanets differ in physical characteristics?
2. Are planets within the Habitable Zone statistically distinct from those outside it?
3. Is planetary composition independent of Habitable Zone membership?
4. Do observed differences remain stable under:
   - Measurement uncertainty?
   - Assumption-free testing?
   - Causal constraints?

---

## Methodology Summary

### 1. Planet Composition Classification
Planets are classified as **rocky or gaseous** using physically motivated thresholds based on radius and mass, informed by current astrophysical literature.

### 2. Hypothesis Testing
The project employs:
- Two-sample t-tests / Welch tests
- Non-parametric alternatives where appropriate
- Chi-squared tests of independence
- Effect size estimation (Cohen’s d, Cliff’s delta)

All tests are accompanied by assumption checks and physical interpretation.

### 3. Stratified Analysis by Habitability
Statistical tests are performed:
- Across the full dataset
- Within Habitable Zone strata
- Across composition strata

This allows for structured comparison without overfitting.

---

## Machine Learning as Hypothesis Generation

A Support Vector Machine (SVM) is used only to explore feature separability between rocky and gaseous planets.

Insights from the SVM (e.g., feature importance near the margin) are translated into formal statistical hypotheses, which are then tested using classical inference.

> Machine learning informs *what to test* — not *what to conclude*.

---

## Robustness, Uncertainty, and Causal Limits (Capstone)

The final notebook integrates three advanced methodological layers:

### Causal Framing
A conceptual Directed Acyclic Graph (DAG) is used to:
- Identify confounders
- Justify conditioning decisions
- Explicitly define inferential boundaries

No causal claims are made.

### Measurement Uncertainty Propagation
Monte Carlo sampling is used to propagate observational uncertainty in planetary measurements through:
- Derived quantities (e.g., density)
- Test statistics
- Effect sizes

Stability of results is evaluated across thousands of uncertainty realizations.

### Permutation Testing
Assumption-free permutation tests are used to:
- Empirically construct null distributions
- Validate parametric p-values
- Assess sensitivity to label randomness

Together, these methods test whether observed results reflect robust physical signals or fragile statistical artifacts.

---

## Project Structure

```text
01_scientific_questions_and_null_hypotheses.ipynb
02_exoplanet_data_and_habitable_zone_definition.ipynb
03_composition_classification_and_assumptions.ipynb
04_two_sample_tests_by_habitability.ipynb
05_chi_squared_composition_vs_hz.ipynb
06_effect_sizes_and_statistical_power.ipynb
07_svm_as_hypothesis_generator.ipynb
08_robustness_uncertainty_and_causal_limits.ipynb
