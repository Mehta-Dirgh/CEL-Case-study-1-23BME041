📌 Flow Rate Modeling Using Nonlinear Power Law
📖 Overview

This project focuses on estimating parameters in the nonlinear model:

𝑄
=
𝐴
(
𝑉
−
𝑐
)
𝑏
Q=A(V−c)
b

where:

𝑄
Q = Flow rate

𝑉
V = Measured voltage

𝑐
c = Offset voltage

𝐴
A = Scaling constant

𝑏
b = Nonlinear exponent

The objective is to determine the optimal value of the exponent 
𝑏
b such that multiple experimental trials produce consistent flow integrals.

The model is solved using the Bisection Method in MATLAB.

🧠 Problem Description

Voltage signals from multiple trials follow an exponential decay behavior.
To estimate flow rate from voltage, the nonlinear power-law relationship is applied:

𝑄
=
𝐴
(
𝑉
−
𝑐
)
𝑏
Q=A(V−c)
b

To calibrate the system:

The integral of flow rate over time is computed:

𝐼
𝑗
=
∫
𝑄
 
𝑑
𝑡
=
∫
𝐴
(
𝑉
𝑗
−
𝑐
)
𝑏
𝑑
𝑡
I
j
	​

=∫Qdt=∫A(V
j
	​

−c)
b
dt

Since 
𝐴
A is constant across trials, consistency requires:

Minimize variation among 
𝐼
𝑗
Minimize variation among I
j
	​


Therefore, the optimal exponent 
𝑏
b is found by minimizing:

𝑓
(
𝑏
)
=
1
𝑛
∑
(
𝐼
𝑗
−
𝐼
ˉ
)
2
f(b)=
n
1
	​

∑(I
j
	​

−
I
ˉ
)
2
	​

⚙️ Methodology
1️⃣ Data Generation

Simulated voltage decay data

5 experimental trials

Different time durations

Sampling frequency: 100 Hz

2️⃣ Numerical Integration

Discrete summation used:

𝐼
𝑗
≈
∑
(
𝑉
𝑗
−
𝑐
)
𝑏
 
Δ
𝑡
I
j
	​

≈∑(V
j
	​

−c)
b
Δt
3️⃣ Optimization Using Bisection Method

Initial bounds: 0.5 ≤ b ≤ 3

Tolerance: 0.001

Iterative interval halving

Convergence monitored using:

Error
=
∣
𝑏
𝑢
−
𝑏
𝑙
∣
Error=∣b
u
	​

−b
l
	​

∣
📊 Results

The script produces:

🔹 Objective Function Plot

Shows 
𝑓
(
𝑏
)
f(b) vs exponent 
𝑏
b

Marks optimal exponent

Confirms minimum visually

🔹 Error Convergence Plot

Displays error reduction per iteration

Shows tolerance line

Highlights final converged solution

Demonstrates numerical stability

🧪 Parameter Values
Parameter	Value
Offset (c)	0.5
Sampling Frequency	100 Hz
Number of Trials	5
Syringe Volume	3
Tolerance	0.001
🏁 Final Outputs

✅ Optimal exponent 
𝑏
b

✅ Scaling constant 
𝐴
A

✅ Convergence validation

✅ Graphical verification

📚 Concepts Used

Nonlinear Modeling

Power-Law Relationships

Numerical Integration

Bisection Method

Error Convergence Analysis

Parameter Calibration

🚀 Applications

This modeling approach is useful for:

Flow sensor calibration

Biomedical infusion systems

Syringe pump modeling

Experimental data fitting

Nonlinear system identification
