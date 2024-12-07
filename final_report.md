
# Efficient Trading with Price Impact

## Introduction
This report explores optimal trading strategies under price impact constraints, focusing on three key tasks:
1. Constructing linear (OW) and nonlinear (AFS) models for price impact.
2. Implementing the optimal strategy with linear impact and visualizing Sharpe Ratio plots.
3. Implementing a deep learning algorithm for discrete settings, evaluating training and validation loss trends for different network structures.

The goal is to understand price impact effects, optimize trading strategies, and evaluate model performance.

## Methodology

### Task 1: Constructing and Coding Linear OW and Nonlinear AFS Models
- **Linear OW Model**: Assumes price impact is linearly proportional to trade size with exponential decay.
- **Nonlinear AFS Model**: Incorporates nonlinear effects, typically using a square-root law.

### Task 2: Implementing the Optimal Strategy with Linear Impact
- **Optimal Strategy**: Uses feedback coefficients \( C_f \) and \( C_J \) to compute holdings.
- **Sharpe Ratio**: Measures risk-adjusted returns.
- **Parameter Optimization**: Explored \( eta, \phi, \lambda \) using gradient-based and grid search methods.

### Task 3: Implementing the Deep Learning Algorithm
- **Neural Network**: Configurable architectures to predict optimal holdings.
- **Training**: Used Mean Squared Error (MSE) loss and Adam optimizer.
- **Validation**: Analyzed training/validation loss trends.

## Results

### Task 1: Price Impact Models
- **Linear OW Model**: Symmetric Gaussian-like distribution.
- **Nonlinear AFS Model**: Wider distribution reflecting nonlinear effects.

### Task 2: Optimal Strategy
- **Sharpe Ratio Trends**: Optimal strategy consistently outperformed the suboptimal one.
- **Optimal Parameters**: \( eta = 0.1 \), \( \phi = 0.5 \), \( \lambda = 0.005 \).
- **Maximum Sharpe Ratio**: 0.0014 for linear, 0.01 for nonlinear.

### Task 3: Deep Learning Algorithm
- **Training/Validation Loss**:
  - Single-layer: Train Loss = 0.9891, Val Loss = 1.031.
  - Two-layer: Train Loss = 0.983, Val Loss = 1.034.
  - Three-layer: Train Loss = 0.0982, Val Loss = 1.035.
- **Trend**: Two-layer networks balanced performance and overfitting.

## Conclusion
1. **Linear vs Nonlinear Models**: Nonlinear models are better for high-impact scenarios.
2. **Optimal vs Suboptimal Strategies**: Optimal strategies outperform simplified approaches.
3. **Deep Learning**: Effective for approximating strategies but requires careful tuning to avoid overfitting.

## Recommendations
1. Use **nonlinear impact models** for significant price effects.
2. Fine-tune predictive signals to improve Sharpe Ratios.
3. Employ neural networks with moderate complexity to balance performance and overfitting risks.
