# Voter Anomaly Detection System

## Problem

Elections can be tampered with or show suspicious patterns. It’s hard to spot anomalies quickly and trust that the recorded votes haven’t been altered.

## What It Does

- Records votes in an immutable way using a basic blockchain (proof-of-work) so you have an audit trail.
- Watches the vote data for clear red flags:  
  - More votes than registered voters  
  - Sudden unexplained spikes  
  - Precincts with zero activity  
  - Other unusual patterns
- Sends alerts when something looks wrong.
- Stores everything in a simple SQLite database and logs the anomalies.
- Comes with test scenarios so you can exercise normal vs. suspicious behavior.

## How to Use

### 1. Requirements
- Python 3.7+
- Install dependencies:
  ```bash
  pip install -r requirements.txt
