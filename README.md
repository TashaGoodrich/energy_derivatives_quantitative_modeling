# Quantitative Modeling for Energy and Derivatives

This project develops and validates numerical methods for stochastic 
price modeling and derivative valuation. It begins with geometric 
Brownian motion and will progress through Monte Carlo simulation, 
analytical Black–Scholes pricing, and a finite-difference solution of the
Black–Scholes partial differential equation.

The project is being built incrementally so that every mathematical 
assumption, numerical method, and modeling decision can be explained and 
tested.

## Current Stage: Geometric Brownian Motion

The first notebook simulates one possible asset-price trajectory over 252
trading-day intervals using the stochastic differential equation

\[
dS_t = \mu S_t\,dt + \sigma S_t\,dW_t.
\]

The simulation combines deterministic log drift with volatility-scaled
Brownian increments:

\[
R_i =
\left(\mu-\frac{1}{2}\sigma^2\right)\Delta t
+\sigma\sqrt{\Delta t}Z_i,
\qquad Z_i\sim N(0,1).
\]

The cumulative log returns are converted into an asset-price path using

\[
S_t=S_0e^{R_t}.
\]

A fixed random seed is currently used to make the notebook reproducible.

## Current Results

Using an initial price of $100, annual drift of 8%, annual volatility of 
20%, and seed 42, the example path ends at approximately $91.07 after 252 
trading days.

This is one possible outcome, not a forecast. The positive drift 
describes an expected trend across many possible paths and does not 
guarantee that every individual path ends above its initial value.

## Repository Structure

```text
energy_derivatives_quantitative_modeling/
├── README.md
└── notebooks/
    └── 01_geometric_brownian_motion.ipynb
