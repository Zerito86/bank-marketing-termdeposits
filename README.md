# Bank Marketing Campaigns — Term Deposit Conversion

Live Dashboard → https://public.tableau.com/app/profile/oscar.ruelas/viz/Oscar_Ruelas_Project_Dashboard/BankTermDepositCampaign?publish=yes

![Project preview](reports/tableau_hero.png)

![Python](https://img.shields.io/badge/Python-3.11-informational)
![Tableau](https://img.shields.io/badge/Tableau-Public-blue)
![License](https://img.shields.io/badge/License-MIT-brightgreen)
![CI](https://img.shields.io/github/actions/workflow/status/YOUR_GITHUB_USER/YOUR_REPO/lint.yml?label=lint)

## Problem
Phone campaigns are expensive; we want to **increase term-deposit conversion** by targeting the right segments and focusing call resources where they matter.

## Data
UCI/Kaggle Bank Marketing dataset (~40k rows, 20+ features). This repo uses a curated subset and engineered features (e.g., `age_group`, unknown flags). See `/docs` for **Scoping**, **Data Curation**, **EDA**, and **Final Report**.

## Key Insights
- Mobile channel outperforms landline; longer calls correlate with subscription.
- Retirees and 50+ show higher propensity.
- Conversion baseline ~11–12%, with strong lift on prioritized segments.

## Reproducibility
```bash
python -m venv .venv && source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
# place the raw CSV under data/raw/ (e.g., bank-full.csv)
python -m src.etl
python -m src.model_baseline  # trains baseline, prints metrics, saves artifacts/
