# Credit Risk Prediction App

This project is a FastAPI-based credit risk assessment app that predicts loan default risk from applicant and loan metadata.

## Features
- FastAPI backend with `/predict` endpoint
- Static HTML/JS frontend for risk assessment
- Trained credit risk model and threshold saved as pickle files

## Run locally

```bash
pip install -r requirements.txt
python -m uvicorn mai:app --host 0.0.0.0 --port 8000
```

Then open:

```text
http://localhost:8000/
```

## Deploy to GitHub + hosting

This app cannot be deployed directly on GitHub Pages because it uses a Python backend and dynamic API routes.

Recommended path:
1. Push this repository to GitHub
2. Deploy from GitHub to a Python host such as Render, Railway, or Fly.io
3. Set the app to run with:

```bash
python -m uvicorn mai:app --host 0.0.0.0 --port 8000
```

## Files
- `mai.py` - FastAPI app
- `static/` - frontend files
- `credit_risk_model.pkl` - trained model
- `best_threshold.pkl` - threshold value
- `credit_risk_dataset.csv` - dataset used for training

## Notes
The app writes and reads the model files from the project directory, so they should remain in the repo root.
