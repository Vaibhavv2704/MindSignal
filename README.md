# MindSignal

MindSignal is a student wellness project that estimates a mental health score from self-reported lifestyle, study, sleep, activity, and social media usage data. It is a machine learning demonstration, not a diagnosis or substitute for professional support.

## Project contents

- `index.html`, `style.css`, `script.js` — browser interface
- `main.py` — FastAPI prediction service
- `Mental_Health_Model.pkl` — trained scikit-learn model loaded by the API
- `ML_Project.ipynb` and `Student Social Media And Mental Health Impact.csv` — model exploration and source dataset
- `ML Project.html` — exported project/architecture page

## Run the API locally

Requires Python 3.10 or newer.

```bash
python -m venv .venv
# Windows: .venv\\Scripts\\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload --port 2200
```

Open `http://127.0.0.1:2200/docs` to view the API documentation. The frontend currently sends predictions to the hosted API configured in `script.js`. To use a local API, change `API_BASE` there to `http://127.0.0.1:2200`, then serve the project root with a local web server.

## GitHub Pages and API hosting

The included Pages workflow publishes the static frontend from the repository. GitHub Pages does not run the Python API. The API must be deployed separately to a Python hosting service, and `API_BASE` in `script.js` must point to that service. The configured URL is `https://mansik-santulan-score.onrender.com`.

## Data note

The included CSV contains student-level records. Review its source and license before redistributing it publicly. The model is loaded with joblib; only load trusted model files.

