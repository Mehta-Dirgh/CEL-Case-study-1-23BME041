# 📌 Flow Rate Modeling Using Nonlinear Power Law

## 📖 Overview

This project implements parameter estimation for the nonlinear flow model:

\[
Q = A (V - c)^b
\]

Where:

- **Q** = Flow rate  
- **V** = Measured voltage  
- **c** = Voltage offset  
- **A** = Scaling constant  
- **b** = Nonlinear exponent  

The goal of this study is to determine the optimal exponent **b** such that flow integrals computed from multiple trials remain consistent. The solution is obtained using the **Bisection Method** in MATLAB.

---

## 🧠 Problem Statement

Experimental voltage signals follow a decaying behavior over time.  
To model flow rate from voltage measurements, a nonlinear power-law relationship is assumed:

\[
Q = A (V - c)^b
\]

For each trial:

\[
I_j = \int Q \, dt = \int A (V_j - c)^b \, dt
\]

To ensure calibration consistency across multiple trials, the exponent **b** is selected such that the variation among computed integrals is minimized.

The objective function minimized is:

\[
f(b) = \sqrt{\frac{1}{n} \sum (I_j - \bar{I})^2}
\]

---

## ⚙️ Methodology

### 1️⃣ Voltage Data Generation
- 5 simulated experimental trials
- Exponential decay signals
- Sampling frequency: 100 Hz
- Different trial durations

### 2️⃣ Numerical Integration
Discrete approximation is used:

\[
I_j \approx \sum (V_j - c)^b \Delta t
\]

### 3️⃣ Bisection Method
- Initial bounds: 0.5 ≤ b ≤ 3
- Tolerance: 0.001
- Iterative interval halving
- Convergence monitored using:

\[
\text{Error} = |b_u - b_l|
\]

---

## 📊 Outputs

### 🔹 Objective Function Plot
- f(b) vs exponent b  
- Optimal exponent highlighted  
- Visual confirmation of minimum  

### 🔹 Error Convergence Plot
- Error vs iteration number  
- Tolerance line shown  
- Final converged point marked  
- Demonstrates stability of Bisection Method  

---

## 🧪 Parameters Used

| Parameter | Value |
|------------|--------|
| Offset (c) | 0.5 |
| Sampling Frequency | 100 Hz |
| Number of Trials | 5 |
| Syringe Volume | 3 |
| Tolerance | 0.001 |

---

## 🏁 Results

- Optimal exponent **b** computed numerically  
- Scaling constant **A** determined from reference integral  
- Convergence verified within specified tolerance  
- Graphical validation included  

---

## 📚 Concepts Applied

- Nonlinear Modeling  
- Power-Law Systems  
- Numerical Integration  
- Bisection Method  
- Error Convergence Analysis  
- Parameter Estimation  

---

## 🚀 Applications

- Flow sensor calibration  
- Biomedical infusion systems  
- Syringe pump modeling  
- Nonlinear data fitting  
- Experimental system identification  

---

## ▶️ How to Run

1. Open MATLAB
2. Run the provided `.m` script
3. Observe iteration outputs in Command Window
4. Analyze generated plots

---

## 📌 Author

Developed as part of a numerical modeling and calibration case study using MATLAB.
