# Digital Twin for Condition Monitoring of Industrial Machines using AI and Simulation

This repository contains the implementation of a **Digital Twin-based predictive maintenance system** for industrial machines. The project uses AI and simulation to monitor machine health, predict Remaining Useful Life (RUL), and detect anomalies in real-time.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Datasets](#datasets)
- [System Architecture](#system-architecture)
- [Methodology](#methodology)
- [Models](#models)
- [Deployment](#deployment)
- [Results](#results)
- [Future Work](#future-work)

---

## Project Overview

Industrial assets such as turbofan engines and rolling-element bearings degrade over time, which can lead to costly unplanned downtime. This project integrates **Digital Twin technology** with AI models to:

- Monitor component health in real-time
- Predict Remaining Useful Life (RUL)
- Detect early anomalies
- Provide actionable maintenance insights via a Streamlit dashboard

---

## Features

- **Data Preprocessing:** Cleaning, normalization, windowing, and feature extraction.
- **Predictive Models:** Random Forest, LSTM, and Autoencoder.
- **Digital Twin Visualization:** Real-time monitoring and health status dashboards.
- **Anomaly Detection:** Early fault detection using Autoencoder reconstruction error.
- **RUL Prediction:** Accurate estimation for turbofan engines.

---

## Datasets

1. **NASA C-MAPSS FD001**
   - Task: Remaining Useful Life (RUL) prediction
   - Data: Multivariate sensor readings from turbofan engines
   - Features: 21 sensors + 3 operational settings

2. **XJTU-SY Bearing Dataset**
   - Task: Bearing anomaly detection
   - Data: High-frequency vibration signals
   - Features: Statistical vibration metrics (RMS, Mean, Std, Max, Min)

---

## System Architecture

The system consists of the following layers:

1. **Physical Asset Layer:** Industrial machines represented by datasets
2. **Data Acquisition Layer:** Sensor telemetry collection
3. **Data Processing & Feature Engineering Layer**
4. **Model Prediction Layer:** RF for RUL, LSTM for sequences, Autoencoder for anomalies
5. **Digital Twin Deployment Layer:** Streamlit-based real-time dashboard

---

## Methodology

1. **Data Preprocessing**
   - Handle missing values and sensor noise
   - Normalize features
   - Window sequences for LSTM

2. **Feature Engineering**
   - Time-domain features: RMS, Mean, Std, Skewness, Kurtosis
   - Frequency-domain features: FFT peaks, spectral energy

3. **Model Training**
   - Random Forest for tabular RUL prediction
   - LSTM for sequential RUL prediction
   - Autoencoder for anomaly detection

4. **Evaluation Metrics**
   - RUL Prediction: RMSE, MAE, R²
   - Anomaly Detection: MSE and classification accuracy

---

## Models

| Model        | Dataset      | Task                     | Key Metric       |
| ------------ | ----------- | ----------------------- | ---------------- |
| Random Forest | NASA FD001 | RUL Prediction           | RMSE = 31.97     |
| LSTM         | NASA FD001 | Sequential RUL Prediction | RMSE = 39.77     |
| Autoencoder  | XJTU-SY    | Bearing Anomaly Detection | MSE = 0.045      |

---

## Deployment

- Built with **Streamlit** for interactive dashboard
- Supports CSV upload simulating real-time sensor streaming
- Real-time RUL and anomaly monitoring
- Health status indicators: Healthy, Degrading, Critical, Failure Imminent
- Downloadable maintenance report

---

## Results

- **Random Forest** achieved highest R² and lowest RMSE for RUL prediction
- **Autoencoder** successfully detected early-stage bearing anomalies
- Dashboard enables actionable insights for maintenance engineers
    
![RUL Predition](https://github.com/VS1245/Digital-Twin-for-Predictive-Maintenance-using-AI-and-Simulation/blob/main/img/1.png)

    
![Anomaly Detection](https://github.com/VS1245/Digital-Twin-for-Predictive-Maintenance-using-AI-and-Simulation/blob/main/img/2.png)
---

## Future Work

- Implement transfer learning across similar machinery
- Integrate physics-based models with AI for hybrid Digital Twin
- Deploy Digital Twin on edge devices for real-time industrial streaming
- Experiment with advanced deep learning architectures (Bi-LSTM, Transformers)

---

