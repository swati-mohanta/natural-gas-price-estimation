# Natural Gas Price Estimation

This project models historical natural gas prices and estimates prices for any given date using seasonal patterns and interpolation.

## 📌 Project Overview
- Uses historical monthly natural gas prices
- Identifies seasonal trends (higher winter demand, lower summer demand)
- Interpolates prices for arbitrary dates
- Extrapolates prices one year into the future

This project was completed as part of the **JPMorgan Quantitative Research Virtual Experience (Forage)**.

## 🛠️ Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- SciPy

## 📈 Methodology
1. Load and visualize historical price data
2. Identify seasonality using month-wise averages
3. Apply linear interpolation for price estimation
4. Adjust estimates using seasonal factors
5. Extrapolate future prices

## ▶️ Usage
```python
from price_estimation import estimate_price

estimate_price("2025-02-15")
````

## 📊 Output

* Historical price visualization
* Seasonal trend analysis
* One-year price extrapolation

## ⚠️ Disclaimer

This project is for educational purposes only and does not constitute financial advice.
