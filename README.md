# Crime Intensity Prediction

A machine learning project that predicts whether a reported crime in India is likely to be classified as **high intensity** (homicide, assault, sexual assault, robbery, kidnapping, domestic violence, arson, firearm offense) or **low intensity**, based on historical case data.

**[Live demo →](https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/)**

## About

This project analyzes 9,919 police case records across 29 Indian cities (2020) and trains a classifier to estimate crime intensity from features like city, time of occurrence, victim age/gender, and weapon used.

Three models were benchmarked:

| Model | Role |
|---|---|
| Logistic Regression | Baseline |
| Gradient Boosting | Tuned via `GridSearchCV` |
| **Random Forest (200 trees)** | **Final model** — trained on a class-balanced (upsampled) dataset |

## Files

- `Crime_Intensity_prediction.ipynb` — full analysis notebook: data cleaning, feature engineering, model training/comparison, evaluation, and an interactive Gradio predictor
- `crime_dataset_india.csv` — source dataset (9,919 records)
- `index.html`, `data.json` — a static frontend that mirrors the notebook's interactive predictor, so the project can be explored without running Python or Gradio

## Running the notebook

```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib gradio ipywidgets
jupyter notebook Crime_Intensity_prediction.ipynb
```

## Running the frontend locally

The frontend is fully static (no build step, no server-side code) — it reads `data.json` in the browser and reproduces the same city/crime/gender filtering logic used in the notebook's Gradio interface.

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Or enable **GitHub Pages** in this repo's Settings → Pages → set source to the `main` branch, and it will be live at `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`.

## Disclaimer

This is an academic project. Predictions reflect patterns in one historical dataset and are not a real-world safety, policing, or profiling tool.
