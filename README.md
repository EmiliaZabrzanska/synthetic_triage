# Synthetic Triage Prediction App (Streamlit + synthcity)

A demo Streamlit app that:
1) generates synthetic data using **synthcity** (CTGAN),
2) trains a **RandomForestClassifier** on the synthetic data, and
3) serves an interactive UI to predict a triage recommendation.

> ⚠️ **Educational demo only — not medical advice.** Do not use for real clinical decisions.

## Features
- One-time model build at app startup (`@st.cache_resource`)
- Clean UI for inputs (age, symptoms, days sick)
- Class probabilities visualised as a bar chart
- 100% synthetic training data (seeded + CTGAN)

## Quick Start

### 1) Create & activate a virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
```

### 2) Install dependencies
```bash
pip install -U pip
pip install -r requirements.txt
pip install synthcity
```

### 3) Run the app
```bash
streamlit run app.py
```

Once started, Streamlit will open a local web page (usually http://localhost:8501). Use the sidebar to input patient symptoms and view the model’s recommendation.

## Project Structure
```
.
├─ app.py             # Main Streamlit application
├─ requirements.txt     # Dependencies
├─ README.md            # Documentation
└─ .gitignore           # Ignored files and folders
```

## Requirements
- Python ≥ 3.9
- Streamlit ≥ 1.28
- pandas ≥ 2.0
- scikit-learn ≥ 1.2
- synthcity ≥ 0.2.21
- PyTorch (auto-installed by synthcity or manually installed per your system)

## How it works

1) Seed data is defined in app.py with simple symptom and outcome examples.
2) Synthetic data is generated using synthcity’s CTGAN plugin.
3) A RandomForestClassifier is trained on this synthetic dataset.
4) The Streamlit interface collects user input and predicts a triage outcome.
5) Prediction confidence scores are displayed as a bar chart for transparency.

## Acknowledgements

- synthcity by the Van der Schaar Lab
- Streamlit for building simple, interactive web apps
- scikit-learn for the machine learning backend
