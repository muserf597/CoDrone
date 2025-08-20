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
Fri Aug 15 12:31:41 2025,37.773950021510444,-122.41984994136325,9.723210738148822,NORMAL
Fri Aug 15 12:31:41 2025,37.77430342048529,-122.41906558222784,9.310149570778238,NORMAL
Fri Aug 15 12:31:41 2025,37.773363014924165,-122.41962830627824,9.315504858881601,NORMAL
Fri Aug 15 12:31:41 2025,37.80131652095163,-122.37363292876707,68.3602381131711,ANOMALY
Fri Aug 15 12:31:41 2025,37.80149505231938,-122.37301406785372,67.86673687284917,NORMAL
Fri Aug 15 12:31:41 2025,37.80189133110936,-122.37333356682068,67.52221637266095,NORMAL
Fri Aug 15 12:31:41 2025,37.801564520199584,-122.37414807513392,67.11893274949442,NORMAL
Fri Aug 15 12:31:41 2025,37.801771972262316,-122.37353381858736,67.34866453618824,NORMAL
Fri Aug 15 12:31:41 2025,37.80271820379028,-122.37377674983294,67.40070516746147,NORMAL
Fri Aug 15 12:31:41 2025,37.802955243295,-122.37305333603231,67.47805731271824,NORMAL
Fri Aug 15 12:31:41 2025,37.802046892062314,-122.37359753948101,67.26744527632034,NORMAL
Fri Aug 15 12:31:41 2025,37.831358527516755,-122.34955748230462,102.28506955622863,ANOMALY


Detects threats using Isolation Forest



Logs decisions with adaptive thresholding



MissionID	Timestamp	Index	Lat	Lon	Alt	Confidence	Trigger	Outcome	FeedbackSource
1	8/15/2025 12:31	0	37.77395002	-122.4198499	9.723210738	0.005535785	FALSE		ML
1	8/15/2025 12:31	1	37.77430342	-122.4190656	9.310149571	0.013797009	FALSE		ML
1	8/15/2025 12:31	2	37.77336301	-122.4196283	9.315504859	0.013689903	FALSE		ML
1	8/15/2025 12:31	31	37.93578425	-122.2561175	320.6030096	1	TRUE		ML
1	8/15/2025 12:31	33	37.93734148	-122.2573311	320.1469252	1	TRUE		ML
1	8/15/2025 12:31	63	38.15281069	-122.0395478	671.6228055	1	TRUE		ML
1	8/15/2025 12:31	92	38.28687219	-121.9314199	934.5244845	1	TRUE		ML
1	8/15/2025 12:31	93	38.28721345	-121.9316914	934.0944583	1	TRUE		ML
1	8/15/2025 12:31	94	38.28687385	-121.9320636	934.4424736	1	TRUE		ML
1	8/15/2025 12:31	96	38.2860658	-121.9331905	934.2713128	1	TRUE		ML
<img width="715" height="221" alt="image" src="https://github.com/user-attachments/assets/99b8a0b7-28e7-4466-b0e4-c9d4d59328ed" />


Sends hardware triggers via Arduino (optional)


Displays everything in a real-time Streamlit dashboard


<img width="1000" height="400" alt="Figure_1" src="https://github.com/user-attachments/assets/91ea509e-a225-417b-ae37-dea15554e630" />


Exports audit reports for post-flight review


Fri Aug 15 12:31:41 2025: ML anomaly detected at index 31 (Lat: 37.935784, Lon: -122.256117, Alt: 320.60)
Fri Aug 15 12:31:41 2025: ML anomaly detected at index 33 (Lat: 37.937341, Lon: -122.257331, Alt: 320.15)
Fri Aug 15 12:31:41 2025: ML anomaly detected at index 63 (Lat: 38.152811, Lon: -122.039548, Alt: 671.62)
Fri Aug 15 12:31:41 2025: ML anomaly detected at index 92 (Lat: 38.286872, Lon: -121.931420, Alt: 934.52)
Fri Aug 15 12:31:41 2025: ML anomaly detected at index 93 (Lat: 38.287213, Lon: -121.931691, Alt: 934.09)
Fri Aug 15 12:31:41 2025: ML anomaly detected at index 94 (Lat: 38.286874, Lon: -121.932064, Alt: 934.44)
Fri Aug 15 12:31:41 2025: ML anomaly detected at index 96 (Lat: 38.286066, Lon: -121.933190, Alt: 934.27)
2025-08-15 12:31:41: Cybvolve decision at index 0 → Trigger: False, Alt deviation: 0.28, Confidence: 0.01, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 1 → Trigger: False, Alt deviation: 0.69, Confidence: 0.01, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 2 → Trigger: False, Alt deviation: 0.68, Confidence: 0.01, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 31 → Trigger: True, Alt deviation: 310.60, Confidence: 1.00, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 33 → Trigger: True, Alt deviation: 310.15, Confidence: 1.00, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 63 → Trigger: True, Alt deviation: 661.62, Confidence: 1.00, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 92 → Trigger: True, Alt deviation: 924.52, Confidence: 1.00, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 93 → Trigger: True, Alt deviation: 924.09, Confidence: 1.00, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 94 → Trigger: True, Alt deviation: 924.44, Confidence: 1.00, Threshold: 0.70
2025-08-15 12:31:41: Cybvolve decision at index 96 → Trigger: True, Alt deviation: 924.27, Confidence: 1.00, Threshold: 0.70
Fri Aug 15 12:31:41 2025: ANOMALY detected at telemetry index 15 (Lat: 37.806924, Lon: -122.388646, Alt: 48.63)
Fri Aug 15 12:31:41 2025: ANOMALY detected at telemetry index 26 (Lat: 37.848411, Lon: -122.365009, Alt: 101.18)
Fri Aug 15 12:31:41 2025: ANOMALY detected at telemetry index 27 (Lat: 37.883575, Lon: -122.336542, Alt: 140.60)
Fri Aug 15 12:31:41 2025: ANOMALY detected at telemetry index 32 (Lat: 37.908801, Lon: -122.310751, Alt: 211.20)
Fri Aug 15 12:31:42 2025: ML anomaly detected at index 12 (Lat: 37.775934, Lon: -122.419263, Alt: 9.94)
Fri Aug 15 12:31:42 2025: ML anomaly detected at index 15 (Lat: 37.806924, Lon: -122.388646, Alt: 48.63)
Fri Aug 15 12:31:42 2025: ML anomaly detected at index 26 (Lat: 37.848411, Lon: -122.365009, Alt: 101.18)
Fri Aug 15 12:31:42 2025: ML anomaly detected at index 27 (Lat: 37.883575, Lon: -122.336542, Alt: 140.60)
Fri Aug 15 12:31:42 2025: ML anomaly detected at index 30 (Lat: 37.882197, Lon: -122.336699, Alt: 141.25)


Author
MF — Aviation safety educator, Python innovator, and cybersecurity builder. Focused on autonomous systems, NDAA-compliant drone safety, and STEM workforce development.
