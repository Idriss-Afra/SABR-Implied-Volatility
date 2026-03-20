# SABR Implied Volatility

A quantitative finance repository focused on constructing the equity implied volatility surface under the **SABR** model.

This project calibrates the **SABR model** to market implied volatilities across quoted expiries in order to construct a fitted **implied volatility surface**.

---

## Repository Structure

```text
SABR-Implied-Volatility/
├── SABR Volatility Model.ipynb
└── MarketData/
    ├── CAC40_MarketData_12022025.csv
    └── EURIBOR6M_ZCRates_12022025.csv
````

---

## Project Overview

This notebook focuses on fitting the **equity implied volatility surface** using the **SABR model**.

Under the **log-normal SABR specification**, the model describes the joint dynamics of the **forward** and its **instantaneous volatility** through four parameters:

- **β** — CEV elasticity parameter
- **σ₀** — initial volatility level
- **α** — volatility of volatility
- **ρ** — correlation between the forward and its volatility

The workflow includes:

- Hagan’s 2002 log-normal volatility expansion
- SABR slice-by-slice calibration
- volatility surface construction

The notebook also highlights an important modelling limitation: while SABR is effective for fitting the implied volatility smile, it does not guarantee arbitrage-free market prices and may even introduce arbitrages at low strikes. As a result, **arbitrage correction on market prices** and **volatility extrapolation at extreme strikes** remain important practical considerations.

---

## Market Data

The `MarketData/` folder includes the market inputs required for the calibration workflow.

* `CAC40_MarketData_12022025.csv` — market option data
* `EURIBOR6M_ZCRates_12022025.csv` — zero-coupon rates used for discounting and forward-related calculations

Users can replace the sample input files with their own market data, provided that the CSV files keep the same structure as the ones included in `MarketData/`.
To run the notebook correctly, the current column layout and overall file format must be respected.

---

## Example Output

**CAC40 Implied SABR Volatility Surface**:

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/c7e57317-6c71-471c-b7a5-0f27362fb942" />


---

## Best use case

Use this notebook when working with **equity option market data** and calibrating the **SABR model** to **market implied volatilities** in order to fit an **implied volatility surface**.

---

## How to Use

Clone the repository:

```bash
git clone https://github.com/Idriss-Afra/SABR-Implied-Volatility.git
cd SABR-Implied-Volatility
jupyter notebook
```

Then open:

* `SABR Volatility Model.ipynb`

---

## Author

**Idriss Afra**
