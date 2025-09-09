![Python](https://img.shields.io/badge/Python-3.11-informational)
![License](https://img.shields.io/badge/License-MIT-brightgreen)
![CI](![CI](https://img.shields.io/github/actions/workflow/status/<tu_usuario>/<tu_repo>/lint.yml?label=lint))

# Bank Marketing Campaigns — Term Deposit Conversion

**Author:** Oscar I. Ruelas · **Last update:** 2025-09-09

Live dashboard → [https://public.tableau.com/app/profile/oscar.ruelas/viz/Oscar_Ruelas_Project_Dashboard/BankTermDepositCampaign?publish=yes](https://public.tableau.com/app/profile/oscar.ruelas/viz/Oscar_Ruelas_Project_Dashboard/BankTermDepositCampaign?publish=yes)

This repository packages the analysis, documentation, and reproducible setup for a marketing-analytics project based on the UCI/Kaggle *Bank Marketing* dataset. The goal: understand which customer segments and call characteristics predict term-deposit subscriptions, and turn those insights into actions for better campaign targeting.

## 🔎 Highlights (from the analysis & EDA)
- **Dataset:** 11,162 records × 17 features (subset used for dashboard), historical phone campaigns.
- **Overall conversion:** ≈ 11–12% across campaigns.
- **Contact channel:** Mobile calls outperform landlines (≈2× conversion).
- **Call duration:** Subscribers stay longer on the line on average (~500+ sec vs ~250 sec for non-subscribers).
- **Segments:** Retirees and older age groups (50+) show consistently higher conversion propensity.

These insights are visualized in the Tableau dashboard (link above) and explained in the docs inside `docs/`.

## 📁 Repo Structure
```
.
├── data/
│   ├── raw/          # original data (not tracked in git)
│   └── processed/    # cleaned/engineered data (not tracked in git)
├── docs/             # project docs (scoping, EDA, final report)
├── notebooks/        # exploratory notebooks / notes
├── reports/          # exported figures/tables
├── src/              # reusable Python modules (ETL, modeling, eval)
├── requirements.txt
├── .gitignore
└── README.md
```

> Tip: keep large/raw data out of version control. Consider Git LFS if you must track binaries.

## 🧪 Reproducibility (local)
```bash
# 1) Create environment
python -m venv .venv && source .venv/bin/activate  # (Windows: .venv\Scripts\activate)
pip install -r requirements.txt

# 2) Place raw CSV into data/raw (not included in repo)
# e.g., bank-full.csv

# 3) Run your ETL / EDA
# (Add your scripts to src/ and notebooks/ as you iterate)
```

## 🧰 Tech Stack
- **Python:** pandas, numpy, matplotlib, scikit-learn
- **BI:** Tableau Public (see dashboard)
- **Docs:** `.docx` reports in `docs/`

## 📊 What to look at
- **Dashboard:** conversion by job, age group, contact channel, and call duration.
- **EDA:** distribution shifts, outliers, and a quick calendar view for activity.
- **Next steps:** add a simple logistic regression baseline, compare with tree-based models, and expose a pre-call conversion score.

## 📄 Documents
Key deliverables are in `docs/` (scoping, data curation, EDA, and final report).

## 🔜 Roadmap
- Add `src/` modules for ETL and training (`src/etl.py`, `src/model.py`).
- Save a trained baseline model and inference script (`src/predict.py`).
- Export a lightweight CSV of aggregated metrics used by the Tableau dashboard.
- Attach screenshot thumbnails of the Tableau sheets in `reports/` for the README.

## 📫 Contact
Questions or feedback? Open an issue or reach out via LinkedIn.


## 🚀 Quickstart (ETL)
```bash
pip install -r requirements.txt
# Put bank-full.csv under data/raw/
python -m src.etl
python -c "from src.predict import score_call; print(score_call(480,55))"
```
