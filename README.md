# Heart Disease Prediction

A Streamlit application that uses a saved K-nearest neighbors model to predict
heart disease risk from user-provided measurements.

## Run locally on Windows

Use Python 3.12 for the dependency environment. The saved model and scaler were
created with scikit-learn 1.6.1, which is pinned in `requirements.txt`.

```powershell
git clone https://github.com/ghoshshrey/HeartDisease.git
cd HeartDisease
py -3.12 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m streamlit run app.py
```

Open the local URL printed by Streamlit, usually http://localhost:8501.
Run the command from the project folder so the app can find its model files.
Using `python -m streamlit` also avoids needing the Streamlit launcher on PATH.

## Using the app

Enter age, sex, chest pain type, resting blood pressure, cholesterol, fasting
blood sugar, resting ECG, maximum heart rate, exercise-induced angina, Oldpeak,
and ST slope. Click **Predict** to display the model's high- or low-risk result.

## Project files

| File | Purpose |
| --- | --- |
| `app.py` | Streamlit interface and prediction pipeline |
| `HeartdiseaseFinal.ipynb` | Data analysis, model training, and evaluation notebook |
| `knn_heart_model.pkl` | Saved K-nearest neighbors classifier |
| `heart_scaler.pkl` | Saved feature scaler |
| `heart_columns.pkl` | Expected model input columns |
| `requirements.txt` | Python dependencies |

The training notebook expects `heart.csv` in its working directory. The dataset
is not included; the Streamlit app uses the bundled saved prediction artifacts.

Loading these artifacts with a different scikit-learn version may produce a
version warning. Use the pinned version when setting up a new environment.
