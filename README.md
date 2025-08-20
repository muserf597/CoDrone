Drone Cybersecurity Simulator
A Python-based simulator for autonomous drone threat detection, response, and audit logging. Built for aviation safety, cybersecurity innovation, and STEM workforce development. Designed to be modular, NDAA-compliant, and extensible to real-world platforms.

Features
Telemetry Simulation Generates realistic GPS and altitude data with injected anomalies

Machine Learning Anomaly Detection Uses Isolation Forest to identify suspicious flight behavior

Adaptive Decision Engine Dynamically adjusts confidence thresholds based on historical feedback

Streamlit Dashboard Visualizes telemetry, logs, and audit reports in real time

Audit Logging Logs anomalies and decisions to text, CSV, and PDF formats

Arduino Trigger Integration Sends serial commands to external hardware (e.g., valves, alarms)

Modular Design Easily extendable for BVLOS, Remote ID, or NDAA-compliant platforms

Requirements
Python 3.8+

numpy, pandas, matplotlib, scikit-learn, fpdf, streamlit

Optional: CoDrone_mini for hardware integration

Optional: pyserial for Arduino support

Install dependencies:

bash
pip install -r requirements.txt
File Structure
File	Purpose
main.py	Entry point for simulation and dashboard
decision_history.csv	Logs decisions with timestamp, confidence, and outcome
flight_log.txt	Logs anomalies and hardware triggers
telemetry_log.txt	Logs raw telemetry data
audit_report.csv / audit_report.pdf	Exportable reports for review or compliance
How It Works
Simulates telemetry with injected anomalies

Detects threats using Isolation Forest

Logs decisions with adaptive thresholding

Sends hardware triggers via Arduino (optional)

Displays everything in a real-time Streamlit dashboard
<img width="1000" height="400" alt="Figure_1" src="https://github.com/user-attachments/assets/91ea509e-a225-417b-ae37-dea15554e630" />


Exports audit reports for post-flight review

Author
MF — Aviation safety educator, Python innovator, and cybersecurity builder. Focused on autonomous systems, NDAA-compliant drone safety, and STEM workforce development.
