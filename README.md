# 🔥 Forest Fire Weather Index (FWI) Predictor

---

## 🌐 Live Demo

> 🔗 **[https://forestfire-hhdtd2d4f3dbdnf5.centralindia-01.azurewebsites.net/predictdata](https://forestfire-hhdtd2d4f3dbdnf5.centralindia-01.azurewebsites.net/predictdata)**

---

## ✨ Features

- 🔮 **ML-Powered Prediction** — Ridge Regression model trained on the Algerian Forest Fires dataset
- 🌡️ **9-Parameter Input** — Temperature, Humidity, Wind Speed, Rain, FFMC, DMC, ISI, Class, Region
- 📊 **Risk Classification** — Color-coded risk level (🟢 Low / 🟡 Moderate / 🟠 High / 🔴 Extreme)
- 🎨 **Premium Dark UI** — Glassmorphism card, animated ember particles, fire gradient theme
- ☁️ **Azure Deployed** — Hosted on Microsoft Azure App Service with Gunicorn WSGI server
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
| **WSGI Server** | Gunicorn |
| **Cloud Platform** | Microsoft Azure App Service |

---

## 📁 Project Structure

```
Forest Fire/
│
├── application.py                                    # Flask app — routes & prediction logic
├── requirements.txt                                  # Python dependencies
├── README.md                                         # Project documentation
│
├── templates/
│   ├── home.html                                     # Prediction form UI (main page)
│   └── index.html                                    # Legacy landing page
│
├── models/
│   ├── ridge.pkl                                     # Trained Ridge Regression model
│   └── scaler.pkl                                    # Fitted StandardScaler
│
├── dataset/
│   └── Algerian_forest_fires_cleaned_dataset.csv     # Cleaned training dataset
│
└── notebooks/
    ├── 2.0-EDA And FE Algerian Forest Fires.ipynb    # Exploratory Data Analysis & Feature Engineering
    └── 3.0-Model Training.ipynb                      # Model training & evaluation
```

---

## 🚀 Run Locally

### Prerequisites

- Python 3.8+
- pip

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/sanjeev-kumar-patel/Forest-Fire.git
cd Forest-Fire

# 2. Create a virtual environment
python -m venv venv

# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Start the app
python application.py
```

Then open **http://127.0.0.1:5000** in your browser.

---

## ☁️ Azure Deployment

This app is deployed on **Microsoft Azure App Service**.

### Deployment Steps Used

1. Created an **Azure App Service** (Linux, Python 3.x runtime)
2. Configured the startup command:
   ```
   gunicorn --bind=0.0.0.0 --timeout 600 application:app
   ```
3. Deployed via:
   > **⚠️ Add how you deployed** — Choose whichever applies:
   > - `GitHub Actions (CI/CD)`
   > - `Azure CLI (az webapp up)`
   > - `VS Code Azure Extension`
   > - `ZIP deploy via Azure Portal`

4. Set **environment variables** in App Service Configuration (if any):
   > **⚠️ Add any environment variables you configured in Azure Portal here**, e.g.:
   > ```
   > SCM_DO_BUILD_DURING_DEPLOYMENT = true
   > ```

### Live URL

```
https://forestfire-hhdtd2d4f3dbdnf5.centralindia-01.azurewebsites.net/predictdata
```

---

## 🌐 API Reference

### `GET /`
Returns the FWI prediction form (home page).

---

### `POST /predictdata`
Submits parameters and returns the predicted FWI score.

**Form Parameters:**

| Parameter | Type | Description | Example |
|---|---|---|---|
| `Temperature` | float | Air temperature (°C) | `29` |
| `RH` | float | Relative Humidity (%) | `57` |
| `Ws` | float | Wind speed (km/h) | `18` |
| `Rain` | float | Daily rainfall (mm) | `0` |
| `FFMC` | float | Fine Fuel Moisture Code | `85.9` |
| `DMC` | float | Duff Moisture Code | `26.2` |
| `ISI` | float | Initial Spread Index | `6.5` |
| `Classes` | int | Fire class (0 = Low, 1 = High) | `0` |
| `Region` | int | Region (0 = Bejaia, 1 = Sidi-Bel Abbès) | `0` |

**Response:** Renders the prediction page with FWI score and risk classification.

---

## 📊 Dataset

**Algerian Forest Fires Dataset**

- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Algerian+Forest+Fires+Dataset++)
- **Regions:** Bejaia (northeast Algeria) & Sidi-Bel-Abbès (northwest Algeria)
- **Period:** June 2012 – September 2012
- **Instances:** 244 (122 per region)
- **Target Variable:** FWI (Fire Weather Index)

---

## 🧠 Model Details

| Property | Value |
|---|---|
| **Algorithm** | Ridge Regression |
| **Preprocessing** | StandardScaler (zero mean, unit variance) |
| **Serialization** | Python `pickle` |
| **Training Notebook** | `notebooks/3.0-Model Training.ipynb` |

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

## 👤 Author

**Sanjeev Kumar Patel**

> **⚠️ Optionally add your links:**
> - GitHub: [github.com/sanjeev-kumar-patel](https://github.com/sanjeev-kumar-patel)
> - LinkedIn: `https://linkedin.com/in/your-profile`

---

> Built as part of an AIML course project — demonstrating end-to-end ML model deployment on Microsoft Azure.
