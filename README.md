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

### 2) Install dependencies
```bash
pip install -U pip
pip install -r requirements.txt

### 3) Run the app
```bash
streamlit run app.py

Once started, Streamlit will open a local web page (usually http://localhost:8501).
Use the sidebar to input patient symptoms and view the model’s recommendation.
