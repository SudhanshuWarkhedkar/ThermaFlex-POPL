ThermalFlex AI ⚡
An AI-based decision-support platform for India's coal thermal power plants, built for Smart India Hackathon 2026.

🚨 The Problem
Indian coal plants struggle to reduce output below a ~55% Minimum Technical Load (MTL), even during peak solar and wind hours. This forces grid operators to curtail clean renewable energy instead.

Rajasthan has seen curtailment spike above 50% during peak solar hours.

No official curtailment dataset currently exists in India.

The added thermal/mechanical ramping stress on plant equipment remains largely unmonitored.

🚀 What ThermalFlex AI Does
Four connected modules unified into a single platform:

AI Flexible Ramping Predictor — Builds a 96-block (15-min) demand/solar/wind duck curve and uses a HiGHS LP scheduler to recommend optimal ramp plans within MTL and ramp-rate constraints.

Curtailment Monitoring Dashboard — Estimates unmonitored curtailment (Potential Generation × CUF × Hours − Actual Generation) backed by a 4-rule root-cause engine (transmission bottleneck, MTL inflexibility, solar saturation, reserve conservation).

Predictive Maintenance — Dual XGBoost models (RUL regression + failure-risk classification) trained on rolling sensor features, validated on the NASA C-MAPSS turbofan dataset as a robust proxy for turbine/boiler degradation.

Unified Cockpit — Cross-checks grid ramping recommendations against real-time equipment health to ensure a fast ramp is never dispatched to a high-risk unit.

🛠️ Tech Stack
Language: Python

UI/Visualization: Streamlit, Plotly

Machine Learning: XGBoost, scikit-learn

Optimization: HiGHS LP

Data Processing: pandas

APIs & Storage: Open-Meteo / OpenWeatherMap APIs, SQLite

📊 Data Sources
Demand: Zenodo (daily electricity demand, Indian states, 2014–2024)

Renewable Generation: CEA REIndia.csv (state/source-wise, monthly)

Installed Capacity: CEA 2024 report

Equipment Sensors: NASA C-MAPSS FD001 (proxy dataset for degradation modeling)

Weather: Open-Meteo / OpenWeatherMap

📈 Validated Results
Automated Tests: 11/11 tests passing ✅

RUL Prediction (Regression): MAE 13.37 cycles, RMSE 18.26

Failure-Risk Classification: 92% accuracy, 0.978 ROC-AUC

Note on Status: Built as a prototype using public and historical data. Curtailment figures are estimated using CEA methodology (as no official direct dataset exists), and predictive maintenance is validated on the NASA C-MAPSS jet-engine degradation proxy dataset.

⚙️ Getting Started
Prerequisites
Python 3.9+

pip

Installation
Clone the repository:

Bash
git clone https://github.com/your-username/thermelflex-ai.git
cd thermelflex-ai
Install dependencies:

Bash
pip install -r requirements.txt
Run the Streamlit app:

Bash
streamlit run app.py
📄 License & Acknowledgments
Built with ❤️ for the Smart India Hackathon (SIH) 2026.
