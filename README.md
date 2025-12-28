# Core–Satellite Portfolio Optimization under Rare Chance Constraints

## Overview

This repository contains a **standalone research project** extending a stochastic optimization framework under **rare chance constraints**, inspired by Tong et al. (2022).

The objective is to study how **tail risk (extreme losses)** can be structurally controlled through a **Core–Satellite portfolio architecture**, where:

- the **Core portfolio** provides diversification and structural stability,
- the **Satellite portfolio** introduces controlled concentration in high-growth assets.

This project is **methodological and academic**.  
It is **not intended as financial advice**.

---

## Core Idea

Traditional portfolio optimization techniques (mean–variance, maximum return) focus on **average behavior** and are largely blind to **systemic tail risk**.

This project explores:

- how rare-event risk propagates through portfolios,
- how a Core–Satellite structure modifies the feasibility of rare chance constraints,
- how the **dominant point** (most likely extreme-loss scenario) shifts as Satellite exposure increases.

---

## Portfolio Decomposition

The total portfolio is defined as a convex combination:

- Core weight: (1 − λ)  
- Satellite weight: λ  

The Core–Satellite structure separates economic roles:

- **Core**: diversification and partial robustness under extreme market stress  
- **Satellite**: concentrated exposure to thematic or growth-oriented assets  

---

## Risk Modeling Framework

- Asset returns are modeled using a **multivariate Gaussian distribution**
- Mean vector and covariance matrix are estimated from historical data
- Covariance estimation uses **Ledoit–Wolf shrinkage** for numerical stability

Portfolio loss is defined as the negative portfolio return.

---

## Optimization Framework

The portfolio optimization problem is formulated under a **rare chance constraint**:

- Objective: maximize expected return
- Constraint: the probability of exceeding a severe loss threshold remains below a small level α
- Constraints: long-only weights, full investment, Core–Satellite allocation structure

The rare chance constraint is enforced using a **first-order large deviations (FORM) approximation**, which:

- avoids brute-force Monte Carlo in rare-event regimes,
- identifies the **dominant point** driving extreme losses.

---

## Satellite Portfolio Construction

The Satellite portfolio represents a **structured exposure to the AI ecosystem**, spanning multiple functional layers such as computation, semiconductors, infrastructure, cloud services, and software platforms.

The Satellite is not designed to be tail-robust, but to introduce controlled concentration whose impact on extreme risk is explicitly analyzed.

---

## Selecting λ: A Tail-Risk–Controlled Decision Policy

The parameter λ controls the fraction of capital allocated to the Satellite portfolio.

Importantly, **λ is treated as a strategic decision variable**, not as a statistical parameter to be estimated.

A grid of λ values is analyzed, and feasibility is assessed using:

- rare-event probability estimates,
- Monte Carlo VaR and CVaR,
- dominant point geometry.

The selected λ reflects a predefined tolerance to tail risk.

---

## Key Insights

- Tail risk is **not additive** across portfolio components.
- Small Satellite allocations can significantly alter extreme-loss scenarios.
- Mean–variance diversification is ineffective against systemic tail risk.
- Dominant points provide a **geometric diagnostic tool** for portfolio fragility.
- Core–Satellite structures require explicit tail-risk analysis.

---

## Technologies Used

- Julia
- JuMP
- OSQP
- Distributions
- LinearAlgebra
- Monte Carlo simulation

---

## Disclaimer

This project is **purely academic**.  
It does **not constitute investment advice**.

---

## Author

Marc-Arthur Sébastien Georges  
MSc Mathematical & Computational Finance
