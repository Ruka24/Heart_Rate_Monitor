Heart Rate Monitor Project using Arduino Uno and AD8232 EKG Module
Introduction
The project aims to set up a heart rate monitor. It will be done by Arduino Uno and AD8232 EKG module. This configuration is created for the purpose of monitoring the heart's electrical signals, processing the information and displaying visual dynamic signals as well as various HRV measures ( high or normal).
What is ECG?
ECG is a graphical representation of the electrical impulses that the heart generates on a paper or digital media. It is additionally known as electrocardiogram or EKG. ECG helps to detect heart rate, rhythm and other disease of heart information. ECGs are done to support in the diagnosis of cardiac arrhythmias, heart attacks, malfunctions of pacemaker and/or heart failures.
 
Components
The following components were used in this project:
- Arduino Uno
- AD8232 EKG Module
- Connecting wires
Circuit Diagram/Connection between Arduino and ECG Sensor AD8232
In the IC, there are six connections that the AD8232 Heart rate Monitor has. Typically we refer to these connections as “pins” since it gives an impression of coming from the pins on the IC, but in reality they are holes to which you can solder wires or header pins.
 
We are going to connect five of the six pins on the board to Arduino. The mentioned five pins are GND, 3.3v, OUTPUT, LO-, and LO+.
 
AD8232 ECG Sensor Placement on Body
The leads should be snapped on the sensor pads before it is attached to the body. It is better to place the pads as near to the heart as possible for optimum measurement. The cables are color coded which makes it easier to know where each one goes.
 
COLOR	NAME
RED	RA(Right Arm)
YELLOW	LA(Left Arm)
GREEN	RL(Right Leg)
	

Arduino Code
In the Arduino code, an analog signal from the EKG module AD8232 is read and sent to a computer via serial sending for further processing.
Data Processing and Visualization in Python
The data received from the Arduino is processed and visualized in real-time using Python. The following steps outline the data processing and visualization stages.
1. Real-Time EKG Signal with Noise
Initially, the captured signal is noisy. This is a real-time representation of a noisy EKG signal:
 
2. R-Peaks Detection
By analyzing the signal, the R-peaks, which are crucial for heart rate calculation, can be detected. The detected R-peaks are marked on the EKG signal as shown below:
 
3. Signal Filtering
Initially, the captured signal is noisy. This is a real-time representation of a noisy EKG signal:
 
4. Real-Time Heart Rate Calculation
The heart rate (in beats per minute, BPM) is calculated in real-time from the filtered signal. The real-time BPM is displayed on the EKG plot:
 

5. HRV Metrics Calculation
Further analysis comprises computation of several HRV metrics e.g. SDNN, RMSSD, VLF Power, LF Power and HF Power. These metrics are key in HRV and overall cardiac health. Values are used for assessing whether or not the patient's cardiovascular and HRV status is within normal ranges.
SDNN (Standard Deviation of NN intervals)
SDNN is a measure of the variability of the time interval between heartbeats (NN intervals). It reflects the overall variability in the heart rate and is used as an indicator of autonomic regulation of the heart. Higher SDNN values typically indicate healthier heart function and greater variability.
Normal Range: 30-50 ms
RMSSD (Root Mean Square of Successive Differences)
RMSSD is a time-domain measure of heart rate variability. It calculates the square root of the mean of the squares of successive differences between adjacent NN intervals. RMSSD is primarily used to assess the parasympathetic activity of the heart. Higher RMSSD values indicate higher parasympathetic activity and better cardiovascular health.
Normal Range: 20-50 ms
VLF (Very Low Frequency) Power
VLF power is a frequency-domain measure of heart rate variability. It represents the power of heart rate oscillations within the very low-frequency range (0.003 to 0.04 Hz). VLF power is influenced by thermoregulation, the renin-angiotensin system, and other long-term regulatory mechanisms.
Normal Range: 0.003-0.04
LF (Low Frequency) Power
LF power measures the power of heart rate oscillations within the low-frequency range (0.04 to 0.15 Hz). It reflects a mix of sympathetic and parasympathetic nervous system activity. Higher LF power is generally associated with increased sympathetic activity.
Normal Range: 0.04-0.15
HF (High Frequency) Power
HF power represents the power of heart rate oscillations within the high-frequency range (0.15 to 0.4 Hz). It is associated with parasympathetic (vagal) activity and respiratory influences on heart rate. Higher HF power indicates higher parasympathetic activity and better autonomic function.
Normal Range: 0.15-0.4

Conclusion
This project successfully demonstrates the use of an Arduino Uno and an AD8232 EKG module to monitor heart rate and analyze HRV metrics. The Arduino captures the EKG signal, which is then processed and visualized in real-time using Python. The system provides valuable insights into heart rate and variability, helping in the assessment of cardiac health.
Future Work
Future improvements could include enhancing the accuracy of the signal processing algorithms, integrating additional HRV metrics, and developing a user-friendly interface for easier monitoring and analysis.
References
•	AD8232 Datasheet - https://www.alldatasheet.com/datasheet-pdf/pdf/527942/AD/AD8232.html
•	ECG Graph Monitoring with AD8232 ECG Sensor & Arduino - https://how2electronics.com/ecg-monitoring-with-ad8232-ecg-sensor-arduino/infor
