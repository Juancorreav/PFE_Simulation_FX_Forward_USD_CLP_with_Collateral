# 📄 FX Forward PFE Simulation with Collateral

## Project Overview

This project simulates the **Potential Future Exposure (PFE)** of a **USD/CLP forward contract** under two conditions:
- **Without collateral** (full exposure).
- **With market-based collateral** (U.S. Treasury bonds + Apple stock).

We apply a **Monte Carlo simulation** to model:
- The future evolution of the USD/CLP exchange rate.
- The future market value of the collateral assets.

The goal is to assess how much credit risk the bank is exposed to if the client defaults, and how the provided collateral mitigates that risk.

This is a practical replication of **real-world risk management workflows** used in corporate lending and derivative trading desks.

---

## Key Questions Addressed

- How much could the bank lose if the FX forward moves against it?
- How volatile are the collateral assets over a 6-month horizon?
- Is the collateral enough to cover the worst-case exposures?
- How does the net exposure change across thousands of future scenarios?

---

## Project Structure

The notebook is structured step-by-step for maximum clarity:

1. **Setting the Contract and Market Parameters**
   - Defines the forward contract size, FX volatility, interest rates, and simulation horizon.

2. **Simulating Future FX Rate Paths**
   - Models 10,000 possible future trajectories for the USD/CLP exchange rate using Geometric Brownian Motion (GBM).

3. **Simulating Collateral Price Paths**
   - Independently simulates the future prices of Treasury bonds (low volatility) and Apple stock (high volatility) over the same period.

4. **Calculating Exposures**
   - Computes the potential positive exposure for the bank in each scenario.

5. **Calculating Net Exposure After Collateral**
   - Subtracts the collateral value from the exposure to get the net exposure for each scenario.

6. **Estimating the PFE (95th Percentile)**
   - Extracts the 95th percentile exposure both with and without collateral.

7. **Visualizing Results**
   - Plots the exposure distributions, showing how collateral effectively neutralizes risk.

8. **Worst-Case Scenario Analysis**
   - Investigates the most extreme drop in collateral value across all simulations.

---

## Results Summary

- **Without collateral**:  
  Potential Future Exposure (PFE) reaches approximately **558 million CLP**.
  
- **With full collateral**:  
  Net exposure drops to **0 CLP** across all scenarios.

- Even in the worst-case drop in collateral value, the bank remains fully protected.

---

## Why This Matters

This project shows how combining market simulations for both derivatives and collateral allows financial institutions to make **better credit decisions**.  
It also illustrates the **real-world impact of collateral quality and liquidity** on mitigating counterparty risk.

The methodology applied here mirrors standard practices in risk management for derivatives and secured lending transactions.

---

## Technologies Used

- Python 3
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## How to Use This Notebook

1. Clone the repository or download the notebook.
2. Run the notebook in Jupyter, VSCode, or Google Colab.
3. Feel free to modify contract parameters, volatilities, or asset types to explore different scenarios.

---

## Author

**Juan de Dios Correa Velasco**  

---
