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

## Deploy with Vercel

GitHub stores the source code; it does not run this Python backend. GitHub Pages is only for static sites, so it cannot serve this app's `/predict` API.

1. Push the project to GitHub.
2. In Vercel, choose **Add New Project** and import this GitHub repository.
3. Keep the project root set to the repository root. Vercel detects `app.py` and deploys the FastAPI app.
4. Deploy. New pushes to the connected GitHub branch will trigger deployments.

The model files (`credit_risk_model.pkl` and `best_threshold.pkl`) must be committed to the repository because the app loads them at startup. The static frontend is served by FastAPI from `static/`.

## Files
- `mai.py` - FastAPI app
- `static/` - frontend files
- `credit_risk_model.pkl` - trained model required at deployment
- `best_threshold.pkl` - threshold value required at deployment
- `credit_risk_dataset.csv` - dataset used for training

## Notes
The app writes and reads the model files from the project directory, so they should remain in the repo root.
