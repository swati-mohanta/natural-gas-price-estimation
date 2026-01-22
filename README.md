# Natural Gas Price Estimation & Storage Contract Pricing

This repository contains a quantitative research prototype developed as part of the **JPMorgan Quantitative Research Virtual Experience (Forage)**.  
The project focuses on modeling natural gas prices with seasonality and valuing a commodity storage contract under realistic operational constraints.

---

## 📌 Project Overview

Commodity storage contracts derive their value from the difference between the price at which a commodity is purchased (injection) and sold (withdrawal), minus all associated costs.  
This project is divided into two tasks:

- **Task 1:** Estimate natural gas prices for any given date using historical monthly data and seasonal trends.
- **Task 2:** Use the estimated prices to value a natural gas storage contract with multiple injection and withdrawal dates, capacity limits, and storage costs.

The final model is intended as a **prototype pricing tool** suitable for further validation before production use.

---

## 🧠 Task 1 – Natural Gas Price Estimation

### Objective

To estimate the purchase or sale price of natural gas on **any arbitrary date**, including extrapolation up to one year into the future.

### Methodology

* Historical **monthly end-of-period prices** are loaded from a CSV file.
* Prices are visualized to identify **seasonal patterns**.
* Linear interpolation is applied to estimate prices between observed dates.
* A **month-wise seasonal adjustment** captures recurring winter and summer price effects.
* A function `estimate_price(date)` returns the estimated price for any input date.

### Output

* Historical price visualization
* Seasonal trend analysis
* One-year price extrapolation
* Callable price estimation function

---

## 🧮 Task 2 – Commodity Storage Contract Pricing

### Objective

To value a natural gas storage contract by aggregating all cash flows associated with buying, storing, and selling gas.

### Key Features

* Supports **multiple injection and withdrawal dates**
* Enforces:

  * Injection and withdrawal rate limits
  * Maximum storage capacity
* Accounts for:

  * Purchase and sale cash flows
  * Fixed monthly storage costs
* Produces:

  * Total contract value
  * Detailed cashflow breakdown by date
  * Storage level tracking over time

### Pricing Logic

The value of the contract is calculated as:

```
Contract Value =
(Sale Proceeds − Purchase Costs)
− Storage Costs
```

A negative value indicates the storage strategy is not economically viable under the given assumptions.

### Interpretation

The model is designed to:

* Identify **profitable vs. unprofitable** storage strategies
* Respond sensibly to changes in prices, costs, and operational constraints
* Reflect realistic commodity market behavior

---

## 🛠 Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* SciPy

---

## ▶️ How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/swati-mohanta/natural-gas-price-estimation.git
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Open the notebooks:

   * `natural_gas_price_estimation.ipynb`
   * `storage_contract_pricing.ipynb`

---

## 📊 Example Output

* Estimated natural gas prices for arbitrary dates
* Cashflow tables showing injection, withdrawal, and storage costs
* Near breakeven or negative contract values under realistic assumptions, reflecting true market conditions

---

## ⚠️ Assumptions & Limitations

* No transport delays
* Zero interest rates (no discounting)
* No market holidays or weekends
* No gas losses during storage
* Prices are estimated using historical trends and seasonality

These simplifications are intentional and appropriate for a prototype model.

---

## 📈 Potential Improvements

* Incorporate stochastic price simulations
* Add interest rate discounting
* Optimize injection and withdrawal schedules
* Model uncertainty in demand and weather
* Integrate real-time market data feeds

---

## 📎 Disclaimer

This project is for **educational and demonstration purposes only**.
It does not constitute financial advice or a production-ready trading system.

---

## ⭐ Acknowledgements

This project was completed as part of the **JPMorgan Quantitative Research Virtual Experience Program (Forage)**.
