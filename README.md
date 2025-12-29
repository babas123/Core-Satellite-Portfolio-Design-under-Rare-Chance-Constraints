# Core–Satellite Portfolio Design under Rare Chance Constraints

## Overview

This repository contains a **standalone research project** investigating portfolio design under **rare chance constraints**, inspired by the large-deviations framework of Tong et al. (2022).

The objective is to analyze how **extreme tail risk** can be structurally controlled through a **Core–Satellite portfolio architecture**, with a particular focus on **policy-driven exposure to a concentrated thematic satellite**.

The project adopts an **academic and methodological perspective**.  
It is **not intended as financial advice**.

---

## Core Motivation

Traditional portfolio optimization methods (mean–variance, maximum return) focus on **average outcomes** and often fail to capture **systemic tail risk**, especially under concentrated exposures.

This project addresses the following questions:

- How does rare-event risk propagate in a Core–Satellite portfolio?
- How does increasing satellite exposure affect the **feasibility of tail-risk constraints**?
- Can extreme-loss behavior be understood through **geometric diagnostics** rather than pointwise risk measures?

---

## Core–Satellite Portfolio Structure

The total portfolio is defined as a convex combination:

- **Core weight**: 1 − λ  
- **Satellite weight**: λ

This separation reflects distinct economic roles:

- **Core portfolio**  
  Provides diversification and structural stability under normal and stressed conditions.

- **Satellite portfolio**  
  Introduces intentional concentration in a high-growth thematic segment, whose tail-risk impact is explicitly analyzed rather than diversified away.

---

## Risk Modeling Framework

- Asset returns are modeled using a **multivariate Gaussian reference distribution**
- Mean vector and covariance matrix are estimated from historical data
- Covariance estimation relies on **Ledoit–Wolf shrinkage** to ensure numerical robustness

Portfolio loss is defined as the negative portfolio return.

---

## Rare Chance–Constrained Optimization

The portfolio design problem is studied under a **rare chance constraint**:

- Objective: maximize expected return
- Constraint:  
  P(Loss ≥ L) ≤ α  
  where:
  - L is a severe loss threshold
  - α is a small probability level
- Constraints: long-only weights, full investment, fixed Core–Satellite structure

To evaluate rare-event feasibility, the constraint is approximated using a **first-order large-deviations (FORM) method**, which:

- avoids brute-force Monte Carlo in extreme regimes,
- identifies the **dominant point** (most likely extreme-loss scenario),
- provides a geometric interpretation of tail risk.

---

## Satellite Portfolio Design

The Satellite portfolio represents a **structured exposure to the AI ecosystem**, covering multiple functional layers such as:

- semiconductors and computation,
- infrastructure and networking,
- cloud platforms and enterprise software.

The Satellite is **not designed to be tail-robust**.  
Its purpose is to introduce controlled concentration and study how such exposure reshapes extreme-loss behavior.

---

## λ as a Policy-Controlled Exposure Parameter

The satellite weight λ is treated as a **strategic decision variable**, not as an optimizable parameter.

A grid of λ values is analyzed, and feasibility is assessed through:

- rare-event probability estimates (FORM and Monte Carlo),
- tail severity metrics (VaR and CVaR),
- **dominant-point geometry and large-deviation diagnostics**.

Rather than selecting a single optimal portfolio, the analysis identifies **risk regimes** (Safe, Transition, Fragile) that guide admissible satellite exposure.

---

## Sensitivity Analysis over the Loss Threshold

The robustness of policy rules is evaluated across multiple loss thresholds L.

Key findings include:

- probability-based constraints lose discriminative power as L increases,
- CVaR-based rules remain informative but become binding abruptly,
- **large-deviation geometry provides early warning signals** of fragility before classical constraints activate.

This highlights the importance of complementing tail-risk constraints with structural diagnostics.

---

## Key Insights

- Tail risk is **structural and non-additive**.
- Small satellite allocations can trigger large shifts in extreme-loss scenarios.
- Mean–variance diversification does not protect against rare systemic events.
- Dominant points offer a **geometric lens** on portfolio fragility.
- Core–Satellite portfolios require **policy-based exposure control**, not pointwise optimization.

---

## Technologies Used

- Julia  
- JuMP  
- OSQP  
- Distributions  
- LinearAlgebra  
- Monte Carlo simulation  

---
## Research Paper

📄 **Full paper (PDF)**  
[Core–Satellite Portfolio Design under Rare Chance Constraints](report/Core_Satellite_Portfolio_Design_under_Rare_Chance_Constraints.pdf)
## Disclaimer

This project is **purely academic**.  
It does **not constitute investment advice**.
