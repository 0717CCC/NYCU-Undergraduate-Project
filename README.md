# Bike Sharing Redistribution with Demand Forecasting

## Overview
This project integrates **deep learning-based demand forecasting** with 
**vehicle routing optimization** to solve the bike-sharing redistribution problem.

We combine:
- LSTM / GRU for station demand prediction
- Genetic Algorithm for route optimization

Objective:
Minimize **total travel distance** and **carbon emissions**

Result:
Achieved ~36% reduction in total cost compared to baseline.


## Problem Description

Bike-sharing systems often suffer from **supply-demand imbalance**:
- Some stations run out of bikes
- Some stations are overloaded

Traditional approaches:
- Only forecasting → cannot rebalance
- Only routing → ignores future demand

Our Solution:
We propose an **integrated framework**:
1. Predict station demand (arrival & departure)
2. Use predictions to optimize redistribution routes

## Methodology 
### Stage 1: Demand Forecasting
We model bike usage as a **time series prediction problem**.

Models used:
- RNN
- LSTM
- GRU

Each station has:
- Arrival prediction model
- Departure prediction model

Net demand:
Net = Arrival - Departure

### Stage 2: Redistribution Routing
We formulate the problem as: VRPPD (Vehicle Routing Problem with Pickup & Delivery)

Objectives:
- Minimize travel distance
- Minimize carbon emissions

Constraints:
- Vehicle capacity
- Start/end at depot
- Demand satisfaction

Models used:
We use a **Genetic Algorithm (GA)** to solve this NP-hard problem.
- Suitable for combinatorial optimization
- Efficient for large-scale routing problems
