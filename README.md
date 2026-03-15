# House Price Prediction — Machine Learning Model

A supervised machine learning project that predicts median house prices using the **California Housing dataset**. Three regression models are trained, compared, and the best one is automatically selected and saved for use.

---

## Project Overview

This project builds a complete ML pipeline from scratch:

- Loads and explores the California Housing dataset
- Preprocesses the data (scaling, train/test split)
- Trains and compares **3 regression models**
- Evaluates each model using MAE, MSE, and RMSE
- Saves the best performing model to disk using Pickle

---

## Dataset

**California Housing Dataset** — a well-known benchmark dataset used in the scikit-learn documentation and the book *Hands-On Machine Learning* by Aurélien Géron.

| Feature | Description |
|---|---|
| `MedInc` | Median income of the block group (in $10,000s) |
| `HouseAge` | Median age of houses in the block (years) |
| `AveRooms` | Average number of rooms per household |
| `AveBedrms` | Average number of bedrooms per household |
| `Population` | Total population of the block group |
| `AveOccup` | Average number of people per household |
| `Latitude` | Geographic latitude |
| `Longitude` | Geographic longitude |

**Target:** Median house value (in $100,000s)

---

## Models Compared

| Model | MAE | MSE | RMSE |
|---|---|---|---|
| Linear Regression | 0.3282 | 0.1828 | 0.4275 |
| Decision Tree | 0.3275 | 0.1756 | 0.4191 |
| **Random Forest**  | **0.2263** | **0.0887** | **0.2978** |

> **Random Forest** was selected as the best model based on lowest RMSE.

---

## Tech Stack

- **Python 3**
- **Pandas** — data loading and manipulation
- **NumPy** — numerical computations
- **Scikit-learn** — ML models, preprocessing, and evaluation
- **Pickle** — saving the trained model to disk

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/Dev-1404/House-Price-Prediction.git
cd house-price-prediction
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Run the training script**
```bash
python train.py
```

This will:
- Train all 3 models
- Print a comparison table of evaluation metrics
- Save the best model as `model.pkl`

---

## Project Structure

```
house-price-prediction/
│
├── train.py            ← Main ML pipeline (load, preprocess, train, evaluate, save)
├── housing.csv         ← Dataset
├── requirements.txt    ← Python dependencies
├── model.pkl           ← Saved best model (generated after running train.py)
└── README.md           ← You are here
```

---

## Sample Output

```
Model                      MAE        MSE     RMSE
-------------------------------------------------------
Linear Regression       0.3282     0.1828   0.4275
Decision Tree           0.3275     0.1756   0.4191
Random Forest           0.2263     0.0887   0.2978

Best model: Random Forest
Model saved to model.pkl
```

---

## Future Scope


- [ ] **Cross-validation** — replace single train/test split with k-fold cross-validation for a more reliable performance estimate
- [ ] **Feature importance visualisation** — plot which features influence price the most using `feature_importances_`
- [ ] **Flask REST API** — expose the model via a `/predict` endpoint so it can be consumed by external applications
- [ ] **Web Interface** — build a simple HTML/CSS/JS frontend where users can enter property details and get a predicted price instantly


---


