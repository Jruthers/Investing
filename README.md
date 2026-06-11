# Investment Growth Calculator

A lightweight, offline-capable investment growth calculator built as a single HTML file. No dependencies to install, no account required — open in any browser and use immediately.

## Usage

Download `investment_growth.html` and open it in any browser. On iPhone, save to Files and open via Safari's share sheet, then optionally add to your home screen for app-like access.

## What it calculates

### Future Value (FV)

The core projection uses the standard **future value of a lump sum with regular contributions**:

```math
FV = P(1 + r)^n + C \cdot \frac{(1 + r)^n - 1}{r}
```

Where:
- `P` = initial portfolio value (£)
- `C` = monthly contribution (£)
- `r` = monthly interest rate (annual rate ÷ 12)
- `n` = number of months

The first term compounds the initial lump sum; the second is the future value of an annuity — each monthly contribution compounding forward to the end of the horizon.

### Total growth (all-time)

To account for gains already made before the projection starts, total growth is reported as:

```
All-time growth = (Final FV − Total contributed from today) + Prior gains
```

### Milestone detection

For each target threshold (£50k, £100k, £250k, £500k, £1m), the calculator steps through the annual series and returns the first year the portfolio value meets or exceeds it.

### Rate comparison panel

The bottom panel recalculates FV at four fixed rates simultaneously:

| Rate | Rationale |
|------|-----------|
| 5%  | Conservative / bonds-heavy |
| 7%  | Moderate balanced portfolio |
| 10% | Long-run historical S&P 500 average |
| 16% | S&P 500 actual 8-year return (2017–2024) |

## Parameters

| Slider | Default | Range |
|--------|---------|-------|
| Initial portfolio value | £18,000 | £0 – £250,000 |
| Monthly contribution | £250 | £0 – £2,000 |
| Annual return | 5% | 1% – 20% |
| Time horizon | 30 years | 1 – 50 years |
| Prior gains already made | £9,100 | £0 – £50,000 |

## Limitations & assumptions

- Returns are assumed **constant** year-on-year — real markets are volatile
- No adjustment for **inflation** — real purchasing power of the final figure will be lower
- No modelling of **tax** (ISA wrapper assumed; adjust manually if not)
- Monthly contributions assumed at start of each month

## Disclaimer

For illustrative purposes only. Not financial advice.

<img width="903" height="853" alt="image" src="https://github.com/user-attachments/assets/29eaaa8f-ae39-41c5-86dc-46e321745760" />
