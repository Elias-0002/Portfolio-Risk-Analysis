# Portfolio-Risk-Analysis

A Python quantitative finance project analyzing portfolio optimization, Value at Risk (VaR), Expected Shortfall, stress testing, and out-of-sample backtesting.

The framework compares portfolio construction strategies and applies Value at Risk (VaR), Conditional Value at Risk (CVaR), Monte Carlo simulation, stress testing, and out-of-sample backtesting to evaluate portfolio risk and performance.

## Project Objectives

- Analyze historical returns and portfolio performance.
- Construct and compare equal-weight and Global Minimum Variance (GMV) portfolios.
- Apply Modern Portfolio Theory to portfolio optimization.
- Estimate portfolio risk using historical and parametric VaR.
- Calculate Conditional Value at Risk (CVaR), also known as Expected Shortfall.
- Simulate potential portfolio losses using Monte Carlo methods.
- Evaluate portfolio resilience under deterministic stress scenarios.
- Compare portfolio strategies using out-of-sample backtesting.

## Portfolio Construction

### 1. Equal-Weight Portfolio

Allocates the same proportion of capital to each asset.

For a portfolio with \(N\) assets, each asset receives a weight of:

\[
w_i = \frac{1}{N}
\]

This provides a simple benchmark for comparing alternative allocation strategies.

### 2. Global Minimum Variance Portfolio

Uses portfolio optimization to minimize total portfolio variance subject to investment constraints.

\[
\min_{\mathbf{w}} \quad \mathbf{w}^{T}\Sigma\mathbf{w}
\]

Subject to:

\[
\sum_{i=1}^{N} w_i = 1, \qquad w_i \geq 0
\]

where \(\mathbf{w}\) represents portfolio weights and \(\Sigma\) is the covariance matrix of asset returns.

The portfolio is fully invested and long-only, without short selling.

## Risk Measurement

### 1. Value at Risk (VaR)

Estimates a loss threshold at a specified confidence level over a defined time horizon.

The project compares:

- **Historical VaR:** Uses the empirical distribution of historical portfolio returns.
- **Parametric VaR:** Estimates risk using a distributional assumption for portfolio returns.

### 2. Conditional Value at Risk (CVaR)

Measures the average loss in the tail beyond the VaR threshold. It provides additional information about the severity of losses during unfavorable market conditions.

### 3. Monte Carlo Simulation

Simulates possible portfolio outcomes to examine the distribution of potential returns and losses under specified modeling assumptions.

### 4. Stress Testing

Evaluates portfolio sensitivity to deterministic adverse scenarios, helping identify potential vulnerabilities that may not be fully captured by historical risk measures.

## Out-of-Sample Backtesting

The project uses a chronological training and testing split to evaluate portfolio strategies on data not used to estimate portfolio weights.

The Global Minimum Variance portfolio is optimized using training-period data and then evaluated alongside the equal-weight benchmark during the testing period.

Performance metrics include:

- Cumulative return
- Annualized return
- Annualized volatility
- Sharpe ratio
- Maximum drawdown

This approach helps assess whether portfolio optimization remains useful beyond the period used to construct the portfolio.

## Technologies

- Python
- NumPy
- pandas
- Matplotlib
- SciPy
- yfinance

## Limitations

- Historical returns may not represent future market behavior.
- Portfolio optimization results depend on estimated returns and covariance matrices.
- VaR estimates may underestimate losses during extreme market conditions.
- Monte Carlo results depend on the assumptions used to simulate returns.
- Stress tests evaluate specified scenarios and cannot cover every possible market event.
- Backtesting results may be affected by the selected training and testing periods.

## Future Improvements

- Incorporate transaction costs and portfolio rebalancing.
- Compare additional portfolio optimization strategies.
- Test portfolio performance across different market regimes.
- Explore alternative return distributions and volatility models.

## Disclaimer

This project is intended for educational and research purposes only. The results are based on historical data and modeling assumptions and should not be considered financial advice or investment recommendations.
