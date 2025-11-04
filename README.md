This project demonstrates how Bayesian inference can be applied to detect regime shifts and model structural changes in time series or derivatives data.
Using PyMC, ArviZ, and NumPy/Pandas, the notebook implements a Bayesian linear regression framework that captures uncertainty in parameters and identifies potential change points in underlying data behavior.

The goal is to estimate posterior distributions for model parameters, visualize uncertainty, and use likelihood-based posterior predictive sampling to infer regime transitions.

⚙️ Features

Bayesian Linear Regression: Models the relationship between features (X) and target (y) using probabilistic priors.

Posterior Inference: Computes posterior distributions for slope, intercept, and noise variance using MCMC sampling.

Change Point Interpretation: Regime changes can be inferred where posterior estimates shift significantly.

Uncertainty Visualization: Uses Highest Density Intervals (HDI) to visualize credible regions around predictions.

Posterior Predictive Sampling: Generates new outcomes to validate model predictions and quantify uncertainty.

🧩 Libraries Used

PyMC – Bayesian modeling and MCMC sampling

ArviZ – Posterior diagnostics and visualization

NumPy & Pandas – Data manipulation and numerical computation

Matplotlib – Visualization

🚀 How to Run
# Clone the repository
git clone https://github.com/yourusername/bayesian-change-point-detection-and-regime-prediction.git
cd bayesian-change-point-detection-and-regime-prediction

# Install dependencies
pip install pymc arviz numpy pandas matplotlib

# Run the main script
python bayesian_regime_model.py

📈 Methodology

Data Generation:
Synthetic linear data is created with Gaussian noise for demonstration.

Model Setup:
Priors are assigned for intercept, slope, and error variance (Normal, HalfNormal distributions).

Inference:
MCMC sampling (pm.sample) estimates posterior distributions.

Posterior Predictive Analysis:
Future outcomes are simulated from the posterior using pm.sample_posterior_predictive.

Visualization:

Scatter plot of observed data

HDI intervals over predictions

Posterior trace and summary statistics

📊 Example Output

Posterior Summary:

Parameter	Mean	SD	HDI 94%
β₀ (Intercept)	≈ 1.5	~0.1	1.3–1.7
β₁ (Slope)	≈ 2.5	~0.05	2.4–2.6
σ (Std. Dev.)	≈ 1.0	~0.1	0.8–1.2

Plots:

Posterior trace plots (via az.plot_trace)

94% HDI credible interval overlay on regression fit

Random posterior regression lines visualizing uncertainty

🧠 Future Work

Extend model for time-dependent change point detection using hierarchical priors.

Apply to financial derivatives (options/futures) for regime prediction.

Integrate with QuantConnect for live data inference.

Add Bayesian model comparison (WAIC, LOO-CV).
