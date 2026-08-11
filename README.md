# 🔥 Forest Fire Weather Index (FWI) Predictor

A machine learning web application that predicts the **Fire Weather Index (FWI)** for Algerian forest regions using a **Ridge Regression** model, served through a **Flask** REST API with a modern dark-themed UI.

---

## 📸 Preview

> Enter environmental parameters (temperature, humidity, wind speed, etc.) and get an instant FWI score with risk level classification — **Low / Moderate / High / Extreme**.

---

## ✨ Features

- 🔮 **ML-Powered Prediction** — Ridge Regression model trained on the Algerian Forest Fires dataset
- 🌡️ **Multi-Parameter Input** — Weather + FWI index inputs (Temperature, RH, Wind Speed, Rain, FFMC, DMC, ISI)
- 🎨 **Premium Dark UI** — Glassmorphism card, animated ember particles, fire gradient theme
- 📊 **Risk Classification** — Color-coded risk level (🟢 Low / 🟡 Moderate / 🟠 High / 🔴 Extreme)
- ⚡ **Fast Flask API** — Lightweight REST endpoint for prediction
- 📱 **Responsive Design** — Works on desktop and mobile

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Backend** | Python, Flask |
| **ML Model** | Ridge Regression (scikit-learn) |
| **Preprocessing** | StandardScaler (scikit-learn) |
| **Frontend** | HTML5, Vanilla CSS, Jinja2 |
| **Font** | Google Fonts — Outfit |
| **Deployment** | Gunicorn (production WSGI) |

---

## 📁 Project Structure

```
Forest Fire/
│
├── application.py                          # Flask app — routes & prediction logic
├── requirements.txt                        # Python dependencies
├── README.md                               # Project documentation
│
├── templates/
│   ├── home.html                           # Prediction form UI (main page)
│   └── index.html                          # Legacy landing page
│
├── models/
│   ├── ridge.pkl                           # Trained Ridge Regression model
│   └── scaler.pkl                          # Fitted StandardScaler
│
├── dataset/
│   └── Algerian_forest_fires_cleaned_dataset.csv   # Cleaned training dataset
│
└── notebooks/
    ├── 2.0-EDA And FE Algerian Forest Fires.ipynb  # Exploratory Data Analysis
    └── 3.0-Model Training.ipynb                    # Model training & evaluation
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- pip

### 1. Clone the repository

```bash
git clone https://github.com/your-username/forest-fire-fwi-predictor.git
cd forest-fire-fwi-predictor
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the application

```bash
python application.py
```

### 5. Open in browser

```
http://127.0.0.1:5000
```

---

## 🌐 API Reference

### `GET /`
Returns the FWI prediction form (home page).

---

### `POST /predictdata`
Submits input parameters and returns the predicted FWI score.

**Form Parameters:**

| Parameter | Type | Description | Example |
|---|---|---|---|
| `Temperature` | float | Air temperature in °C | `29` |
| `RH` | float | Relative Humidity (%) | `57` |
| `Ws` | float | Wind speed in km/h | `18` |
| `Rain` | float | Daily rainfall in mm | `0` |
| `FFMC` | float | Fine Fuel Moisture Code | `85.9` |
| `DMC` | float | Duff Moisture Code | `26.2` |
| `ISI` | float | Initial Spread Index | `6.5` |
| `Classes` | int | Fire class (0 = Low, 1 = High) | `0` |
| `Region` | int | Region (0 = Bejaia, 1 = Sidi-Bel Abbès) | `0` |

**Response:** Renders `home.html` with the predicted FWI value and risk level.

---

## 📊 Dataset

**Algerian Forest Fires Dataset**

- **Source:** UCI Machine Learning Repository
- **Regions:** Bejaia (northeast Algeria) & Sidi-Bel-Abbès (northwest Algeria)
- **Period:** June 2012 – September 2012
- **Instances:** 244 (122 per region)
- **Target Variable:** FWI (Fire Weather Index)

The dataset contains meteorological data and FWI system components observed daily over the summer fire season.

---

## 🧠 Model Details

| Property | Value |
|---|---|
| **Algorithm** | Ridge Regression |
| **Preprocessing** | StandardScaler (zero mean, unit variance) |
| **Serialization** | Python `pickle` |
| **Training Notebook** | `notebooks/3.0-Model Training.ipynb` |

The model was selected after comparing multiple regression algorithms. Ridge regularization was applied to handle multicollinearity among the FWI system features.

---

## 🔴 Risk Level Classification

| FWI Score | Risk Level |
|---|---|
| < 5 | 🟢 Low Risk |
| 5 – 14.9 | 🟡 Moderate Risk |
| 15 – 29.9 | 🟠 High Risk |
| ≥ 30 | 🔴 Extreme Risk |

---

## 📦 Dependencies

```
Flask
numpy
pandas
scikit-learn
gunicorn
```

---

## 🤝 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👤 Author

**Sanjeev Kumar Patel**

---

> Built as part of an AIML course project — demonstrating end-to-end ML model deployment with Flask.
