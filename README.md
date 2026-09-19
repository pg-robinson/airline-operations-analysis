# Airline Operations Analysis

**Using flight data, machine learning and systems thinking to understand airline disruption, delay propagation and operational recovery.**

Airline delays are rarely isolated events. Aircraft rotate through multiple sectors, operational constraints interact, and disruption can propagate through a network over the course of a day.

This project explores a practical question:

> **Can historical operational data help us understand where delays originate, how they propagate, and where an airline has meaningful opportunities to intervene?**

## What I'm exploring

The analysis combines large-scale flight data with operational reasoning to investigate:

- How delay performance varies across airlines, airports and routes
- How delays propagate through aircraft rotations
- Whether previous sectors provide useful information about downstream delay risk
- How much delay airlines recover during flight
- Which operational factors appear associated with better or worse recovery
- Whether machine-learning models can identify flights at elevated risk before arrival

## Initial results

Analysis of approximately **5.7 million US domestic flights** produced:

| Model / measure | Result |
|---|---:|
| Delay classification ROC-AUC | **0.929** |
| Delay classification PR-AUC | **0.865** |
| Arrival-delay regression MAE | **10.7 min** |
| Arrival-delay regression RMSE | **21.6 min** |
| Aircraft rotation continuity identified | **97.5%** |

One particularly useful signal is the recent history of the aircraft rotation.

In the analysed data, the observed probability of a late arrival increased as preceding sectors accumulated delays:

| Previous 3 sectors delayed | Observed late-arrival rate |
|---:|---:|
| 0 | **7.18%** |
| 1 | **15.89%** |
| 2 | **23.95%** |
| 3 | **33.58%** |

This suggests that disruption history contains useful information about downstream operational risk.

## From prediction to decision

Prediction alone is not particularly useful to an airline.

The more interesting question is:

> **If we know a flight is at risk, what can someone actually do about it?**

That leads into questions of operational control: which decisions can be made months ahead through scheduling and network design, which can be influenced on the day of operation, and which factors sit largely outside the airline's control.

The aim of this project is therefore not simply to produce increasingly accurate models. It is to explore how data and prediction might support **better operational decisions**.

## Current work

The project is currently expanding into:

- Airport and hub performance
- Aircraft rotation reconstruction
- Delay propagation
- Delay recovery
- Route and network effects
- Operational locus of control
- Predictive modelling
- Decision-support concepts

## Tools

Python · PySpark · Databricks · pandas · scikit-learn · MLflow · Matplotlib

## About this project

This is an independent portfolio project using public flight data.

It reflects my interest in applying systems engineering, data analysis and machine learning to complex operational problems.

## Airport performance

Delay performance varies substantially across airports, and an airline's hub structure creates a distinctive operational footprint.

![Average departure delay by airport](images/hub-delay-performance.png)

*Average departure delay across the airline's network, with principal hubs grouped for comparison. Lower values indicate better departure performance.*
