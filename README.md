# Bike Sharing Redistribution with Demand Forecasting

## Overview
This project integrates **bike demand forecasting** with 
**vehicle routing optimization** to solve the bike-sharing redistribution problem.
<img width="1017" height="443" alt="image" src="https://github.com/user-attachments/assets/9645ac2e-5f67-4287-bac3-1d11a8a85358" />

We combine:
- LSTM / GRU for station demand prediction
- Genetic Algorithm for route optimization

Objective:
Minimize **total travel distance** and **carbon emissions**

Result:
Achieved ~36% reduction in total cost compared to baseline.


## Problem Description

Modern bike-sharing systems frequently face supply-demand imbalances:

- Stockouts: Users cannot find a bike when needed.
- Overloading: Users cannot return a bike because the station is full.

Our Integrated Framework:

- Anticipate: Predict station demand (arrivals vs. departures) for the next time window.
- Optimize: Generate redistribution routes that prioritize stations with the highest predicted urgency.

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

Algorithm used:

We use a **Genetic Algorithm (GA)** to solve this NP-hard problem.
- Suitable for combinatorial optimization
- Efficient for large-scale routing problems
