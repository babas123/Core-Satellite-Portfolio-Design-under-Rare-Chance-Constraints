# Core–Satellite Portfolio Optimization under Rare Chance Constraints

## Overview

This repository contains a **standalone research project** extending a stochastic optimization framework under **rare chance constraints**, inspired by Tong et al. (2022).

The goal is to study how **tail risk (extreme losses)** can be structurally controlled through a **Core–Satellite portfolio architecture**, where:

- the **Core portfolio** is explicitly protected against rare extreme losses,
- the **Satellite portfolio** is allowed to take controlled risk in pursuit of higher returns.

This project is **methodological and academic**.  
It is **not intended as financial advice**.

---

## Core Idea

Traditional portfolio optimization techniques (mean–variance, maximum return) focus on **average behavior** and are largely blind to **systemic tail risk**.

This project explores:

- how rare-event risk propagates through portfolios,
- how imposing tail-risk protection **only on the Core** modifies the geometry of extreme losses,
- how the **dominant point** (most likely extreme-loss scenario) shifts as Satellite exposure increases.

---

## Portfolio Decomposition

The total portfolio is defined as a convex combination:

- Core weight: (1 − λ)  
- Satellite weight: λ  

The Core–Satellite structure separates economic roles:

- **Core**: structural stability under extreme market stress  
- **Satellite**: controlled exposure to volatile or growth-oriented assets

---

## Risk Modeling Framework

- Asset returns are modeled using a **multivariate Gaussian distribution**
- Mean vector and covariance matrix are estimated from historical data
- Covariance estimation uses **Ledoit–Wolf shrinkage** for numerical stability

Portfolio loss is defined as the negative portfolio return.

---

## Optimization Problem (Core Portfolio)

The Core portfolio is obtained by solving a **rare chance-constrained optimization problem**:

- Objective: maximize the admissible extreme-loss threshold
- Constraint: probability of exceeding this loss remains below a small alpha level
- Constraints: long-only weights, full investment

The problem is solved using a **first-order large deviations approximation**, which:

- avoids brute-force Monte Carlo in rare-event regimes,
- identifies both the admissible loss threshold and the **dominant point** driving extreme losses.

---

## Satellite Portfolio Construction

The Satellite portfolio is **not subject to the chance constraint**.

It is constructed independently using return-oriented criteria such as:

- maximum expected return,
- concentrated exposure to high-growth assets.

Only the Core is required to be robust to rare extreme losses.

---

## Risk Analysis

The project analyzes:

- evolution of extreme-loss thresholds as Satellite weight increases,
- Value-at-Risk and Conditional Value-at-Risk of the aggregated portfolio,
- changes in dominant points as lambda varies,
- concentration of tail risk between Core and Satellite components.

This highlights the **nonlinear interaction between diversification and tail risk**.

---

## Key Insights

- Tail risk is **not additive** across portfolio components.
- Small Satellite allocations can significantly alter extreme-loss scenarios.
- Mean–variance diversification is ineffective against systemic tail risk.
- Dominant points provide a **geometric diagnostic tool** for portfolio fragility.

---

## Project Structure

