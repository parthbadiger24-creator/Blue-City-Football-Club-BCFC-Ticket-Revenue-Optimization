# Blue City FC — Ticket Revenue Optimisation (Excel Solver LP)

> Linear-programming model in **Excel Solver** maximising Blue City FC's ticket revenue subject to stadium, promotional-inventory and demand constraints. Includes shadow-price and sensitivity analysis.

---

## 🎯 Problem

Blue City FC sells **VIP** (£350) and **regular** (£100) match tickets. Each ticket comes with a free promotional T-shirt (VIP = 2 shirts, regular = 1 shirt). The club must decide how many of each to sell to **maximise revenue** given:

- Stadium capacity: **27,500** seats
- T-shirt inventory: **35,000** shirts
- VIP demand cap: **9,000** · Regular demand cap: **25,000**

## 🧮 LP Formulation

Let `V` = VIP tickets sold, `R` = Regular tickets sold.

```text
Maximise   Z = 350·V + 100·R

Subject to
  V + R    ≤ 27,500      (stadium capacity)
  2V + R   ≤ 35,000      (t-shirt inventory)
  V        ≤ 9,000       (VIP demand cap)
  R        ≤ 25,000      (regular demand cap)
  V, R ≥ 0
```

## 📈 Results

| Metric | Value |
|---|---|
| Optimal VIP tickets (V*) | **9,000** |
| Optimal Regular tickets (R*) | **17,000** |
| **Maximum revenue** | **£4,850,000** |
| Binding constraints | VIP cap · T-shirt inventory |
| Slack — stadium | 1,500 seats |
| Slack — regular demand | 8,000 tickets |

### Shadow-price analysis (sensitivity)

- **T-shirt shadow price = £100** — losing 1 shirt costs BCFC £100 in revenue (must drop 1 regular ticket sale).
- **Scenario: shirts ↑ from 35,000 → 36,000** → additional revenue = 1,000 × £100 = **+£100,000** (new optimum £4.95M).
- The £100 shadow price holds until ~36,500 shirts, when stadium capacity starts to bind.

## 🧰 Tech

`Microsoft Excel` · `Solver` (Simplex LP) · Sensitivity + Answer reports

## 📁 Repo Structure

```text
.
├── model/BCFC_SOLVED.xlsx              # the workable Solver model
├── docs/
│   └── BCFC_Linear_Programming_Guide.pdf   # full write-up (Parts A–D)
├── img/
└── README.md
```

## ▶️ How to open

1. Open `model/BCFC_SOLVED.xlsx` in Excel
2. `Data` → `Solver` — parameters are already configured (Set `D5` Max, By changing `B5:C5`, constraints as above, method **Simplex LP**)
3. Click **Solve** to reproduce £4.85M

## 📄 Report

Full four-part solution (formulation, Solver run, shadow prices, scenario) → [`docs/BCFC_Linear_Programming_Guide.pdf`](docs/BCFC_Linear_Programming_Guide.pdf)

---

<sub>MIT-licensed · Author: [Parth Badiger](https://github.com/parthbadiger24-creator)</sub>
