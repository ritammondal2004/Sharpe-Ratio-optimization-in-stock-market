
# Sharpe Ratio Optimization - Financial Portfolio Project
## 👤 Author  
**Ritam Mondal**  
Indian Institute of Technology (IIT), Kharagpur 
- Dual Degree, Industrial & Systems Engineering
- Indian Institute of Technology Kharagpur  
- connect me on: [LinkedIn](https://www.linkedin.com/in/ritam-mondal-86a369287/)
- Email: ritamm134@gmail.com

**Under the guidance of**  
Prof. Abhishek Sharma, IIT Kharagpur

---

## 📌 Project Overview
This project implements Sharpe Ratio-based financial portfolio optimization using real Indian stock data. The model **maximizes return** per unit of risk under practical constraints such as sector allocation limits, ESG scores, liquidity thresholds, and volatility caps. The optimization is solved using **SLSQP** and visualized through **Monte Carlo** simulation and efficient frontier plots.

---

## 📈 Introduction
Financial portfolio optimization is the backbone of informed investment decision-making. Our project builds on this by maximizing the **Sharpe Ratio**, an industry-standard metric for evaluating risk-adjusted returns. Using data from Indian equities, we formulate a constrained optimization model that reflects real-world investor limitations.

---

## 🔍 Literature Review
Rooted in **Modern Portfolio Theory (MPT)** by Harry Markowitz. It relies on mean-variance optimization—essentially balancing average returns against volatility. This work integrates extensions like:
- ESG considerations
- Liquidity constraints
- Sector allocation caps

We bridge theory and practice by enhancing the mean-variance model to align with fund manager behavior and sustainability requirements.

---

## 🎯 Objective
To allocate weights to a set of stocks such that the portfolio achieves:
- Maximum Sharpe Ratio or maximize net return per unit of risk taken
- Subject to constraints on sector bounds, volatility, ESG scores, and liquidity

---

## 🧮 Mathematical Model
### Objective:
   
![image](https://github.com/user-attachments/assets/d7585ee2-aea8-47d7-b3ea-4c26cffcc7a9)  

### or in algebric form


![image](https://github.com/user-attachments/assets/25340f26-322d-413b-b922-16690a8d803d)


### Constraints:

![image](https://github.com/user-attachments/assets/4749c13d-fe3e-4052-bed7-4008fecb1a38)


Used parameter In this model:

- n = number of assets in the portfolio
- μᵢ = expected mean return of asset i
- μ = Vector of expected returns of the assets
- Σ = Covariance matrix of asset returns 
- COV(i,j) = Covariance between stock i and stock j
- wᵢ = weight assigned to asset i (decision variable)
- w = vector of weight allocated (vector of decision variable)

---

## 🧠 Parametric Grid Search (NEW SECTION)
To evaluate how varying constraint values impact portfolio performance, we performed a **grid search** across:
- Sector bounds: [10%, 30%, ..., 90%] (with UB > LB)
- Volatility caps: [1%, 6%, ..., 30%]
- ESG minimums: [35, 50, 65, 80]
- Liquidity minimums: [40k to 440k in steps of 80k]

> 🧮 Total combinations tested: **2160**

Each combination was optimized using SLSQP, and results were stored to evaluate which constraint set gave the highest Sharpe Ratio.

📍 
**Best Optimization parameters as per Sharpe Ratio**

![image](https://github.com/user-attachments/assets/6c81e937-f436-4f20-81c5-0a249ece2435)

📍 **optimal weight allocation**

![image](https://github.com/user-attachments/assets/e844333c-2cee-4f21-879a-e5cccea0723c)

---

## ⚙️ Methodology
1. Calculate expected returns and covariance matrix from daily price data
2. Normalize and structure sector, ESG, and liquidity data
3. Define optimization problem using `scipy.optimize.minimize`
4. Solve for each constraint configuration
5. Optimization Algorithm: SLSQP (Sequential Least Squares Programming)
   - SLSQP is a gradient-based optimization algorithm that handles both equality and inequality constraints.
   - It solves a series of quadratic subproblems to move toward an optimum.
   - Well-suited for portfolio optimization where constraints are linear or nonlinear.
6. Visualize:
   - Efficient Frontier
   - Sector-wise allocation

📍 _[Insert Efficient Frontier chart image here]_

---

## 📊 Data Insights
### Cumulative Return - Individual Stocks
Shows how ₹100 would grow from 2019–2024 for each stock.
📍 _[Insert individual stock return plot here]_

### Cumulative Return - Sector-wise
Tracks sector-level performance for portfolio components.
📍 _[Insert sector-wise cumulative return plot here]_

---

## 📌 Optimization Results
- **Optimal Sharpe Ratio**: 1.120895
- **Portfolio Return**: 12.707%
- **Portfolio Volatility**: 11.31%

### Optimal Weights (Top 3)
- INFY: 21.93%
- ADANIPOWER: 19.01%
- TATACOMM: 12.25%

📍 _[Insert table or pie chart of optimal weights here]_

### Sector Allocation
- IT: 32.69%
- Energy: 25.06%
- Telecom: 12.25%

📍 _[Insert sector-wise allocation pie chart here]_

---

## 🔎 Risk Analysis
### Sector-Wise Risk
Calculated risk per sector based on variance contribution.
📍 _[Insert sector-wise risk bar chart here]_

### Stock-Wise Risk
Breakdown of risk exposure at individual stock level.
📍 _[Insert stock-wise risk bar chart here]_

---

## 🧾 Conclusion
This project demonstrates how Sharpe Ratio optimization can be used to build a realistic and robust portfolio. Incorporating ESG, sector, and liquidity constraints makes the solution applicable in real-world asset management. Our results show clear risk-return tradeoffs and how optimal asset allocation shifts under different scenarios.

---

## 💻 System Configuration
- Google Colab (Jupyter notebook)
- CPU: Intel i5-12500H, 16 GB RAM
- GPU: NVIDIA RTX 1650 Ti

---

## 🔗 Code & Notebook
Colab link: [Sharpe Ratio Optimization Notebook](https://colab.research.google.com/drive/1roOJ9X7M8An_cfsTYwKi5Yrank8gqOKb)

---

## 📚 References
[List of references copied from original PDF...]

---

## 📂 Appendix
📍 _[Place for screenshots or extra data outputs as needed]_
