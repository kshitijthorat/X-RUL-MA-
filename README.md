# X-RUL-MA: Explainable RUL-based Maintenance Assistance

An Explainable AI Framework for Remaining Useful Life (RUL) Prediction and Intelligent Maintenance Recommendations Using Machine Learning, SHAP, and Generative AI.

---

## 📌 Project Overview

**X-RUL-MA** is a research-first, end-to-end framework designed to address the challenges of traditional reactive and fixed-interval equipment maintenance. By combining **Machine Learning** for accurate Remaining Useful Life (RUL) prediction, **Explainable AI (SHAP)** for feature attribution analysis, and **Generative AI (LLM)** for natural language maintenance decision support, X-RUL-MA transforms raw sensor degradation signals into actionable intelligence.

---

## ⚠️ Dataset Limitation & Notice

- **Primary Dataset**: NASA Commercial Modular Aero-Propulsion System Simulation (**C-MAPSS**), subset **FD001**.
- **Data Nature**: Simulated turbofan aircraft engine sensor degradation data.
- **Important**: This framework is evaluated on simulated aerospace turbofan engines. It does **not** represent real-world automotive or OBD-II engine data. Future validation on real industrial automotive sensor data is identified as future work.

---

## 🔬 Core Research Pipeline

```text
NASA C-MAPSS FD001
        ↓
Data Exploration & Preprocessing
        ↓
RUL Target Label Generation
        ↓
Feature Engineering & Selection
        ↓
ML Model Benchmark (Linear Regression, Random Forest, XGBoost)
        ↓
Model Comparison (MAE, RMSE, R²)
        ↓
SHAP Explainability Analysis (Sensor Attribution)
        ↓
LLM Decision Support (Maintenance Recommendations)
        ↓
FastAPI Backend & React Dashboard
```

---

## 🏛️ Technology Stack

- **Language & Runtime**: Python 3.13+
- **Data & Processing**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Machine Learning**: Scikit-Learn, XGBoost
- **Explainable AI**: SHAP
- **API Backend**: FastAPI, Uvicorn, Pydantic
- **Database**: PostgreSQL (SQLAlchemy)
- **Frontend**: React, Vite, Tailwind CSS, Recharts

*Note: No Java, Spring Boot, or Jupyter Notebooks are used.*

---

## 📁 Repository Structure

```text
engine-rul-research/
│
├── data/
│   ├── raw/                 # NASA C-MAPSS FD001 dataset text files
│   └── processed/           # Processed datasets with generated RUL target labels
│
├── src/                     # Core Python ML and data processing packages
│   ├── config.py            # Centralized project configurations and paths
│   ├── data/                # Loaders, exploration, preprocessing, and RUL calculation
│   ├── features/            # Feature engineering and scaling
│   ├── models/              # Model builders, training logic, and inference handlers
│   ├── evaluation/          # Evaluation metrics (MAE, RMSE, R2) and comparisons
│   ├── explainability/      # SHAP feature attribution and global/local explanations
│   └── llm/                 # Prompt engineering and LLM recommendation integration
│
├── scripts/                 # Standalone reproducible execution scripts for each phase
│
├── models/                  # Saved model artifacts, metadata, and feature lists
│   ├── linear_regression/
│   ├── random_forest/
│   └── xgboost/
│
├── results/                 # Experimental outputs
│   ├── metrics/             # Quantitative metrics (CSV/JSON)
│   ├── figures/             # Correlation heatmaps, error plots, sensor trends
│   ├── shap/                # SHAP summary and waterfall plots
│   ├── tables/              # Model and feature selection comparison tables
│   └── experiments/         # Detailed tracking of experiment runs
│
├── api/                     # FastAPI backend application
│   ├── routes/              # Health, prediction, explanation, recommendation endpoints
│   ├── schemas/             # Pydantic request and response models
│   └── services/            # Service handlers connecting API to ML and LLM engines
│
├── database/                # PostgreSQL models and connection management
├── frontend/                # React + Vite + Tailwind CSS dashboard
├── tests/                   # Automated unit and integration tests
├── docs/                    # Architecture docs, methodology, and research paper drafts
├── .env.example             # Environment variables template
├── .gitignore               # Git exclusion rules
├── requirements.txt         # Project dependency list
├── README.md                # Project documentation
└── LICENSE                  # Open-source license (MIT)
```

---

## 🚀 Quick Start (Phase 0 Setup)

### 1. Environment Setup

```powershell
# Create Python virtual environment
python -m venv venv

# Activate virtual environment (Windows PowerShell)
.\venv\Scripts\Activate.ps1
```

### 2. Install Initial Dependencies

```powershell
.\venv\Scripts\pip.exe install -r requirements.txt
```

### 3. Verify Setup

```powershell
.\venv\Scripts\python.exe -c "import numpy; import pandas; import matplotlib; import seaborn; import sklearn; print('Phase 0 Verification Successful!')"
```

---

## 📜 Research Questions & Hypotheses

- **RQ1**: Which machine-learning model provides the best Remaining Useful Life prediction performance on C-MAPSS FD001?
- **RQ2**: Which sensor parameters contribute most significantly to RUL predictions?
- **RQ3**: Can feature selection reduce the number of sensor inputs while maintaining prediction performance?
- **RQ4**: Can SHAP improve the interpretability of RUL predictions?
- **RQ5**: Does providing SHAP-derived sensor contributions to an LLM produce more consistent and useful maintenance recommendations?

---

## 📄 License

Distributed under the [MIT License](LICENSE).
