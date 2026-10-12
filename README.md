# Combined-Power-Plant-Optimization-Model
ML-Based Combined-Cycle Power Plant Optimization
Overview
This project develops a machine learning-based optimization framework for a Combined-Cycle Power Plant (CCPP). It combines machine learning regression models with a differential evolution optimization algorithm to identify operating conditions that may improve power plant efficiency, reduce heat rate, and lower carbon dioxide emissions while meeting a specified net power output target.
The framework models key gas turbine, heat recovery steam generator, steam turbine, and cooling-system operating conditions. It is designed as a research prototype for intelligent energy management and data-driven power plant optimization.
Objectives
•	Develop machine learning models to estimate net power output, net heat rate, and CO₂ emissions.
•	Optimize selected gas turbine operating conditions and duct burner settings.
•	Minimize a weighted objective combining heat rate and CO₂ emissions.
•	Enforce a minimum net power output requirement.
•	Compare baseline and optimized operating conditions.
•	Evaluate model accuracy and visualize optimization results.
Methodology
The project follows a machine learning and optimization workflow:
1.	Data preparation: Load, inspect, and clean plant operating data.
2.	Feature engineering: Select relevant operating parameters and performance targets while avoiding direct target leakage.
3.	Model development: Train Random Forest regression models for net power output, net heat rate, and CO₂ emissions.
4.	Model evaluation: Assess predictive performance using MAE, RMSE, and R².
5.	Optimization: Apply differential evolution to search for improved operating conditions within specified bounds.
6.	Performance comparison: Compare baseline and optimized performance estimates.
7.	Visualization and export: Generate comparison plots and save trained models, metrics, and optimization results.
Technologies Used
•	Python
•	Google Colab
•	Pandas and NumPy
•	Scikit-learn
•	SciPy
•	Matplotlib
•	Joblib
Input Parameters
The model uses selected operating variables, including:
•	Ambient temperature, pressure, and relative humidity
•	Gas turbine inlet temperature and load percentage
•	Gas turbine filter pressure drop
•	Fuel lower heating value
•	Duct burner status and fuel flow
•	Cooling water inlet temperature
•	Time since selected maintenance activities
•	Equivalent operating hours
Optimization Targets
The framework estimates three performance variables:
Target	Purpose
Net power output (MW)	Meet the required electricity output
Net heat rate (kJ/kWh)	Evaluate fuel-energy requirements per unit of electricity
CO₂ emissions (tonnes/hour)	Estimate hourly carbon emissions
The optimization objective combines normalized heat rate and emissions estimates, with a penalty for failing to meet the required power output.
Optimization Algorithm
Differential evolution, a population-based global optimization algorithm, searches the defined operating space for candidate operating conditions.
The framework can compare duct burner operating scenarios when supported by the selected plant's configuration. Candidate solutions must be checked for feasibility, model reliability, and compliance with actual plant operating limits.
Model Evaluation
Predictive performance is evaluated using:
•	Mean Absolute Error (MAE): Average absolute prediction error.
•	Root Mean Squared Error (RMSE): Prediction error measure that penalizes larger errors.
•	Coefficient of Determination (R²): Measures how well the model explains variation in the test data.
A chronological train-test split is used to evaluate predictions on later observations. Optimization results should only be interpreted after reviewing these metrics and verifying that the proposed operating conditions are supported by the training data.
Repository Structure
ccpp-optimization/
├── README.md
├── ccpp_optimization.ipynb
├── plant_operating_data.csv
├── plant_metadata.csv
├── model_validation_metrics.csv
├── optimization_scenarios.csv
├── baseline_vs_optimized.csv
├── net_power_output_mw_model.pkl
├── net_heat_rate_kj_kwh_model.pkl
├── co2_emission_t_h_model.pkl
└── optimization_configuration.pkl
The notebook, datasets, and result files should be included only when available and appropriate for sharing. Adjust the filenames to match your actual repository.
How to Run the Project
1.	Open Google Colab.
2.	Upload or open the project notebook.
3.	Upload the dataset ZIP file or provide the required CSV files.
4.	Install the required Python libraries.
5.	Select a plant block and configure the required power output.
6.	Run the notebook cells sequentially.
7.	Review predictive metrics, optimization feasibility, and performance comparisons.
8.	Export the generated results for further analysis.
Results and Interpretation
The framework produces trained regression models, candidate operating conditions, scenario comparisons, and visualizations of estimated plant performance.
Quantitative savings and performance improvements should be reported only after running the notebook and validating its outputs. Predicted improvements are not guaranteed real-world savings, and comparisons should account for power output, ambient conditions, fuel characteristics, and operating constraints.
Limitations and Future Work
This prototype uses a synthetic, physics-inspired dataset and should not be considered a validated model of a real power plant.
Future development will focus on:
•	Validation using real plant measurements or trusted thermodynamic simulations.
•	Multi-objective optimization of power output, heat rate, emissions, and operating costs.
•	More rigorous equipment and operational constraints.
•	Comparison of differential evolution, genetic algorithms, and Bayesian optimization.
•	Sensitivity analysis and uncertainty quantification.
•	Integration with CFD or thermodynamic simulation tools.
•	Development of an interactive dashboard for exploring optimization scenarios.
Applications
Potential research applications include combined-cycle power plant performance analysis, energy efficiency improvement, intelligent operating-condition selection, emissions assessment, and machine learning-assisted energy system optimization.
Disclaimer
This project is an educational and research prototype. The dataset is synthetic, and all optimization results are model estimates. The framework has not been validated for real-world plant operation. No recommended settings should be implemented on operating equipment without independent engineering validation and approval.
Author
Mechanical Engineering | Machine Learning | Energy Systems Optimization
This project explores the integration of machine learning and numerical optimization to support more efficient and data-driven energy system design and operation.

