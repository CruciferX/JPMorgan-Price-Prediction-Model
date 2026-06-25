# JPMorgan Quantitative Research — Virtual Experience

> Python-based financial modeling solutions from the JPMorgan Chase Quantitative Research Virtual Experience Program, covering **credit risk analytics** (FICO score bucketing, default prediction, expected loss) and **commodities pricing** (natural gas price forecasting, contract valuation).

---

## 📁 Project Structure

```
JPMORGANMODEL/
├── company_profile_presentation.py   # Auto-generates JP Morgan themed PPTX
├── FICO_score_bucketing.py           # FICO quantization via Dynamic Programming
├── gas_predictor.py                  # Natural gas price forecasting
├── gas_price_contract.py             # Gas storage contract pricing model
├── sample.py                         # Expected loss prediction (Logistic Regression)
├──
├── loan_data.csv                     # Loan portfolio dataset
├── gas_prices.csv                    # Historical natural gas prices
├── Task 3 and 4_Loan_Data (1).csv    # Extended loan & borrower records
├──
├── default_chart.png                 # Generated: Default rate by bucket chart
├── jpmorgan_logo.png                 # Generated: JP Morgan logo asset
└── JP_Morgan_Quant_Themed_Presentation.pptx  # Generated: Final presentation
```

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib scikit-learn python-pptx
```

### Running the Modules

| Task | Command |
|------|---------|
| FICO Score Bucketing | `python FICO_score_bucketing.py` |
| Expected Loss Prediction | `python sample.py` |
| Gas Price Forecasting | `python gas_predictor.py` |
| Gas Contract Pricing | `python gas_price_contract.py` |
| Generate Presentation | `python company_profile_presentation.py` |

---

## 📊 Module 1: FICO Score Bucketing (`FICO_score_bucketing.py`)

Discretizes continuous FICO scores into optimal rating buckets using **Dynamic Programming** and **MSE minimization**.

**Key Features:**
- Precomputes MSE for all FICO sub-ranges in O(n²)
- Uses DP memoization to find globally optimal 5-bucket partition
- Maps scores to discrete rating labels (B1–B5)
- Calculates Probability of Default (PD) per bucket

```python
# Output
FICO Buckets:
  Bucket 1: 300 to 579
  Bucket 2: 580 to 669
  Bucket 3: 670 to 739
  Bucket 4: 740 to 799
  Bucket 5: 800 to 850
```

---

## 📊 Module 2: Expected Loss Prediction (`sample.py`)

Predicts loan defaults and calculates **Expected Loss (EL)** using Logistic Regression.

**Methodology:**
- Trains logistic regression on loan features
- Predicts Probability of Default (PD) for each loan
- Computes EL = PD × Loan Amount × (1 - Recovery Rate)
- Outputs results to `expected_loss_results.csv`

```python
# Formula
Expected_Loss = PD * loan_amt_outstanding * (1 - recovery_rate)
# Recovery rate assumed: 10%
```

**Evaluation Metrics:** Accuracy, Confusion Matrix, Classification Report

---

## ⛽ Module 3: Natural Gas Price Forecasting (`gas_predictor.py`)

Forecasts natural gas prices using **Polynomial Regression (degree 2)** with seasonality analysis.

**Key Features:**
- Trains on historical price data with datetime features
- Predicts prices for next 12 months
- Includes monthly seasonality boxplot analysis
- Interactive `predict_price(date_string)` function for any date

```python
predict_price("2025-03-31")  # Returns predicted price in ₹
```

---

## ⛽ Module 4: Gas Storage Contract Pricing (`gas_price_contract.py`)

Values gas storage contracts by modeling **injection/withdrawal cash flows**.

**Inputs:**
- Injection & withdrawal dates/volumes
- Price data lookup
- Storage, injection, and withdrawal cost parameters

**Outputs:**
| Metric | Description |
|--------|-------------|
| Buy Cost | Cost of gas purchased at injection |
| Sell Revenue | Revenue from gas sold at withdrawal |
| Storage Cost | Monthly storage fees |
| Net Value | Total contract P&L |

---

## 📈 Module 5: Presentation Generator (`company_profile_presentation.py`)

Auto-generates a **JP Morgan branded PowerPoint presentation** using `python-pptx`.

**Features:**
- Custom JP Morgan blue & gray color theme
- Branded header/footer bars
- Slide types: Title, Content (bullets), Charts
- Auto-generated logo and default rate bar chart
- Speaker notes for presentation guidance

---

## 📊 Results Summary

| Module | Output |
|--------|--------|
| FICO Bucketing | 5 optimal buckets with low intra-bucket MSE |
| Expected Loss | `expected_loss_results.csv` with PD & EL per loan |
| Gas Forecast | 12-month forward price prediction |
| Gas Contract | Net P&L valuation for storage contracts |
| Presentation | `JP_Morgan_Quant_Themed_Presentation.pptx` |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| Python 3.x | Core language |
| Pandas | Data manipulation |
| NumPy | Numerical computing |
| Matplotlib | Visualization |
| scikit-learn | Machine learning (Logistic Regression, Polynomial Regression) |
| python-pptx | PowerPoint automation |

---

## 📌 Key Concepts Applied

- **Dynamic Programming** — Optimal FICO score segmentation
- **MSE Minimization** — Intra-bucket variance reduction
- **Maximum Likelihood Estimation** — Probabilistic bucketing (future extension)
- **Polynomial Regression** — Time-series price forecasting
- **Logistic Regression** — Binary default classification
- **Expected Loss Framework** — PD × LGD × EAD

---

## 📄 License

This project was created as part of the JPMorgan Chase Quantitative Research Virtual Experience Program. For educational purposes only.

---

> **Author:** Tushar Verma
