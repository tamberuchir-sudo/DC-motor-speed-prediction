# DC-motor-speed-prediction
DC Motor Speed prediction using Linear Regression
DC Motor Speed Prediction using Linear Regression

This repository demonstrates a simple, engineering-oriented machine learning project to predict DC motor speed (RPM) based on armature voltage. The project is designed for students and engineers with a background in Instrumentation, Control Systems, and Mechanical Engineering.


---

1. Problem Statement

To build a regression model that predicts motor speed (RPM) as a function of applied voltage, assuming approximately linear behavior under constant load.

Mathematically:

Speed ≈ k·Voltage + b


---

2. Project Structure

DC-Motor-Speed-Prediction/
│
├── data/
│   └── motor_data.csv
│
├── src/
│   ├── train_model.py
│   ├── visualize.py
│   └── predict.py
│
├── models/
│   └── dc_motor_speed_model.pkl
│
├── requirements.txt
├── README.md
└── .gitignore


---

3. Dataset (data/motor_data.csv)

Voltage,Speed_RPM
50,600
75,900
100,1200
125,1500
150,1800
175,2100
200,2400

Inputs: Voltage (V)
Output: Speed (RPM)


---

4. Model Training (src/train_model.py)

import pandas as pd
from sklearn.linear_model import LinearRegression
import joblib

# Load data
data = pd.read_csv("data/motor_data.csv")

X = data[["Voltage"]]
y = data["Speed_RPM"]

# Train model
model = LinearRegression()
model.fit(X, y)

# Save model
joblib.dump(model, "models/dc_motor_speed_model.pkl")

print("Model trained and saved successfully")
print("Gain (RPM/V):", model.coef_[0])
print("Offset:", model.intercept_)


---

5. Visualization (src/visualize.py)

import pandas as pd
import matplotlib.pyplot as plt
import joblib

# Load data and model
data = pd.read_csv("data/motor_data.csv")
model = joblib.load("models/dc_motor_speed_model.pkl")

X = data[["Voltage"]]
y = data["Speed_RPM"]
y_pred = model.predict(X)

plt.scatter(X, y, label="Actual")
plt.plot(X, y_pred, label="Predicted")
plt.xlabel("Voltage (V)")
plt.ylabel("Speed (RPM)")
plt.title("DC Motor Speed vs Voltage")
plt.legend()
plt.show()


---

6. Prediction Script (src/predict.py)

import joblib

model = joblib.load("models/dc_motor_speed_model.pkl")

voltage = [[160]]
pred_speed = model.predict(voltage)

print("Predicted speed at 160 V:", pred_speed[0], "RPM")


---

7. Requirements (requirements.txt)

pandas
scikit-learn
matplotlib
joblib
