(https://github.com/ramirazodi/ercot_ordc_engine_simulator/assets/106940649/813e2c5d-2dc3-4db2-94a9-0f217a323487)
![stacked_plot](https://github.com/ramirazodi/ercot_ordc_engine_simulator/assets/106940649/0f89e929-6c16-4065-97ba-9a4b68c8a57b)

# Short Description
ERCOT Scarcity Pricing Engine & Simulator: A Python-based analytical toolkit for generating, simulating and visualizing the ERCOT Operating Reserve Demand Curve (ORDC), 
incorporating RTORPA and RTOFFPA calculations, loss of load expectation, and other key protocols. This project enables detailed scenario analysis and forecasting of scarcity pricing mechanisms 
in ERCOT electricity markets.

# ERCOT Scarcity Pricing Engine & Simulation Project

Overview
This Python project simulates the scarcity pricing mechanism of ERCOT, focusing on the ORDC (Operating Reserve Demand Curve) by replicating the RTORPA (Real-Time Online Reserve Price Adder) 
and RTOFFPA (Real-Time Offline Reserve Price Adder) formulas and protocols. It creates various scenarios and visualizations to understand and predict the behavior of ERCOT's scarcity pricing.

# Modules

library_versions.py
Functionality: Prints the version of libraries currently installed in your environment 

file_reader.py
Functionality: Reads input files, including the Loss Of Load Probability (LOLP) distribution metrics and historical Real-Time ORDC, Reliability Deployment Price Adders, and Reserves data.
Key Functions: None. Mainly used for data preparation and formatting.

functions.py
Functionality: Contains key functions using ERCOT nodal protocols to generate ORDC adders.
Key Functions:
musigma: Calculates the mean and standard deviation of the LOLP distribution.
pbmcl: Computes the probability of reserves falling below the minimum contingency level (PBMCL).
rtoffpa: Calculates the RTORPA adder.
rtorpa: Generates the RTORPA adder with various input parameters.

ordc_verification.py
Functionality: Uses ERCOT reserves and adder file to independently calculate RTORPA and RTOFFPA, serving as a model verification tool.
Key Functions: None. Focuses on applying the rtorpa function to data for verification.

interval_scenario.py
Functionality: Provides a testing ground for individual scenarios using the rtorpa function.
Key Functions: None. Used for scenario testing.

period_scenarios.py
Functionality: Generates ORDC adders for various scenarios, including different reserve scenarios and ORDC parameters like VOLL, MCL, LOLE values. You can add your own scenarios in this module which can include 
custom values for all the key parameters such as system lambda, RTOLCAP, RTOFFCAP, LOLE distribution parameters such as sigma, mu, VOLL, MCL, pretty much anything. Resulting dataframe which includes the input
dataframe in the 'input' subfolder as well as new columns showing all the key scarcity pricing components from the scenarios defined will be saved in the 'output' subfolder as 'ordc_scenarios.xlsx'![scatter_plot]

Key Functions: None. Used for batch processing of scenarios.

scatter_plot.py
Functionality: Plots the actual ORDC values vs. defined ORDC scenarios using Plotly. Plot results will be saved in the 'output' subfolder as Plotly HTML files and autorun should display them in your browser
Key Functions: None. Focused on data visualization.

stacked_plot.py
Functionality: Creates stacked plots for ORDC values and scenarios, again using Plotly. Plot results will be saved in the 'output' subfolder as Plotly HTML files and autorun should display them in your browser
Key Functions: None. Used for advanced data visualization.
Running the Project

Ensure all dependencies are installed using requirements.txt. Each module is designed to be run independently based on the specific analysis or visualization required.
