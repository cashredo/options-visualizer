# Black-Scholes Options Visualizer

**Live:** https://optionsvisualizer.netlify.app

Prices European call and put options using the Black-Scholes model, implemented from scratch in vanilla JavaScript — no math libraries. Computes all five Greeks analytically from the closed-form partial derivatives of the formula.

## What it does

- Real-time call/put pricing as you adjust S, K, T, σ, r
- All five Greeks (Δ Γ Θ ν ρ) with live Chart.js curves
- Finnhub API integration — type any ticker to pull a live quote into the model
- Wikipedia links on every parameter for context
- WebGL fragment shader background

## The math

The Black-Scholes formula gives the price of a European option as a function of five inputs: stock price (S), strike price (K), time to expiry (T), implied volatility (σ), and risk-free rate (r). The Greeks are the partial derivatives of the option price with respect to each input — computed analytically here, not numerically.

```
d1 = (ln(S/K) + (r + σ²/2)·T) / (σ·√T)
d2 = d1 − σ·√T

Call = S·N(d1) − K·e^(−rT)·N(d2)
Put  = K·e^(−rT)·N(−d2) − S·N(−d1)
```

## Stack

Vanilla JS · Chart.js · WebGL · Finnhub API
