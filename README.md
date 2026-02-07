# DC-motor-speed-prediction
DC Motor Speed prediction using Linear Regression
DC Motor Speed Prediction using Linear Regression

This repository demonstrates a simple, engineering-oriented machine learning project to predict DC motor speed (RPM) based on armature voltage. The project is designed for students and engineers with a background in Instrumentation, Control Systems, and Mechanical 
# DC Motor Speed Prediction using Linear Regression

## Overview
This project demonstrates **motor speed prediction** for a **DC motor** using **Linear Regression**, based on applied armature voltage.  
It combines **control systems fundamentals** with **machine learning**, making it suitable for roles in **industrial automation, robotics, and control engineering**.

The objective is to model the relationship:

Speed (RPM) = f(Voltage)

This mirrors the physical DC motor equation:
ω ≈ K × V (under constant load and field conditions)

---

## Motivation
In real industrial systems:
- Sensors introduce noise
- Parameters vary with temperature and aging
- Data-driven models complement analytical models

This project shows how **ML can estimate motor behavior** from experimental or simulated data.

---

## Project Structure
# Requirements (requirements.txt)

pandas
scikit-learn
matplotlib
joblib---

## Dataset Description
The dataset contains:
- **Voltage (V)** – DC motor input voltage
- **Speed (RPM)** – Measured motor speed

Example:Voltage,Speed 5,520 10,1050 15,1580 20,2100
The data may be:
- Experimentally measured
- Generated from a DC motor model
- Augmented with noise to simulate sensors

---

## Technologies Used
- Python 3
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Joblib

---

## Model Used
**Linear Regression**

Why linear?
- DC motor speed is approximately linear with voltage
- Coefficient has physical meaning (speed constant)
- Easy to interpret and validate

---

## How to Run the Project

### 1. Install dependencies
```bash
pip install -r requirements.txt
Author
Ruchir Tambe
Background: Instrumentation & Control Engineering, Mechanical Engineering, Automation Systems
